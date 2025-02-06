# 鱼书二摘要之二
基于分布式假设的word2vec的CBOW模型没有考虑单词顺序所携带的信息  
![alt text](rnn/image-1.png ':size=600')  
$\Uparrow$ 拼接（concatenate）可增加单词顺序信息，但会增加权重参数数量，而RNN(Recurrent Neutral Network)专门针对时间序列  
![alt text](rnn/image.png ':size=600')  
$\Uparrow$ RNN层有两重含义，单就一个RNN层而言，其内部的层级是时间维度上的展开，而在空间维度上全部为同一层，即`第t个RNN层`等价于`时刻t的RNN层`  
>$h_t=\tan h(h_{t-1}W_h+x_tW_x+b)$  

![alt text](rnn/image-2.png ':size=600')  
$\Uparrow$ 在处理长度为1000 的时序数据时，如果展开RNN 层，它将成为在水平方向上排列有1000 个层的网络。当然，无论排列多少层，都可以根据误差反向传播法计算梯度。但是，如果序列太长，就会出现计算量或者内存使用量方面的问题。此外，随着层变长，梯度逐渐变小，梯度将无法向前一层传递。因此，如图5-11 所示，我们来考虑在水平方向上以适当的长度截断网络的反向传播的连接。  
我们之前看到的神经网络在进行mini-batch学习时，数据都是随机选择的。但是，在RNN执行Truncated BPTT时，数据需要按顺序输入。  
![alt text](rnn/image-4.png ':size=600')  
![alt text](rnn/image-5.png ':size=600')  
$\Uparrow$ 由于顺序本身也是携带信息，因此rnn的mini batch不是随机的，而是顺序的  
![alt text](rnn/image-6.png ':size=600')  
![alt text](rnn/image-7.png ':size=600')
![alt text](rnn/image-8.png ':size=600')

