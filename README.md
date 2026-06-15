# kunpeng-github-publisher

> 把一个能跑的项目，包装成 GitHub 上别人愿意点开、试用、安装、star 的开源项目。
> Turn a working project into a GitHub-ready public release with a Chinese-first bilingual README, GitHub showcase surfaces, community health checks, verification, PR, and merge flow.

[![Install Skill](https://img.shields.io/badge/Install-npx%20skills%20add-111827?style=for-the-badge)](#install)
[![GitHub](https://img.shields.io/badge/GitHub-AIKunpeng%2Fkunpeng--github--publisher-0f172a?style=for-the-badge&logo=github)](https://github.com/AIKunpeng/kunpeng-github-publisher)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## 为什么需要它

很多项目已经能跑，但 GitHub 首屏仍然像内部备忘录：README 没有痛点、没有截图、没有清晰安装路径，About 也没有抓住关键词。`kunpeng-github-publisher` 专门处理最后这一步：把项目变成一个陌生人也能理解、信任并愿意尝试的公开仓库。

## 它会帮你做什么

- 重写或修补默认 `README.md`，让它成为中文优先、中英双语的产品页，而不是开发日志
- 写中英双语 GitHub About 描述，设置 homepage 和 focused topics
- 检查首屏是否能让陌生人在 60 秒内理解：价值、受众、行动、证据、信任
- 检查截图、徽章、安装步骤、API 示例、Troubleshooting 和 social preview
- 按项目姿态补齐或说明 license、SECURITY、CONTRIBUTING、CODE_OF_CONDUCT、issue/PR templates
- 跑项目对应的 lint/build/test/install 验证
- 扫描 diff 中的敏感信息
- 创建 PR，并在验证通过后合并到 `main`
- 对 Kunpeng-owned 项目默认加入鲲鹏 profile、链接和支持入口

## Install

```bash
npx skills add AIKunpeng/kunpeng-github-publisher
```

## Usage

安装后你可以这样说：

- `把这个项目整理成适合 GitHub 发布的 README，并设置 About`
- `这个 repo 要开源，帮我包装一下再发到 GitHub`
- `重写 README，中文优先中英双语，验证后自动合并 main`
- `优化 GitHub topics、homepage 和项目描述`

## Workflow

1. Inspect repo state and existing metadata.
2. Rewrite the default `README.md` with a Chinese-first bilingual structure by default.
3. Apply the first-viewport stranger test: value, audience, action, proof, trust.
4. Update GitHub About, homepage, topics, badges, social-preview guidance, and community-health posture.
5. Run project-specific verification.
6. Create a PR and merge verified changes into `main` unless explicitly held.

## README Language Gate

For Kunpeng-owned public repos, the GitHub default `README.md` must open with Chinese first and still serve English readers. A separate `README.zh-CN.md` can exist, but it is not a substitute for a Chinese-first default README.

Minimum expectation:

- Chinese value proposition and main sections appear first.
- English value proposition and install/try/limits path are visible through an English section or linked English README.
- GitHub About is compact bilingual by default: `中文短描述 | English short description.`
- If the default README is English-only or English-first, fix it before release.

## GitHub Showcase Gate

The skill now checks the whole repository presentation, not only the README:

- About/homepage/topics are concrete, bilingual where appropriate, and discoverable.
- README first viewport contains a real CTA and proof: screenshot, demo, sample output, CI, or verified command.
- License is present for open-source repos, or absence is treated as a blocker.
- External-contributor projects get community-health files: `SECURITY.md`, `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, issue templates, and PR template.
- Social preview is set when possible, or a manual GitHub Settings follow-up is recorded.

## English

`kunpeng-github-publisher` is an Agent Skill for GitHub release polish. It helps turn working projects into public repositories with a Chinese-first bilingual README, discoverable GitHub metadata, social-preview guidance, community-health checks, real verification, and a complete PR-to-main publishing flow.

<!-- kunpeng-profile:start -->
## 关于鲲鹏

鲲鹏（乔向阳 / Joe）是一位实践型 AI 产品与内容创作者，长期把前沿 AI 变化转译成可复用的工作流、产品判断、AI 编程实践、AI 搜索实践和 GEO/AI 营销方法。

- 个人网站: https://kunpeng.ai
- 博客: https://blog.kunpeng.ai
- 乔木推荐: https://tuijian.kunpeng.ai
- X: https://x.com/
- GitHub: https://github.com/AIKunpeng/
- 微信公众号: 鲲鹏推荐看

### 支持与关注

| 打赏支持 | 微信公众号 |
|---|---|
| <img src="assets/kunpeng-profile/kunpeng_reward_qr.png" alt="鲲鹏打赏二维码" width="180" /> | <img src="assets/kunpeng-profile/kunpeng_wechat_public_account_qr.jpg" alt="鲲鹏推荐看公众号二维码" width="180" /> |
| 感谢支持乔木持续分享 AI 实践 | 扫码关注「鲲鹏推荐看」 |

<!-- kunpeng-profile:end -->

## License

MIT
