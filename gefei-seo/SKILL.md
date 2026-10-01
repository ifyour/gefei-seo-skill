---
name: gefei-seo
description: "《Google SEO 实战教程》知识库。基于哥飞 SEO 实战经验整理的 Google SEO 教程（Jayin/gefei-seo-cookbook）。用于：关键词研究（KGR、新词优先）、页面/技术 SEO（TDH、SSR、Core Web Vitals）、外链建设节奏、程序化 SEO、多语言 SEO、AI 搜索优化、惩罚恢复、GSC/GA 数据分析、工具站与内容站案例复盘。讨论 SEO、建站获取谷歌流量、网站排名问题时调用。"
---

<!-- argument-hint: [主题 / 框架名 / 章节号，如 KGR、外链、程序化SEO、ch09] -->

# Google SEO 实战教程
**来源**：哥飞公众号文章整理（Jayin/gefei-seo-cookbook） | **章节**：22（4 部分） | **生成**：2026-01-02

## How to Use This Skill

- **无参数** — 加载核心框架（排名三句话 + 关键词研究 + 发布节奏）
- **带主题** — 问 `KGR`、`外链`、`程序化SEO`、`惩罚恢复` 等，读对应章节
- **带章节** — 问 `ch09` / `ch16`，加载该章节文件
- **浏览** — 问"有哪些章节"，看 Chapter Index

问到 Core Frameworks 未覆盖的主题，先读相关章节文件再回答。

---

## Core Frameworks & Mental Models

**1. 排名三句话（全书主模型）**（ch03）
① Title 和 H1 关键词让页面进入候选池；② 外链帮你进入前 10；③ 网站体验（停留时间、跳出率、页访问数）决定最终位置。诊断排名问题时按此三段定位瓶颈。

**2. 爬取→索引→排名三层漏斗**（ch02）
排查永远按顺序：能不能被爬（robots/noindex/CSR）→ 有没有被索引（GSC）→ 为什么排名不好。硬红线：Googlebot 对小站不执行 JS——纯 CSR/SPA = 空 body，必须 SSR。

**3. TDH 取代 TDK**（ch03, ch05）
Keywords meta 已死。优化 Title（50–60 字符）、Description（150–160，影响 CTR 非排名）、Headings（H1 唯一含主词）。

**4. KGR 公式 + 新词优先**（ch04, ch18）
KGR = allintitle 结果数 ÷ 月搜索量，<0.25 易排名。6 个月新词（KD 50）比 1 年老词（KD 30）好做——SERP 未被优化。你不是和全网竞争，只和前 10–20 个真做 SEO 的结果竞争。

**5. 新站发布节奏**（ch09）
新站（域名<6–12月 / 引用域<100 / DR<40 / 前20页<100）禁止程序化批量页=必死。前 3–6 月一词一页手做 → 100 页进前 20 → 先发 10 个程序化页 → GSC 观察 → 逐步扩展。

**6. CDSD：搜索量来自共识**（ch09）
新需求 + 先发 SEO = 以最小竞争获取巨大流量（getimg.ai 抢 "Ghibli AI"，160 万→1240 万月访问）。用 Google Trends 监控新词，第一时间上落地页。

**7. 外链节奏与锚文本多样化**（ch07）
新站三阶段：0–3 月内容+基础外链 → 3–6 月客座+竞对 → 6 月后大规模。锚文本必须混合品牌词/URL/通用词/关键词——单一锚文本有 770→47 展示/天的实证惨案。Nofollow 也要，全 dofollow 反而可疑。

**8. 体验信号驱动排名与恢复**（ch13）
惩罚恢复五步排查中，恢复关键通常是用户体验指标而非技术：跳出率降、页访问升、停留增 → 排名回。免费试用（免登录可用）是工具站最强的体验杠杆。

**9. AI 搜索 = 引用而非排名**（ch12）
把品牌布局到 ≥3 个高权重平台（Reddit/Quora/YouTube/行业媒体）；纯文本 URL 也被 AI 引用；传统 SEO 为主、AI SEO 为辅。

**10. 工具站内容配方**（ch08, ch21）
Google 不运行你的工具，只看文字。工具本体 + 详细说明 + 教程 + FAQ + 定期更新。日本工具站：仅 90 个收录页年访问 2300 万——精品路线，每页都打磨到能带流量。

