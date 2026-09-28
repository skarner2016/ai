# Frontend Instructions

> 本文件适用于 React + Vite + TypeScript 前端项目。

## 目录结构

- 遵循 Monorepo 管理规范
- **frontend/**：仅存放前端代码
- 根目录仅放置跨项目配置文件（如 `CLAUDE.md`、`docker-compose.yaml`）
- 不在根目录混放前后端代码文件

## 技术栈

| 类别 | 技术 | 版本 |
|------|------|------|
| 框架 | React | 19.x |
| 路由 | react-router-dom | 7.x |
| UI 组件 | Ant Design + Pro Components | antd 5.x / Pro 2.x |
| 状态管理 | Zustand | 5.x |
| HTTP 客户端 | Axios | 1.x |
| 日期处理 | dayjs | 1.x |
| 构建工具 | Vite | 8.x |
| 类型检查 | TypeScript | 6.x |
| 代码检查 | oxlint | 1.x |
