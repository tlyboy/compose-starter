# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

这是一个 Docker Compose 配置模板集合，提供常用服务的快速启动配置。每个服务独立存放在单独的目录中，包含自己的 `compose.yaml` 文件。

## 项目结构

```
├── caddy/          # 标准 Caddy 服务器
├── caddy-cf/       # Caddy + Cloudflare DNS 插件（用于 DNS 验证 TLS）
├── caddy-ali/      # Caddy + 阿里云 DNS 插件（用于 DNS 验证 TLS）
├── mysql/          # MySQL 8.1 数据库
├── redis/          # Redis 缓存服务
├── nginx/          # Nginx 服务器
├── n8n/            # n8n 自动化工作流工具
├── open-webui/     # Open WebUI (无 GPU)
├── open-webui-cuda/# Open WebUI (CUDA GPU 支持)
├── verdaccio/      # npm 私有仓库
```

## 使用模板

推荐使用 [degit](https://github.com/Rich-Harris/degit) 拉取单个服务模板：

```bash
# 拉取指定服务模板（例如 caddy-cf）
npx degit tlyboy/compose-starter/caddy-cf my-caddy

# 或安装后使用
npm install -g degit
degit tlyboy/compose-starter/redis my-redis
```

## 常用命令

启动服务（在对应目录下执行）：
```bash
docker compose up -d
```

停止服务：
```bash
docker compose down
```

构建自定义镜像（caddy-cf/caddy-ali）：
```bash
docker compose build
docker compose up -d
```

## Caddy DNS 验证配置

- **caddy-cf**: 需要设置环境变量 `CF_API_TOKEN`（Cloudflare API Token）
- **caddy-ali**: 需要设置环境变量 `ALIYUN_ACCESS_KEY_ID` 和 `ALIYUN_ACCESS_KEY_SECRET`

## 代码格式化

- 使用 Prettier 格式化，配置：无分号、单引号
- 缩进：2 空格
- 换行符：LF
- Dockerfile 使用 VSCode Docker 扩展格式化
