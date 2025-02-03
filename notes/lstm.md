# 鱼书二摘要之三
RNN存在梯度消失和梯度爆炸的问题，采用门控RNN解决  
![alt text](lstm/image.png ':size=600')  
$\Uparrow$ LSTM记忆单元$C_t$只在LSTM层内部传递信息，不输出到其他层（如affine, softmax等）  
  
![alt text](lstm/image-1.png ':size=600')  

![alt text](lstm/image-2.png ':size=600')  
$\Uparrow$ g--记忆单元，i--g的门控（输入门），f--遗忘门，o--输出门，$C_t$--记忆信息，$h_t$--状态信息（隐藏层，输出信息）  
>$\begin{array} {l} {{{{f=\sigma( x_{t} W_{x}^{( \mathrm{f} )}+h_{t-1} W_{h}^{( \mathrm{f} )}+b^{( \mathrm{f} )} )}}}} \\ {{{{g=\operatorname{t a n h} ( x_{t} W_{x}^{( \mathrm{g} )}+h_{t-1} W_{h}^{( \mathrm{g} )}+b^{( \mathrm{g} )} )}}}} \\ {{{{i=\sigma( x_{t} W_{x}^{( \mathrm{i} )}+h_{t-1} W_{h}^{( \mathrm{i} )}+b^{( \mathrm{i} )} )}}}} \\ {{{{o=\sigma( x_{t} W_{x}^{( \mathrm{o} )}+h_{t-1} W_{h}^{( \mathrm{o} )}+b^{( \mathrm{o} )} )}}}} \\ \end{array} $  
$\boldsymbol{c}_{t}=\boldsymbol{f} \odot\boldsymbol{c}_{t-1}+\boldsymbol{g} \odot\boldsymbol{i} $  
$h_{t}=o \odot\operatorname{t a n h} ( c_{t} ) $  

门控均使用sigmoid，取值[0, 1]，起到开关作用；记忆单元使用tanh，取值[-1, 1]，收敛快（中心值为0）。
![alt text](lstm/image-4.png ':size=600')
