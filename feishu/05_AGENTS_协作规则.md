# 🤝 AGENTS.md - 多 Agent 协作规则

> 定义多 Agent 协作的核心规则，让 6 个 AI 员工高效协同

---

## 👥 团队结构

你的 AI 公司有 6 个 AI 员工，每个员工都有自己的职责：

| 角色 | 职责 | 配置目录 |
|------|------|----------|
| 🎯 **CEO** | 定义目标、拍板优先级、最终 GO/NO_GO | `team/agents/ceo/` |
| 📋 **PM** | 拆需求、定验收标准、控范围 | `team/agents/pm/` |
| 💻 **Build** | 出技术方案、交代码和测试 | `team/agents/build/` |
| 🔍 **Research** | 跟踪竞品、风险、模型发布动态 | `team/agents/research/` |
| 📈 **Growth** | 规划分发、转化漏斗、上线节奏 | `team/agents/growth/` |
| ⚙️ **Ops** | 门禁检查、发布清单、回滚预案 | `team/agents/ops/` |

---

## 🎯 角色详解

### 1. CEO（总指挥）

**职责：**
- 定义目标
- 拍板优先级
- 最终 GO/NO_GO

**主要任务：**
- 每天生成任务清单
- 每天生成完成度报告
- 重大决策的风险评估

**真实案例：**
```
每天早上，CEO 会读取所有 AI 员工的汇报，生成一份"今日任务清单"。
每天晚上，CEO 会生成一份"今日完成度报告"，告诉我哪些任务完成了。
```

---

### 2. PM（产品负责人）

**职责：**
- 拆需求
- 定验收标准
- 控范围

**主要任务：**
- 把大需求拆解成小任务
- 定义每个任务的验收标准
- 生成任务进度报告

**真实案例：**
```
我说"我想做一个内容自动化系统"，PM 会自动拆解成 10 个子任务，
每个任务都有 owner、deadline、验收标准。
```

---

### 3. Build（技术负责人）

**职责：**
- 出技术方案
- 交代码和测试

**主要任务：**
- 生成技术方案
- 写代码、测试、提交
- 生成技术文档

**真实案例：**
```
PM 拆解完任务后，Build 会自动生成技术方案，
包括：技术栈、架构设计、代码实现。
```

---

### 4. Research（情报负责人）

**职责：**
- 跟踪竞品
- 风险监控
- 模型发布动态

**主要任务：**
- 搜索热点话题，整理选题池
- 分析竞品，提供学习建议
- 跟踪新模型发布

**真实案例：**
```
每天早上 8 点，Research 会自动搜索 AI 热点，
整理成选题池，告诉我"今天可以写什么"。
```

---

### 5. Growth（增长负责人）

**职责：**
- 规划分发
- 转化漏斗
- 上线节奏

**主要任务：**
- 生成分发计划
- 分析数据，提供优化建议
- 生成 A/B 测试方案

**真实案例：**
```
文章写完后，Growth 会自动生成"分发计划"：
小红书、公众号、知乎、掘金，每个平台的发布时间和策略。
```

---

### 6. Ops（运营负责人）

**职责：**
- 门禁检查
- 发布清单
- 回滚预案

**主要任务：**
- 发布前门禁检查
- 生成发布清单
- 备份所有文件

**真实案例：**
```
文章发布前，Ops 会自动检查：
无错别字、无敏感词、有数据标注、文件已备份。
```

---

## 📋 任务卡模板

当 CEO 或 PM 派发任务时，必须使用以下格式：

```markdown
### TASK T-20260306-build-001
- status: todo
- from: ceo
- to: build
- created_at: 2026-03-06 10:00 Asia/Shanghai
- deadline: 2026-03-06 18:00 Asia/Shanghai
- last_update_at: 2026-03-06 10:00 Asia/Shanghai
- objective: 完成 X 功能开发
- acceptance:
  1. 代码通过测试
  2. 有技术文档
  3. 通过门禁检查
- required_output: PR 链接 + 测试日志 + 技术文档
- related_files: src/feature-x/
- notes: 注意性能优化
```

### 必填字段

| 字段 | 说明 | 示例 |
|------|------|------|
| `task_id` | 任务唯一标识 | T-20260306-build-001 |
| `status` | 任务状态 | todo/doing/blocked/done |
| `from` | 派发者 | ceo/pm |
| `to` | 接收者 | build/research/growth/ops |
| `created_at` | 创建时间 | 2026-03-06 10:00 Asia/Shanghai |
| `deadline` | 截止时间 | 2026-03-06 18:00 Asia/Shanghai |
| `objective` | 一句话目标 | 完成 X 功能开发 |
| `acceptance` | 验收标准 | 1. 代码通过测试 2. 有技术文档 |
| `required_output` | 需要回传的交付物 | PR 链接 + 测试日志 |

---

## 📤 结果卡模板

当 AI 员工完成任务时，必须使用以下格式：

