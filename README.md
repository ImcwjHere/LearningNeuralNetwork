# Important
**This project is prohibited to use for commercial purposes! If needed, please contact me.**<br>
**禁止商业使用！如有需要请联系作者。**<br>
**尤其是中国大陆某些“十块钱学透深度学习”等所谓“教育机构”！**<br /><br>
**For reprinting, please indicate the author's information**<br>
**转载请注明作者信息，谢谢！**<br>
**尤其是抖音（特别是中国大陆地区）、快手等短视频平台**<br>

 In the future, I will try my best to use English comments in the code. For some Chinese comments in my previous code, please use translation software, I'm sorry for that. :(

# Introduce
This is a repository which documents my learning experience in Deep Learning. The programming language is Python.<br><br>

You might be wondering how AMD GPU (even doesn't support RoCm) works for deep learning? But in fact this is possible, the principle is to use Microsoft DirectX 12 (DirectML), You can read this: [Enable PyTorch with DirectML on Windows](https://docs.microsoft.com/zh-cn/windows/ai/directml/gpu-pytorch-windows).<br><br>

So all graphics cards that support DirectX 12 can run the deep learning framework. :)<br><br>

For some projects with low performance requirements, I use CPU for calculation, and the others I use "dml" (AMD GPU) or "cuda" (Nvidia GPU).<br><br>

# Environment
All the codes are confirmed to work on my computer.<br>
|Item|Info|
|:-:|:-:|
|System|Windows 11 Build 25126<br>Windows 2019 DataCenter|
|CPU|AMD Ryzen7 2700X|
|GPU|AMD Radeon RX580 8G<br>Nvidia Tesla V100<br>Nvidia Tesla T4|
|Python Version|Python 3.8 (dml)<br>Python 3.10 (cpu,cuda)|
|PyTorch Version|PyTorch 1.8 (dml)<br>PyTorch 1.11 (cpu,cuda)|
|IDE|Microsoft Visual Stuido Code - Insiders|

*Please install [MiniConda](https://docs.conda.io/en/latest/miniconda.html) by yourself.

# Devices
Just modify ``torch.device("xxx")`` in the code.<br>
|device|name|
|:-:|:-:|
|CPU|"cpu"|
|AMD GPU|"dml"|
|Nvidia GPU|"cuda"|

# Install PyTorch
*For Nvidia GPU/CPU, go to this page: [Install PyTorch](https://pytorch.org/get-started/locally/), install PyTorch as normal.<br><br>

For AMD GPU, the directml only supports PyTorch 1.8, and Python 3.8.<br><br>
***DO NOT USE `pip install pytorch`**<br><br>
The following command are all copied from [Microsoft Docs](https://docs.microsoft.com/zh-cn/windows/ai/directml/gpu-pytorch-windows).<br><br>
```bash
conda create --name pydml -y
conda activate pydml
conda install -c anaconda python=3.8 -y
conda install -n pydml pandas -y
conda install -n pydml tensorboard -y
conda install -n pydml matplotlib -y
conda install -n pydml tqdm -y
conda install -n pydml pyyaml -y
pip install opencv-python
pip install wget
pip install torchvision==0.9.0
pip install pytorch-directml
```

For testing, use:
```bash
import torch
tensor1 = torch.tensor([1]).to("dml")
tensor2 = torch.tensor([2]).to("dml")
dml_algebra = tensor1 + tensor2
dml_algebra.item()
```

If installed well, the program will be like this:<br>
>\>\>\> import torch<br>
>\>\>\> tensor1 = torch.tensor([1]).to("dml")<br>
>\>\>\> tensor2 = torch.tensor([2]).to("dml")<br>
>\>\>\> dml_algebra = tensor1 + tensor2<br>
>\>\>\> dml_algebra.item()<br>
>3

# Notes
|Learning Order|File Name|Notes|
|:-:|:-:|:-:|
|0|BasicFunctions|Learning some basic operations of `torch.tensor`.|
|1|线性回归|The most basic framework.|
|2|FNN-MNIST|Add some functions, and try to recognize handwrite numbers.|
|3|CNN-MNIST|Learn CNN (Convolutional Neural Networks)|
|4|CNN-FashionMNIST|Apparel classification problem using CNN|
|5|CNN-CIFAR10|(NOT FINISHED) Object Recognition Based on CNN VGG16 Model|

# Contact
Please contact me if you have any problems.<br>
Both emails are available, please make sure that emails sent from these two are not listed as spam.<br>
founder@imcwj.cn<br>
imcwj@stu.ahau.edu.cn<br>
I will reply you soon!<br>
I'm Wenjun Chen, glad to chat with you :)