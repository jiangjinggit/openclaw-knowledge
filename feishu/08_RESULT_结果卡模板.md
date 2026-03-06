# ✅ RESULT 模板（可直接复制）

> 用于任务回传，确保“已交付 + 有证据 + 有下一步”

---

## 一、标准模板

```markdown
### RESULT T-YYYYMMDD-<role>-NNN
- status: done
- owner: build
- reported_at: YYYY-MM-DD HH:MM Asia/Shanghai
- deliverables:
  1. [交付物1：文件路径/链接]
  2. [交付物2：文件路径/链接]
- evidence:
  1. [证据1：可验证数据]
  2. [证据2：可验证结果]
- blockers: 无
- next_step: [下一步动作] (owner: [角色], deadline: [时间])
- ledger_ref: team/agents/<role>/RESULT_OUTBOX.md#RESULT T-YYYYMMDD-<role>-NNN
```

---

## 二、可直接用示例（内容任务完成）

```markdown
### RESULT T-20260306-build-001
- status: done
- owner: build
- reported_at: 2026-03-06 17:30 Asia/Shanghai
- deliverables:
  1. 文稿：team/content/wechat/2026-03-06/article.md
  2. 配图：team/content/wechat/2026-03-06/images/
  3. 发布版：team/content/wechat/2026-03-06/article.html
- evidence:
  1. 字数：3240（达标）
  2. 案例：3个（达标）
  3. 表格：2个（达标）
  4. 门禁检查：通过
- blockers: 无
- next_step: Ops做最终发布检查 (owner: ops, deadline: 2026-03-06 18:00)
- ledger_ref: team/agents/build/RESULT_OUTBOX.md#RESULT T-20260306-build-001
```

---

## 三、状态说明

- `done`：已完成且可验收
- `blocked`：卡住，需要升级处理
- `needs_info`：任务信息不足，需要补卡

---

## 四、常见错误

- ❌ “已经完成了”
- ✅ “交付物路径 + 量化证据 + next step”
