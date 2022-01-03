# 使用转移学习的多类图像分类

> 原文:[https://www . geesforgeks . org/multi class-image-classing-use-transfer-learning/](https://www.geeksforgeeks.org/multiclass-image-classification-using-transfer-learning/)

图像分类是有监督的机器学习问题之一，旨在将数据集的图像分类到它们各自的类别或标签中。各种狗品种的图像分类是一个经典的图像分类问题，在本文中，我们将通过使用预训练的模型**incentiresnetv2**和对其进行定制来做同样的事情。

让我们首先讨论一些术语。

**迁移学习:**迁移学习是一种流行的深度学习方法，它遵循使用在某个任务中学习的知识并将其应用于解决相关目标任务的问题的方法。因此，我们不是从头开始创建神经网络，而是“**转移**”基本上是网络的“**权重**”的学习特征。为了贯彻迁移学习的理念，我们利用“**预训练模型**”。

**预训练模型:**预训练模型是在非常大的数据集上训练的深度学习模型，由希望为这个机器学习社区做出贡献以解决类似类型问题的其他开发人员开发并提供。它包含神经网络的偏差和权重，代表它所训练的数据集的特征。学到的特征总是可以转移的。例如，在花卉图像的大数据集上训练的模型将包含学习的特征，例如角、边、形状、颜色等。

**InceptionResNetV2:**InceptionResNetV2 是一个深度为 164 层的卷积神经网络，在来自 ImageNet 数据库的数百万幅图像上进行训练，可以将图像分为花卉、动物等 1000 多个类别。图像的输入大小是 299 乘 299。

**数据集描述:**

> *   The data set used includes a total of 120 kinds of dogs.
> *   Each image has a file name, which is its unique id.
> *   <u>Training data set (train.zip)</u> : It contains 10,222 images for training our model.
> *   <u>Test data set (test.zip)</u> : There are 10,357 images, which we must classify into their own categories or labels.
> *   <u>Label. csv</u> : Contains the name of the variety corresponding to the picture id.
> *   <u>sample _ submission.csv</u> : contains the correct format of the sample to be submitted.
> 
> 上述所有文件都可以从 [**<u>这里</u>**](https://drive.google.com/drive/folders/1z31bsh7gNrUiwameOEWhqtWNZuKEdKQ7?usp=sharing) 下载。
> 
> <u>注</u>:为了更好的性能使用 GPU。

我们首先**导入所有必要的库。**

## 蟒 3

```
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

from sklearn.metrics import classification_report, confusion_matrix

# deep learning libraries
import tensorflow as tf
import keras
from keras.preprocessing.image import ImageDataGenerator
from tensorflow.keras import applications
from keras.models import Sequential, load_model
from keras.layers import Conv2D, MaxPooling2D, GlobalAveragePooling2D, Flatten, Dense, Dropout
from keras.preprocessing import image

import cv2

import warnings
warnings.filterwarnings('ignore')
```

**加载数据集和图像文件夹**

## python 3

```
from google.colab import drive
drive.mount("/content/drive")

# datasets
labels = pd.read_csv("/content/drive/My Drive/dog/labels.csv")
sample = pd.read_csv('/content/drive/My Drive/dog/sample_submission.csv')

# folders paths
train_path = "/content/drive/MyDrive/dog/train"
test_path = "/content/drive/MyDrive/dog/test"
```