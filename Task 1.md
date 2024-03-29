### 1 什么是Pytorch，为什么选择Pytroch？
它是一个搭建深度学习神经网络科学计算python包，里面封装了很多函数和类。1.使用GPUs算力可取代Numpy。2.高灵活性和高速的深度学习研究平台。  
使用它我们可以不怎么懂神经网络参数调整细节就可以设计一个神经网络。因为它自带了自动调节参数的功能。并且它的使用模式和python非常像，比tensorflow更直观。所以很多论文会提供用pytorch写的神经网络代码。  
### 2 Pytroch的安装
在安装pytorch之前一定要先安装python，然后再安装numpy。python版本、cuda版本（版本号在NVIDIA控制面板中查询，若电脑无显卡支持GPU加速也有对应pytorch版本）与pytorch版本要相匹配。需安装的版本及指令可通过https://pytorch.org/get-started/locally/ 查询。
### 3 配置Python环境
通过官网下载并安装Anaconda，在系统设置的PATH中检查Python已被添加到系统路径，打开Anaconda Prompt,输入python，返回python版本信息，并进入python编译环境。
### 4 通过命令行安装PyTorch
我所预装的python版本号为3.6.5，cuda版本号为10.0，通过官网查询得pip安装指令为  
```
pip install https://download.pytorch.org/whl/cu100/torch-1.1.0-cp36-cp36m-win_amd64.whl  
pip install https://download.pytorch.org/whl/cu100/torchvision-0.3.0-cp36-cp36m-win_amd64.whl  
```
### 5 PyTorch基础概念
#### Tensor
表示的是一个多维的矩阵，比如零维就是一个点，一维就是向量，二维就是一般的矩阵，多维就相当于一个多维的数组。
#### Variable
Variable主要包含三个属性。  
•data : 保存Variable所包含的Tensor。  
•grad : 保存data对应的梯度，grad也是个Variable, 而不是Tensor, 它和data的形状—样。  
•grad fn : 指向一个Functio n对象，这个Function用来反向传播计算输入的梯度。  
### 6 通用代码实现流程(实现一个深度学习的代码流程)
加载数据和标签（如手写数字识别中的数据就是一张图片，而一张图片在计算机里面是一个由整数组成的矩阵，它的标签是当前这个图片到底是数字几）  
设计网络结构（如是共有几层神经网络，每层输入输出的矩阵格式，每层的激活函数是怎样的，当前层到底是卷积层还是循环神经网络层等等）  
设计损失（误差）函数（以手写数字识别为例，神经网络会输出一个值表明当前这个图片到底是几，但是一开始肯定不准确。所以我们需要计算神经网络输出值与标签之间的误差。而误差计算有很多种我们需要告诉pytorch怎么计算误差。然后pytorch就会自动根据我们设定的误差计算方法去自动调整神经网络的参数）  
设置用于自动调整神经网络参数的优化器（在上一步我们提到了pytorch会自动帮我们自动调整神经网络的参数，但是具体用哪种优化器去调整参数呢？这需要我们告诉pytorch，因此我们需要用代码设置具体用哪个优化器调整参数）  
使用数据和标签训练神经网络  
这个神经网络已经训练好可以用于解决你的问题了。（你只用输入数据，然后用神经网络输出结果即可）  
