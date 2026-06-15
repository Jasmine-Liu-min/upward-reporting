# Base Templates And Rewrite Rules

Use this file for lightweight formats, rewrite heuristics, and tone variants. Use `audience-modes.md`, `scenario-templates.md`, and the `roles/` folder for deeper structures.

## Fast Chat Update

```text
结论：{项目/事项}目前{当前判断}，核心原因是{一句话原因}。

- 已完成：{1-2个有结果的进展}
- 当前风险：{风险 + 影响 + 截止时间}
- 下一步：{负责人 + 动作 + 日期}
- 需要您：{如果需要动作，写清楚审批/拍板/协调/资源}
```

## Email Update

```text
主题：【{FYI/需决策/需支持}】{事项} - {进展/结论}

{称呼}，

结论先说：{一句话说明当前情况、影响、是否需要对方动作}。

进展：
- {结果1，尽量带数字/交付物/日期}
- {结果2}

风险/问题：
- {风险/问题}。影响：{业务影响}。应对：{已采取或计划采取的动作}。

需要您：
- {明确动作}，建议在{日期/时间}前完成，因为{原因/后果}。

下一步：
- {负责人}会在{日期}前完成{动作}，并同步{下一次汇报节点}。
```

## 30-Second Spoken Update

```text
我先说结论：{事项}现在{当前判断}，对{目标}的影响是{影响}。
这周最重要的进展是{成果}。
目前最大的风险是{风险}，我已经在做{应对}。
需要您帮忙的是{具体动作}，最好在{日期}前定下来。
如果您同意，我下一步会{动作}，{日期}给您下一版结果。
```

## Rewrite Heuristics

Bad: "这周开了几个会，推进了一些事情，整体还可以。"

Better: "本周已完成供应商方案对齐，采购和法务均确认无阻塞；项目仍按 6 月 28 日上线推进。当前唯一风险是测试环境不稳定，可能压缩 2 天验收时间，我已安排周三前完成环境修复。"

Bad: "希望领导支持一下。"

Better: "需要您在周五 18:00 前确认是否采用方案 B；如果无法本周确认，供应商排期会顺延至少 1 周。"

Bad: "这个问题比较复杂，可能会有一些影响。"

Better: "如果本周无法拿到数据权限，模型评估会从 6 月 20 日延后到 6 月 27 日，并影响下游答辩材料准备。我建议今天由您帮忙协调数据负责人授权临时只读权限。"

## Tone Variants

Stronger:
- Use when the risk is urgent or a decision is blocked.
- Use direct verbs: "需要决定", "建议暂停", "不建议继续投入".

Softer:
- Use when preserving relationship matters.
- Keep the ask clear while adding room: "我的建议是...", "如果您认可，我会...".

More executive:
- Start with impact and recommendation.
- Move background into bullets or appendix.
- Cut process detail unless it changes the decision.

Shorter:
- Keep conclusion, one evidence bullet, one risk/next-step bullet, and one ask.
- Remove background unless it changes the decision.
