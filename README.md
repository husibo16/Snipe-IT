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

交互模式（推荐首次使用）
```bash
sudo bash snipeit_installer.sh
```
你可以一条命令直接运行脚本
```bash
curl -fsSL https://raw.githubusercontent.com/husibo16/Snipe-IT/main/snipeit_installer.sh | sudo bash -s 一键全装
```
---
🖼️ 运行效果截图
★ Snipe-IT 全量安装器（中文交互）★
  1) 体检_precheck          - 环境体检/基础工具安装（含 Git）
  2) 安装_db_mariadb        - 安装并初始化 MariaDB，创建库和账户
  3) 安装_php               - 安装 PHP(自动识别次版本) 及扩展 + PHP-FPM
  4) 安装_composer          - 安装 Composer
  5) 安装_node              - 安装 Node.js & npm
  6) 安装_redis             - 安装并启用 Redis
  7) 安装_supervisor        - 安装并配置 Supervisor（Laravel 队列）
  8) 拉取_配置_snipeit      - 克隆 Snipe-IT 并生成/校正 .env
  9) 配置_nginx             - 安装并配置 Nginx（指向 public/）
 10) 初始化_依赖_数据库     - composer 依赖 + APP_KEY + migrate
 11) 配置_防火墙            - UFW 放行 OpenSSH & Nginx Full
 12) 测试_smtp              - 测试到 SMTP 主机:端口的连通性（不发信）
 13) 一键全装               - 按最佳顺序执行全部步骤
 14) 状态_status            - 展示环境信息（IP/PHP/FPM 等）
  q) 退出
👉 你的选择: 
---

⚠️ 注意事项

默认只配置 HTTP (80)，生产环境请额外配置 HTTPS (443)（推荐 certbot）

数据库 root 密码请执行 mysql_secure_installation 加固

邮件测试需在 后台界面完成，脚本仅检测端口连通性

Redis 默认关闭，如需启用会自动写入 .env

建议定期备份数据库 + storage/ + .env
