---
# ==================== 必填字段 ====================
# 文章标题（必填）
title: pnpm/npm

# 发布日期（必填，格式 YYYY-MM-DD）
published: 2026-06-04

# ==================== 推荐填写的常用字段 ====================

updated: 2026-06-04
pinned: true
description: "前端包管理器的常见命令"
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
password: "032722"
passwordHint: ""
---

# 🚀 前端包管理器（npm / pnpm）及 Astro 常用命令指南
在前端开发中，合理使用包管理器能让你的开发效率翻倍。由于本项目推荐使用 `pnpm`，建议在日常开发中优先使用 `pnpm` 相关的命令。
---
## 📌 1. 核心命令对比表

| 命令功能 | `npm` 标准命令 | `pnpm` 高效命令 | 简写与实际应用场景说明 |
| :--- | :--- | :--- | :--- |
| **初始化新项目** | `npm init` | `pnpm init` | 创建一个基础的 `package.json` 文件 |
| **安装项目所有依赖** | `npm install` | `pnpm install` | 简写：`pnpm i`。**切换系统/拉取代码后必跑** |
| **添加单包（正式环境）** | `npm install <包名>` | `pnpm add <包名>` | 示例：`pnpm add gl-matrix`（代码中需要引入） |
| **添加单包（开发环境）** | `npm install <包名> -D` | `pnpm add <包名> -D` | `-D` / `--save-dev`：只在开发打包时使用（如 TypeScript） |
| **全局安装工具** | `npm install <包名> -g` | `pnpm add <包名> -g` | 安装到本地电脑全局环境（如一些脚手架工具 CLI） |
| **卸载/删除依赖包** | `npm uninstall <包名>` | `pnpm remove <包名>` | 简写：`pnpm rm`。会同步从 `package.json` 中抹去 |
| **更新所有依赖包** | `npm update` | `pnpm update` | 简写：`pnpm up`。根据版本号规则更新最新补丁 |
| **运行项目自定义脚本** | `npm run <脚本名>` | `pnpm <脚本名>` | **`pnpm` 运行脚本时可省略 `run`**，如 `pnpm dev` |
| **执行临时远程命令** | `npx <命令>` | `pnpm dlx <命令>` | 示例：`pnpm dlx shadcn@latest add <组件名>` |
| **强制清理本地缓存** | `npm cache clean --force` | `pnpm store prune` | 解决安装卡死、依赖损坏、腾出硬盘空间时使用 |

---
## 🧭 2. 团队协作与多系统切换流水线
当你换到另一台电脑，或者从 GitHub 上 `pull` / `clone` 了最新的代码，请严格按照以下步骤在终端执行，确保项目零报错运行：
1. **进入项目根目录**：
   ```bash
   cd Firefly

2. **一键还原并安装所有依赖包**：
   ```bash
   pnpm install

3. **启动本地开发预览服务器**：
   ```bash
   pnpm dev