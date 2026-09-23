# AI 配置中心

集中管理 AI 编码助手的配置指令文件。

## 软链接配置

为 Claude Code、Codex CLI、OpenCode 创建软链接，指向统一的指令文件：

```bash
# Claude Code
ln -s /Users/skarner/.ai/AGENTS.md ~/.claude/CLAUDE.md

# Codex CLI
ln -s /Users/skarner/.ai/AGENTS.md ~/.codex/AGENTS.md

# OpenCode
ln -s /Users/skarner/.ai/AGENTS.md ~/.config/opencode/AGENTS.md

# zcode
ln -s /Users/skarner/.ai/AGENTS.md ~/.zcode/AGENTS.md
```

## 文件说明

| 文件 | 用途 |
|------|------|
| `AGENTS.md` | 通用编码规范 |
| `AGENTS.FRONT.md` | 前端开发规范 |
| `AGENTS.GO.md` | Go 开发规范 |
| `AGENTS.MYSQL.md` | MySQL 规范 |
| `AGENTS.PGSQL.md` | PostgreSQL 规范 |
| `AGENTS.PHP.md` | PHP 开发规范 |
| `AGENTS.PY.md` | Python 开发规范 |
