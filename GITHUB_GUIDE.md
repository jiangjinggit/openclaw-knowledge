# GitHub 提交指南

## 方法1：使用 GitHub 网页（最简单）

### Step 1：创建新仓库
1. 打开 https://github.com/new
2. 仓库名称：`openclaw-config-template`
3. 描述：`OpenClaw 多 Agent 协作配置模板`
4. 选择：Public（公开）
5. 不要勾选"Initialize this repository with a README"
6. 点击"Create repository"

### Step 2：上传文件
1. 在新仓库页面，点击"uploading an existing file"
2. 拖拽所有文件到页面（除了 feishu/ 文件夹和 .tar.gz 文件）
3. 或者点击"choose your files"选择文件
4. Commit message：`Initial commit: OpenClaw 配置模板`
5. 点击"Commit changes"

### Step 3：获取仓库链接
复制仓库链接，格式：`https://github.com/你的用户名/openclaw-config-template`

---

## 方法2：使用命令行（推荐）

### Step 1：初始化 Git 仓库

```bash
cd /root/.openclaw/workspace-djy-ceo/team/content/openclaw_config_template

# 初始化 git
git init

# 添加所有文件（排除不需要的）
git add *.md

# 提交
git commit -m "Initial commit: OpenClaw 配置模板

包含：
- 5个核心配置文件（SOUL/IDENTITY/AGENTS/USER/MEMORY）
- 3个模板文件（TASK/RESULT/CHECKLIST）
- 2个教程文件（INSTALL/USAGE）
- README 和回复话术
"
```

### Step 2：创建 GitHub 仓库

**方法A：在 GitHub 网页创建**
1. 打开 https://github.com/new
2. 仓库名称：`openclaw-config-template`
3. 描述：`OpenClaw 多 Agent 协作配置模板`
4. 选择：Public
5. 不要勾选任何初始化选项
6. 点击"Create repository"

**方法B：使用 GitHub CLI（如果已安装）**
```bash
gh repo create openclaw-config-template --public --description "OpenClaw 多 Agent 协作配置模板"
```

### Step 3：推送到 GitHub

```bash
# 添加远程仓库（替换成你的用户名）
git remote add origin https://github.com/你的用户名/openclaw-config-template.git

# 推送到 GitHub
git branch -M main
git push -u origin main
```

---

## 需要的信息

请告诉我：
1. **GitHub 用户名**：你的 GitHub 用户名是什么？
2. **仓库名称**：想叫什么名字？（建议：`openclaw-config-template`）
3. **是否公开**：Public（公开）还是 Private（私有）？

我可以帮你生成完整的命令。

---

## 推荐配置

```
仓库名称：openclaw-config-template
描述：OpenClaw 多 Agent 协作配置模板 - 5分钟搭建你的 AI 公司
可见性：Public（公开）
主题标签：openclaw, ai-agent, multi-agent, automation, productivity
```

---

## 完整命令（待填写）

```bash
# 1. 初始化 git
cd /root/.openclaw/workspace-djy-ceo/team/content/openclaw_config_template
git init
git add *.md
git commit -m "Initial commit: OpenClaw 配置模板"

# 2. 添加远程仓库（替换成你的用户名）
git remote add origin https://github.com/[你的用户名]/openclaw-config-template.git

# 3. 推送到 GitHub
git branch -M main
git push -u origin main
```

---

## 如果遇到问题

### 问题1：需要输入用户名和密码
- 用户名：你的 GitHub 用户名
- 密码：使用 Personal Access Token（不是密码）
- 获取 Token：https://github.com/settings/tokens

### 问题2：推送失败
```bash
# 强制推送（慎用）
git push -u origin main --force
```

### 问题3：文件太大
```bash
# 删除 tar.gz 文件
rm openclaw_config_template.tar.gz
git add -A
git commit -m "Remove tar.gz file"
```

---

告诉我你的 GitHub 用户名，我帮你生成完整的命令！
