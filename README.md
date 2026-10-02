<p align="center">
  <img src="./assets/readme/hero.svg" width="100%" alt="gefei-seo-skill — turns gefei's hands-on Google SEO experience into an agent-ready knowledge base, with a KGR decision card example">
</p>

<p align="center"><sub>English · <a href="README.zh-CN.md">简体中文</a></sub></p>

# gefei-seo-skill

An Agent Skill for *Google SEO in Practice* — a knowledge base that AI coding assistants (Claude Code, Codex, OpenCode, etc.) can load and query.

## Install

```bash
npx skills add https://github.com/ifyour/gefei-seo-skill --skill gefei-seo
```

Or manually: clone this repo and drop the `gefei-seo/` directory into your skills folder (`~/.agents/skills/`, `~/.claude/skills/`, or a project-level `.claude/skills/` all work).

## Knowledge structure

| File | Contents |
|---|---|
| `gefei-seo/SKILL.md` | Core framework + chapter/topic index (entry point) |
| `gefei-seo/chapters/` | 22 chapter digests, loaded on demand |
| `gefei-seo/glossary.md` | Key terms |
| `gefei-seo/patterns.md` | 11 reusable patterns |
| `gefei-seo/cheatsheet.md` | Decision quick reference (rules / hard numbers / decision trees) |

## Usage

After installing, the agent invokes the skill automatically whenever you discuss SEO. Three levels of loading granularity:

- **No argument** → loads the core framework (the three-sentence ranking model, KGR, publishing cadence, etc.)
- **By topic** → `KGR`, `link building`, `programmatic SEO`, `penalty recovery` …, reads the matching chapter
- **By chapter** → `ch09`, `ch16` …, loads a chapter file directly
- **Browse** → ask "what chapters are there" to see the index

No commands to memorize — just ask in natural language, for example:

```
Use KGR to judge whether this keyword is worth targeting
How should a new site build links in its first three months
Is this tool site a good fit for programmatic SEO
```

## Use cases

**Keyword research**
- Evaluate whether a keyword is worth pursuing: search volume, competition, KGR judgment
- Discovering and prioritizing emerging / trending keywords
- Building long-tail keyword matrices

**Site building & on-page optimization**
- Page structure and TDH (Title/Description/Heading) for new sites
- SSR/SSG choices, meeting Core Web Vitals
- How content sites differ from tool sites

**Links & growth**
- Link-building cadence and safety boundaries (avoiding penalties)
- Programmatic SEO: when it fits and how to avoid doorway pages
- Multilingual SEO and hreflang setup

**AI search era**
- Getting cited in AI Overviews / AI search results
- Day-to-day GSC/GA analysis and anomaly triage

**Firefighting**
- Troubleshooting a sudden traffic drop
- Diagnosing and recovering from a Google penalty

## License & data source

- Code and curated content in this repo are released under **MIT**.
- Knowledge content comes from [Jayin/gefei-seo-cookbook](https://github.com/Jayin/gefei-seo-cookbook).
- Numbers in the book (weight percentages, costs, etc.) reflect the time of writing and may be outdated — defer to official Google docs and live data.
