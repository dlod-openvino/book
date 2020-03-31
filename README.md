# 《深度学习图像识别技术：基于TensorFlow Object Detection API和OpenVINO<sup>TM</sup>工具套件》
![front_cover](https://github.com/dlod-openvino/book/blob/master/封面.jpg)

## 【随书资料下载链接】
[360网盘](https://yunpan.360.cn/surl_yrkBV8cRhDT) （提取码：d52e）
[百度网盘](https://pan.baidu.com/s/1OMXOlN_Cr4aITG9LfhTWNQ) （提取码：ftco）

## 【注意项】

**安装TensorFlow前请卸掉之前安装的TensorFlow、Python和CUDA**
+ 问题：有读者用命令conda install tensorflow-gpu=1.13，但TF的版本却是1.15.1
+ 原因：该读者之前在自己的电脑上已安装过TensorFlow，遇到了多版本冲突
+ 解决：请读者在按照本书搭建TensorFlow开发环境前，先卸掉之前安装的TensorFlow、Python、Anaconda和CUDA，从一个干净的环境开始搭建

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
+ 请确保Anaconda Navigator的版本大于1.7，或者卸掉您已经安装的老版本，从清华镜像源下载最新的Anaconda
---

由于笔者的水平有限，书中难免会出现错误或者不准确的地方，恳请读者批评指正。读者可以将书中的错误以及遇到的任何问题反馈给我们，我们将尽量在线上为读者提供最满意的解答。
Email: dlod_openvino@163.com

## 【问题回复】
