# Go Backend Instructions

> 本文件适用于 Go + Echo + GORM 后端项目。

## 目录结构

```
backend/
├── cmd/server/          # 入口
│   └── main.go
├── internal/            # 内部实现
│   ├── handler/         # HTTP Handler
│   ├── service/         # 业务逻辑
│   ├── repository/      # 数据访问
│   ├── model/           # 数据模型
│   └── middleware/      # 中间件
├── pkg/                 # 可复用的包
│   ├── auth/            # 认证工具
│   ├── config/          # 配置加载
│   └── logger/          # 日志工具
├── configs/             # 配置文件
├── migrations/          # 数据库迁移
├── server/              # 编译产物
├── Makefile
├── Dockerfile
└── docker-compose.yaml
```

## 代码规范

- 遵循官方 Effective Go 和 `gofmt`
- 命名使用 camelCase（未导出）和 PascalCase（导出），遵循常见 initialism 规则（如 `URL`、`HTTP`）
- 错误通过 `error` 返回和处理，不使用 `panic` 处理可预期错误
- 遵循项目现有分层：handler → service → repository

## Echo 框架

- 使用 `echo.Context` 处理请求/响应
- 统一 JSON 响应格式：`{"code": 0, "message": "success", "data": ...}`
- 中间件链：Recover → CORS → RequestID → Auth（需要时）
- 路由分组：`/api/v1` 前缀，受保护路由使用 Auth 中间件

## GORM

- Model 定义使用 `gorm.Model` 嵌入
- 字段类型：使用 GORM 支持的类型，JSON 字段用 `datatypes.JSON`
- 关联：使用 `HasMany`、`BelongsTo` 等声明式关联
- 查询：优先使用链式调用，复杂查询使用原生 SQL

## 配置管理

- 使用 Viper 加载 YAML/TOML 配置
- 环境变量覆盖：支持 `XXX_YYY` 格式覆盖配置
- 敏感信息：JWT Secret、数据库密码等通过环境变量注入
- 配置文件：`configs/config.yaml`（不提交到仓库）

## 日志

- 使用 zap 结构化日志
- 日志级别：debug/info/warn/error
- 必须记录：启动信息、错误、关键操作
- 生产环境：JSON 格式输出

## 认证

- JWT Token：Header `Authorization: Bearer <token>`
- Token 结构：包含 user_id、exp、iss
- 刷新机制：提供 `/auth/refresh` 接口
- 密码存储：bcrypt 加密（golang.org/x/crypto/bcrypt）
