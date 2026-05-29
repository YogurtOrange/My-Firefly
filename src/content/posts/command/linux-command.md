---
# ==================== 必填字段 ====================

# 文章标题（必填）
title: Linux--命令

# 发布日期（必填，格式 YYYY-MM-DD）
published: 2026-05-15

# ==================== 推荐填写的常用字段 ====================

updated: 2026-05-15
pinned: true
description: "Linux常用命令"
image: "./images/ubuntu.avif"
tags: ["命令"]
category: Linux

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

## Linux常用命令行

供快速复制使用

### 常用命令

### 创建空文件或更新文件时间
```bash
mkdir
```

### 复制文件/目录
```bash
cp
```

### 移动/重命名
```bash
mv
```

### 删除文件或目录
```bash
rm
```

### 搜索文件
```bash
find
```

### 输出文件全部内容
```bash
cat
```

### 文本搜索，常用
```bash
grep
```

### 修改文件权限
```bash
chmod +x script.sh
chmod 755 file
```

### 实时进程和资源监控
```bash
htop
```

### 终止进程
```bash
kill -9 PID
pkill -f process_name
```


### 查看磁盘分区空间
```bash
df -h
```

### 查看内存
```bash
free -h
```

### 系统信息
```bash
uname -a
```

### 测试网络连通性
```bash
ping -c 4 8.8.8.8
```

### 下载文件
```bash
wget url
#断点续传
wget -c url
```

### 远程复制
```bash
scp file user@host:/path
```

### 远程登录
```bash
ssh user@host
```

### 压缩/解压 .gz
```bash
#解压
gzip file
#压缩
gunzip file.gz
```

### 跨平台 .zip
```bash
zip -r archive.zip dir/
unzip archive.zip
```
> 快捷复制