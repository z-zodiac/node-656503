# Cloudflare Worker Auto-Sync

[![Auto Update Worker](https://github.com/your-username/node-656503/actions/workflows/node.yml/badge.svg)](https://github.com/your-username/node-656503/actions/workflows/node.yml)
[![Version](https://img.shields.io/badge/version-v3.3.1-blue)](https://github.com/your-username/node-656503)

自动同步和维护 Cloudflare Worker 脚本的最新版本。

## 📋 项目简介

这是一个自动化同步仓库，用于：
- 🔄 自动跟踪上游项目的最新发布版本
- 📦 自动下载并解压最新的 worker.zip 文件
- 🚀 提供即用的 Cloudflare Worker 脚本
- 📊 版本追踪和更新日志

## 📁 文件结构

```
├── _worker.js          # Cloudflare Worker 脚本文件
├── version.txt         # 当前同步的版本号
├── README.md          # 项目说明文档
└── .github/
    └── workflows/
        └── node.yml   # 自动更新工作流
```

## 🚀 使用方法

### 方法一：直接使用 Worker 脚本

1. 复制 `_worker.js` 文件的内容
2. 在 Cloudflare Dashboard 中创建新的 Worker
3. 粘贴代码并部署

### 方法二：Fork 此仓库

1. Fork 此仓库到你的 GitHub 账户
2. 启用 GitHub Actions（如果需要自动更新）
3. 使用仓库中的 `_worker.js` 文件

## ⚙️ 自动更新机制

### 触发条件
- 📅 **定时更新**：每天凌晨 1 点自动检查更新
- 🔄 **推送触发**：向 main 分支推送代码时
- 🎯 **手动触发**：支持手动运行工作流

### 更新流程
1. 检查本地版本与远程最新版本
2. 如有新版本，自动下载 `worker.zip`
3. 解压并更新 `_worker.js` 文件
4. 更新 `version.txt` 版本记录
5. 自动提交更改到仓库

### 手动强制更新
```bash
# 在 GitHub Actions 页面手动运行工作流
# 设置 force_update 参数为 true 可忽略版本检查强制更新
```

## 📊 版本信息

- **当前版本**：`v3.3.1`
- **更新频率**：每日检查
- **最后更新**：自动维护
- **脚本类型**：Cloudflare Worker

## 🔧 配置说明

### 环境变量
- `REPO_URL`：源仓库 API 地址
- `TARGET_FILE`：目标文件名 (worker.zip)
- `GITHUB_TOKEN`：GitHub 访问令牌（自动提供）

### 工作流权限
- `contents: write` - 用于提交更新后的文件

## 📝 更新日志

所有更新都会自动记录在 Git 提交历史中，提交信息格式：
```
🔄 自动同步 Worker 版本: v3.3.1
```

## ⚠️ 注意事项

1. **代码审查**：虽然自动同步，但建议定期检查更新的代码
2. **备份重要**：部署前请备份现有的 Worker 配置
3. **测试环境**：建议先在测试环境验证新版本
4. **依赖关系**：确保 Cloudflare Worker 环境支持新版本特性

## 🤝 贡献

欢迎提交 Issue 和 Pull Request 来改进这个自动同步工具。

### 贡献指南
1. Fork 项目
2. 创建特性分支
3. 提交更改
4. 推送到分支
5. 创建 Pull Request

## 📄 许可证

本项目遵循 MIT 许可证，详情请查看 LICENSE 文件。

## 🔗 相关链接

- [Cloudflare Workers 文档](https://developers.cloudflare.com/workers/)
- [GitHub Actions 文档](https://docs.github.com/en/actions)
- [Node.js 官方文档](https://nodejs.org/docs/)

---

> 🤖 此仓库由 GitHub Actions 自动维护，确保始终同步最新版本的 Worker 脚本。