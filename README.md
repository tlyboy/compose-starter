# compose-starter

🐋 Docker Compose 配置模板集合，快速启动常用服务。

## 包含服务

| 服务 | 说明 |
|------|------|
| `caddy` | Caddy 服务器 |
| `caddy-cf` | Caddy + Cloudflare DNS 插件 |
| `caddy-ali` | Caddy + 阿里云 DNS 插件 |
| `mysql` | MySQL 8.1 数据库 |
| `redis` | Redis 缓存 |
| `nginx` | Nginx 服务器 |
| `n8n` | 自动化工作流工具 |
| `open-webui` | Open WebUI |
| `open-webui-cuda` | Open WebUI (CUDA GPU) |
| `verdaccio` | npm 私有仓库 |

## 使用方法

推荐使用 [degit](https://github.com/Rich-Harris/degit) 拉取单个服务模板：

```bash
npx degit tlyboy/compose-starter/caddy-cf my-caddy
cd my-caddy
docker compose up -d
```

## 环境变量

**caddy-cf:**
- `CF_API_TOKEN` - Cloudflare API Token

**caddy-ali:**
- `ALIYUN_ACCESS_KEY_ID` - 阿里云 AccessKey ID
- `ALIYUN_ACCESS_KEY_SECRET` - 阿里云 AccessKey Secret
