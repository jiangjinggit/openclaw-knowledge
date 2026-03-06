# OpenClaw 多 Agent 协作配置模板

这是一套完整的 OpenClaw 配置模板，帮助你快速搭建自己的 AI 公司。

## 📦 包含内容

1. **核心配置文件**（5个）
   - `SOUL.md` - AI 价值观与决策框架
   - `IDENTITY.md` - AI 身份与风格
   - `AGENTS.md` - 多 Agent 协作规则
   - `USER.md` - 用户画像与偏好
   - `MEMORY.md` - 长期记忆模板

2. **6个 AI 员工配置**
   - CEO（总指挥）
   - PM（产品负责人）
   - Build（技术负责人）
   - Research（情报负责人）
   - Growth（增长负责人）
   - Ops（运营负责人）

3. **协作协议**
   - 任务卡模板
   - 结果卡模板
   - 门禁检查清单

4. **安装与配置教程**

## 🚀 快速开始

### Step 1: 安装 OpenClaw（5分钟）

```bash
# 安装 OpenClaw
npm install -g openclaw

# 启动 Gateway
openclaw gateway start
```

### Step 2: 创建工作区（2分钟）

```bash
# 创建工作区目录
mkdir -p ~/.openclaw/workspace-my-ai-company
cd ~/.openclaw/workspace-my-ai-company

# 复制配置模板（从本目录复制所有文件）
cp -r /path/to/this/template/* .
```

### Step 3: 修改配置（10分钟）

1. **修改 `SOUL.md`**
   - 定义你的核心使命
   - 设置决策框架
   - 定义行为准则

2. **修改 `IDENTITY.md`**
   - 给 AI 起个名字
   - 定义性格与风格
   - 设置说话方式

3. **修改 `USER.md`**
   - 填写你的信息
   - 设置时区
   - 定义业务方向

4. **修改 `AGENTS.md`**
   - 根据需要调整 6 个 AI 员工的职责
   - 可以删除不需要的角色
   - 可以添加新角色

### Step 4: 运行第一个任务（5分钟）

```bash
# 通过 Telegram 发送消息
# 或使用命令行
openclaw chat "帮我写一篇关于 AI 的文章"
```

## 📝 配置说明

### SOUL.md - 价值观

这是 AI 的"内在信念"，定义了：
- 核心使命
- 决策框架
- 行为准则
- 输出标准

**关键原则：**
- 聪明大于听话
- 效率大于完美
- 学习大于遗忘

### IDENTITY.md - 身份

这是 AI 的"外在表达"，定义了：
- 名字与角色
- 性格与风格
- 说话方式

**关键设置：**
- 结论先行，背景后置
- 用"我"而不是"本系统"
- 完成任务后一句话收尾

### AGENTS.md - 协作规则

这是多 Agent 协作的核心，定义了：
- 每个 AI 员工的职责
- 任务卡格式
- 结果卡格式
- 门禁规则

**3条硬规则：**
1. 任务卡必须完整（owner、deadline、acceptance）
2. 结果卡必须可追溯（deliverables、evidence、ledger_ref）
3. 门禁不过不发布

### USER.md - 用户画像

告诉 AI "你是谁、你的偏好、你的上下文"：
- 身份与时区
- 核心路线
- 决策偏好
- 业务方向

### MEMORY.md - 长期记忆

跨会话持久化的记忆，记录：
- 每次犯错
- 每次学习
- 每次决策

## 🎯 6个 AI 员工

### 1. CEO（总指挥）
- **职责**：定义目标、拍板优先级、最终 GO/NO_GO
- **配置文件**：`team/agents/ceo/`

### 2. PM（产品负责人）
- **职责**：拆需求、定验收标准、控范围
- **配置文件**：`team/agents/pm/`

### 3. Build（技术负责人）
- **职责**：出技术方案、交代码和测试
- **配置文件**：`team/agents/build/`

### 4. Research（情报负责人）
- **职责**：跟踪竞品、风险、模型发布动态
- **配置文件**：`team/agents/research/`

### 5. Growth（增长负责人）
- **职责**：规划分发、转化漏斗、上线节奏
- **配置文件**：`team/agents/growth/`

### 6. Ops（运营负责人）
- **职责**：门禁检查、发布清单、回滚预案
- **配置文件**：`team/agents/ops/`

## ⚠️ 避坑指南

### 错误1：过度依赖 AI
- ❌ 把所有事情都交给 AI
- ✅ AI 负责 80%，你负责 20% 的检查和决策

### 错误2：配置文件太复杂
- ❌ 一开始就写很长的配置文件
- ✅ 从简单开始，逐步优化

### 错误3：没有验收标准
- ❌ 任务没有明确的验收标准
- ✅ 每个任务都要有可量化、可验证的标准

## 📚 进阶使用

### 定时任务

在 `~/.openclaw/cron/jobs.json` 中配置定时任务：

```json
{
  "jobs": [
    {
      "id": "daily-report",
      "schedule": "0 8 * * *",
      "agent": "your_ceo_agent",
      "task": "生成今日任务清单"
    }
  ]
}
```

### 多平台接入

OpenClaw 支持 20+ 消息平台：
- Telegram
- 飞书
- Slack
- Discord
- 微信
- ...

## 🆘 常见问题

### Q: 我不会编程，能用吗？
A: 能。只需要修改配置文件（都是纯文本），不需要写代码。

### Q: 需要多少钱？
A: OpenClaw 本身免费。只需要支付 AI 模型的 API 费用（Claude、GPT 等）。

### Q: 数据安全吗？
A: 完全安全。所有数据都在你的电脑上，不会上传到任何服务器。

### Q: 可以自定义 AI 员工吗？
A: 可以。你可以删除不需要的角色，也可以添加新角色。

## 📞 获取帮助

- 加入 OpenClaw 中文社区（1000+ 开发者）
- 每周分享最新的 AI Agent 实战案例
- 免费答疑，帮你解决配置问题

## 📄 许可证

本配置模板基于 MIT 许可证开源，你可以自由使用、修改、分发。

---

**关注「Your AI Team」，一起用 AI 成为超级个体**
