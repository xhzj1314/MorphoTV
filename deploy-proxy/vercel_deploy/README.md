# MorphoTV 代理服务器 - Vercel 版本

> 🚀 基于 Vercel 的高性能代理服务器，支持 `/proxy` 路径格式

## 🌟 特性

- ✅ **零配置部署**：与 GitHub 无缝集成
- ✅ **全球 CDN**：自动分发到全球节点
- ✅ **CORS 支持**：解决跨域访问问题
- ✅ **智能缓存**：提升响应速度
- ✅ **错误处理**：友好的错误信息
- ✅ **实时监控**：内置性能监控

## 🚀 快速部署

### 方法一：GitHub 自动部署（推荐）

1. **Fork 项目到您的 GitHub**
2. **访问 [Vercel Dashboard](https://vercel.com/dashboard)**
3. **点击 "New Project"**
4. **选择您的 GitHub 仓库**
5. **设置项目根目录为 `deploy-proxy/vercel-deploy`**
6. **点击 "Deploy"**

### 方法二：Vercel CLI 部署

```bash
# 安装 Vercel CLI
npm i -g vercel

# 进入项目目录
cd deploy-proxy/vercel-deploy

# 登录 Vercel
vercel login

# 部署项目
vercel --prod
```

## 🔧 配置 MorphoTV

部署成功后，在 MorphoTV 中配置代理地址：

```json
{
  "PROXY_BASE_URL": "https://your-app.vercel.app/api/proxy?url="
}
```

## 📝 API 使用

### 代理请求格式

```
https://your-app.vercel.app/api/proxy/[目标URL]
```

### 示例

```bash
# 代理豆瓣电影 API
curl "https://your-app.vercel.app/api/proxy/https://movie.douban.com/j/search_subjects?type=movie"

# 代理 GitHub API
curl "https://your-app.vercel.app/api/proxy/https://api.github.com/users/octocat"
```

## 🛠️ 本地开发

```bash
# 安装依赖（可选，本项目无外部依赖）
npm install

# 启动开发服务器
npm run dev

# 访问 http://localhost:3000
```

## 📊 性能特点

- **响应时间**：< 100ms（全球 CDN）
- **免费额度**：100GB 带宽/月
- **并发支持**：高并发处理
- **缓存策略**：智能缓存优化

## 🔒 安全特性

- 自动 HTTPS 加密
- CORS 跨域支持
- 请求头过滤
- 错误信息脱敏

## 📈 监控和日志

- Vercel Analytics 性能监控
- 函数执行日志
- 错误追踪和报告
- 实时性能指标

## 🔧 自定义配置

### 环境变量

在 Vercel 项目设置中可以配置：

- `ALLOWED_DOMAINS`：允许的域名白名单
- `CACHE_TTL`：缓存过期时间（秒）
- `MAX_CACHE_SIZE`：最大缓存条目数

### 域名配置

1. 在 Vercel 项目设置中添加自定义域名
2. 配置 DNS 记录
3. 自动获得 SSL 证书

## 🐛 故障排除

### 常见问题

1. **部署失败**：检查项目目录设置
2. **代理不工作**：验证目标 URL 格式
3. **CORS 错误**：确认代理服务器状态

### 调试方法

1. 查看 Vercel 函数日志
2. 使用浏览器开发者工具
3. 测试代理端点响应

## 📞 技术支持

- 📖 [Vercel 官方文档](https://vercel.com/docs)
- 🐛 [GitHub Issues](https://github.com/your-username/MorphoTV/issues)
- 💬 [社区讨论](https://github.com/your-username/MorphoTV/discussions)

---

**部署成功后，记得在 MorphoTV 中配置正确的代理地址！**
