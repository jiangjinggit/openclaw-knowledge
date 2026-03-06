# 任务卡模板

## 使用说明

当 CEO 或 PM 派发任务时，使用此模板创建任务卡。

---

## 标准任务卡模板

```markdown
### TASK T-YYYYMMDD-<role>-NNN
- status: todo
- from: [派发者：ceo/pm]
- to: [接收者：build/research/growth/ops]
- created_at: YYYY-MM-DD HH:MM Asia/Shanghai
- deadline: YYYY-MM-DD HH:MM Asia/Shanghai
- last_update_at: YYYY-MM-DD HH:MM Asia/Shanghai
- objective: [一句话目标]
- acceptance:
  1. [验收标准1 - 可量化、可验证]
  2. [验收标准2 - 可量化、可验证]
  3. [验收标准3 - 可量化、可验证]
- required_output: [需要回传的交付物]
- related_files: [相关文件路径]
- notes: [可选备注]
```

---

## 示例1：内容创作任务

```markdown
### TASK T-20260306-build-001
- status: todo
- from: ceo
- to: build
- created_at: 2026-03-06 10:00 Asia/Shanghai
- deadline: 2026-03-06 18:00 Asia/Shanghai
- last_update_at: 2026-03-06 10:00 Asia/Shanghai
- objective: 完成"OpenClaw多Agent协作"文章
- acceptance:
  1. 字数3000字以上
  2. 包含3个真实案例
  3. 有配图（至少3张）
  4. 通过门禁检查（无错别字、无敏感词）
- required_output: 文章Markdown文件 + 配图文件
- related_files: team/content/wechat/2026-03-06/
- notes: 重点突出效率提升数据
```

---

## 示例2：产品开发任务

```markdown
### TASK T-20260306-build-002
- status: todo
- from: pm
- to: build
- created_at: 2026-03-06 14:00 Asia/Shanghai
- deadline: 2026-03-07 18:00 Asia/Shanghai
- last_update_at: 2026-03-06 14:00 Asia/Shanghai
- objective: 完成用户登录功能开发
- acceptance:
  1. 代码通过所有测试（100% coverage）
  2. 有技术文档
  3. 通过代码review
  4. 无安全漏洞
- required_output: PR链接 + 测试日志 + 技术文档
- related_files: src/auth/
- notes: 注意密码加密和session管理
```

---

## 示例3：数据分析任务

```markdown
### TASK T-20260306-research-001
- status: todo
- from: ceo
- to: research
- created_at: 2026-03-06 09:00 Asia/Shanghai
- deadline: 2026-03-06 12:00 Asia/Shanghai
- last_update_at: 2026-03-06 09:00 Asia/Shanghai
- objective: 分析上周内容数据，找出最佳发布时间
- acceptance:
  1. 分析至少10篇文章的数据
  2. 有数据可视化图表
  3. 有明确的结论和建议
  4. 有下一步行动计划
- required_output: 数据分析报告 + 图表 + 建议清单
- related_files: team/data/weekly_report/
- notes: 重点关注阅读量和互动率
```

---

## 必填字段说明

| 字段 | 说明 | 示例 |
|------|------|------|
| task_id | 格式：T-YYYYMMDD-<role>-NNN | T-20260306-build-001 |
| status | todo/doing/blocked/done | todo |
| from | 派发者 | ceo/pm |
| to | 接收者 | build/research/growth/ops |
| created_at | 创建时间 | 2026-03-06 10:00 Asia/Shanghai |
| deadline | 截止时间 | 2026-03-06 18:00 Asia/Shanghai |
| last_update_at | 最后更新时间 | 2026-03-06 10:00 Asia/Shanghai |
| objective | 一句话目标 | 完成X功能开发 |
| acceptance | 验收标准（可量化） | 1. 代码通过测试 2. 有文档 |
| required_output | 需要回传的交付物 | PR链接 + 测试日志 |

---

## 状态说明

| 状态 | 说明 | 何时使用 |
|------|------|----------|
| todo | 待开始 | 任务刚创建 |
| doing | 进行中 | 开始执行任务 |
| blocked | 受阻 | 遇到阻塞，无法继续 |
| done | 已完成 | 任务完成并验收通过 |

---

## 验收标准编写原则

### ✅ 好的验收标准

1. **可量化**
   - ✅ "字数3000字以上"
   - ✅ "测试覆盖率100%"
   - ✅ "响应时间<100ms"

2. **可验证**
   - ✅ "代码通过所有测试"
   - ✅ "有技术文档"
   - ✅ "通过门禁检查"

3. **具体明确**
   - ✅ "包含3个真实案例"
   - ✅ "有配图（至少3张）"
   - ✅ "无错别字、无敏感词"

### ❌ 不好的验收标准

1. **不可量化**
   - ❌ "写一篇好文章"
   - ❌ "代码质量高"
   - ❌ "用户体验好"

2. **不可验证**
   - ❌ "尽力完成"
   - ❌ "差不多就行"
   - ❌ "看起来不错"

3. **模糊不清**
   - ❌ "写一些内容"
   - ❌ "做一些优化"
   - ❌ "改进一下"

---

## 快速创建任务卡

### 方法1：复制模板
1. 复制上面的标准模板
2. 填写必填字段
3. 保存到 `team/agents/<role>/TASK_INBOX.md`

### 方法2：使用脚本（如果有）
```bash
# 创建任务卡
bash team/agents/create_task.sh \
  --to build \
  --objective "完成X功能" \
  --deadline "2026-03-06 18:00"
```

---

## 常见问题

### Q: task_id 怎么生成？
A: 格式：`T-YYYYMMDD-<role>-NNN`
- YYYYMMDD：日期
- role：接收者角色
- NNN：当天的序号（001, 002, 003...）

### Q: deadline 怎么设置？
A: 
- 紧急任务：当天18:00
- 普通任务：1-3天
- 复杂任务：3-7天

### Q: 验收标准写几条？
A: 
- 最少2条
- 最多5条
- 推荐3条

### Q: 如果任务被阻塞怎么办？
A: 
1. 更新 status 为 blocked
2. 在 notes 里写明阻塞原因
3. 通知 CEO 或 PM
4. 等待解决后继续

---

## 相关文档

- [结果卡模板](./RESULT_TEMPLATE.md)
- [门禁检查清单](./CHECKLIST.md)
- [AGENTS.md - 协作规则](../AGENTS.md)
