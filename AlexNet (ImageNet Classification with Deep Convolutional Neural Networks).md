<!-- 原文件: AlexNet (ImageNet Classification with Deep Convolutional Neural Networks).md -->
<!-- 图片托管于 GitHub -->

# AlexNet (ImageNet Classification with Deep Convolutional Neural Networks)

**Title: ImageNet Classification with Deep Convolutional Neural Networks**

**Paper:** [https://proceedings.neurips.cc/paper_files/paper/2012/file/c399862d3b9d6b76c8436e924a68c45b-Paper.pdf](https://proceedings.neurips.cc/paper_files/paper/2012/file/c399862d3b9d6b76c8436e924a68c45b-Paper.pdf) 【**NIPS 2012**】

## Introduction

- 60 million parameters

- 8 layers（five convolutional layers + <span style="color: #000000">three fully-connected layers）, 1000-way softmax</span>

- <span style="color: #000000">ReLU (计算更简单；使训练模型更加容易) </span>

- Reducing Overfitting

	- <span style="color: #000000">Dropout (regularization) </span>

	- Data Augmentation (更大的训练样本量)

### ImageNet

**ImageNet**: [https://www.image-net.org/](https://www.image-net.org/)

![](https://raw.githubusercontent.com/wwxu-zx/blog/main/assets/AlexNet%20%28ImageNet%20Classification%20with%20Deep%20Convolutional%20Neural%20Networks%29/WEBRESOURCEe69ba3e815e9404d97b31a295481dcf4%E6%88%AA%E5%B1%8F2026-01-28%2016.02.37.png)

> <span style="color: #000000">**ImageNet**</span><span style="color: #000000"> is a </span><span style="color: #000000">dataset**</span><span style="color: #000000"> of over </span><span style="color: #000000">**15 million**</span><span style="color: #000000"> labeled high-resolution images belonging to roughly </span><span style="color: #000000">**22,000 categories**</span><span style="color: #000000">.</span>
> <span style="color: #000000">ImageNet Large-Scale Visual Recognition Challenge (</span><span style="color: #000000">**ILSVRC**</span><span style="color: #000000">) uses a subset of ImageNet with roughly 1000 images in each of</span>
> <span style="color: #000000">**1000 categories**</span><span style="color: #000000">. In all, there are roughly </span><span style="color: #000000">**1.2 million training images**</span><span style="color: #000000">, 50,000 validation images, and 150,000 testing images.</span>


![](https://raw.githubusercontent.com/wwxu-zx/blog/main/assets/AlexNet%20%28ImageNet%20Classification%20with%20Deep%20Convolutional%20Neural%20Networks%29/WEBRESOURCEf82f28899b2046b3b7884eb0636e969a%E6%88%AA%E5%B1%8F2026-01-25%2017.39.12.png)

AlexNet 赢下了 2012 ImageNet 竞赛后，标注着新一轮神经网络热潮的开始。

### CNNs

![](https://raw.githubusercontent.com/wwxu-zx/blog/main/assets/AlexNet%20%28ImageNet%20Classification%20with%20Deep%20Convolutional%20Neural%20Networks%29/WEBRESOURCE3d84ecc0b13c44b8b475d304d5c0fa4c%E6%88%AA%E5%B1%8F2026-01-28%2015.42.23.png)

### AlexNet带来第三波AI浪潮

![](https://raw.githubusercontent.com/wwxu-zx/blog/main/assets/AlexNet%20%28ImageNet%20Classification%20with%20Deep%20Convolutional%20Neural%20Networks%29/WEBRESOURCE35c4d6e9090247088a2deaa28643a17a965fb92a6edb597d9847dc2328d198de.jpg)

**人工特征 -> 神经网络自动提取特征**

如上图所示，左侧人工特征提取和SVM是独立的过程；而右侧通过神经网络自动提取特征和Softmax分类是**一起训练的过程**。

**End-to-end（端到端，没有复杂的特征工程），直接处理原始像素（raw RGB values of the pixels），简化了数据预处理。**

**Learn from data（数据驱动）**

![](https://raw.githubusercontent.com/wwxu-zx/blog/main/assets/AlexNet%20%28ImageNet%20Classification%20with%20Deep%20Convolutional%20Neural%20Networks%29/WEBRESOURCEad87411b3c0b4a80a063b42fd004796d9ea854d2bc0b2a44831ee5f03f5b0008.jpg)

- 除了在训练集上对像素减去平均活跃度（mean activity），没有进行任何其他方式的预处理。【相比传统方法，**简化了预处理操作**】

- 算均值时通常有两种计算方法。一种是image mean，是对RGB三个通道都求均值，然后再从各个通道减去该均值；另一种是pixel mean，直接全图减去全部像素的均值。本文应该是取的第一种。

## AlexNet架构

![](https://raw.githubusercontent.com/wwxu-zx/blog/main/assets/AlexNet%20%28ImageNet%20Classification%20with%20Deep%20Convolutional%20Neural%20Networks%29/WEBRESOURCEc77716572a094bf99ecf6956680eb237066db393ac340505235ab54489056dc6.jpg)

AlexNet 可视化：[https://dgschwend.github.io/netscope/#/preset/alexnet](https://dgschwend.github.io/netscope/#/preset/alexnet)

- Netscope 是一个在线可视化工具，使用它可以把 Caffe 的 .prototxt文件（定义模型结构）可视化，直观地理解模型结构和数据流动。

![](https://raw.githubusercontent.com/wwxu-zx/blog/main/assets/AlexNet%20%28ImageNet%20Classification%20with%20Deep%20Convolutional%20Neural%20Networks%29/WEBRESOURCE568f077fb5d54f32a2fde32bf19d2fe514c16e057061d26d784f2be38b0f4e34.jpg)

![](https://raw.githubusercontent.com/wwxu-zx/blog/main/assets/AlexNet%20%28ImageNet%20Classification%20with%20Deep%20Convolutional%20Neural%20Networks%29/WEBRESOURCEea17629a1bf343cab388f5aa596058e914dae810f8eb126315b04d4fb77f8340.jpg)

**注意：**

`(224-11)/4` 不能整除，会向下取整，也就是说 Kernel 在水平移动时，最后几个不足 kernel_size 的像素会被丢掉。在 Netscope 中这里被修改了，里面的输入被 resize 到 `227*227*3`。

- [0, 10], [11, 20], ..., [211, 220]

- [221, 223]三个像素被丢掉

**如想要计算 **<span style="color: #222832; background-color: rgb(255, 255, 255)">**Shape 的变化，可参考：**</span>

[https://docs.pytorch.org/docs/stable/generated/torch.nn.Conv2d.html#conv2d](https://docs.pytorch.org/docs/stable/generated/torch.nn.Conv2d.html#conv2d)

![](https://raw.githubusercontent.com/wwxu-zx/blog/main/assets/AlexNet%20%28ImageNet%20Classification%20with%20Deep%20Convolutional%20Neural%20Networks%29/WEBRESOURCE43108c59c3734b26b0e5f414ca40a014%E6%88%AA%E5%B1%8F2026-01-29%2013.01.53.png)

简化版的公式为：

`（w + 2*padding - kernel_size）/ stride + 1`

以这里 [https://zh-v2.d2l.ai/chapter_convolutional-modern/alexnet.html#id14](https://zh-v2.d2l.ai/chapter_convolutional-modern/alexnet.html#id14) 网络各层shape变化为例，

```python
import torch
from torch import nn
from d2l import torch as d2l

net = nn.Sequential(
    # 这里使用一个11*11的更大窗口来捕捉对象。
    # 同时，步幅为4，以减少输出的高度和宽度。
    # 另外，输出通道的数目远大于LeNet
    nn.Conv2d(1, 96, kernel_size=11, stride=4, padding=1), nn.ReLU(),
    nn.MaxPool2d(kernel_size=3, stride=2),
    # 减小卷积窗口，使用填充为2来使得输入与输出的高和宽一致，且增大输出通道数
    nn.Conv2d(96, 256, kernel_size=5, padding=2), nn.ReLU(),
    nn.MaxPool2d(kernel_size=3, stride=2),
    # 使用三个连续的卷积层和较小的卷积窗口。
    # 除了最后的卷积层，输出通道的数量进一步增加。
    # 在前两个卷积层之后，汇聚层不用于减少输入的高度和宽度
    nn.Conv2d(256, 384, kernel_size=3, padding=1), nn.ReLU(),
    nn.Conv2d(384, 384, kernel_size=3, padding=1), nn.ReLU(),
    nn.Conv2d(384, 256, kernel_size=3, padding=1), nn.ReLU(),
    nn.MaxPool2d(kernel_size=3, stride=2),
    nn.Flatten(),
    # 这里，全连接层的输出数量是LeNet中的好几倍。使用dropout层来减轻过拟合
    nn.Linear(6400, 4096), nn.ReLU(),
    nn.Dropout(p=0.5),
    nn.Linear(4096, 4096), nn.ReLU(),
    nn.Dropout(p=0.5),
    # 最后是输出层。由于这里使用Fashion-MNIST，所以用类别数为10，而非论文中的1000
    nn.Linear(4096, 10))
    
X = torch.randn(1, 1, 224, 224)
for layer in net:
    X=layer(X)
    print(layer.__class__.__name__,'output shape:\t',X.shape)
    
    
    
"""
Conv2d output shape:     torch.Size([1, 96, 54, 54])           # (224+2*1-11)/4 + 1 = 53 + 1 = 54
ReLU output shape:       torch.Size([1, 96, 54, 54])
MaxPool2d output shape:  torch.Size([1, 96, 26, 26])        # (54-3)/2 + 1 = 26
Conv2d output shape:     torch.Size([1, 256, 26, 26])         # (26+2*2-5)/1 + 1 = 26
ReLU output shape:       torch.Size([1, 256, 26, 26])
MaxPool2d output shape:  torch.Size([1, 256, 12, 12])       # (26-3)/2 + 1 = 12
Conv2d output shape:     torch.Size([1, 384, 12, 12])
ReLU output shape:       torch.Size([1, 384, 12, 12])
Conv2d output shape:     torch.Size([1, 384, 12, 12])         # (12+2*1-3)/1 + 1 = 12 
ReLU output shape:       torch.Size([1, 384, 12, 12])
Conv2d output shape:     torch.Size([1, 256, 12, 12])         # (12+2*1-3)/1 + 1 = 12
ReLU output shape:       torch.Size([1, 256, 12, 12])
MaxPool2d output shape:  torch.Size([1, 256, 5, 5])         # (12-3)/2 + 1 = 5
Flatten output shape:    torch.Size([1, 6400])                    # 256*5*5 = 6400
Linear output shape:     torch.Size([1, 4096])
ReLU output shape:       torch.Size([1, 4096])
Dropout output shape:    torch.Size([1, 4096])
Linear output shape:     torch.Size([1, 4096])
ReLU output shape:       torch.Size([1, 4096])
Dropout output shape:    torch.Size([1, 4096])
Linear output shape:     torch.Size([1, 10])
"""
```

### AlexNet 是更大更深的 LeNet。

![](https://raw.githubusercontent.com/wwxu-zx/blog/main/assets/AlexNet%20%28ImageNet%20Classification%20with%20Deep%20Convolutional%20Neural%20Networks%29/WEBRESOURCE60d46971e58c411385f8247fe04387bf%E6%88%AA%E5%B1%8F2026-01-26%2011.19.08.png)

![](https://raw.githubusercontent.com/wwxu-zx/blog/main/assets/AlexNet%20%28ImageNet%20Classification%20with%20Deep%20Convolutional%20Neural%20Networks%29/WEBRESOURCEe9ea80bda72740b69b042b0f1e34863b%E6%88%AA%E5%B1%8F2026-01-26%2011.33.37.png)

![](https://raw.githubusercontent.com/wwxu-zx/blog/main/assets/AlexNet%20%28ImageNet%20Classification%20with%20Deep%20Convolutional%20Neural%20Networks%29/WEBRESOURCEeb80e5014eaa455798447bc381ca497b%E6%88%AA%E5%B1%8F2026-01-26%2011.36.13.png)

![](https://raw.githubusercontent.com/wwxu-zx/blog/main/assets/AlexNet%20%28ImageNet%20Classification%20with%20Deep%20Convolutional%20Neural%20Networks%29/WEBRESOURCE4a3c310a1a1d4a029769285737625689%E6%88%AA%E5%B1%8F2026-01-26%2011.38.27.png)

## 学习表征（Representations）

![](https://raw.githubusercontent.com/wwxu-zx/blog/main/assets/AlexNet%20%28ImageNet%20Classification%20with%20Deep%20Convolutional%20Neural%20Networks%29/WEBRESOURCE46c4fd8c2f44475295ddb69b1854f6c9%E6%88%AA%E5%B1%8F2026-01-28%2015.33.47.png)

如上图右侧第2行，这些大象图片之间的像素值本身非常不同，但是它们是高度相似的概念。【<span style="color: #000000">**semantically similar**</span>】

AlexNet 确实学会了数据的高维表示。<span style="color: #e74c3c">**This high dimensional space is often called a latent or embedding space.**</span>

## 数据/算力/模型的scaling

![](https://raw.githubusercontent.com/wwxu-zx/blog/main/assets/AlexNet%20%28ImageNet%20Classification%20with%20Deep%20Convolutional%20Neural%20Networks%29/WEBRESOURCE8126961bd8be4d16aa5575a6bebdbf98%E6%88%AA%E5%B1%8F2026-01-19%2015.23.34.png)

![](https://raw.githubusercontent.com/wwxu-zx/blog/main/assets/AlexNet%20%28ImageNet%20Classification%20with%20Deep%20Convolutional%20Neural%20Networks%29/WEBRESOURCE7d5606c93df14bca985ccb90fe128244%E6%88%AA%E5%B1%8F2026-01-25%2017.44.13.png)

![](https://raw.githubusercontent.com/wwxu-zx/blog/main/assets/AlexNet%20%28ImageNet%20Classification%20with%20Deep%20Convolutional%20Neural%20Networks%29/WEBRESOURCE8e50691e7ded425382c48814f346a962%E6%88%AA%E5%B1%8F2026-01-28%2017.49.00.png)

**scale of data and compute**

## References

[<span style="color: #3498db">Krizhevsky A, Sutskever I, Hinton G E. Imagenet classification with deep convolutional neural networks[J]. Advances in neural information processing systems, 2012, 25.</span>](https://proceedings.neurips.cc/paper/2012/file/c399862d3b9d6b76c8436e924a68c45b-Paper.pdf)

[<span style="color: #3498db">Krizhevsky A, Sutskever I, Hinton G E. ImageNet classification with deep convolutional neural networks[J]. Communications of the ACM, 2017, 60(6): 84-90.</span>](https://dl.acm.org/doi/pdf/10.1145/3065386)

[<span style="color: #3498db">【7.1. 深度卷积神经网络（AlexNet）【动手学深度学习v2】】</span>](https://zh-v2.d2l.ai/chapter_convolutional-modern/alexnet.html)

【9年后重读深度学习奠基作之一：AlexNet【论文精读·2】】 [https://www.bilibili.com/video/BV1ih411J7Kz/?share_source=copy_web&vd_source=6771d35251ef5959f68e7e6ca14fb957](https://www.bilibili.com/video/BV1ih411J7Kz/?share_source=copy_web&vd_source=6771d35251ef5959f68e7e6ca14fb957)

【AlexNet论文逐段精读【论文精读】】 [https://www.bilibili.com/video/BV1hq4y157t1/?share_source=copy_web&vd_source=6771d35251ef5959f68e7e6ca14fb957](https://www.bilibili.com/video/BV1hq4y157t1/?share_source=copy_web&vd_source=6771d35251ef5959f68e7e6ca14fb957)

【24 深度卷积神经网络 AlexNet【动手学深度学习v2】】 [https://www.bilibili.com/video/BV1h54y1L7oe/?share_source=copy_web&vd_source=6771d35251ef5959f68e7e6ca14fb957](https://www.bilibili.com/video/BV1h54y1L7oe/?share_source=copy_web&vd_source=6771d35251ef5959f68e7e6ca14fb957)

【从 AlexNet 开始，人们就无法理解 AI 在干什么了】 [https://www.bilibili.com/video/BV1SvDfYDEDA/?share_source=copy_web&vd_source=6771d35251ef5959f68e7e6ca14fb957](https://www.bilibili.com/video/BV1SvDfYDEDA/?share_source=copy_web&vd_source=6771d35251ef5959f68e7e6ca14fb957)