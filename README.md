# kunpeng-github-publisher

> 把一个能跑的项目，包装成 GitHub 上别人愿意点开、试用、安装、star 的开源项目。
> Turn a working project into a GitHub-ready public release with a sharper README, bilingual About, topics, verification, PR, and merge flow.

[![Install Skill](https://img.shields.io/badge/Install-npx%20skills%20add-111827?style=for-the-badge)](#install)
[![GitHub](https://img.shields.io/badge/GitHub-AIKunpeng%2Fkunpeng--github--publisher-0f172a?style=for-the-badge&logo=github)](https://github.com/AIKunpeng/kunpeng-github-publisher)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## 为什么需要它

很多项目已经能跑，但 GitHub 首屏仍然像内部备忘录：README 没有痛点、没有截图、没有清晰安装路径，About 也没有抓住关键词。`kunpeng-github-publisher` 专门处理最后这一步：把项目变成一个陌生人也能理解、信任并愿意尝试的公开仓库。

## 它会帮你做什么

- 重写或修补 README，让它像产品页而不是开发日志
- 写中英双语 GitHub About 描述
- 设置 homepage 和 focused topics
- 检查截图、徽章、安装步骤、API 示例和 Troubleshooting
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
- `重写 README，中英双语，验证后自动合并 main`
- `优化 GitHub topics、homepage 和项目描述`

## Workflow

1. Inspect repo state and existing metadata.
2. Rewrite README with Chinese-first bilingual structure when appropriate.
3. Update GitHub About, homepage, and topics via `gh`.
4. Run project-specific verification.
5. Create a PR and merge verified changes into `main` unless explicitly held.

## English

`kunpeng-github-publisher` is an Agent Skill for GitHub release polish. It helps turn working projects into public repositories with a clear README, bilingual About text, useful topics, real verification, and a complete PR-to-main publishing flow.

<!-- kunpeng-profile:start -->
## 关于鲲鹏

鲲鹏（乔向阳 / Joe）是一位实践型 AI 产品与内容创作者，长期把前沿 AI 变化转译成可复用的工作流、产品判断、AI 编程实践、AI 搜索实践和 GEO/AI 营销方法。

- 个人网站: https://kunpeng.ai
- 博客: https://blog.kunpeng.ai
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
