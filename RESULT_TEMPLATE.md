# 结果卡模板

## 使用说明

当 AI 员工完成任务时，使用此模板创建结果卡。

---

## 标准结果卡模板

```markdown
### RESULT T-YYYYMMDD-<role>-NNN
- status: done
- owner: [执行者：build/research/growth/ops]
- reported_at: YYYY-MM-DD HH:MM Your/Timezone
- deliverables:
  1. [交付物1：文件路径/链接]
  2. [交付物2：文件路径/链接]
  3. [交付物3：文件路径/链接]
- evidence:
  1. [证据1：可验证的证据]
  2. [证据2：可验证的证据]
  3. [证据3：可验证的证据]
- blockers: [阻塞问题，如果有]
- next_step: [下一步动作] (owner: [谁], deadline: [时间])
- ledger_ref: team/agents/<role>/RESULT_OUTBOX.md#RESULT T-YYYYMMDD-<role>-NNN
```

---

## 示例1：内容创作任务完成

```markdown
### RESULT T-20260306-build-001
- status: done
- owner: build
- reported_at: 2026-03-06 17:30 Your/Timezone
- deliverables:
  1. 文章：team/content/wechat/2026-03-06/article.md
  2. 配图：team/content/wechat/2026-03-06/images/ (3张)
  3. HTML版本：team/content/wechat/2026-03-06/article.html
- evidence:
  1. 字数统计：3245字（超过3000字要求）
  2. 案例数量：3个真实案例（符合要求）
  3. 门禁检查：通过（无错别字、无敏感词）
  4. 配图数量：3张（符合要求）
- blockers: 无
- next_step: 等待 Ops 最终门禁检查 (owner: ops, deadline: 2026-03-06 18:00)
- ledger_ref: team/agents/build/RESULT_OUTBOX.md#RESULT T-20260306-build-001
```

---

## 示例2：产品开发任务完成

```markdown
### RESULT T-20260306-build-002
- status: done
- owner: build
- reported_at: 2026-03-07 17:00 Your/Timezone
- deliverables:
  1. PR：https://github.com/xxx/pull/123
  2. 测试日志：logs/test-20260307.log
  3. 技术文档：docs/auth-login.md
- evidence:
  1. 测试覆盖率：100%（所有测试通过）
  2. 代码review：已通过（reviewer: @senior-dev）
  3. 安全检查：无漏洞（使用 npm audit）
  4. 文档完整性：包含API文档、使用示例、故障排查
- blockers: 无
- next_step: 等待 PM 验收并合并到主分支 (owner: pm, deadline: 2026-03-07 18:00)
- ledger_ref: team/agents/build/RESULT_OUTBOX.md#RESULT T-20260306-build-002
```

---

## 示例3：数据分析任务完成

```markdown
### RESULT T-20260306-research-001
- status: done
- owner: research
- reported_at: 2026-03-06 11:45 Your/Timezone
- deliverables:
  1. 数据分析报告：team/data/weekly_report/2026-03-06-analysis.md
  2. 数据图表：team/data/weekly_report/charts/ (5张)
  3. 建议清单：team/data/weekly_report/recommendations.md
- evidence:
  1. 分析样本：12篇文章（超过10篇要求）
  2. 图表数量：5张（阅读量趋势、互动率对比、发布时间分布、平台对比、内容类型分析）
  3. 结论明确：最佳发布时间为晚上8-10点，周末效果最好
  4. 行动计划：3条具体建议（调整发布时间、优化内容类型、增加互动引导）
- blockers: 无
- next_step: CEO 审阅并决定是否执行建议 (owner: ceo, deadline: 2026-03-06 18:00)
- ledger_ref: team/agents/research/RESULT_OUTBOX.md#RESULT T-20260306-research-001
```

---

## 示例4：任务受阻

```markdown
### RESULT T-20260306-build-003
- status: blocked
- owner: build
- reported_at: 2026-03-06 15:00 Your/Timezone
- deliverables:
  1. 部分代码：src/feature-x/ (50%完成)
- evidence:
  1. 已完成：基础框架搭建
  2. 已完成：单元测试编写
  3. 未完成：API集成（受阻）
- blockers: 
  1. 第三方API文档不完整，无法完成集成
  2. 需要PM联系供应商获取完整文档
  3. 预计延迟1-2天
- next_step: PM 联系供应商获取API文档 (owner: pm, deadline: 2026-03-07 12:00)
- ledger_ref: team/agents/build/RESULT_OUTBOX.md#RESULT T-20260306-build-003
```

