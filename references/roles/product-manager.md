# Product Manager Role

Use when the user is a PM, product owner, product lead, or when the task concerns product roadmap, requirements, launch, iteration, experiments, user feedback, growth, or cross-functional delivery.

## Core Structure

1. User or business problem.
2. Product judgment or recommendation.
3. Evidence: user feedback, data, experiment, support ticket, customer input, sales signal.
4. Scope and tradeoff: time, quality, cost, UX, technical debt, opportunity cost.
5. Cross-functional dependency.
6. Launch or iteration risk.
7. Decision or support needed.

## What To Emphasize

- User/customer problem and business goal.
- Product decision: scope, priority, tradeoff, launch readiness, rollback, or experiment choice.
- Evidence: user feedback, funnel data, adoption, retention, support tickets, sales/customer input, experiment result.
- Cross-functional dependency: design, engineering, data, operations, legal, sales, support.
- Timeline and launch risk: what changes if a decision is late.
- Recommendation: choose a path, cut scope, adjust roadmap, run experiment, delay launch, or align owners.

## Avoid

- Over-indexing on feature progress without explaining user or business value.
- Reporting every coordination detail.
- Asking for "资源支持" without specifying the tradeoff: scope, timeline, quality, or opportunity cost.
- Presenting options without a recommendation.

## 向+1汇报 Pattern

```text
结论：{产品事项}当前的关键问题是{用户问题/范围/依赖/上线风险}。我建议{产品处理方案}，以保证{目标}。

当前进展：
- {需求/方案/评审/研发/实验/上线准备的关键进展}
- {用户反馈或数据证据}

我的判断：
- {为什么当前方案可行/哪里有风险/需要取舍什么}
- {如果不调整，会影响什么上线目标或用户体验}

下一步：
- {我会推动的动作 + 日期}
- {设计/研发/数据/运营等依赖动作 + 日期}

需要您支持：
- {请+1帮忙判断优先级/确认取舍/协调资源/统一对外口径}
```

## 向老板汇报 Pattern

```text
结论：{产品事项}会影响{业务目标/用户体验/上线节奏}。我的建议是{推荐方案}，需要您确认{决策点}。

关键事实：
- {用户/业务证据}
- {当前方案或上线准备情况}
- {主要依赖或风险}

取舍：
- 方案A：{收益}，代价是{代价}。
- 方案B：{收益}，代价是{代价}。
- 建议：{推荐方案 + 原因}

业务影响：
- {对收入/留存/转化/客户承诺/品牌/成本/团队节奏的影响}

需要您：
- {拍板范围/优先级/延期/资源/跨部门协调}，建议在{日期}前确认。
```

## Common Scenarios

Launch risk:
- Lead with impact on launch goal, customer commitment, or business window.
- Name the decision: delay, cut scope, add resource, or accept risk.

Requirement change:
- Lead with why the change matters and what it displaces.
- Include impact on user value, timeline, engineering cost, and roadmap priority.

Experiment readout:
- Lead with whether the result changes product direction.
- Include target metric, guardrail metrics, sample, confidence, and recommendation.
- 统计严谨同样适用 PM:没过显著就别说"有效",分群相关别说成"功能带来了提升"。引用实验或数据下结论时,遵循 `data-analyst.md` 的 Causal Rigor 与显著性口径。

Roadmap tradeoff:
- Lead with the business choice, not the feature list.
- Present options with opportunity cost.
