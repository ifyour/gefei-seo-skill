# Chapter 6: 技术 SEO

## Core Idea
技术 SEO 确保搜索引擎能正确抓取、索引、渲染和理解网站——它是排名的地基：地基不通，内容和外链都白费。

## Frameworks Introduced
- **可访问性四件套**：robots.txt（控制抓取）+ Sitemap（列出规范页）+ 清晰架构（3 层内）+ GSC 提交监控。上线新站先跑通这四件。
- **渲染方式决策**：SSR（服务器出完整 HTML，利于 SEO）> 预渲染（提前生成静态 HTML）> CSR（浏览器跑 JS 生成内容，对小站致命）。核心事实：Googlebot 只发 GET 解析 HTML，不会为小站执行 JavaScript。
- **Core Web Vitals 速度框架**：LCP（最大内容绘制）、FID（首次输入延迟）、CLS（累积布局偏移），用 PageSpeed Insights 测量，对应图片/代码/服务器/字体四类优化。
- **重复内容处理工具箱**：canonical 标签（指定规范版本）、301 重定向（合并 URL）、noindex（不收录）、合并内容——按场景选择。
- **技术 SEO 检查清单**：基础（可访问/robots/Sitemap/HTTPS）→ 页面（可索引/canonical/速度）→ 移动端 → 结构四层逐级检查。

## Key Concepts
- **robots.txt**：声明哪些路径允许/禁止抓取，末尾指向 Sitemap。
- **Sitemap**：XML 文件列出全部规范页面，含 lastmod 更新时间，提交到 GSC。
- **SSR / CSR / 预渲染**：三种页面渲染方式，对 SEO 的影响天差地别。
- **HTTPS**：排名因素 + 用户信任，用 Let's Encrypt 可免费启用；注意修复混合内容和缩短重定向链。
- **Core Web Vitals**：Google 的三项页面体验核心指标。
- **结构化数据（Schema.org + JSON-LD）**：标准化格式帮助搜索引擎理解页面类型（Article/Product/FAQ 等），JSON-LD 为推荐实现。
- **Canonical 标签**：声明页面规范 URL，解决同内容多 URL 问题；指向自己也允许，必须用绝对 URL。
- **Hreflang 标签**：声明语言/地区版本，多语言站必备（详见 Ch 10）。
- **移动优先索引**：Google 用移动版内容索引排名，按钮 ≥44×44px、无水平滚动。

## Mental Models
- 把技术 SEO 当"入场费"：不解决，后面所有内容优化都到不了评委面前。
- 把 canonical 当"官方发言人"：多个 URL 版本里，你指定哪个代表内容。
- 把重定向链当"转机航班"：HTTP → HTTPS → www 直飞最终地址，别让爬虫转三次机。

## Anti-patterns
- **纯前端渲染（SPA 不做 SSR）**：Googlebot 看到空 body，对中小站致命。
- **robots.txt 误阻止重要页面**：定期在 GSC 测试。
- **混合内容**：HTTPS 页面加载 HTTP 资源，浏览器警告伤害信任。
- **Sitemap 收录非规范页面**：只列 canonical 页面，及时更新 lastmod。
- **忽略软 404**：返回 200 但内容是"页面不存在"，浪费爬虫预算。

## Code Examples
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "Google SEO 入门教程",
  "author": { "@type": "Person", "name": "SEO Book" },
  "datePublished": "2024-01-01"
}
</script>
<link rel="canonical" href="https://example.com/page">
<link rel="alternate" hreflang="zh" href="https://example.com/zh/">
```
- **What it demonstrates**: JSON-LD 结构化数据、canonical、hreflang 三大 head 区标签的标准写法。

## Reference Tables
| 渲染方式 | 爬虫可见性 | SEO 影响 | 适用 |
|---|---|---|---|
| SSR | 完整 HTML 直接可见 | 最佳 | 所有正式站点 |
| 预渲染 | 静态 HTML | 良好 | 内容稳定的站 |
| CSR | 空 body（小站） | 致命 | 尽量避免 |

## Worked Example
页面未被索引的标准排查：① robots.txt 阻止？→ ② 有 noindex？→ ③ 可访问吗（5xx/404/软 404）？→ ④ canonical 指向别处？→ ⑤ 重复内容未处理？定位后对应修复：移除阻止、修复服务器、改正 canonical、合并重复内容。配合 Core Web Vitals 检查速度短板（多半是图片过大或第三方脚本）。

## Key Takeaways
1. 技术 SEO 是入场费：抓取不通，一切归零。
2. 小站绝不用纯 CSR，核心内容必须在 HTML 源码中。
3. canonical 用绝对 URL，指向规范页，防重复内容稀释权重。
4. HTTPS + 无混合内容 + 短重定向链是标配。
5. Core Web Vitals 三指标对应四类优化：图片、代码、服务器、字体。
6. JSON-LD 是结构化数据的首选实现。
7. 用 GSC 作为技术问题的第一诊断入口。

## Connects To
- **Ch 2**: 本章是爬取/索引原理的工程化落地。
- **Ch 10**: hreflang 的完整展开。
- **Ch 11**: 架构设计的技术细节。
