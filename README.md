# TaichiNeuS

A Taichi implementation of extended NeuS with faster training and high quality surface reconstruction.  <br>



## Taichi Hackthon

* 团队名： **TaiGL**



### 项目介绍

NeRF是近几年三维视觉领域的一个火热工作，其对高质量的三维内容重建、机器人感知、自动驾驶、游戏等领域有着重要的意义。游戏、3D打印、AR/VR的三维资产很多都是使用Mesh来表达，然而，NeRF产生的density使用marching cube生成Mesh非常noisy。扩展工作(NeuS、volSDF)尝试针对volume rendering中的PDF或CDF进行改写，使其能拟合一个神经隐式表面，再使用marching cube生成Mesh。虽然这里所产生Mesh质量相对较好，但对于单个物体的训练非常耗时，大约20小时。因此，本项目尝试借助instant-NGP的思想和taichi框架，使用纯python代码编写，让NeuS的训练耗时缩减到分钟级别，大大减少重建三维资产的时长。



## Project

这里的扩展NeuS分为三个部分：

* Hash Grid Encoder，主要参考Instant-NGP的编码器设计
* Signed Distance Function(SDF)的表示，实现多种不同的表达接口，如SIREN, MLP with PE
* Fully Fused MLP using taichi，主要用于texture的表示



## Usage

coming soon.



## Application

主要灵感来源于[twitter](https://twitter.com/nathanwchan/status/1595267321802944513)，使用手机扫描物体(一个人型玩偶)，然后使用Blender把扫描重建出的三维玩偶做mesh cleanup，再使用Mixamo对数字玩偶进行rigging and animation，最后使用webAR进行展示。
