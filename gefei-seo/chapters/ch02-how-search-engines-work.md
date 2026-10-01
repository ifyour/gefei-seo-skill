# Chapter 2: 搜索引擎工作原理

## Core Idea
搜索引擎只做三件事：爬取（发现页面）、索引（存储理解页面）、排名（按相关性排序展示）。所有 SEO 工作都是在为这三步扫清障碍。

## Frameworks Introduced
- **爬取 → 索引 → 排名 流水线**：三步严格串行且有反馈循环——只有被爬取的页面才能被索引，只有被索引的页面才能排名，排名结果又反过来影响爬取优先级。排查"页面没流量"时按此顺序检查：被爬了吗？被索引了吗？排名差在哪？
- **爬虫工作循环**：取 URL → 发 HTTP GET → 下载 HTML → 提取链接 → 入队。关键推论：爬虫主要看 HTML 源码，纯前端渲染（CSR）的小站等于对爬虫隐形。
- **反向索引（Inverted Index）**：关键词 → 文档列表的映射，是搜索引擎毫秒级返回结果的数据结构基础；正向索引是文档 → 关键词。

## Key Concepts
- **Googlebot**：Google 的爬虫程序，负责发现和抓取网页。
- **爬虫预算（Crawl Budget）**：Google 分配给每个网站的抓取资源上限，由网站权重、服务器速度、更新频率、内容质量决定。
- **索引（Indexing）**：把爬取到的内容提取、分词、语义分析后存入数据库的过程。
- **robots.txt**：告诉爬虫哪些路径可以/不可以抓取的文本文件。
- **Sitemap**：列出网站所有重要页面的 XML 文件，是内链发现机制的补充。
- **noindex 标签**：阻止页面被索引的 meta 标签——注意与 robots.txt 区别：后者阻止抓取，前者允许抓取但不收录。
- **Google Search Console（GSC）**：官方免费工具，监控索引状态、提交 Sitemap、查看抓取错误。
- **前端渲染（CSR）陷阱**：爬虫只抓 HTML 源码，JavaScript 渲染的内容小站大概率不被看到。

## Mental Models
- 把爬虫预算当作"配额"：低质量页面在浪费配额，砍掉它们等于给重要页面让路。
- 用"图书馆"理解索引：爬取是收书，索引是编目，排名是按查询找书——没编目的书永远借不到。
- 内链 > Sitemap：Google 更信任通过链接发现页面，Sitemap 只是建议清单。

## Anti-patterns
- **新站用纯前端渲染（SPA 不做 SSR）**：Google 虽能执行 JS，但只为大站这样做，小站内容直接隐形。
- **用 robots.txt 阻止不想收录的页面**：阻止抓取反而让 Google 不知道页面存在；不想收录应该用 noindex。
- **把 Sitemap 当救命稻草**：没有内链支撑，Sitemap 里的孤岛页面很难被收录。

## Code Examples
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://example.com/</loc>
    <lastmod>2024-01-01</lastmod>
    <changefreq>daily</changefreq>
    <priority>1.0</priority>
  </url>
</urlset>
```
- **What it demonstrates**: Sitemap 的标准结构，只列规范页面并及时更新 lastmod。

```
User-agent: *
Allow: /
Disallow: /admin/
Sitemap: https://example.com/sitemap.xml
```
- **What it demonstrates**: robots.txt 基本格式，末尾声明 Sitemap 位置。

## Worked Example
页面没被索引的排查路径：① robots.txt 是否误阻止 → ② 页面是否有 noindex → ③ 是否被 canonical 指向别处 → ④ 内容质量是否太低、爬虫预算不足 → ⑤ 是否前端渲染导致内容为空。对应加速收录的手段：在 GSC 请求编入索引、在首页添加新页面链接、社媒分享获取外链。

## Reference Tables
| 阶段 | 做什么 | 你能控制的手段 |
|---|---|---|
| 爬取 | 发现并下载页面 | robots.txt、Sitemap、内链、服务器速度 |
| 索引 | 提取存储理解内容 | noindex、canonical、内容质量、服务端渲染 |
| 排名 | 按相关性排序 | 内容相关性、外链、用户体验 |

## Key Takeaways
1. 排名的前提是索引，索引的前提是爬取——排查问题按这条链路走。
2. 爬虫预算有限，低质量页面在浪费抓取资源。
3. 反向索引解释了为什么内容相关性靠"词"匹配 + 语义理解。
4. 内链比 Sitemap 更重要，Sitemap 只是补充。
5. 小站不要依赖 JS 渲染，核心内容必须在 HTML 源码中。
6. GSC 是免费且官方的诊断入口，每个站点都应接入。

## Connects To
- **Ch 6**: 技术 SEO 就是把本章的爬取/索引障碍系统性清除。
- **Ch 3**: 排名阶段的因素详解在下一章。
