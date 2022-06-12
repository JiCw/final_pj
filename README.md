## 目标检测任务

### 随机初始化

使用VOC2007数据集进行训练和测试，将数据集解压至`VOCdevkit`文件夹。
	
修改代码文件：
`utils/config.py`修改参数`voc_data_dir`为数据集对应路径；修改预训练模型路径以加载随机初始化参数。
	
`model/faster_rcnn_vgg16.py`修改`line20`为`model = vgg16(pretrained=False)`

运行`model_train.ipynb`中`train()`函数开始训练。

### ImageNet预训练

使用VOC2007数据集进行训练和测试，将数据集解压至`VOCdevkit`文件夹。
	
修改代码文件：
`utils/config.py`修改参数`voc_data_dir`为数据集对应路径；修改预训练模型路径以加载ImageNet预训练参数。
	
`model/faster_rcnn_vgg16.py`修改`line20`为`model = vgg16(pretrained=True)`

运行`model_train.ipynb`中`train()`函数开始训练。

### COCO预训练Mask R-CNN

使用VOC2012数据集进行训练和测试，将数据集解压至`VOCdevkit`文件夹。
	
预训练参数设置：
运行`参数读取.ipynb`修改参数，Faster R-CNN模型的backbone参数部分替换为COCO数据集上预训练的Mask R-CNN模型的backbone参数，head部分使用numpy进行随机初始化。

运行`python train_res50_fpn.py`命令开始训练。