**11. 内页提权五步检查**（ch07）
加外链前：① On-Page 好了吗 → ② 内容深度够吗 → ③ 前 10 实力如何 → ④ 先内链提权 → ⑤ 给足 3–4 个月。外链 $200–400/条，能省则省。

**12. 数据分析节奏**（ch14, ch16）
每周 GSC 搜索报告（抓高展示低点击）、每月索引+链接报告、每季度全面审计。GSC 站在搜索侧、GA 站在网站侧，口径不同需配合。

---

## Chapter Index

| # | Title | Key Frameworks |
|---|-------|----------------|
| [ch01](chapters/ch01-what-is-seo.md) | 什么是 SEO | 四大支柱 |
| [ch02](chapters/ch02-how-search-engines-work.md) | 搜索引擎工作原理 | 三层漏斗、爬虫预算 |
| [ch03](chapters/ch03-google-ranking-factors.md) | Google 排名因素 | 排名三句话、权重表 |
| [ch04](chapters/ch04-keyword-research.md) | 关键词研究 | KGR、新词优先、四标准 |
| [ch05](chapters/ch05-on-page-seo.md) | 页面 SEO | TDH、内链、URL 规范 |
| [ch06](chapters/ch06-technical-seo.md) | 技术 SEO | SSR 红线、CWV、canonical |
| [ch07](chapters/ch07-link-building.md) | 外链建设 | 三阶段节奏、锚文本 |
| [ch08](chapters/ch08-content-seo.md) | 内容 SEO | 首页密度、免费试用杠杆 |
| [ch09](chapters/ch09-programmatic-seo.md) | 程序化 SEO | 新站定义、CDSD |
| [ch10](chapters/ch10-multilingual-seo.md) | 多语言 SEO | hreflang 铁律、子目录 |
| [ch11](chapters/ch11-site-architecture.md) | 网站架构 | 3 次点击、深度换宽度 |
| [ch12](chapters/ch12-ai-seo.md) | AI 搜索优化 | 平台布局清单 |
| [ch13](chapters/ch13-penalty-recovery.md) | 惩罚恢复 | 三类惩罚、恢复时间表 |
| [ch14](chapters/ch14-seo-analytics.md) | SEO 数据分析 | 四类指标、监控节奏 |
| [ch15](chapters/ch15-tools-overview.md) | SEO 工具概览 | 免费五件套、预算档 |
| [ch16](chapters/ch16-google-search-console.md) | Google Search Console | 报告行动表 |
| [ch17](chapters/ch17-google-analytics.md) | Google Analytics | GA 闭环、ROI 公式 |
| [ch18](chapters/ch18-keyword-tools.md) | 关键词研究工具 | 工具对比、五步流程 |
| [ch19](chapters/ch19-technical-tools.md) | 技术 SEO 工具 | 五步检查流程 |
| [ch20](chapters/ch20-case-method.md) | 案例学习方法 | 四维分析、八段报告 |
| [ch21](chapters/ch21-tool-site-case.md) | 工具站案例 | 精品路线、子域名 |
| [ch22](chapters/ch22-content-site-case.md) | 内容站案例 | CNN 六打法、时效性 |

## Topic Index

- **AI SEO / AI 搜索** → ch12
- **canonical** → ch06
- **Core Web Vitals** → ch06, ch16, ch19
- **GSC / Search Console** → ch14, ch16
- **GA / Analytics** → ch14, ch17
- **hreflang / 多语言** → ch10
- **KGR / 关键词研究** → ch04, ch18
- **SSR / 渲染 / CSR** → ch02, ch06, ch08
- **程序化 SEO** → ch09
- **惩罚 / 恢复 / 被 K** → ch13
- **外链 / 锚文本** → ch03, ch07
- **网站架构 / 内链** → ch05, ch11
- **案例复盘** → ch20, ch21, ch22
- **工具推荐** → ch15–ch19

## Supporting Files

- [glossary.md](glossary.md) — 关键术语
- [patterns.md](patterns.md) — 可复用模式
- [cheatsheet.md](cheatsheet.md) — 决策速查（触境即决）

---

## Scope & Limits

本 skill 只覆盖教程内容（基于哥飞公开文章整理，MIT 授权部分）。原始公众号文章版权归原作者。实际落地请结合具体项目与最新 Google 算法动态——书中数字（权重百分比、成本）为写作时点数据，会过期。
