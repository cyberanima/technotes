# 鱼书摘记之三
基于链式法则（chain rule）的反向传播，是偏导数的逆行而上，是搜寻原因的变化对结果的变化的影响程度，是微分而非积分，星星之火可以燎原，萌芽的式微并不代表力量对比的始终如此，反向传播是涌动的暗流  
![alt text](bp/image-1.png ':size=600')  
```python
# 构建乘法层
class MulLayer: 
    def __init__(self):
        self.x = None # 此处必须对x和y两个变量实例化，因为后面backward会调用二者
        self.y = None # 这是与加法层不一样的地方
    def forward(self, x, y): # 正向传播——直接计算
        self.x = x
        self.y = y
        out = x * y
        return out
    def backward(self, dout): # 反向传播——偏导计算
        dx = dout * self.y  # 翻转x和y：if z=x*y, then local derivative dz/dx=y,
                            # so the 'x' branch of the output of this MulLayer is 
                            # y multipling the input of this MulLayer -- y*dout
                            # 'dout' is the input in backward
                            # 'dx' means one of the outputs, the other one is 'dy'
                            # here 'd' is just a prefix of x branch to indicate the
                            # difference to x, say 'd' means backward 
        dy = dout * self.x # 如前所述，调用变量x和y
        return dx, dy
```    
![alt text](bp/image.png ':size=600')  
```python
# 构建加法层
class AddLayer:
    def __init__(self): # backward中不涉及x和y的调用
        pass            # 不需要实例化
    def forward(self, x, y):
        out = x + y
        return out
    def backward(self, dout):
        dx = dout * 1   # 系数为1，常数
        dy = dout * 1
        return dx, dy
```   
>relu, sigmoid, affine, softmax and other activation functions are same with mul and add
