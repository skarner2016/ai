# PHP Backend Instructions

> 本文件适用于 PHP 后端项目。

## 代码规范

- 遵循 PSR-12
- 新建文件或项目已启用严格类型时使用 `declare(strict_types=1)`；不要为兼容性未知的旧文件盲目加入
- PHP 8+ 优先使用 typed properties 和 union types

## 目录结构参考

```
backend/
├── public/              # 入口和静态资源
│   └── index.php
├── app/                 # 应用代码
│   ├── Controller/      # 控制器
│   ├── Service/         # 业务逻辑
│   ├── Repository/      # 数据访问
│   ├── Model/           # 数据模型
│   └── Middleware/      # 中间件
├── config/              # 配置文件
├── database/            # 数据库迁移
├── routes/              # 路由定义
├── storage/             # 日志、缓存
├── tests/               # 测试
├── composer.json
├── Dockerfile
└── docker-compose.yaml
```
