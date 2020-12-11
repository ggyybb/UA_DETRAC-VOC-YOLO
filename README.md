# UA_DETRAC-VOC-YOLO
车辆检测数据集：UA-DETRAC是一个具有挑战性的真实世界多目标检测和多目标跟踪基准。该数据集包括在中国北京和天津的24个不同地点使用Cannon EOS 550D相机拍摄的10小时视频。视频以每秒25帧（fps）的速度录制，分辨率为960×540像素。UA-DETRAC数据集中有超过14万个帧，手动注释了8250个车辆，总共有121万个标记的对象边界框。
# 1.解析转换过程（注意改对自己的路径）
## （1）解压数据集
    解压 DETRAC-Train-Images和DETRAC-Train-Annotations-XML
## （2）运行DETRAC_xmlParser_test.py
    基于此https://blog.csdn.net/w5688414/article/details/78931910博客做了一点改进。
    a.正确的车辆类别（原来的代码只用了car代替了所有类别）
    b.原数据集中bbox坐标点是小数，原来的转换代码直接用了int，我观察生成的框有错位的情况，索性直接用float，因为转换yolo格式不需要是整数，这样框更准一点。
## 可以看文件夹里的图片体验一下
## （3）把图片移动到一起
    运行voc_data_migrate.py
    对应名称+移动位置
## （4）剩下就和yolo训练一样
    图片xml放好在yolo的data里，运行maketext和voc_label_coco，配置好yaml文件就可以训练了。
# 参考链接
## 博客：https://blog.csdn.net/w5688414/article/details/78931910
## github：https://github.com/w5688414/datasets-preprocessing-for-object-detection
