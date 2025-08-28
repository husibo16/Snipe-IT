# Snipe-IT 自动安装脚本

这是一个 **全自动化的 Bash 脚本**，用于在 Ubuntu Server 上快速部署 [Snipe-IT](https://snipeitapp.com/) 资产管理系统。  
脚本内置 **交互式菜单** 与 **子命令模式**，既适合新手一步步操作，也方便老手一键自动化安装。  

---

## ✨ 功能特性

- 一键安装 **Snipe-IT** 及全部依赖：
  - MariaDB（数据库）
  - PHP（含扩展、FPM、Redis、LDAP）
  - Node.js & npm
  - Redis（缓存/队列/会话）
  - Supervisor（队列守护进程）
  - Nginx（反向代理）
- 自动生成并配置 **`.env` 文件**
  - 支持 APP_URL、数据库参数、邮件（SMTP）、Redis 等
  - 支持交互式输入与智能默认值
- 支持 **SMTP 邮件配置测试**（不发信，仅验证连通性）
- 支持 **Redis 开关选择**
- 提供 **防火墙配置（UFW）**
- 支持 **交互式菜单** 或 **命令模式** 两种方式
- 日志记录、错误堆栈、并发锁定、临时目录自动清理
- 中文提示，彩色输出，友好直观

---

## 📦 环境要求

- 系统：Ubuntu Server 20.04 / 22.04（推荐）
- Bash：版本 >= 4.2
- Root 权限（或 sudo）

---

## 🚀 快速安装

你可以一条命令直接运行脚本：

```bash
curl -fsSL https://raw.githubusercontent.com/husibo16/Snipe-IT/main/snipeit_installer.sh | sudo bash -s


