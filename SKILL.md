---
name: kunpeng-github-publisher
description: |
  Use when publishing or polishing a GitHub repository for a Kunpeng-owned project:
  rewrite public READMEs, set bilingual GitHub About descriptions, choose topics,
  add screenshots and badges, verify deploy/install paths, create PRs, and merge
  verified changes to main. Trigger on requests like "发布到 GitHub", "开源",
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
   - One-line hook in Chinese and English.
   - Target users and why they should try it now.
   - Clear boundary between product value, technical architecture, and private/local setup.
3. Rewrite or patch README as a product page:
   - Chinese first, English second unless the repo is explicitly English-first.
   - Put hook, CTAs, badges, screenshot, feature list, quick start, examples, verification, limitations, and troubleshooting near the top.
   - Use real screenshots or output samples when available; do not invent screenshots.
4. Set GitHub About:
   - Use bilingual description when the user asks or the repo targets both Chinese and English audiences.
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
## 限制与边界
## Troubleshooting
## 关于鲲鹏

---

<a name="english"></a>
# English section
```

## GitHub About Standard

Use a compact bilingual form when appropriate:

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
- Do not leave a verified PR dangling when the user expects publication.
