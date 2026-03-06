# OpenClaw 配置模板使用指南

## 快速开始

### 1. 下载配置模板
将本目录的所有文件复制到你的 OpenClaw 工作区：
```bash
cp -r openclaw_config_template/* ~/.openclaw/workspace-my-ai-company/
```

### 2. 修改配置文件（必做）
按顺序修改以下文件：

#### 2.1 USER.md（最重要）
```bash
nano USER.md
```
- 填写你的名字、时区、身份
- 描述你的核心战略
- 列出你的重点业务

#### 2.2 IDENTITY.md
```bash
nano IDENTITY.md
```
- 给 AI 起个名字
- 选择性格类型（务实/温和/幽默）
- 定义说话风格

#### 2.3 SOUL.md（可选）
```bash
nano SOUL.md
```
- 根据需要调整核心使命
- 根据需要调整决策框架

#### 2.4 AGENTS.md（可选）
```bash
nano AGENTS.md
```
- 如果不需要 6 个 AI 员工，可以删除不需要的角色
- 最小配置：CEO + Build

### 3. 测试配置
```bash
openclaw chat "你好，介绍一下你自己"
```

如果 AI 按照你设置的风格回复，说明配置成功。

## 配置文件说明

### SOUL.md - AI 价值观
**作用：** 定义 AI 的"内在信念"，是 AI 在没有明确指令时的判断依据。

**核心内容：**
- 核心使命
- 决策框架（ICRS：Impact、Cost、Risk、Speed）
- 3个核心原则（聪明大于听话、效率大于完美、学习大于遗忘）
- 决策权限（自主决定/征询意见/明确授权）

**修改建议：**
- 保留核心原则（已验证有效）
- 根据你的业务调整"核心使命"
- 根据你的风险偏好调整"决策权限"

### IDENTITY.md - AI 身份
**作用：** 定义 AI 的"外在表达"，是 AI 的说话方式和性格。

**核心内容：**
- 名字与角色
- 性格类型（务实/温和/幽默）
- 说话风格（结论先行、简洁直接、有温度）
- 禁止行为（客服腔、过度解释）

**修改建议：**
- 给 AI 起个你喜欢的名字
- 选择一个性格类型
- 根据你的喜好调整说话风格

### USER.md - 用户画像
**作用：** 告诉 AI "你是谁、你的偏好、你的上下文"。

**核心内容：**
- 基本信息（名字、时区、身份）
- 核心战略
- 关注的结果
- 决策偏好
- 重点业务方向

**修改建议：**
- 越具体越好，AI 才能更好地理解你
- 可以随时更新

### AGENTS.md - 协作规则
**作用：** 定义多 Agent 协作的核心规则。

**核心内容：**
- 6 个 AI 员工的职责
- 任务卡模板
- 结果卡模板
- 3条硬规则

**修改建议：**
- 根据需要调整 AI 员工数量
- 可以删除不需要的角色
- 可以添加新角色

### MEMORY.md - 长期记忆
**作用：** 跨会话持久化的记忆，记录经验教训。

**核心内容：**
- 错误记录（ERROR）
- 学习记录（LEARN）
- 决策记录（DECISION）

**修改建议：**
- 删除示例记录
- 开始记录你的第一条记忆

## 最佳实践

### 1. 从简单开始
不要一开始就配置所有 6 个 AI 员工，建议：
- 第1周：只用 CEO（熟悉基本操作）
- 第2周：加入 Build（体验协作）
- 第3周：根据需要加入其他角色

### 2. 逐步优化
不要一开始就写很长的配置文件，建议：
- 先用默认配置
- 遇到问题时再调整
- 每次只改 1-2 个地方

### 3. 记录经验
每次犯错或学到新东西，立即记录到 MEMORY.md：
```markdown
### 2026-03-06 ERROR 任务没有验收标准
- **问题**：任务完成后不满意
- **根因**：没有明确验收标准
- **修正**：增加验收标准
- **预防**：以后每个任务都要有验收标准
```

### 4. 定期复盘
每周回顾一次：
- 哪些配置有效？
- 哪些配置无效？
- 需要调整什么？

### 5. 备份配置
定期备份你的配置文件：
```bash
# 备份到 Git
cd ~/.openclaw/workspace-my-ai-company
git init
git add .
git commit -m "backup config"

# 或者备份到云盘
cp -r ~/.openclaw/workspace-my-ai-company ~/Dropbox/openclaw-backup
```

## 常见问题

### Q: 配置文件太复杂，看不懂怎么办？
A: 只需要修改 3 个文件：
1. USER.md（填写你的信息）
2. IDENTITY.md（给 AI 起个名字）
3. AGENTS.md（选择需要的 AI 员工）

其他文件可以先用默认配置。

### Q: 我不需要 6 个 AI 员工，怎么办？
A: 删除不需要的角色目录：
```bash
# 只保留 CEO 和 Build
rm -rf team/agents/pm
rm -rf team/agents/research
rm -rf team/agents/growth
rm -rf team/agents/ops
```

然后修改 AGENTS.md，删除对应的角色说明。

### Q: 可以自定义 AI 员工吗？
A: 可以。复制一个现有角色的目录，然后修改配置：
```bash
# 创建新角色 Design
cp -r team/agents/build team/agents/design

# 修改配置
nano team/agents/design/IDENTITY.md
```

### Q: 配置文件可以用中文吗？
A: 可以。所有配置文件都支持中文。

### Q: 配置错误怎么办？
A: 
1. 检查语法（Markdown 格式）
2. 查看日志：`openclaw logs`
3. 恢复默认配置：重新复制模板

### Q: 如何分享我的配置？
A: 
1. 删除个人信息（USER.md）
2. 打包配置文件：`tar -czf my-config.tar.gz *`
3. 分享到社区

## 进阶技巧

### 1. 使用变量
在配置文件中使用变量：
```markdown
- **Timezone:** {{USER_TIMEZONE}}
- **Name:** {{USER_NAME}}
```

然后在 `~/.openclaw/config.json` 中定义：
```json
{
  "variables": {
    "USER_TIMEZONE": "Your/Timezone",
    "USER_NAME": "张三"
  }
}
```

### 2. 使用模板
创建多个配置模板，快速切换：
```bash
# 创建模板
cp -r ~/.openclaw/workspace-my-ai-company ~/.openclaw/templates/default

# 使用模板
openclaw workspace create new-project --template default
```

### 3. 使用脚本
自动化配置过程：
```bash
#!/bin/bash
# setup.sh

# 复制模板
cp -r openclaw_config_template/* ~/.openclaw/workspace-my-ai-company/

# 替换变量
sed -i "s/\[你的名字\]/$USER_NAME/g" ~/.openclaw/workspace-my-ai-company/USER.md
sed -i "s/\[你的时区\]/$USER_TIMEZONE/g" ~/.openclaw/workspace-my-ai-company/USER.md

echo "配置完成！"
```

## 获取帮助

- 查看完整文档：[INSTALL.md](./INSTALL.md)
- 加入社区：[README.md](./README.md)
- 提交问题：https://github.com/openclaw/openclaw/issues

## 下一步

1. 完成配置后，运行第一个任务
2. 查看 [最佳实践](./BEST_PRACTICES.md)
3. 分享你的经验到社区
