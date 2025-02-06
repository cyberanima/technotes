# 鱼书二摘要之一
>`某个单词的含义由它周围的单词形成`，称为分布式假设（distributional hypothesis）

>人的本质是一切社会关系的总和

存在两种分布式：基于计数（共现矩阵，pmi）、基于推理。都是基于`单词共现`建模  
![alt text](hypo/image.png ':size=600')  
![alt text](hypo/image-2.png ':size=600')  
![alt text](hypo/image-1.png ':size=600')  
![alt text](hypo/image-3.png ':size=600')  
$\Uparrow$ 因为是考虑上下文两个单词，所以是两个输入  
>中间层的神经元数量比输入层少这一点很重要。中间层需要将预测单词所需的信息压缩保存，从而产生密集的向量表示。这时，中间层被写入了我们人类无法解读的代码，这相当于“编码”工作。而从中间层的信息获得期望结果的过程则称为“解码”。这一过程将被编码的信息复原为我们可以理解的形式。  

![alt text](hypo/image-4.png ':size=600')  
