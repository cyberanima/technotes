# tensorflow and tensorflow-gpu

如独显，安装cuda，下载cudnn，后者各文件夹内容复制到cuda安装路径相应文件夹内
![alt text](env/image-1.png ':size=600')  
$\Uparrow$ tensorflow官网给出的配置  

![alt text](env/image.png ':size=600')  
$\Uparrow$ conda源提供的版本，应该是tensorflow官网测试稳定的  
>以下配置都能运行  
Anaconda：Python3.7.13，tensorflow-gpu2.6.0，numpy1.21.5  
非虚拟环境：Python3.7.9，tensorflow-gpu2.7.0，numpy1.21.6

<strong>datasets合成代码</strong>  

```python
import pandas as pd
import numpy as np
from datetime import datetime, timedelta

# Generate synthetic data
np.random.seed(42)

# Generate date-time range
start_date = datetime(2023, 1, 1)
end_date = datetime(2023, 12, 31)
date_range = [start_date + timedelta(hours=x) for x in range(0, (end_date - start_date).days * 24)]

# Generate synthetic environmental data
temperature = np.random.uniform(20, 30, len(date_range))  # Ensure len(date_range)
humidity = np.random.uniform(50, 70, len(date_range))      # Ensure len(date_range)
co2 = np.random.uniform(400, 800, len(date_range))        # Ensure len(date_range)
fan_state = np.random.choice([0, 1], len(date_range), p=[0.7, 0.3])  # Ensure len(date_range)
crop_yield = temperature * 0.1 + humidity * 0.05 + np.random.uniform(5, 10, len(date_range))

# Create DataFrame
data = pd.DataFrame({
    'DateTime': date_range,
    'CO2': co2,
    'Temperature': temperature,
    'Humidity': humidity,
    'FanState': fan_state,
    'CropYield': crop_yield
})

# Save as CSV
data.to_csv('synthetic_greenhouse_data.csv', index=False)

print("Synthetic dataset saved as 'synthetic_greenhouse_data.csv'")
```  
  
<strong>lstm测试代码</strong>

```python
import pandas as pd
import numpy as np
from sklearn.preprocessing import MinMaxScaler
from sklearn.model_selection import train_test_split
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import LSTM, Dense, Dropout
import matplotlib.pyplot as plt
import seaborn as sns

# Load the synthetic dataset
data = pd.read_csv('synthetic_greenhouse_data.csv')

# Normalize the data
scaler = MinMaxScaler()
scaled_data = scaler.fit_transform(data[['CO2', 'Temperature', 'Humidity', 'FanState', 'CropYield']])

# Function to create sequences for LSTM
def create_sequences(data, sequence_length):
    X, y = [], []
    for i in range(len(data) - sequence_length):
        X.append(data[i:i + sequence_length, :-1])  # Input features (excluding 'CropYield')
        y.append(data[i + sequence_length, -1])    # CropYield (target)
    return np.array(X), np.array(y)

sequence_length = 24  # Use the past 24 hours to predict the next hour's crop yield
X, y = create_sequences(scaled_data, sequence_length)

# Check the shape of the data
print(X.shape, y.shape)

# Split data into train and test sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Check the shape of the data after split
print(X_train.shape, X_test.shape)

# Build the LSTM model
model = Sequential([
    LSTM(64, activation='relu', return_sequences=True, input_shape=(X_train.shape[1], X_train.shape[2])),
    Dropout(0.2),
    LSTM(32, activation='relu'),
    Dropout(0.2),
    Dense(1)  # Output layer
])

model.compile(optimizer='adam', loss='mse', metrics=['mae'])

# Function to plot training loss and validation loss
def plot_loss(history):
    plt.plot(history.history['loss'], label='Train Loss')
    plt.plot(history.history['val_loss'], label='Validation Loss')
    plt.title('Model Loss')
    plt.xlabel('Epochs')
    plt.ylabel('Loss')
    plt.legend()
    plt.show()

# Function to plot training and validation MAE
def plot_mae(history):
    plt.plot(history.history['mae'], label='Train MAE')
    plt.plot(history.history['val_mae'], label='Validation MAE')
    plt.title('Model Mean Absolute Error (MAE)')
    plt.xlabel('Epochs')
    plt.ylabel('MAE')
    plt.legend()
    plt.show()

# Function to plot predictions vs true values
def plot_predictions(y_test, predictions):
    plt.figure(figsize=(10, 6))
    plt.plot(y_test, label='True Crop Yield')
    plt.plot(predictions, label='Predicted Crop Yield')
    plt.title('True vs Predicted Crop Yield')
    plt.xlabel('Time Step')
    plt.ylabel('Crop Yield')
    plt.legend()
    plt.show()

# Train the model
history = model.fit(X_train, y_train, epochs=50, batch_size=32, validation_split=0.2, verbose=1)

# Plot loss and MAE curves
plot_loss(history)
plot_mae(history)

# Evaluate the model and make predictions
predictions = model.predict(X_test)

# Plot the true vs predicted values
plot_predictions(y_test, predictions)
```