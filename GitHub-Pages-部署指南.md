# GitHub Pages 部署指南 - 智慧大棚管理系统

## 📋 部署状态

✅ **已完成配置**：
- GitHub Actions 自动部署工作流
- Vite 基础路径配置（`/励铭科技aaa/`）
- SPA 路由支持（404.html 重定向）
- 项目构建优化
- 代码已提交到本地 master 分支

⏳ **待完成**：
- 推送代码到 GitHub（网络连接问题）
- 启用 GitHub Pages 服务

## 🚀 部署步骤

### 1. 推送代码到 GitHub

**方案A：网络恢复后直接推送**
```bash
git push origin master
```

**方案B：使用 SSH 协议**
```bash
# 添加 SSH 远程仓库
git remote add ssh-origin git@github.com:sss887-li/zhihuidapeng1.git
# 推送代码
git push ssh-origin master
```

**方案C：使用代理或VPN**
- 配置网络代理后执行推送命令
- 或使用VPN连接后推送

### 2. 启用 GitHub Pages

1. 进入 GitHub 仓库设置页面
2. 找到 "Pages" 选项
3. 选择 "Deploy from a branch"
4. 选择 "gh-pages" 分支（GitHub Actions 会自动创建）
5. 点击 "Save" 保存设置

### 3. 访问部署的网站

部署成功后，网站将在以下地址可用：
```
https://sss887-li.github.io/zhihuidapeng1/
```

## 🌐 国内访问优化方案

### 方案1：CDN 加速服务

**jsDelivr CDN**（推荐）
```
https://cdn.jsdelivr.net/gh/sss887-li/zhihuidapeng1@gh-pages/
```

**Statically CDN**
```
https://cdn.statically.io/gh/sss887-li/zhihuidapeng1/gh-pages/
```

### 方案2：国内镜像站点

**GitHub 镜像站**
- https://hub.fastgit.xyz/sss887-li/zhihuidapeng1
- https://github.com.cnpmjs.org/sss887-li/zhihuidapeng1

### 方案3：自定义域名

1. 购买域名并配置 DNS
2. 在仓库根目录创建 `CNAME` 文件
3. 在 GitHub Pages 设置中配置自定义域名
4. 启用 HTTPS

### 方案4：国内云服务部署

**Gitee Pages**（最佳国内方案）
1. 将代码同步到 Gitee
2. 启用 Gitee Pages 服务
3. 获得国内高速访问地址

**Vercel 国内访问**
- 使用 Vercel 部署（已有链接）
- 配置自定义域名改善访问速度

## 🔧 技术配置详情

### Vite 配置
```typescript
// vite.config.ts
export default defineConfig({
  base: process.env.NODE_ENV === 'production' ? '/励铭科技aaa/' : '/',
  build: {
    sourcemap: 'hidden',
    outDir: 'dist',
  },
  // ... 其他配置
})
```

### GitHub Actions 工作流
- 自动检测 main/master 分支推送
- Node.js 18 环境
- 自动构建和部署到 gh-pages 分支
- 支持自定义域名配置

### SPA 路由支持
- 404.html 重定向脚本
- index.html 路由恢复脚本
- 确保前端路由正常工作

## 📱 系统特色

- **品牌标识**：励铭科技 mAi 品牌
- **功能模块**：环境监控、设备控制、数据分析、用户管理、系统设置、报警管理、报表统计
- **技术栈**：React 18 + TypeScript + Tailwind CSS + Vite
- **演示账户**：admin / 123456
- **响应式设计**：支持桌面端和移动端

## 🚨 故障排除

### 网络连接问题
- 检查网络连接
- 尝试使用移动热点
- 配置代理或VPN
- 使用 SSH 协议推送

### 部署失败
- 检查 GitHub Actions 日志
- 确认分支名称正确
- 验证构建命令
- 检查依赖安装

### 访问问题
- 等待 DNS 传播（最多24小时）
- 清除浏览器缓存
- 尝试不同的 CDN 服务
- 使用国内镜像站点

## 📞 技术支持

如遇到部署问题，可以：
1. 检查 GitHub Actions 构建日志
2. 验证 GitHub Pages 设置
3. 测试不同的访问方案
4. 考虑使用 Gitee Pages 作为备选方案

---

**智慧大棚管理系统** - 励铭科技 mAi 品牌  
现代化农业管理解决方案，助力智慧农业发展。