# OpenClaw Knowledge

![Status](https://img.shields.io/badge/status-active-brightgreen)
![Positioning](https://img.shields.io/badge/positioning-knowledge%20%2F%20training%20%2F%20methodology-blue)
![License](https://img.shields.io/badge/license-MIT-black)

OpenClaw 的知识沉淀仓库：面向内容创作、培训交付、方法论沉淀和模板复用。

> 一个把 OpenClaw 配置模板、多 Agent 协作经验、培训材料和方法论，沉淀成可复用知识资产的仓库。

## Start here
- **第一次了解本项目**：先看 `docs/PROJECT_POSITIONING.md`
- **想直接搭模板**：看 `SOUL.md`、`IDENTITY.md`、`USER.md`、`AGENTS.md`
- **想看最值得卖的产品**：看 `docs/FLAGSHIP_PRODUCTS.md`
- **想看变现与销售路径**：看 `docs/FREE_TO_PAID.md`、`docs/SALES_STACK.md`
- **想看内容与渠道打法**：看 `docs/CONTENT_CHANNEL_STRATEGY.md`、`docs/CONTENT_SERIES_PLAN.md`

## 这个项目的定位
`openclaw-knowledge` 不是监控工具，也不是安全审计产品。

它的定位是：

> **OpenClaw 知识库 + 教学模板库 + 多 Agent 协作方法论仓库**

当前仓库先从 **多 Agent 协作配置模板** 切入，后续逐步扩展到：
- 内容创作与分发方法论
- 培训交付包
- 飞书知识库版本
- 行业场景 SOP
- 教程型 lead magnet

## 它解决什么问题
很多人知道 OpenClaw 很强，但真正卡住他们的不是“有没有能力”，而是：
- 不知道怎么开始配置
- 不知道多 Agent 如何分工
- 不知道哪些文件最关键
- 不知道怎么把个人试验升级成团队协作
- 不知道怎么把经验沉淀成可复用模板

这个仓库就是把这些经验整理成：
- 模板
- 教程
- 方法论
- 可交付材料

## 适合谁
- 想搭建自己 AI 工作流的独立开发者
- 想做多 Agent 协作的 OpenClaw 用户
- 想把 OpenClaw 用于内容、产品、研发、增长的人
- 想做培训、咨询、教学交付的人
- 想把个人经验沉淀成模板包的人

## 当前包含内容
### 1. 核心配置文件
- `SOUL.md` - AI 价值观与决策框架
- `IDENTITY.md` - AI 身份与风格
- `AGENTS.md` - 多 Agent 协作规则
- `USER.md` - 用户画像与偏好
- `MEMORY.md` - 长期记忆模板

### 2. 协作模板
- `TASK_TEMPLATE.md`
- `RESULT_TEMPLATE.md`
- `CHECKLIST.md`
- `REPLY_TEMPLATE.md`

### 3. 教学与安装说明
- `INSTALL.md`
- `USAGE.md`
- `GITHUB_GUIDE.md`

### 4. 飞书知识库版本
- `feishu/` 目录下的结构化文档

## 当前阶段
当前仓库主要聚焦在：

> **多 Agent 协作配置模板**

也就是先把 OpenClaw 的多人/多角色协作方式，沉淀成一个可复制、可教学、可交付的模板包。

这只是第一阶段，不是最终形态。

## 导航
### 先看定位
- [项目定位](docs/PROJECT_POSITIONING.md)
- [仓库演进说明](docs/REPO_EVOLUTION.md)
- [仓库导航](docs/NAVIGATION.md)

### 再看产品化
- [旗舰产品建议](docs/FLAGSHIP_PRODUCTS.md)
- [内容 / 培训 / 方法论变现路径](docs/CONTENT_TRAINING_MONETIZATION.md)
- [产品分层设计](docs/PRODUCT_LAYERS.md)
- [免费到付费转化路径](docs/FREE_TO_PAID.md)
- [可售卖 Offers 设计](docs/OFFERS.md)
- [内容产品计划](docs/CONTENT_PRODUCT_PLAN.md)

### 再看运营与增长
- [资产地图](docs/ASSET_MAP.md)
- [Lead Magnets 清单](docs/LEAD_MAGNETS.md)
- [内容渠道策略](docs/CONTENT_CHANNEL_STRATEGY.md)
- [内容系列规划](docs/CONTENT_SERIES_PLAN.md)
- [用户分层](docs/USER_SEGMENTS.md)
- [上线顺序](docs/LAUNCH_SEQUENCE.md)

## 后续扩展方向
### A. 知识沉淀
- OpenClaw 配置方法论
- 常见误区与最佳实践
- 不同工作流的角色设计方法

### B. 内容变现
- 公众号选题配套模板
- 小红书/知乎/公众号教程母版
- 可下载的检查清单与 lead magnet

### C. 培训变现
- 训练营讲义
- 工作坊材料
- 企业内训版模板
- 顾问交付前置资料包

### D. 方法论产品化
- AI 公司配置模板
- 多 Agent 协作 SOP
- 团队协作与门禁规则模板
- 行业化模板手册

## 与其他项目的关系
- `openclaw-money-radar`：商业洞察 / 商机雷达 / 哪些方向值得做
- `openclaw-template-market`：模板商店 / 场景商品化展示
- `openclaw-monitor-lite`：运行监控 / AgentOps / 成本与告警
- `openclaw-security-audit-lite`：安全审计 / 权限基线 / 上线体检
- `openclaw-knowledge`：知识沉淀 / 教学模板 / 方法论资产

## 快速开始
### Step 1: 安装 OpenClaw
```bash
npm install -g openclaw
openclaw gateway start
```

### Step 2: 创建工作区
```bash
mkdir -p ~/.openclaw/workspace-my-ai-company
cd ~/.openclaw/workspace-my-ai-company
cp -r /path/to/this/template/* .
```

### Step 3: 修改核心文件
优先调整：
1. `SOUL.md`
2. `IDENTITY.md`
3. `USER.md`
4. `AGENTS.md`

### Step 4: 跑第一个任务
```bash
openclaw chat "帮我写一篇关于 AI 的文章"
```

## 推荐使用方式
### 如果你是个人用户
直接把它当作你的 OpenClaw 协作模板起点。

### 如果你是内容创作者
把它当作：
- 公众号 / 小红书方法论沉淀仓库
- 模板下载包
- 内容 lead magnet 生产仓库

### 如果你是培训/咨询交付方
把它当作：
- 课程模板包
- 多 Agent 演示模板
- 交付前置配置资产

## 适合谁使用
- 想快速搭起第一套 OpenClaw 多 Agent 协作结构的人
- 想把个人经验沉淀成模板的人
- 想用内容吸引用户，再卖模板/训练营/咨询升级包的人
- 想做 AI 公司协作模板、飞书知识库模板、交付模板的人

## 使用场景
### 场景 1：你想快速搭出自己的多 Agent 协作结构
这个仓库提供最小可用的配置骨架和角色分工模板。

### 场景 2：你想把经验写成公众号 / 小红书 / 知识产品
这个仓库可以作为方法论底稿、模板来源和 lead magnet 资产池。

### 场景 3：你想做培训 / 顾问 / 企业内训
这个仓库可以作为教学模板、交付资料和飞书知识库底板。

## 更适合公开访客的理解方式
你可以把这个仓库理解成：
- GitHub 上的免费知识入口
- 模板包与方法论产品的底层资产库
- 公众号 / 小红书 / 私域内容的结构化来源
- 培训、工作坊、顾问交付的前置材料仓库

## 当前最值得关注的 3 个产品方向
1. **多 Agent 协作模板包**：最低门槛的第一层成交产品
2. **AI 公司配置模板包**：更有方法论辨识度的中层产品
3. **飞书知识库交付模板包**：更偏培训/顾问/企业场景的升级产品

## 一屏理解这个仓库
- 它首先是一个 **免费知识入口**
- 其次是一个 **模板与方法论资产库**
- 再往上是一个 **低价知识产品与培训升级的中台**

## 版本层级理解
- **免费开源层**：基础模板、方法论入口、安装说明
- **低价知识产品层**：模板包、清单包、SOP 包
- **培训升级层**：训练营、工作坊、企业内训模板
- **长期资产层**：方法论沉淀与可复用教学结构

## 关联项目
- [openclaw-money-radar](https://github.com/jiangjinggit/openclaw-money-radar)
- [openclaw-template-market](https://github.com/jiangjinggit/openclaw-template-market)
- [openclaw-monitor-lite](https://github.com/jiangjinggit/openclaw-monitor-lite)
- [openclaw-security-audit-lite](https://github.com/jiangjinggit/openclaw-security-audit-lite)

## 项目价值一句话
> **不是只教你“怎么装 OpenClaw”，而是帮你把经验沉淀成可复制、可教学、可变现的知识资产。**

## License
MIT
