---
# ==================== 必填字段 ====================

# 文章标题（必填）
title: github使用教程

# 发布日期（必填，格式 YYYY-MM-DD）
published: 2026-05-24

# ==================== 推荐填写的常用字段 ====================

updated: 2026-06-04
pinned: true
description: "github常用指令"
image: ./github.avif
tags: ["github"]
category: github

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

## github

### 克隆远程仓库到本地
```bash
git clone 
```

### 初始化本地仓库并关联远程
```bash
git init
git remote add origin <仓库地址>
```

### 查看远程仓库信息
```bash
git remote -v
```

### 查看当前状态（修改了哪些文件）
```bash
git status
```

### 将修改添加到暂存区
```bash
git add . 
```

### 提交到本地仓库
```bash
git commit -m "提交说明"
```

### 推送到 GitHub
```bash
git push origin <分支名>
```

### 拉取远程更新并合并到本地
```bash
git pull origin <分支名>
```

### 查看所有分支(包含远程分支)
```bash
git branch -a       
```

### 创建新分支
```bash
git branch <分支名>
```

### 允许合并无关历史（从 ZIP 包连接仓库时用）
```bash
git merge origin/分支名 --allow-unrelated-histories
```