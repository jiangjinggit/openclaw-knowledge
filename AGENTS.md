# AGENTS.md - 多 Agent 协作规则

## 团队结构

你的 AI 公司有 6 个 AI 员工，每个员工都有自己的职责：

### 1. CEO（总指挥）
- **职责**：定义目标、拍板优先级、最终 GO/NO_GO
- **配置目录**：`team/agents/ceo/`
- **主要任务**：
  - 每天生成任务清单
  - 每天生成完成度报告
  - 重大决策的风险评估

### 2. PM（产品负责人）
- **职责**：拆需求、定验收标准、控范围
- **配置目录**：`team/agents/pm/`
- **主要任务**：
  - 把大需求拆解成小任务
  - 定义每个任务的验收标准
  - 生成任务进度报告

### 3. Build（技术负责人）
- **职责**：出技术方案、交代码和测试
- **配置目录**：`team/agents/build/`
- **主要任务**：
  - 生成技术方案
  - 写代码、测试、提交
  - 生成技术文档

### 4. Research（情报负责人）
- **职责**：跟踪竞品、风险、模型发布动态
- **配置目录**：`team/agents/research/`
- **主要任务**：
  - 搜索热点话题，整理选题池
  - 分析竞品，提供学习建议
  - 跟踪新模型发布

### 5. Growth（增长负责人）
- **职责**：规划分发、转化漏斗、上线节奏
- **配置目录**：`team/agents/growth/`
- **主要任务**：
  - 生成分发计划
  - 分析数据，提供优化建议
  - 生成 A/B 测试方案

### 6. Ops（运营负责人）
- **职责**：门禁检查、发布清单、回滚预案
- **配置目录**：`team/agents/ops/`
- **主要任务**：
  - 发布前门禁检查
  - 生成发布清单
  - 备份所有文件

## 协作协议

### 任务卡模板

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

**必填字段：**
- `task_id`：格式为 `T-YYYYMMDD-<role>-NNN`
- `status`：`todo|doing|blocked|done`
- `from`：派发者
- `to`：接收者
- `created_at`：创建时间
- `deadline`：截止时间
- `last_update_at`：最后更新时间
- `objective`：一句话目标
- `acceptance`：验收标准（可量化、可验证）
- `required_output`：需要回传的交付物

### 结果卡模板

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

**必填字段：**
- `task_id`：对应的任务 ID
- `status`：`done|blocked|needs_info`
- `owner`：执行者
- `reported_at`：报告时间
- `deliverables`：交付物（文件/链接/输出）
- `evidence`：证据（可验证）
- `next_step`：下一步动作（owner + deadline）
- `ledger_ref`：结果卡路径

## 3条硬规则

### 规则1：任务卡必须完整
- owner、deadline、acceptance 缺一不可
- 没有验收标准，就不算任务
- 缺失必填字段，专家应返回 `needs_info`

### 规则2：结果卡必须可追溯
- deliverables、evidence、ledger_ref 必须落盘
- 没有证据，就不算完成
- 交付物路径必须存在

### 规则3：门禁不过不发布
- 无论文章还是产品，NO_GO 就不能上线
- 门禁检查包括：错别字、敏感词、数据标注、文件备份
- 通过门禁才能标记为 `done`

## 任务状态流转

```
todo -> doing -> done
         ↓
      blocked
```

**不允许：**
- `todo -> done`（直接跳过 doing）
- `done -> doing`（已完成不能回退）

## 超时处理

### Stale 任务
- 定义：`status=todo|doing` 且 `last_update_at` 超过 6 小时
- 处理：CEO 升级到 `team/PROJECT_STATUS.md` 的阻塞/风险区域

### Deadline Missed
- 定义：当前时间已超过 `deadline` 且任务非 `done`
- 处理：CEO 升级并重新分配 owner

### Dead-Letter
- 定义：升级后 12 小时仍无更新
- 处理：标记为 dead-letter 并重新分配

## 门禁检查

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

## 使用说明

这个文件定义了多 Agent 协作的核心规则。

**修改建议：**
1. 根据你的需要调整 6 个 AI 员工的职责
2. 可以删除不需要的角色（比如只保留 CEO + Build）
3. 可以添加新角色（比如 Design、Marketing）
4. 根据你的业务调整门禁检查清单

**记住：**
- 任务卡和结果卡的格式不要改（保持一致性）
- 3条硬规则不要改（保证质量）
- 从简单开始，逐步优化

**最小配置：**
如果你觉得 6 个 AI 员工太多，可以只保留：
- CEO（总指挥）
- Build（执行者）

这样就是一个"1+1"的最小团队。

**扩展配置：**
如果你需要更多角色，可以添加：
- Design（设计负责人）
- Marketing（市场负责人）
- Support（客服负责人）
- Finance（财务负责人）

每个角色都按照相同的模板配置即可。
