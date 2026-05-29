---
# ==================== 必填字段 ====================

# 文章标题（必填）
title: 仿真

# 发布日期（必填，格式 YYYY-MM-DD）
published: 2026-05-24

# ==================== 推荐填写的常用字段 ====================

updated: 2026-05-24
pinned: true
description: "仿真指令"
image: ./images/gazebo.avif
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

### 启动仿真世界
```bash
roslaunch px4 outdoor1.launch
```

### 开启ego路径规划
```bash
roslaunch fly_px4 ego_sim.launch
```

### 启动主程序
```bash
rosrun fly_px4 fly_px4_3
```

### 一键复位世界
```bash
rosservice call /gazebo/reset_world
```

### 查看视觉画面
```bash
rosrun rqt_image_view rqt_image_view
```
