# Snipe-IT 自动安装脚本

这是一个 **全自动化的 Bash 安装脚本**，用于在 Ubuntu Server 上部署 [Snipe-IT](https://snipeitapp.com/) 资产管理系统。  
支持 **数据库、PHP、Redis、Supervisor、Nginx、SMTP 邮件** 等完整配置，适合快速搭建生产环境。

---

## ✨ 功能特性
- 一键安装 Snipe-IT 及依赖（MariaDB、PHP、Composer、Node.js、Redis、Supervisor）
- 自动生成并校正 `.env` 配置文件（支持交互式输入）
- 支持 **SMTP 邮件** 配置（含用户名、密码、回复地址）
- 支持 Redis 缓存、队列、会话
- 自动配置 Nginx（默认 80 端口，可扩展 HTTPS）
- 提供环境检查、日志、重试机制、锁机制、防并发
- 中文交互菜单，彩色输出

---

## 📦 环境要求
- 系统：Ubuntu Server 20.04/22.04（推荐）
- Bash：版本 >= 4.2
- 需要 **root 权限**（或 sudo）

---

## 🚀 快速开始

1. 下载脚本：
   ```bash
   git clone https://github.com/husibo16/Snipe-IT.git
   cd Snipe-IT

## 🚀 一键安装（推荐）
2. 如果你不想手动下载脚本，可以直接用下面的一条命令自动获取并运行：

   ```bash
   curl -fsSL https://raw.githubusercontent.com/husibo16/Snipe-IT/main/snipeit_installer.sh | sudo bash

