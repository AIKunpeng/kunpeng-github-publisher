---
name: kunpeng-github-publisher
description: |
  Use when publishing or polishing a GitHub repository for a Kunpeng-owned project:
  rewrite public READMEs as Chinese-first bilingual product pages, set bilingual
  GitHub About descriptions, choose topics, add screenshots, badges, community
  health files, social-preview guidance, verify deploy/install paths, create PRs,
  and merge verified changes to main.
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
   - GitHub and community surfaces: About description, homepage, topics, social preview, license, `SECURITY.md`, `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, issue templates, PR template, releases/changelog when present.
   - GitHub remote state via `gh repo view --json name,description,homepageUrl,repositoryTopics,url,defaultBranchRef,isPrivate,licenseInfo`.
2. Decide the public positioning:
   - One-line hook in Chinese and English, with the Chinese version first.
   - Target users and why they should try it now.
   - Clear boundary between product value, technical architecture, and private/local setup.
   - Intended release posture: showcase-only, user-installable tool, external-contributor project, library/package, or deployed product.
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
   - For public launch polish, create or request a social preview image. If it cannot be automated, record the manual GitHub Settings step as a follow-up instead of pretending it was set.
5. Improve trust surfaces according to release posture:
   - Always verify license state for open source repos.
   - For external-contributor projects, add or update `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `SECURITY.md`, issue templates, and a PR template when missing or stale.
   - For showcase-only repos, explain if contribution/community files are intentionally omitted.
6. Verify what the README promises:
   - Run project-provided lint/build/test commands when relevant.
   - For skills, verify `npx skills add` discoverability/installability.
   - For websites, verify live URL/API/health after deployment when applicable.
7. Publish through a clean GitHub flow:
   - Use a feature branch and PR.
   - Never push directly to `main`.
   - If verification passes and the user has not explicitly asked to hold, merge the PR into `main`.
   - In the final response, include the PR URL and merge commit.

## Source-Backed Presentation Model

This skill is grounded in GitHub's own repository presentation surfaces:

- README: GitHub says a repository README should explain what the project does, why it is useful, how users get started, where to get help, and who maintains it. GitHub automatically surfaces a recognized README to visitors.
- Topics: GitHub topics help people discover repositories by purpose, subject area, community, language, or other important qualities.
- License: GitHub's license guidance says a public repository needs an open source license before others are clearly free to use, change, and distribute it.
- Community profile: GitHub's public repository checklist looks for README, license, code of conduct, contributing guide, security policy, and issue/PR templates.
- Security policy: `SECURITY.md` tells people how to report vulnerabilities.
- Issue and PR templates: templates standardize the information contributors provide when opening issues or pull requests.
- Social preview: GitHub lets repository maintainers set a social preview image from repository settings; use solid backgrounds when transparency may render unpredictably.

Use official docs first when this guidance conflicts with a blog checklist.

## README Standard

### Language Gate

For Kunpeng-owned public repositories, `README.md` must be Chinese-first bilingual before release:

- First viewport: project name, Chinese value proposition, English value proposition, badges/links, and a visible language switch such as `**中文** | [English](#english)`.
- Main body: Chinese sections first, written as the default reader experience.
- English access: provide a substantive English section or linked English README. At minimum, English readers must understand what it does, how to try/install it, what is verified, and the main limits/prerequisites.
- Translation files such as `README.zh-CN.md` and `README.en.md` may exist, but the GitHub default `README.md` still has to open with Chinese first unless the user explicitly approved a different audience.
- If `README.md` is English-only, English-first, or relies on a separate Chinese file for the Chinese experience, stop and fix it before opening/merging the release PR.

### First-Viewport Gate

The top of `README.md` should pass a 60-second stranger test:

- What is this, in one concrete sentence?
- Who is it for and what pain does it remove?
- What can I click, install, or try immediately?
- What proof can I see: screenshot, demo, sample output, CI badge, or verified command?
- What should I trust: license, maintainer, security/privacy boundary, and last verified status?

Avoid badge walls, abstract taglines, and architecture-first openings. Architecture belongs after the user understands the product value.

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

[Live Demo] [Install] [Docs] [License] [CI]

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