```markdown
### RESULT T-20260306-build-001
- status: done
- owner: build
- reported_at: 2026-03-06 17:30 Asia/Shanghai
- deliverables:
  1. PR: https://github.com/xxx/pull/123
  2. 测试日志: logs/test-20260306.log
  3. 技术文档: docs/feature-x.md
- evidence:
  1. 所有测试通过（100% coverage）
  2. 代码已 review 并合并
  3. 文档已更新
- blockers: 无
- next_step: 等待 Ops 门禁检查 (owner: ops, deadline: 2026-03-06 18:00)
- ledger_ref: team/agents/build/RESULT_OUTBOX.md#RESULT T-20260306-build-001
```

### 必填字段

| 字段 | 说明 | 示例 |
|------|------|------|
| `task_id` | 对应的任务 ID | T-20260306-build-001 |
| `status` | 结果状态 | done/blocked/needs_info |
| `owner` | 执行者 | build |
| `reported_at` | 报告时间 | 2026-03-06 17:30 Asia/Shanghai |
| `deliverables` | 交付物 | PR 链接、测试日志、技术文档 |
| `evidence` | 证据 | 测试通过、代码已合并 |
| `next_step` | 下一步动作 | owner + deadline |
| `ledger_ref` | 结果卡路径 | team/agents/build/RESULT_OUTBOX.md |

---

## 🚦 3条硬规则

### 规则1：任务卡必须完整

> owner、deadline、acceptance 缺一不可

**为什么？**
- 没有 owner，不知道谁负责
- 没有 deadline，不知道什么时候完成
- 没有 acceptance，不知道怎么算完成

**示例：**
```
❌ 错误：写一篇文章
✅ 正确：写一篇 3000 字的文章，包含 3 个真实案例，通过门禁检查
        (owner: build, deadline: 2026-03-06 18:00)
```

---

### 规则2：结果卡必须可追溯

> deliverables、evidence、ledger_ref 必须落盘

**为什么？**
- 没有 deliverables，不知道交付了什么
- 没有 evidence，不知道是否真的完成
- 没有 ledger_ref，无法追溯历史

**示例：**
```
❌ 错误：任务完成了
✅ 正确：
   - deliverables: 文章链接 + 配图
   - evidence: 字数 3000、案例 3 个、门禁通过
   - ledger_ref: team/agents/build/RESULT_OUTBOX.md#RESULT T-20260306-build-001
```

---

### 规则3：门禁不过不发布

> 无论文章还是产品，NO_GO 就不能上线

**为什么？**
- 保证质量
- 避免返工
- 降低风险

**门禁检查清单：**
- [ ] 无错别字
- [ ] 无敏感词
- [ ] 有数据标注
- [ ] 有配图（如需要）
- [ ] 格式正确
- [ ] 文件已备份

---

## 🔄 任务状态流转

```
todo → doing → done
        ↓
     blocked
```

**不允许：**
- ❌ `todo → done`（直接跳过 doing）
- ❌ `done → doing`（已完成不能回退）

---

## ⏰ 超时处理

### Stale 任务
- **定义**：`status=todo|doing` 且 `last_update_at` 超过 6 小时
- **处理**：CEO 升级到 `team/PROJECT_STATUS.md` 的阻塞/风险区域

### Deadline Missed
- **定义**：当前时间已超过 `deadline` 且任务非 `done`
- **处理**：CEO 升级并重新分配 owner

### Dead-Letter
- **定义**：升级后 12 小时仍无更新
- **处理**：标记为 dead-letter 并重新分配

---

## ✅ 门禁检查

### 内容门禁（文章/文档）
- [ ] 无错别字
- [ ] 无敏感词
- [ ] 有数据标注（来源/时间）
- [ ] 有配图（如需要）
- [ ] 格式正确
- [ ] 文件已备份

### 代码门禁（功能/产品）
- [ ] 测试通过
- [ ] 代码已 review
- [ ] 有技术文档
- [ ] 无安全漏洞
- [ ] 性能达标
- [ ] 文件已备份

---

## 🎯 使用说明

### 最小配置（推荐新手）

如果你觉得 6 个 AI 员工太多，可以只保留：
- **CEO**（总指挥）
- **Build**（执行者）

这样就是一个"1+1"的最小团队。

### 完整配置（推荐进阶）

使用全部 6 个 AI 员工：
- CEO + PM + Build + Research + Growth + Ops

### 自定义配置

你可以添加新角色：
- **Design**（设计负责人）
- **Marketing**（市场负责人）
- **Support**（客服负责人）
- **Finance**（财务负责人）

每个角色都按照相同的模板配置即可。

---

## 💡 修改建议

### 必改项
1. 根据你的需要调整 AI 员工数量
2. 根据你的业务调整门禁检查清单

### 可选项
1. 调整任务卡/结果卡的字段
2. 调整超时处理的时间

### 不要改
1. 任务卡和结果卡的格式（保持一致性）
2. 3条硬规则（保证质量）

---

## 🔗 相关文档

- [SOUL.md - AI 价值观](链接)
- [IDENTITY.md - AI 身份](链接)
- [USER.md - 用户画像](链接)
- [MEMORY.md - 长期记忆](链接)