---

## 必填字段说明

| 字段 | 说明 | 示例 |
|------|------|------|
| task_id | 对应的任务ID | T-20260306-build-001 |
| status | done/blocked/needs_info | done |
| owner | 执行者 | build |
| reported_at | 报告时间 | 2026-03-06 17:30 Your/Timezone |
| deliverables | 交付物（文件/链接） | 文章、代码、报告 |
| evidence | 证据（可验证） | 字数统计、测试结果 |
| blockers | 阻塞问题 | 无 或 具体问题 |
| next_step | 下一步动作 | owner + deadline |
| ledger_ref | 结果卡路径 | team/agents/build/RESULT_OUTBOX.md |

---

## 状态说明

| 状态 | 说明 | 何时使用 |
|------|------|----------|
| done | 已完成 | 任务完成并通过验收 |
| blocked | 受阻 | 遇到阻塞，无法继续 |
| needs_info | 需要更多信息 | 任务卡信息不完整 |

---

## 交付物编写原则

### ✅ 好的交付物

1. **具体路径**
   - ✅ "文章：team/content/wechat/2026-03-06/article.md"
   - ✅ "PR：https://github.com/xxx/pull/123"
   - ✅ "报告：team/data/weekly_report/2026-03-06-analysis.md"

2. **可访问**
   - ✅ 文件路径存在
   - ✅ 链接可以打开
   - ✅ 权限设置正确

3. **完整性**
   - ✅ 包含所有要求的交付物
   - ✅ 格式正确
   - ✅ 内容完整

### ❌ 不好的交付物

1. **模糊不清**
   - ❌ "文章已完成"
   - ❌ "代码在某个文件夹"
   - ❌ "报告写好了"

2. **无法访问**
   - ❌ 文件路径不存在
   - ❌ 链接打不开
   - ❌ 权限不对

3. **不完整**
   - ❌ 缺少部分交付物
   - ❌ 格式错误
   - ❌ 内容不完整

---

## 证据编写原则

### ✅ 好的证据

1. **可验证**
   - ✅ "字数统计：3245字"
   - ✅ "测试覆盖率：100%"
   - ✅ "门禁检查：通过"

2. **具体数据**
   - ✅ "分析样本：12篇文章"
   - ✅ "图表数量：5张"
   - ✅ "响应时间：85ms"

3. **对应验收标准**
   - ✅ 每个验收标准都有对应证据
   - ✅ 证据能证明标准已达成

### ❌ 不好的证据

1. **不可验证**
   - ❌ "质量很好"
   - ❌ "应该没问题"
   - ❌ "看起来不错"

2. **模糊数据**
   - ❌ "写了很多字"
   - ❌ "测试基本通过"
   - ❌ "差不多完成了"

3. **缺少证据**
   - ❌ 验收标准有3条，证据只有1条
   - ❌ 无法证明标准已达成

---

## 快速创建结果卡

### 方法1：复制模板
1. 复制上面的标准模板
2. 填写必填字段
3. 保存到 `team/agents/<role>/RESULT_OUTBOX.md`

### 方法2：使用脚本（如果有）
```bash
# 创建结果卡
bash team/agents/create_result.sh \
  --task-id T-20260306-build-001 \
  --status done \
  --deliverables "article.md,images/"
```

---

## 常见问题

### Q: 如果任务没完成怎么办？
A: 
1. status 设为 blocked
2. 在 blockers 里写明原因
3. 在 next_step 里写明解决方案
4. 通知 CEO 或 PM

### Q: 如果部分完成怎么办？
A: 
1. 在 deliverables 里列出已完成的部分
2. 在 evidence 里说明完成度（如 50%）
3. 在 blockers 里说明未完成的原因
4. 在 next_step 里说明如何继续

### Q: 如果验收标准不清楚怎么办？
A: 
1. status 设为 needs_info
2. 在 blockers 里说明哪些标准不清楚
3. 在 next_step 里要求 PM 或 CEO 澄清
4. 等待澄清后继续

### Q: ledger_ref 是什么？
A: 
- 结果卡在文件系统中的路径
- 格式：`team/agents/<role>/RESULT_OUTBOX.md#RESULT <task_id>`
- 用于追溯和审计

---

## 相关文档

- [任务卡模板](./TASK_TEMPLATE.md)
- [门禁检查清单](./CHECKLIST.md)
- [AGENTS.md - 协作规则](../AGENTS.md)
