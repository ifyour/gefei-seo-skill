# Chapter 19: 技术 SEO 工具

## Core Idea
技术 SEO 是基础——保证搜索引擎能正确抓取和索引网站；用爬取、速度、移动端、结构化数据、链接五类工具，按"爬取 → 速度 → 移动端 → 结构化数据 → 链接"的流程做月度体检。

## Frameworks Introduced
- **技术 SEO 五步检查流程**: ①网站爬取（Screaming Frog 爬全站，查爬取错误，分析页面数据，出审计报告）→ ②页面速度（PageSpeed Insights + GTmetrix，分析核心网页指标）→ ③移动端（移动设备适合性测试 + GSC 移动可用性报告）→ ④结构化数据（富媒体搜索结果测试验证）→ ⑤链接（Ahrefs 分析外链、查内链结构和断链）。何时用：每月一次，每次网站更新后加查。
- **Screaming Frog 关键功能清单**: 爬取概览、Title 标签、Meta Description、H1、图片 Alt、内外链、重定向链、404/500 错误——一次爬取覆盖全部基础审计项。
- **页面速度指标体系**: FCP（首次内容绘制）、LCP（最大内容绘制）、FID（首次输入延迟）、CLS（累积布局偏移）——PageSpeed Insights 官方免费，GTmetrix 有历史记录，WebPageTest 支持多地点多浏览器。

## Key Concepts
- **网站爬取工具**: 模拟爬虫遍历全站，发现技术问题的工具；Screaming Frog 免费版限 500 URL，付费 £199/年。
- **Sitebulb**: 可视化审计报告 + 问题优先级排序，£13.50/月起。
- **DeepCrawl**: 企业级大型网站审计，定制价格。
- **核心网页指标**: LCP/FID/CLS 三项，GSC 和 PageSpeed Insights 都能看。
- **富媒体搜索结果测试**: 验证结构化数据并预览富摘要效果。
- **Check My Links**: Chrome 插件，高亮显示当前页面的断链。

## Mental Models
- 把技术 SEO 当"地基"：它保证搜索引擎能抓取和索引（基础），内容 SEO 保证内容有价值（核心），两者缺一不可。
- 把全站爬取当"体检"：每月一次 Screaming Frog，任何改版后加做一次。
- 用"免费官方工具优先"建检查链：PageSpeed Insights、移动适合性测试、富媒体测试三个免费工具覆盖 80% 的检查项。

## Anti-patterns
- **只做技术不做内容（或反之）**: 技术 SEO 和内容 SEO 都重要，一个管收录一个管价值。
- **只测单个页面就下结论**: PageSpeed Insights 等工具只测单页，需抽样代表性页面或配合全站爬取。
- **改版后不复查技术 SEO**: 每次网站更新后都要重新检查。
- **发现断链不修**: 内链断链浪费抓取预算和权重传递。

## Reference Tables
爬取工具对比：

| 工具 | 价格 | 定位 |
|------|------|------|
| Screaming Frog | 免费 500 URL / £199/年 | 全功能爬取审计，首选 |
| Sitebulb | £13.50/月起 | 可视化报告 + 优先级建议 |
| DeepCrawl | 定制 | 企业级大站 |

选型档位：初学者 $0（三个免费官方工具 + Screaming Frog 免费版）→ 进阶 $200-300/月（+ Screaming Frog 付费 + Ahrefs/SEMrush 一个）→ 专业 $500-1000/月（全配）。

## Worked Example
一个月度体检走完：Screaming Frog 爬站发现 12 个 404 和 3 条重定向链；PageSpeed Insights 显示首页 LCP 4.2s（不达标），按建议压缩图片 + 启用缓存 + 上 CDN；富媒体测试发现 FAQ schema 有两个错误并修复；Ahrefs 找到 5 个内链断链并修复。全部完成后在 GSC 验证修复、监控核心网页指标状态变化。

## Key Takeaways
1. 月度技术 SEO 检查 + 每次更新后加查，是基本节奏。
2. Screaming Frog 一次爬取覆盖 Title/Meta/H1/Alt/链接/重定向/错误全部基础项。
3. 三个免费官方工具（PageSpeed、移动适合性、富媒体测试）是检查链起点。
4. 页面速度四指标：FCP、LCP、FID、CLS，对照核心网页指标优化。
5. 结构化数据必须验证后才上线，富摘要效果可预览。
6. 链接检查不止外链：内链结构和断链同样影响抓取与权重。

## Connects To
- **Ch 16**: GSC 的索引和体验报告承接本章的检查结果。
- **Ch 21**: 工具站案例里页面速度和移动端是核心成功因素。
