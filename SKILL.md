---
name: kunpeng-github-publisher
description: |
  Use when publishing or polishing a GitHub repository for a Kunpeng-owned project:
  rewrite public READMEs as Chinese-first bilingual product pages, set bilingual
  GitHub About descriptions, choose topics, add screenshots and badges, verify
  deploy/install paths, create PRs, and merge verified changes to main.
  Trigger on requests like "发布到 GitHub", "开源",
  "重写 README", "设置 About", "优化 GitHub repo", "release this repo", or
  "make this project installable/attractive on GitHub".
---

# Kunpeng GitHub Publisher

Turn a working project into a GitHub repository people can understand, try, star, install, and trust.

Copyright (c) 鲲鹏

- X: https://x.com/
- GitHub: https://github.com/AIKunpeng/
- Profile source: `~/.agents/skills/kunpeng-profile`

## Core Workflow

1. Inspect the repo before writing:
   - `README.md`, `package.json` / project metadata, screenshots, examples, docs, license, deploy scripts, test scripts.
   - GitHub remote state via `gh repo view --json name,description,homepageUrl,repositoryTopics,url`.
2. Decide the public positioning:
   - One-line hook in Chinese and English, with the Chinese version first.
   - Target users and why they should try it now.
   - Clear boundary between product value, technical architecture, and private/local setup.
3. Rewrite or patch README as a product page:
   - `README.md` is the GitHub front door. For Kunpeng-owned repos, it must be Chinese-first and bilingual by default.
   - Put Chinese first, then English. Do this unless the user explicitly asks for English-only or the repo has a documented non-Kunpeng upstream requirement.
   - A separate `README.zh-CN.md` is allowed, but it does not satisfy this requirement by itself; the default `README.md` must show Chinese first.
   - English can be a full lower section anchored by `# English`, a linked `README.en.md`, or a compact mirrored section, but install/try, verification, limits, and license/access expectations must be understandable to English readers.
   - Put hook, CTAs, badges, screenshot, feature list, quick start, examples, verification, limitations, and troubleshooting near the top.
   - Use real screenshots or output samples when available; do not invent screenshots.
4. Set GitHub About:
   - Use a compact bilingual description by default for Kunpeng-owned public repos, Chinese first and English second.
   - Add homepage URL when there is a live demo.
   - Add focused topics; avoid topic spam.
5. Verify what the README promises:
   - Run project-provided lint/build/test commands when relevant.
   - For skills, verify `npx skills add` discoverability/installability.
   - For websites, verify live URL/API/health after deployment when applicable.
6. Publish through a clean GitHub flow:
   - Use a feature branch and PR.
   - Never push directly to `main`.
   - If verification passes and the user has not explicitly asked to hold, merge the PR into `main`.
   - In the final response, include the PR URL and merge commit.

## README Standard

### Language Gate

For Kunpeng-owned public repositories, `README.md` must be Chinese-first bilingual before release:

- First viewport: project name, Chinese value proposition, English value proposition, badges/links, and a visible language switch such as `**中文** | [English](#english)`.
- Main body: Chinese sections first, written as the default reader experience.
- English access: provide a substantive English section or linked English README. At minimum, English readers must understand what it does, how to try/install it, what is verified, and the main limits/prerequisites.
- Translation files such as `README.zh-CN.md` and `README.en.md` may exist, but the GitHub default `README.md` still has to open with Chinese first unless the user explicitly approved a different audience.
- If `README.md` is English-only, English-first, or relies on a separate Chinese file for the Chinese experience, stop and fix it before opening/merging the release PR.

Public README must answer five questions fast:

- What pain does this solve?
- What do I get after installing/running it?
- Can I see proof in a screenshot, demo, or example output?
- How do I try it in less than five minutes?
- What are the limits, costs, or prerequisites?

Recommended structure:

```markdown
# Project Name

> 中文价值主张
> English value proposition

[Live Demo] [Install] [License] [Stars]

![Screenshot](docs/assets/product-screenshot.png)

**中文** | [English](#english)

## 为什么值得用
## 核心能力
## 样例输出
## 快速开始
## 部署 / API / Skill
## 实测验证
## 限制与边界
## Troubleshooting
## 关于鲲鹏

---

<a name="english"></a>
# English section
```

## GitHub About Standard

Use a compact bilingual form by default for Kunpeng-owned public repos:

```text
中文短描述 | English short description.
```

Keep it concrete. Good examples:

- `把 App Store 评价变成产品研究证据，发现痛点、机会和版本风险 | Turn App Store reviews into product research evidence: pain points, opportunities, and version risks.`
- `把任意资料整理成 NotebookLM 可用知识包 | Turn messy sources into NotebookLM-ready knowledge packs.`

Topics should be narrow and useful:

- domain: `app-store`, `app-reviews`, `notebooklm`, `geo`
- stack: `nextjs`, `agent-skill`, `deepseek`
- audience/workflow: `product-management`, `ai-workflow`

Avoid generic topics like `tool`, `website`, `ai` unless they add discoverability.

## Kunpeng Profile Block

For Kunpeng-owned public repos, include profile/support links by default:

- `kunpeng.ai`
- `blog.kunpeng.ai`
- `tuijian.kunpeng.ai`
- X `@`
- GitHub `@AIKunpeng`
- WeChat public account `鲲鹏推荐看`

Use `kunpeng-profile` as the source of truth for bios and assets. Do not invent personal claims.

## Release Checklist

Before claiming done:

- `README.md` is Chinese-first bilingual by default; a separate `README.zh-CN.md` alone is not enough.
- README has no TODO/placeholders.
- Screenshots and links exist.
- `LICENSE` exists or the repo intentionally omits one.
- `gh repo view` confirms About/homepage/topics.
- Relevant build/test/install checks passed.
- Git diff was scanned for secrets.
- PR was merged into `main` unless explicitly held.

## Guardrails

- Do not publish secrets, `.env.local`, private paths, cache data, tokens, or runtime databases.
- Do not overpromise current features; mark roadmap items clearly.
- Do not bury setup failures in the README; make prerequisites explicit.
- Do not treat Chinese-first bilingual README work as optional polish for Kunpeng-owned GitHub releases.
- Do not leave a verified PR dangling when the user expects publication.
