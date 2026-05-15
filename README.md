# GitTok

像刷短视频一样发现 GitHub 开源项目，自动生成中文 README 摘要。

## 立即在线体验

<p align="center">
  <a href="https://gittok.onrender.com/">
    <img alt="立即打开 GitTok 在线体验" src="https://img.shields.io/badge/立即打开-GitTok%20在线体验-16a34a?style=for-the-badge&logo=github&logoColor=white">
  </a>
</p>

<p align="center">
  <strong>体验地址：</strong>
  <a href="https://gittok.onrender.com/"><strong>https://gittok.onrender.com/</strong></a>
</p>

## Demos

### GitTok 移动端推荐流

任务：像刷短视频一样发现 GitHub 优质开源项目。

<p align="center">
  <img src="https://raw.githubusercontent.com/Mad12345-qw/gittok/main/docs/images/gittok-mobile-feed.gif" alt="GitTok 移动端推荐流 Demo" width="320">
</p>

[在线体验 ↗](https://gittok.onrender.com/)

GitTok 是一个面向中文开发者的 GitHub 仓库发现工具。它把传统的列表式 GitHub 搜索，改造成沉浸式竖向信息流：滑动浏览仓库、自动生成中文 README 摘要、查看项目图片、星标/关注作者、分享当前仓库页面，并在站内评论区或官方 Discussions 里参与讨论。

适合这些场景：

- 每天用碎片时间发现新的开源工具。
- 快速看懂英文 README，不必逐个仓库点进去翻译。
- 给自己的开源项目找曝光入口。
- 做技术选型、周报、开源项目推荐时快速找素材。

推广与投稿素材见：[第一期推广计划](docs/marketing/first-launch-plan.md)。

<p align="center">
  <a href="https://github.com/Mad12345-qw/gittok"><img alt="GitHub 仓库" src="https://img.shields.io/badge/GitHub-Mad12345--qw%2Fgittok-24292f?style=for-the-badge&logo=github"></a>
  <img alt="Next.js" src="https://img.shields.io/badge/Next.js-14-black?style=for-the-badge&logo=nextdotjs">
  <img alt="TypeScript" src="https://img.shields.io/badge/TypeScript-Ready-3178c6?style=for-the-badge&logo=typescript&logoColor=white">
</p>

<p align="center">
  <a href="#项目亮点">项目亮点</a> ·
  <a href="#系统架构">系统架构</a> ·
  <a href="#推荐系统">推荐系统</a> ·
  <a href="#本地开发">本地开发</a> ·
  <a href="#部署说明">部署说明</a>
</p>

## 项目定位

GitHub 上有大量优秀项目，但发现过程往往依赖搜索关键词、榜单、收藏夹和社交推荐。GitTok 想解决的是另一个问题：

> 让开发者用更低成本、更高频率、更接近内容流的方式发现值得关注的开源项目。

它不是简单的 GitHub Trending 复制品，而是一个带推荐、摘要、评论和分享链路的仓库发现产品。

## 项目亮点

### 沉浸式仓库信息流

- 类似短视频的上下滑动浏览体验。
- 每张卡片展示仓库名称、作者、语言、星标、更新时间、README 摘要和主题标签。
- 100 张大批量推荐缓冲，提前预加载，减少滑动卡顿。
- 支持“不感兴趣”反馈，用于后续推荐优化。
- 分享链接会回到 GitTok 当前仓库页面，而不是只跳 GitHub 原仓库。

### 中文 README 摘要

- 自动读取 GitHub README。
- 生成面向中文用户的项目摘要。
- 提取 README 中适合展示的项目图片。
- 过滤徽章、坏图、非图片链接，避免页面出现破图。
- GitHub API 限流或翻译失败时，提供安全中文提示，不展示空白内容。

### 个性化推荐

- 冷启动用户也能获得可浏览内容。
- 根据语言、主题、星标、fork、停留时长、星标、关注、不感兴趣等信号调整推荐。
- 混入探索内容，避免推荐越刷越窄。
- 使用 session seed 避免每次打开都是同一批开头内容。

### 双评论系统

- GitTok 站内评论：所有仓库都能留言，不受 GitHub 组织 OAuth 限制影响。
- 官方 Discussions：仓库开启 GitHub Discussions 时，可同步查看和评论。
- 评论按钮默认展示 GitTok 评论数 + 官方 Discussions 数的合计。
- 官方 GitHub 权限受限时，前端会给出明确提示。

### GitHub 交互

- GitHub OAuth 登录。
- 星标 / 取消星标仓库。
- 关注 / 取消关注作者。
- 读取收藏、关注、设置等用户状态。
- 支持服务端 GitHub Token 提升公开数据读取稳定性。

### 健康检查清单

项目内置 `npm run health`，用于避免修改一个功能又把另一个功能弄坏。当前检查覆盖：

- 首页和 CSS 是否正常加载；
- GitHub OAuth 回调地址是否正确；
- 推荐流是否支持 100 张批量；
- 深分页是否仍能继续出内容；
- 是否不再出现“没有更多了”终点页；
- 尾部加载是否能提前触发；
- 简介、标签等详情内容滚动时是否不会误触发推荐流翻页；
- README 摘要是否返回中文；
- README 摘要是否不会长期停在“正在生成中”；
- README 图片提取是否避开坏链接；
- GitTok 评论是否能独立加载和发布；
- 官方 Discussions 权限错误是否可读；
- 评论按钮是否永远显示数字；
- 评论数是否合并 GitTok 与官方 Discussions。

## 系统架构

```mermaid
flowchart TD
  Browser["浏览器 / 移动端 Web"] --> NextApp["Next.js App Router"]
  NextApp --> FeedAPI["/api/feed 推荐流"]
  NextApp --> EnrichAPI["/api/feed/enrich README 摘要"]
  NextApp --> GitTokComments["/api/gittok/comments 站内评论"]
  NextApp --> GitHubDiscussions["/api/github/discussions 官方讨论"]
  NextApp --> Auth["NextAuth GitHub 登录"]

  FeedAPI --> FeedService["Feed Service"]
  FeedService --> Recommendation["推荐算法"]
  FeedService --> GitHubAPI["GitHub REST API"]
  FeedService --> Prisma["Prisma / PostgreSQL"]

  EnrichAPI --> GitHubReadme["GitHub README API"]
  EnrichAPI --> Translate["百度翻译 API"]
  EnrichAPI --> Redis["Redis 缓存"]

  GitTokComments --> Prisma
  GitHubDiscussions --> GitHubGraphQL["GitHub GraphQL API"]
  Auth --> GitHubOAuth["GitHub OAuth"]
```

## 技术栈

| 模块 | 技术 |
| --- | --- |
| 前端框架 | Next.js 14 App Router |
| 开发语言 | TypeScript |
| UI | React, Tailwind CSS |
| 状态管理 | Zustand |
| 登录鉴权 | NextAuth.js + GitHub OAuth |
| 数据库 | PostgreSQL + Prisma |
| 缓存 | Redis / Upstash Redis |
| 外部 API | GitHub REST, GitHub GraphQL, 百度翻译 |
| 部署 | Render 或任意 Node.js 运行环境 |

## 项目结构

```text
src/
  app/
    api/                  推荐、认证、GitHub、评论、设置等 API
    favorites/            星标仓库页面
    follows/              关注作者页面
    login/                GitHub 登录页
    settings/             用户设置页
  components/
    feed/                 推荐流、仓库卡片、右侧操作栏、评论抽屉
  hooks/                  README 摘要、评论数等客户端 hooks
  lib/                    鉴权、Prisma、GitHub Discussions、解析器、工具函数
  services/               推荐生成、评分、GitHub 客户端、用户画像更新
  stores/                 Zustand 状态管理
scripts/
  health-check.mjs        本地健康检查脚本
```

## 推荐系统

GitTok 当前采用可解释、可迭代的推荐链路：

1. 从 GitHub Search 或冷启动池获取候选仓库。
2. 根据用户设置过滤低质量内容、归档仓库、fork 仓库或屏蔽语言。
3. 基于用户画像对仓库打分。
4. 混入一定比例的探索内容，避免信息流过窄。
5. 一次返回大批量仓库，前端提前预加载。
6. 根据停留时长、星标、关注、不感兴趣等行为更新用户画像。

本地开发可以开启 mock feed，保证没有 GitHub Token 或数据库时也能稳定测试。

## 本地开发

### 环境要求

- Node.js 20+
- npm
- PostgreSQL 数据库
- Redis 实例
- GitHub OAuth App

### 安装依赖

```bash
npm install
```

### 配置环境变量

复制示例文件：

```bash
cp .env.example .env.local
```

常用配置如下：

```env
NEXTAUTH_URL=http://localhost:3000
NEXTAUTH_SECRET=generate-with-openssl-rand-base64-32

GITHUB_CLIENT_ID=your_github_client_id
GITHUB_CLIENT_SECRET=your_github_client_secret
GITHUB_TOKEN=optional_public_repo_token

DATABASE_URL=postgresql://user:password@host/dbname?sslmode=require
REDIS_URL=rediss://default:your_token@your-host.upstash.io:6379

BAIDU_TRANSLATE_APPID=your_appid
BAIDU_TRANSLATE_API_KEY=your_api_key

USE_MOCK_FEED=false
NEXT_PUBLIC_USE_MOCK_FEED=false
```

### 启动开发服务

```bash
npm run dev
```

浏览器打开：

```text
http://localhost:3000
```

局域网测试时可访问类似：

```text
http://192.168.0.111:3000
```

### 验证项目状态

```bash
npm run build
npm run health
```

指定测试地址：

```bash
TEST_BASE_URL=http://192.168.0.111:3000 npm run health
```

## 部署说明

GitTok 可部署在 Render、Vercel 或其他支持 Node.js 的平台。

生产环境需要重点确认：

- `NEXTAUTH_URL` 必须等于线上站点地址；
- GitHub OAuth Callback URL 必须配置为：

```text
https://your-domain.com/api/auth/callback/github
```

- `DATABASE_URL` 必须指向可用 PostgreSQL；
- `REDIS_URL` 建议配置，用于缓存 README 和仓库数据；
- `GITHUB_TOKEN` 建议配置，用于提高公开 GitHub 数据读取稳定性；
- `BAIDU_TRANSLATE_APPID` 和 `BAIDU_TRANSLATE_API_KEY` 用于中文摘要生成。

构建命令：

```bash
npm run build
```

启动命令：

```bash
npm run start
```

## GitHub OAuth 权限说明

部分 GitHub 组织会限制第三方 OAuth App 访问。遇到这种情况时：

- GitTok 站内评论仍然可用；
- 官方 Discussions 可能需要登录或无法写入；
- 能否向官方 Discussions 发评论，取决于仓库和组织权限设置。

因此 GitTok 设计了两个 Tab：

- `GitTok 评论区`：站内独立评论，保证任何仓库都能留言；
- `官方讨论区`：同步 GitHub Discussions，权限允许时可直接互动。

## 路线图

- 更细的用户画像和推荐权重调节；
- 更稳定的中文摘要生成；
- GitTok 评论点赞、回复折叠和通知；
- 仓库合集与专题榜单；
- 更完善的 Render 部署诊断；
- 移动端手势和性能继续优化。

## 参与贡献

欢迎提交 issue、建议和 pull request。

提交前建议运行：

```bash
npm run build
npm run health
```

## 友链

- [LINUX DO](https://linux.do/)：新的理想型社区。

## 许可证

MIT
