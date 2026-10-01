# open-gf-seo

《Google SEO 实战教程》Agent Skill — 基于 [Jayin/gefei-seo-cookbook](https://github.com/Jayin/gefei-seo-cookbook) 的 `seo-book/`（MIT 授权）提炼的可复用知识库技能。

把书里的框架变成 agent 可调用的思维模型与决策规则：关键词研究（KGR）、页面/技术 SEO、外链节奏、程序化 SEO、多语言 SEO、AI 搜索优化、惩罚恢复、GSC/GA 数据分析、工具站/内容站案例。

由 [book-to-skill](https://github.com/virgiliojr94/book-to-skill) 生成；内容为提炼摘要，非原文照录。

## 安装

```bash
npx skills add https://github.com/ifyour/open-gf-seo --skill open-gf-seo
```

或手动：克隆本仓库，把 `open-gf-seo/` 放入你的 skills 目录（`~/.agents/skills/`、`~/.claude/skills/`、`.claude/skills/` 等均可）。

## 文件结构

| 文件 | 内容 |
|---|---|
| `SKILL.md` | 核心框架 + 章节/主题索引（入口） |
| `chapters/` | 22 个章节提炼，按需加载 |
| `glossary.md` | 关键术语表 |
| `patterns.md` | 11 个可复用模式 |
| `cheatsheet.md` | 决策速查（决策规则 / 硬数字 / 决策树） |

## 用法

- 无参数 → 加载核心框架（排名三句话、KGR、发布节奏等）
- 带主题 → `KGR`、`外链`、`程序化SEO`、`惩罚恢复` …
- 带章节 → `ch09`、`ch16` …

## 许可

MIT。内容源自 MIT 授权的 [gefei-seo-cookbook/seo-book](https://github.com/Jayin/gefei-seo-cookbook)。书中数字（权重百分比、成本等）为写作时点数据，会过期。
