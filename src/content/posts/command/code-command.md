---
# ==================== 必填字段 ====================

# 文章标题（必填）
title: 命令行

# 发布日期（必填，格式 YYYY-MM-DD）
published: 2026-05-15

# ==================== 推荐填写的常用字段 ====================

updated: 2026-06-11
pinned: true
description: "快捷命令"
image: ""
tags: ["命令"]
category: 飞控指令

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

## 命令行

供快速复制使用

### 代码示例

### 启动奥比中光
```bash
ros2 launch orbbec_camera gemini2.launch.py 
```

### 启动yolo配置文件
```bash
python3 yolo_config.py 
```

### 运行斜视识别程序
```bash
python3 ch_robot_up.py 
```

### 模拟雷达发送程序
```bash
python3 odom_pub.py
```

### 发布话题订阅
```bash
ros2 topic echo /multi/position/class
```

> 快捷复制