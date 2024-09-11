# LADSMPN:Libraries for Autonomous Driving Static Motion Planning Nonholonomic

## 1，Introduction

 		为求解自动驾驶静态避障任务，我们建立了一个路径规划库和场景库：考虑运动学的自动驾驶静态路径规划库(Libraries for Autonomous Driving Static Motion Planning Nonholonomic, LADSMPN)，如下图所示，该库包括一组算法和测试场景。

![image-20240911190124963](C:\Users\zhou\AppData\Roaming\Typora\typora-user-images\image-20240911190124963.png)

​		==**该库可以分为对象模块、算法模块和结果模块，对LADSMPN的详细介绍将在论文接收后进行开源。==**

![image-20240911190332383](C:\Users\zhou\AppData\Roaming\Typora\typora-user-images\image-20240911190332383.png)

## 2，Question

​        静态路障下的局部避障规划是在全局路径规划的基础上，依据感知信息，输出一条满足**运动学约束、两点边值约束、曲率约束及碰撞躲避约束**的光滑的、安全的路径。主要解决的问题为：如下面示意图所示，给定起始位姿和终止位姿，障碍物位置，尺寸等，规划一条安全平滑的路径供车辆执行。

![image-20240911185221104](C:\Users\zhou\AppData\Roaming\Typora\typora-user-images\image-20240911185221104.png)

## 3，Vehicle Kinematic

​		使用的车辆模型为阿克曼转向模型：

![image-20240911185548851](C:\Users\zhou\AppData\Roaming\Typora\typora-user-images\image-20240911185548851.png)

![img](file:///C:\Users\zhou\AppData\Local\Temp\ksohtml14100\wps1.png       )        

在此等式中：

·时刻![img](file:///C:\Users\zhou\AppData\Local\Temp\ksohtml14100\wps2.png)为待定变量；

·![img](file:///C:\Users\zhou\AppData\Local\Temp\ksohtml14100\wps3.png)为车辆后轮轴中点坐标；

·![img](file:///C:\Users\zhou\AppData\Local\Temp\ksohtml14100\wps4.png)分别为沿车体纵轴方向的速度及加速度，以车辆前进的方向为正；

·![img](file:///C:\Users\zhou\AppData\Local\Temp\ksohtml14100\wps5.png)为前轮转向角，以左偏为正；

·![img](file:///C:\Users\zhou\AppData\Local\Temp\ksohtml14100\wps6.png)为前轮转向角速度；

·![img](file:///C:\Users\zhou\AppData\Local\Temp\ksohtml14100\wps7.png)为车辆航向角，即从![img](file:///C:\Users\zhou\AppData\Local\Temp\ksohtml14100\wps8.png)轴正方向到车体纵轴正方向的角度，以逆时针转向为正；

·![img](file:///C:\Users\zhou\AppData\Local\Temp\ksohtml14100\wps9.png)为前后轮轴距，![img](file:///C:\Users\zhou\AppData\Local\Temp\ksohtml14100\wps10.png)为车辆前悬距离，![img](file:///C:\Users\zhou\AppData\Local\Temp\ksohtml14100\wps11.png)为车辆后悬距离，![img](file:///C:\Users\zhou\AppData\Local\Temp\ksohtml14100\wps12.png)为车长，![img](file:///C:\Users\zhou\AppData\Local\Temp\ksohtml14100\wps13.png)为车宽。

## 4，Results

​		我们设置了27种仿真场景，评价指标涵盖如下5种，某种直行场景的规划结果如下。

| 评价指标               | 指标含义                                                     | 单位 |
| ---------------------- | ------------------------------------------------------------ | ---- |
| 算法循环次数           | 指的是搜索算法前向搜索到终点的采样次数，其值可以反映算法搜索效率，越小越好 | /    |
| 算法运行时间           | 指的是算法搜索到从起点到终点的路径时程序运行所用的时间，其值可以反映算法实时性，越小越好 | ms   |
| 算法规划路径长度       | 指的是算法规划的路径的长度，其值可以反映算法优化能力，越小越好 | m    |
| 算法规划路径曲率平方和 | 指的是算法规划的路径上路径点的曲率平方和，其值可以反映算法稳定性，越小越好 | /    |
| 算法规划路径成功率     | 指的是算法路径规划成功的次数比上路径规划的总次数，其值可以反映算法有效性，越大越好 | %    |

![1_3](D:\0other\Github\static_motion_planning\static_motion_planning_nonholonomic4\result\gif\1_3.gif)

​		最后，我们也做了不同障碍物密度下仿真，规划路径示意图如下：

| 初始场景                                                     | 障碍物密度0.1                                                | 障碍物密度0.3                                                |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![img](file:///C:\Users\zhou\AppData\Local\Temp\ksohtml14100\wps20.jpg) | ![img](file:///C:\Users\zhou\AppData\Local\Temp\ksohtml14100\wps21.jpg) | ![img](file:///C:\Users\zhou\AppData\Local\Temp\ksohtml14100\wps22.jpg) |
| 障碍物密度0.5                                                | 障碍物密度0.7                                                | 障碍物密度0.9                                                |
| ![img](file:///C:\Users\zhou\AppData\Local\Temp\ksohtml14100\wps23.jpg) | ![img](file:///C:\Users\zhou\AppData\Local\Temp\ksohtml14100\wps24.jpg) | ![img](file:///C:\Users\zhou\AppData\Local\Temp\ksohtml14100\wps25.jpg) |

## 5，Historical Version

在开始该库之前，进行了多个版本的尝试：

版本v1:https://www.baidu.com/s?

版本v2:https://www.baidu.com/s?