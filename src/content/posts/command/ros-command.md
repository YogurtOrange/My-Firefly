---
# ==================== 必填字段 ====================
# 文章标题（必填）
title: ROS常见命令

# 发布日期（必填，格式 YYYY-MM-DD）
published: 2026-06-04

# ==================== 推荐填写的常用字段 ====================

updated: 2026-06-04
pinned: true
description: "常见的ROS1/ROS2命令"
image: ""
tags: ["命令"]
category: 命令

# ==================== 可选字段 ====================

lang: ""
author: ""
licenseName: ""
licenseUrl: ""
sourceLink: ""
draft: false
comment: true
slug: ""
password: ""
passwordHint: ""
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# ROS1 与 ROS2 常用命令对照表

本文将 ROS1 与 ROS2 中**最常用**的命令进行并列对比，并单独列出**多语言功能包的创建方法**。无论你是从 ROS1 迁移到 ROS2 的新手，还是需要随时查阅的老手，都能快速找到需要的命令。

:::tip 环境提示
- ROS1 通常使用 `catkin` 工作空间，环境变量脚本为 `devel/setup.bash`。
- ROS2 通常使用 `colcon` 工作空间，环境变量脚本为 `install/setup.bash`。
- 本文假设你已创建好对应的工作空间。
:::

---

## 一、核心概念速查表

| 操作目的 | ROS1 命令 | ROS2 命令 |
| :--- | :--- | :--- |
| **启动 ROS Master** | `roscore` | 无需 Master，直接运行节点 |
| **列出运行中的节点** | `rosnode list` | `ros2 node list` |
| **查看节点信息** | `rosnode info /node_name` | `ros2 node info /node_name` |
| **运行一个节点** | `rosrun pkg_name node_name` | `ros2 run pkg_name node_name` |
| **列出所有话题** | `rostopic list` | `ros2 topic list` |
| **输出话题内容** | `rostopic echo /topic` | `ros2 topic echo /topic` |
| **手动发布话题消息** | `rostopic pub /topic type "data"` | `ros2 topic pub /topic type "{data: value}"` |
| **话题发布频率** | `rostopic hz /topic` | `ros2 topic hz /topic` |
| **列出所有服务** | `rosservice list` | `ros2 service list` |
| **调用服务** | `rosservice call /service "request"` | `ros2 service call /service type "request"` |
| **列出所有参数** | `rosparam list` | `ros2 param list` |
| **获取参数值** | `rosparam get /param` | `ros2 param get /node param` |
| **设置参数值** | `rosparam set /param value` | `ros2 param set /node param value` |
| **录制数据包（bag）** | `rosbag record -a` | `ros2 bag record -a` |
| **回放数据包** | `rosbag play file.bag` | `ros2 bag play file` |
| **查看功能包列表** | `rospack list` | `ros2 pkg list` |
| **查找功能包路径** | `rospack find pkg` | `ros2 pkg prefix pkg` |
| **创建新功能包** | `catkin_create_pkg` | `ros2 pkg create` |

---

## 二、多语言功能包的创建（详细步骤）

<Tabs groupId="ros-version" queryString>
  <TabItem value="ros1" label="ROS1 (catkin)" default>


### ROS1
```bash
# 1. 创建并初始化工作空间
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/src
catkin_init_workspace
cd ~/catkin_ws
catkin_make
source devel/setup.bash

# 2. 创建 C++ 功能包（依赖 roscpp 和 std_msgs）
cd ~/catkin_ws/src
catkin_create_pkg my_cpp_pkg roscpp std_msgs
cd ~/catkin_ws
catkin_make

# 3. 创建 Python 功能包（依赖 rospy 和 std_msgs）
cd ~/catkin_ws/src
catkin_create_pkg my_py_pkg rospy std_msgs
cd my_py_pkg
mkdir scripts
touch scripts/my_node.py
chmod +x scripts/my_node.py
cd ~/catkin_ws
catkin_make
```

### ROS2
```bash
# 1. 创建并构建工作空间
mkdir -p ~/ros2_ws/src
cd ~/ros2_ws
colcon build
source install/setup.bash

# 2. 创建 C++ 功能包（依赖 rclcpp 和 std_msgs）
cd ~/ros2_ws/src
ros2 pkg create my_cpp_pkg --build-type ament_cmake --dependencies rclcpp std_msgs
cd ~/ros2_ws
colcon build --packages-select my_cpp_pkg
source install/setup.bash

# 3. 创建 Python 功能包（依赖 rclpy 和 std_msgs）
cd ~/ros2_ws/src
ros2 pkg create my_py_pkg --build-type ament_python --dependencies rclpy std_msgs
cd ~/ros2_ws
colcon build --packages-select my_py_pkg
source install/setup.bash
```