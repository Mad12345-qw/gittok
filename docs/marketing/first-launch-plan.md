# GitTok 第一期推广计划

目标：用 7 天验证 GitTok 在中文开发者圈的传播潜力，拿到第一批真实用户、star、反馈和内容素材。

## 一句话定位

GitTok 是一个“程序员版短视频信息流”：像刷抖音一样刷 GitHub 仓库，自动生成中文 README 摘要，帮开发者用碎片时间发现好项目。

## 首期目标

- GitHub stars：从 2 增长到 100。
- 线上体验访问：1000 UV。
- 有效反馈：30 条。
- 收藏、star、外跳 GitHub 等关键行为：至少 100 次。
- 拿到 3 个可复用传播素材：演示视频、技术帖、周刊投稿。

## 核心卖点

- 刷 GitHub：上下滑动浏览仓库，比列表更适合碎片时间。
- 中文摘要：不用逐个打开英文 README，先看懂项目是干什么的。
- 即点即用：在线 demo 可直接体验。
- 开源透明：Next.js + TypeScript 实现，代码可学习、可二开。
- 对项目作者友好：仓库卡片天然适合分享和曝光。

## 15-30 秒演示视频脚本

画面比例：9:16，手机录屏优先。不要做复杂包装，真实滑动最有说服力。

### 标题备选

1. 我做了一个程序员版抖音：刷 GitHub 项目
2. 刷抖音一样刷 GitHub，README 还能自动变中文
3. 再也不用一个个点开英文 README 了
4. 每天摸鱼 5 分钟，发现 10 个开源项目
5. GitTok：给程序员刷的短视频流

### 分镜

| 时间 | 画面 | 字幕 |
| --- | --- | --- |
| 0-3s | 打开 GitTok 首页，第一张卡片出现 | 我把 GitHub 做成了短视频流 |
| 3-8s | 连续上滑 3-5 张仓库卡片 | 上下滑动，直接发现开源项目 |
| 8-13s | 停在一个英文项目，展示中文摘要 | 英文 README 自动生成中文摘要 |
| 13-18s | 点 star / 收藏 / 评论按钮 | 喜欢就收藏、star、讨论 |
| 18-24s | 展示 GitHub 仓库 README 和 demo 链接 | 项目已开源，在线可试 |
| 24-30s | 回到 GitTok 名称和链接 | 搜 GitTok，欢迎来提建议 |

### 口播

我做了一个程序员版抖音，名字叫 GitTok。它可以像刷短视频一样刷 GitHub 开源项目，每张卡片会自动生成中文 README 摘要，不用一个个点进去翻英文。看到有用的项目，可以直接 star、收藏、关注作者，也能评论讨论。项目已经开源，在线 demo 可以直接体验，欢迎来试试。

## 渠道首发文案

### V2EX / 掘金 / CSDN 标题

我做了一个程序员版抖音：像刷短视频一样发现 GitHub 开源项目

### 长帖正文

大家好，我最近做了一个小项目 GitTok，想解决一个很朴素的问题：GitHub 上好项目很多，但发现成本太高。

平时我们找项目，要么看 GitHub Trending，要么靠关键词搜索，要么刷别人整理的列表。问题是这些方式都偏“主动搜索”，不太适合碎片时间随便看看。

所以我把 GitHub 仓库做成了一个竖向信息流：

- 上下滑动浏览仓库，像刷短视频一样。
- 自动读取 README，生成中文摘要。
- 展示项目图片、语言、stars、topics、更新时间。
- 支持 star、收藏、关注作者、不感兴趣反馈。
- 支持站内评论，也能对接 GitHub Discussions。

在线体验：
https://gittok.onrender.com/

GitHub：
https://github.com/Mad12345-qw/gittok

技术栈是 Next.js 14、TypeScript、Tailwind CSS、NextAuth、Prisma、PostgreSQL、Redis。推荐部分目前还是早期版本，主要基于语言、topics、stars、停留时长、收藏、关注、不感兴趣等信号做排序，后面会继续优化“最近增长很快的小项目”和个性化推荐。

现在最想听大家吐槽三件事：

1. 这种刷 GitHub 的方式有没有用？
2. 中文 README 摘要是否真的降低了理解成本？
3. 你希望推荐流按什么维度筛选？语言、主题、star 增长、AI 项目、前端工具，还是别的？

欢迎体验、star、提 issue。也欢迎把自己的开源项目丢给我，我会测试是否适合进入推荐流。

### 小红书/朋友圈短文案

做了一个程序员版抖音：GitTok。

它可以像刷短视频一样刷 GitHub 开源项目，还会自动生成中文 README 摘要。看到有用的项目，可以直接收藏、star、关注作者。

适合每天摸鱼 5 分钟，发现几个新工具。

