# Chapter 10: 多语言 SEO

## Core Idea
多语言 SEO 让网站在不同语言/地区的搜索结果中排名：三种语言要齐备——架构语言（子目录 URL）、声明语言（hreflang 标签）、内容语言（本地化翻译）。JS 切换语言而不换 URL 等于白做。

## Frameworks Introduced
- **URL 架构三选一**：子目录（`example.com/en/`，推荐——继承主域名权重、维护简单、Google 推荐）、子域名（`en.example.com`，独立性强）、独立域名（`example.cn`，本地化信号最强、成本最高）。大多数网站选子目录。
- **Hreflang 三实现 + 互指规则**：HTML `<link>` / HTTP 头 / Sitemap 三种实现任选；铁律：每个版本都必须指向所有版本（含自己），必须包含 `x-default`，必须用绝对 URL 和正确语言代码（ISO 639-1 + 可选地区码如 zh-CN、zh-TW）。
- **翻译 vs 本地化分层**：技术内容直接翻译（成本低）、核心/营销内容本地化（适应文化、调整策略）。关键词必须按语言单独研究——各语言搜索习惯和竞争度不同。
- **多语言检查清单**：架构（独立 URL/切换正常）→ hreflang（全互指/x-default/绝对 URL）→ 内容（本地化质量/关键词本地化）→ 技术（可索引/无重复/速度）。

## Key Concepts
- **Hreflang 标签**：告诉搜索引擎页面的语言和地区版本，让正确版本出现在正确用户面前。
- **x-default**：为不匹配任何语言版本的用户指定的默认版本。
- **子目录架构**：`/en/ /zh/ /ja/` 共享主域名权重的多语言目录结构。
- **本地化（Localization）**：不只是翻译，还要适应本地文化和表达习惯。
- **JS 语言切换陷阱**：不改变 URL 的语言切换使爬虫只能看到一种语言，多语言形同虚设。
- **重复内容问题**：不同语言版本内容可能被误判重复——hreflang + canonical + 内容差异化共同解决。
- **语言检测重定向**：基于浏览器语言/位置自动跳转，应与语言选择器结合，避免强制。

## Mental Models
- 把 hreflang 当"名片夹"：每个版本要递出完整的一套名片（互相指向），少一张就可能被认错人。
- 把每种语言当"独立竞争场"：西语关键词在 Google 墨西哥和西班牙的竞争格局完全不同，要分别研究。
- 把 JS 切换当"只换封面的书"：用户能翻到不同语言，但爬虫只看到一种——白做。

## Anti-patterns
- **用 JavaScript 切换语言且不改 URL**：搜索引擎只能抓到一种语言，多语言无效（Pixverse 案例的三大根因之一）。
- **纯机器翻译直接上线**：质量低、体验差、可能被惩罚；机器翻译只能作辅助，需人工审核。
- **Hreflang 只指向部分版本 / 用相对 URL / 指向 404**：声明失效，Google 忽略。
- **语言代码错误**（如 zh 与 zh-CN 混用不当）：指向错误的版本组。
- **只翻译不本地化关键词**：直接翻译英文关键词，错失本地真实搜索词。

## Code Examples
```html
<link rel="alternate" hreflang="en" href="https://example.com/en/">
<link rel="alternate" hreflang="zh" href="https://example.com/zh/">
<link rel="alternate" hreflang="ja" href="https://example.com/ja/">
<link rel="alternate" hreflang="x-default" href="https://example.com/">
```
- **What it demonstrates**: hreflang 标准实现——全版本互指、含 x-default、全部绝对 URL；同样的声明也可放进 HTTP 头或 Sitemap。

## Reference Tables
| 方案 | URL 示例 | 权重 | 适用 |
|---|---|---|---|
| 子目录 | example.com/en/ | 共享主域，推荐 | 大多数网站 |
| 子域名 | en.example.com | 较独立 | 需隔离管理 |
| 独立域名 | example.co.jp | 本地信号最强 | 重仓单一市场 |

| 实现 | 适用场景 |
|---|---|
| HTML `<link>` | 普通页面 |
| HTTP 头 | 非 HTML 文件（如 PDF） |
| Sitemap | 页面多、集中管理 |

## Worked Example
SaaS 产品出海案例：已有英文站，需加中文和日文。实施：① 选子目录 /en/ /zh/ /ja/；② 每个页面部署完整 hreflang 互指 + x-default；③ 内容分层——核心功能页和营销页本地化、技术文档翻译；④ 各语言单独做关键词研究并优化页面；⑤ SSR 保证爬虫可见。结果：各语言版本被正确索引、本地搜索流量增长、转化率提升。

## Key Takeaways
1. 每种语言必须有独立 URL——JS 切换语言等于没做多语言。
2. 子目录是大多数网站的默认选择，继承主域名权重。
3. Hreflang 铁律：全版本互指 + x-default + 绝对 URL + 正确语言码。
4. 关键词研究必须按语言分别做，不能直接翻译。
5. 核心和营销内容本地化，技术内容可翻译，机器翻译需人工审核。
6. 多语言 + 重复内容问题用 hreflang + canonical + 内容差异化组合解决。

## Connects To
- **Ch 6**: hreflang 与 canonical 的技术基础。
- **Ch 8**: JS 切换语言是 Pixverse 案例的根因之一。
- **Ch 9**: 程序化 + 多语言是常见组合，但新站别同时开两个大招。
