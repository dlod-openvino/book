# 《深度学习图像识别技术：基于TensorFlow Object Detection API和OpenVINO<sup>TM</sup>工具套件》
![front_cover](https://github.com/dlod-openvino/book/blob/master/封面.jpg)

## 【随书资料下载链接】
[360网盘](https://yunpan.360.cn/surl_yrkBV8cRhDT) （提取码：d52e）
[百度网盘](https://pan.baidu.com/s/1OMXOlN_Cr4aITG9LfhTWNQ) （提取码：ftco）
---
## 【注意项】

#### 【OpenVINO版本】请选择2019R3版，跟本书保持一致;
#### 【安装到C盘！！】在Windows中安装OpenVINO，一定要安装到C盘！！！
下载链接：
https://software.intel.com/en-us/openvino-toolkit/choose-download?innovator=CONT-0017856

#### 【下载须知】 360网盘资料下载不成功问题
+ 问题：超过1GB会自动断掉
+ 原因：非360会员
+ 解决：用浏览器打开360云盘分享链接后，请进入 **深度学习目标检测技术** 文件夹，**分别逐个下载所有的压缩文件**。每个压缩文件都在500M左右，经过东莞、北京、上海、深圳多地测试，下载成功率100%

#### 【搭建TensorFlow开发环境须知】安装TensorFlow前请卸掉之前安装的TensorFlow、Python和CUDA
+ 问题：有读者用命令conda install tensorflow-gpu=1.13.1，但查看TensorFlow的版本却是1.15.1
+ 原因：该读者之前在自己的电脑上已安装过TensorFlow，遇到了多版本冲突
+ 解决：请读者在按照本书搭建TensorFlow开发环境前，先卸掉之前安装的TensorFlow、Python、Anaconda和CUDA，从一个干净的环境开始搭建

#### 【numpy版本≥1.16导致训练不成功】请卸载掉numpy，然后用pip install numpy==1.16.4重装numpy
+ 问题：用命令conda install tensorflow-gpu=1.13.1，conda会安装最新版的Numpy≥1.18.2，这会导致命令：python train.py --logtostderr --train_dir=training\ --pipeline_config_path=training\ssd_inception_v2_coco.config 无法成功启动训练
+ 原因：Tensorflow object detection api 不支持numpy 1.18.2
+ 解决：请用命令pip uninstall numpy先卸载掉numpy，然后用pip install numpy==1.16.4重装numpy

#### 【3.8节，运行train.py训练模型时报错：NotFoundError: NewRandomAccessFile failed to Create/Open】
+ 问题：读者没有按照本书的路径配置训练文件夹，且没有按照3.4.3节重新标注图片，导致标注文件的路径跟实际图片的路径不一致。
+ 解决：参考3.4.4节，打开标注文件.xml，核对路径; 若不一致，请重新标注并保存标注文件; 或者先建立跟本书一样的路径

#### 【3.8节，运行train.py训练模型时报错：ValueError: Tensor conversion requested dtype string for Tensor with dtype float32: 'Tensor("arg0:0", shape=(), dtype=float32, device=/device:CPU:0)'】
+ 问题：读者没有按照本书3.7.3节配置文件，尤其是train.tfrecord的路径 或 文件名 写错
+ 解决：pipeline.config文件中的train_input_reader的配置参数与文件所在的实际路径一定要一致！

**勘误1 Page39**
+ 原文：conda install tensorflow-gpu=1.13
+ 改为：conda install tensorflow-gpu=1.13.1
+ 原因：anaconda软件服务器版本变化

**注意1 Page124 OpenVINO 2020 R1版开始，cpu_extension库已经集成到推理引擎中去了，不用用户手动编译了**
+ 原文：将intel64→Debug文件夹下的cpu_extension.lib文件复制到C:\Program Files (x86)\IntelSWTools\openvino_2019.3.334\inference_engine\lib\intel64\Debug文件夹
+ 注意：OpenVINO 2020 R1版开始不需要通过编译Samples获得cpu_extension库；OpenVINO 2020 R1之前的版本都需要

**注意2 Anaconda官网打不开，请从清华镜像源下载**
+ 多名读者反馈Anaconda官网打不开，无法下载Anaconda
+ 解决方案：从清华镜像源下载 https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/
+ 配置Anaconda清华源镜像，参看：https://mirrors.tuna.tsinghua.edu.cn/help/anaconda/

**注意3 有读者反馈git clone -b r1.13.0 https://github.com/tensorflow/models.git 下载速度慢**
+ 请从云盘下载本书附带资料，本书已帮读者下载了models文件夹
+ 或者请参考利用码云来克隆GitHub项目，解决github下载速度慢的问题
https://blog.csdn.net/TeFuirnever/article/details/99110367

**注意4 Page32 有读者反馈Anaconda Navigator里面找不到VS Code**
+ 请确保Anaconda Navigator的版本大于1.7，或者卸掉您已经安装的Anaconda，从清华镜像源下载并安装最新的Anaconda
+ 当前最新版的Anaconda没有VScode的安装选项了，建议**读者到VSCode官网下载(https://code.visualstudio.com/)，手动安装即可**

**注意5 有读者在转换OpenVINO IR模型时不成功，错误为：Graph object has no attribute 'node'**
+ 原因: OpenVINO 2019以及之前所有版本，不支持networkx2.4
+ 解决方案:先卸载networkx2.4：pip uninstall networkx; 然后安装networkx 2.0版本：pip install networkx==2.0
+ 参考资料：https://www.jianshu.com/p/2be7b448b788

**注意6 demo_squeezenet_download_convert_run.bat 运行不成功**
+ 原因: squeezenet.1.1.caffemodel模型的服务器有问题，下载不容易成功
+ 解决方案: 1, 连接手机4G热点后再运行；2, 运行demo_security_barrier_camera.bat，该模型下载成功率高，若能正确运行，也说明OpenVINO开发环境安装成功！
---

由于笔者的水平有限，书中难免会出现错误或者不准确的地方，恳请读者批评指正。读者可以将书中的错误以及遇到的任何问题反馈给我们，我们将尽量在线上为读者提供最满意的解答。
Email: dlod_openvino@163.com

## 【问题回复】