在线体验：https://gittok.onrender.com/
GitHub：https://github.com/Mad12345-qw/gittok

### X / Reddit 英文短文案

I built GitTok: a TikTok-style feed for discovering GitHub repositories.

Swipe through repos, read quick Chinese README summaries, star/favorite projects, follow authors, and discuss repos in one flow.

Live demo: https://gittok.onrender.com/
GitHub: https://github.com/Mad12345-qw/gittok

Feedback welcome, especially on recommendation quality and repo discovery UX.

## 周刊投稿模板

### 阮一峰科技爱好者周刊

标题：GitTok：像刷短视频一样发现 GitHub 开源项目

正文：

GitTok 是一个面向中文开发者的 GitHub 仓库发现工具。它把传统的 GitHub 搜索和 Trending 榜单，改造成竖向滑动信息流：用户可以像刷短视频一样浏览开源项目，并自动查看中文 README 摘要、项目图片、语言、stars、topics 和更新时间。项目还支持 star、收藏、关注作者、站内评论和 GitHub Discussions。

项目适合用碎片时间发现开源工具，也适合中文开发者快速看懂英文 README。

在线体验：https://gittok.onrender.com/
源码：https://github.com/Mad12345-qw/gittok

### HelloGitHub / GitHubDaily

项目名称：GitTok

项目地址：https://github.com/Mad12345-qw/gittok

一句话介绍：像刷短视频一样发现 GitHub 开源项目，自动生成中文 README 摘要。

推荐理由：

GitTok 把 GitHub 仓库发现做成了移动端友好的竖向信息流，适合开发者在碎片时间发现新项目。它会自动读取 README 并生成中文摘要，降低中文开发者理解英文项目的成本。项目还支持 star、收藏、关注作者、站内评论、GitHub Discussions 和个性化推荐反馈，是一个有趣且实用的开源项目发现工具。

## 7 天执行排期

### Day 1：准备和首发

- 更新 README 首屏、仓库描述、topics、demo 链接。
- 录制 15-30 秒移动端滑动视频。
- 发布 V2EX 和掘金长帖。
- GitHub 开一个 feedback issue，集中收集用户建议。

### Day 2：短视频扩散

- 发布 B 站、抖音、快手、小红书。
- 评论区置顶在线 demo 和 GitHub 地址。
- 收集前三类问题：访问速度、推荐质量、摘要质量。

### Day 3：周刊投稿

- 向阮一峰科技爱好者周刊提交 issue。
- 向 HelloGitHub / GitHubDaily 投稿。
- 找 5 个中文开源周报或公众号私信推荐。

### Day 4：技术复盘内容

- 发《我是怎么用 Next.js 做一个 GitHub 推荐流的》。
- 重点讲 README 摘要、GitHub API 限流、推荐流、移动端滑动。
- 引导开发者 star 和提 issue。

### Day 5：社区反馈迭代

- 整理用户反馈，修 1-3 个最影响体验的问题。
- 发布 changelog：感谢反馈 + 今天修了什么。
- 邀请用户二次体验。

### Day 6：项目作者传播

- 挑 20 个被推荐的开源项目，给作者发简短说明。
- 重点说“你的项目在 GitTok 获得了展示”，邀请他们查看卡片。
- 避免刷屏，不要在无关 issue 里硬广。

### Day 7：复盘和第二轮

- 统计 stars、访问量、收藏/外跳、反馈数量。
- 选出转化最高的标题和渠道。
- 决定第二期主攻方向：AI 项目、前端工具、中文开源、独立开发工具。

## 发布检查清单

- 首页 5 秒内能看到产品价值。
- README 顶部有 demo GIF、在线体验、GitHub 地址。
- 仓库 description、homepage、topics 已配置。
- 移动端访问速度可接受。
- 首屏不出现乱码、空白摘要或长时间加载。
- 有一个专门收集反馈的 GitHub issue。
- 每个平台发帖都带 demo 链接、GitHub 链接、明确求反馈问题。

## 关键指标

- GitHub star 转化率：访问 GitHub 后 star 的比例。
- Demo 到 GitHub 点击率：线上体验用户是否愿意看源码。
- 卡片互动率：收藏、star、评论、不感兴趣。
- 平均浏览卡片数：判断信息流是否有吸引力。
- 分享回流：分享链接带来的访问量。
- 有效反馈数：能产生下一轮迭代的真实建议。

## 风险和底线

- 不要去无关开源项目 issue 区硬广，容易伤害口碑。
- 不要夸大“AI 推荐”，当前推荐还在早期，应诚实说是可迭代推荐。
- 不要把它包装成替代 GitHub Trending，而是“更轻、更快、更适合碎片时间的发现方式”。
- 推广前优先修复明显的乱码、密钥 fallback、测试失败和访问速度问题。