### Proof And Media

- Prefer one real screenshot, demo GIF, terminal transcript, API response, generated artifact, or hosted demo near the top.
- Every screenshot or sample must match a current verified state. Do not use mock images unless clearly labelled as design mockups.
- For CLI/tools, include a short successful command transcript and a failure/troubleshooting example.
- For websites/apps, include live URL, deployment target, health/API check, and a desktop/mobile screenshot when feasible.
- Keep README comfortably below GitHub's 500 KiB render-truncation limit; if docs grow large, split deeper material into `docs/` and link it.

## GitHub Surface Standard

### GitHub About Standard

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

### Homepage, Badges, And Social Preview

- Set homepage to the live demo, documentation, install page, or product home. If none exists, leave it blank rather than pointing to an unrelated page.
- Use a small badge row: CI/build, license, package/install, live demo, version, or coverage only when those links are real and maintained.
- Add or request a social preview image for public launches, especially when the repo will be shared on X, WeChat, newsletters, or product directories.
- If social preview cannot be set via CLI/API in the current environment, leave an explicit manual checklist item: GitHub repo Settings -> Social preview -> Upload image.
- Social preview art should show the project name, one concrete promise, and the relevant UI/output. Use a solid background unless transparency has been checked.

### Reference URLs

- GitHub README docs: https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes
- GitHub topics docs: https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/classifying-your-repository-with-topics
- GitHub license docs: https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/licensing-a-repository
- GitHub social preview docs: https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/customizing-your-repositorys-social-media-preview
- GitHub community profile docs: https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/about-community-profiles-for-public-repositories
- GitHub security policy docs: https://docs.github.com/en/code-security/how-tos/report-and-fix-vulnerabilities/configure-vulnerability-reporting/add-security-policy
- GitHub issue/PR templates docs: https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/about-issue-and-pull-request-templates
- Open Source Guides starting a project: https://opensource.guide/starting-a-project/

## Kunpeng Profile Block

For Kunpeng-owned public repos, include profile/support links by default:

- `kunpeng.ai`
- `blog.kunpeng.ai`
- `tuijian.kunpeng.ai`
- X `@`
- GitHub `@AIKunpeng`
- WeChat public account `鲲鹏推荐看`

Use `kunpeng-profile` as the source of truth for bios and assets. Do not invent personal claims.

## Community Health Standard

Apply this based on project posture, not mechanically:

- Open-source repos must have a license or an explicit "not yet licensed" blocker.
- External-contributor projects should include `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `SECURITY.md`, issue templates, and a PR template.
- User-installable tools should at least document support/help, security/privacy boundaries, and how to report bugs.
- Small showcase repos may omit contribution files, but README should say whether contributions are welcome, not expected, or not supported.
- For issue templates, prefer structured forms for bugs/features when the project expects outside reports.
- PR templates should ask for summary, verification, screenshots/output when relevant, and linked issues.

## Release Checklist

Before claiming done:

- `README.md` is Chinese-first bilingual by default; a separate `README.zh-CN.md` alone is not enough.
- README first viewport passes the stranger test: value, audience, action, proof, trust.
- README has no TODO/placeholders.
- Screenshots, demos, samples, and links exist or are explicitly marked not applicable.
- `LICENSE` exists or the repo intentionally omits one.
- Community health files are present or intentionally omitted based on release posture.
- `gh repo view` confirms About/homepage/topics.
- Social preview was set, or a manual follow-up was recorded.
- Relevant build/test/install checks passed.
- Git diff was scanned for secrets.
- PR was merged into `main` unless explicitly held.

## Guardrails

- Do not publish secrets, `.env.local`, private paths, cache data, tokens, or runtime databases.
- Do not overpromise current features; mark roadmap items clearly.
- Do not bury setup failures in the README; make prerequisites explicit.
- Do not treat Chinese-first bilingual README work as optional polish for Kunpeng-owned GitHub releases.
- Do not create performative community files for a repo that is not ready for contributors; explain the posture instead.
- Do not claim a social preview, screenshot, demo, package install, or live URL exists unless verified in the current run.
- Do not leave a verified PR dangling when the user expects publication.
