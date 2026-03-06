# 安装与配置教程

## 前提条件

1. **一台电脑**（Mac、Windows、Linux 都可以）
2. **安装 Node.js**（版本 >= 18）
   - 下载地址：https://nodejs.org/
   - 安装后验证：`node --version`

## Step 1: 安装 OpenClaw（5分钟）

### 方法1：使用 npm（推荐）

```bash
# 安装 OpenClaw
npm install -g openclaw

# 验证安装
openclaw --version

# 启动 Gateway
openclaw gateway start
```

看到以下提示说明安装成功：
```
✅ Gateway started at ws://127.0.0.1:18789
```

### 方法2：使用源码安装

```bash
# 克隆仓库
git clone https://github.com/openclaw/openclaw.git
cd openclaw

# 安装依赖
npm install

# 启动
npm start
```

## Step 2: 创建工作区（2分钟）

```bash
# 创建工作区目录
mkdir -p ~/.openclaw/workspace-my-ai-company
cd ~/.openclaw/workspace-my-ai-company

# 复制配置模板
# 把本目录的所有文件复制到工作区
cp -r /path/to/openclaw_config_template/* .
```

**目录结构：**
```
~/.openclaw/workspace-my-ai-company/
├── SOUL.md              # AI 价值观
├── IDENTITY.md          # AI 身份
├── AGENTS.md            # 协作规则
├── USER.md              # 用户画像
├── MEMORY.md            # 长期记忆
└── team/
    └── agents/
        ├── ceo/         # CEO 配置
        ├── pm/          # PM 配置
        ├── build/       # Build 配置
        ├── research/    # Research 配置
        ├── growth/      # Growth 配置
        └── ops/         # Ops 配置
```

## Step 3: 配置 AI 模型（5分钟）

OpenClaw 支持多种 AI 模型，你需要配置至少一个。

### 配置 Claude（推荐）

1. 获取 API Key：https://console.anthropic.com/
2. 配置环境变量：

```bash
# 编辑配置文件
nano ~/.openclaw/config.json

# 添加以下内容
{
  "models": {
    "default": "claude-3-5-sonnet-20241022",
    "providers": {
      "anthropic": {
        "apiKey": "your-api-key-here"
      }
    }
  }
}
```

### 配置 OpenAI（可选）

```json
{
  "models": {
    "default": "gpt-4",
    "providers": {
      "openai": {
        "apiKey": "your-api-key-here"
      }
    }
  }
}
```

## Step 4: 修改配置文件（10分钟）

### 4.1 修改 SOUL.md

```bash
nano SOUL.md
```

**必改项：**
- `核心使命`：改成你的使命
- `决策框架`：根据你的偏好调整

**可选项：**
- `行为准则`：根据你的风格调整
- `语气与风格`：根据你的喜好调整

### 4.2 修改 IDENTITY.md

```bash
nano IDENTITY.md
```

**必改项：**
- `Name`：给你的 AI 起个名字
- `Role`：定义 AI 的角色
- `Vibe`：选择性格类型

**可选项：**
- `说话风格`：根据你的喜好调整

### 4.3 修改 USER.md

```bash
nano USER.md
```

**必改项：**
- `Name`：你的名字
- `Timezone`：你的时区
- `Identity`：你的身份
- `核心路线`：你的战略
- `重点业务方向`：你的业务

**可选项：**
- `工作时间`：你的工作时间
- `个人偏好`：你的喜好

### 4.4 修改 AGENTS.md（可选）

```bash
nano AGENTS.md
```

如果你不需要 6 个 AI 员工，可以删除不需要的角色。

**最小配置：**
- CEO（总指挥）
- Build（执行者）

**完整配置：**
- CEO + PM + Build + Research + Growth + Ops

## Step 5: 配置消息平台（可选）

OpenClaw 支持 20+ 消息平台，推荐使用 Telegram。

### 配置 Telegram

1. 创建 Telegram Bot：
   - 找 @BotFather
   - 发送 `/newbot`
   - 按提示创建 Bot
   - 获取 Bot Token

2. 配置 OpenClaw：

```bash
nano ~/.openclaw/config.json
```

添加：
```json
{
  "channels": {
    "telegram": {
      "token": "your-bot-token-here",
      "enabled": true
    }
  }
}
```

3. 启动 Telegram 连接：

```bash
openclaw channel telegram start
```

4. 在 Telegram 中发送消息给你的 Bot，测试是否正常。

## Step 6: 运行第一个任务（5分钟）

### 方法1：通过 Telegram

在 Telegram 中给你的 Bot 发送消息：
```
帮我写一篇关于 AI 的文章
```

### 方法2：通过命令行

```bash
openclaw chat "帮我写一篇关于 AI 的文章"
```

### 方法3：通过 Web 界面（开发中）

```bash
openclaw web start
```

然后打开浏览器访问：http://localhost:3000

## Step 7: 查看结果

所有结果都会保存在工作区目录下：

```bash
# 查看工作区
ls -la ~/.openclaw/workspace-my-ai-company/

# 查看任务记录
cat team/agents/ceo/TASK_INBOX.md

# 查看结果记录
cat team/agents/ceo/RESULT_OUTBOX.md
```

## 常见问题

### Q: 安装失败怎么办？

**错误1：npm install 失败**
```bash
# 清理缓存
npm cache clean --force

# 重新安装
npm install -g openclaw
```

**错误2：权限不足**
```bash
# 使用 sudo（Mac/Linux）
sudo npm install -g openclaw

# 或者使用 nvm（推荐）
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
nvm install 18
npm install -g openclaw
```

### Q: Gateway 启动失败怎么办？

```bash
# 检查端口是否被占用
lsof -i :18789

# 如果被占用，杀掉进程
kill -9 <PID>

# 重新启动
openclaw gateway start
```

### Q: AI 不回复怎么办？

1. 检查 API Key 是否正确
2. 检查网络连接
3. 查看日志：`openclaw logs`
4. 检查配置文件：`cat ~/.openclaw/config.json`

### Q: 如何更新 OpenClaw？

```bash
# 更新到最新版本
npm update -g openclaw

# 重启 Gateway
openclaw gateway restart
```

### Q: 如何卸载 OpenClaw？

```bash
# 卸载
npm uninstall -g openclaw

# 删除配置文件（可选）
rm -rf ~/.openclaw
```

## 进阶配置

### 配置定时任务

编辑 `~/.openclaw/cron/jobs.json`：

```json
{
  "jobs": [
    {
      "id": "daily-report",
      "schedule": "0 8 * * *",
      "agent": "my_ceo",
      "task": "生成今日任务清单"
    },
    {
      "id": "weekly-review",
      "schedule": "0 18 * * 5",
      "agent": "my_ceo",
      "task": "生成本周复盘报告"
    }
  ]
}
```

### 配置多个工作区

```bash
# 创建多个工作区
mkdir -p ~/.openclaw/workspace-project-a
mkdir -p ~/.openclaw/workspace-project-b

# 切换工作区
openclaw workspace use workspace-project-a
```

### 配置团队协作

```bash
# 创建团队
openclaw team create my-team

# 邀请成员
openclaw team invite user@example.com

# 共享工作区
openclaw workspace share my-team
```

## 获取帮助

- 官方文档：https://docs.openclaw.ai
- GitHub：https://github.com/openclaw/openclaw
- Discord 社区：https://discord.com/invite/clawd
- 中文社区：[加入方式见 README.md]

## 下一步

1. 阅读 [使用指南](./USAGE.md)
2. 查看 [最佳实践](./BEST_PRACTICES.md)
3. 加入社区，分享你的经验
