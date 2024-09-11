# LADSMPN:Libraries for Autonomous Driving Static Motion Planning Nonholonomic

## 1，Introduction

 		为求解自动驾驶静态避障任务，我们建立了一个路径规划库和场景库：考虑运动学的自动驾驶静态路径规划库(Libraries for Autonomous Driving Static Motion Planning Nonholonomic, LADSMPN)，如下图所示，该库包括一组算法和测试场景。

 <img width="426" alt="image" src="https://github.com/user-attachments/assets/bea8c1e8-7121-4ffb-a189-001ea68b5086">

​		==**该库可以分为对象模块、算法模块和结果模块，对LADSMPN的详细介绍将在论文接收后进行开源。==**

<img width="284" alt="image" src="https://github.com/user-attachments/assets/a2591a47-4040-4300-9a4d-d9723b903363">

## 2，Question

​        静态路障下的局部避障规划是在全局路径规划的基础上，依据感知信息，输出一条满足**运动学约束、两点边值约束、曲率约束及碰撞躲避约束**的光滑的、安全的路径。主要解决的问题为：如下面示意图所示，给定起始位姿和终止位姿，障碍物位置，尺寸等，规划一条安全平滑的路径供车辆执行。

<img width="388" alt="image" src="https://github.com/user-attachments/assets/27163c10-da80-4620-8238-c0d4487eebd6">

## 3，Vehicle Kinematic

​		使用的车辆模型为阿克曼转向模型：
<img width="284" alt="image" src="https://github.com/user-attachments/assets/4a8b8a2b-4958-475e-8da6-bf9569a2a54e">

![image](https://github.com/user-attachments/assets/6895ae70-a4d1-423e-9179-97ae5465a4fd)


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
| <img width="124" alt="image" src="https://github.com/user-attachments/assets/809103ae-4d52-4d14-9024-22da478f2a60">
 |<img width="124" alt="image" src="https://github.com/user-attachments/assets/b2ef8e79-61be-432f-a840-be5191151c5e">
 | <img width="124" alt="image" src="https://github.com/user-attachments/assets/4b01c6bf-bbb2-47e8-904e-7852fa33d2ea">
 |
| 障碍物密度0.5                                                | 障碍物密度0.7                                                | 障碍物密度0.9                                                |
| <img width="124" alt="image" src="https://github.com/user-attachments/assets/d3c751a9-8d50-43f3-aca8-17111cacd5bd">
 | <img width="124" alt="image" src="https://github.com/user-attachments/assets/c2990aeb-a06a-4004-846f-d18069e194b5">
| <img width="124" alt="image" src="https://github.com/user-attachments/assets/d33a2cf1-792a-4904-aae6-aca356b29c31">

 |

## 5，Historical Version

在开始该库之前，进行了多个版本的尝试：

版本v1:https://www.baidu.com/s?

版本v2:https://www.baidu.com/s?
