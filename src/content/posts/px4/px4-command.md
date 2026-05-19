---
# ==================== 必填字段 ====================

# 文章标题（必填）
title: PX4 仿真

# 发布日期（必填，格式 YYYY-MM-DD）
published: 2026-05-19

# ==================== 推荐填写的常用字段 ====================

updated: 2026-05-15
pinned: true
description: "仿真"
image: "./cover.avif"
tags: ["仿真"]
category: 仿真

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

## 仿真

### ego相关
#启动仿真程序
cd ~/PX4_Firmware
roslaunch px4 indoor1.launch 

#启动VINS-Fusion
cd ~/catkin_ws
bash scripts/xtdrone_run_vio.sh

#转换PX4所需要话题
cd ~/XTDrone/sensing/slam/vio
python vins_transfer.py iris 0

#建立通信
cd ~/XTDrone/communication
python multirotor_communication.py iris 0 

#键盘控制起飞
cd ~/XTDrone/control/keyboard
python multirotor_keyboard_control.py iris 1 vel

#深度数据
roslaunch vins rtabmap_vins.launch


> 快捷复制