# 前端项目

这是一个简单的 Vue 3 前端项目，用于演示 CI/CD 自动部署流程。

## 功能

- 点击按钮发送数据到后端 API
- 显示后端 API 的反馈结果

## 技术栈

- Vue 3
- Vite

## 安装依赖

```bash
pnpm install
```

## 开发环境运行

```bash
pnpm dev
```

## 构建

```bash
pnpm run build
```

## CI/CD 配置

项目已配置 GitHub Actions 工作流，当代码推送到 master 分支时，会自动构建并部署到远程服务器。