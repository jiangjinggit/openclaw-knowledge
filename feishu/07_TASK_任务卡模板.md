# 🧾 TASK 模板（可直接复制）

> 用于给 AI 员工派发任务，确保“目标清晰 + 可验收 + 可追踪”

---

## 一、标准模板

```markdown
### TASK T-YYYYMMDD-<role>-NNN
- status: todo
- from: ceo
- to: build
- created_at: YYYY-MM-DD HH:MM Your/Timezone
- deadline: YYYY-MM-DD HH:MM Your/Timezone
- last_update_at: YYYY-MM-DD HH:MM Your/Timezone
- objective: [一句话目标]
- acceptance:
  1. [可量化标准1]
  2. [可量化标准2]
  3. [可量化标准3]
- required_output: [要回传的交付物]
- related_files: [相关路径]
- notes: [可选备注]
```

---

## 二、可直接用示例（内容任务）

```markdown
### TASK T-20260306-build-001
- status: todo
- from: ceo
- to: build
- created_at: 2026-03-06 10:00 Your/Timezone
- deadline: 2026-03-06 18:00 Your/Timezone
- last_update_at: 2026-03-06 10:00 Your/Timezone
- objective: 完成《OpenClaw 多Agent协作》公众号文章
- acceptance:
  1. 字数≥3000
  2. 至少3个真实案例
  3. 至少2个数据表格
  4. 通过门禁检查（错别字/敏感词/格式）
- required_output: markdown文稿 + 配图说明 + 发布版HTML
- related_files: team/content/wechat/2026-03-06/
- notes: 标题需包含数字锚点
```

---

## 三、填写原则

- objective：一句话，不要写虚词
- acceptance：必须可量化、可验证
- required_output：必须有文件路径或链接
- deadline：必须带时区

---

## 四、常见错误

- ❌ “写一篇好文章”
- ✅ “3000字+3案例+2表格+门禁通过”

- ❌ “尽快完成”
- ✅ “今天18:00前完成”
