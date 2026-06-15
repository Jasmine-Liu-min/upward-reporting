# Data Analyst Role

Default role for this user unless another role is specified.

## Core Structure

Prefer an insight-led structure over a task-led structure:

1. Business question: what decision, risk, or opportunity this analysis supports.
2. Bottom-line finding: the most important answer in one sentence.
3. Evidence: the 2-4 metrics, cuts, comparisons, or segments that support the finding.
4. Confidence and caveats: data window, coverage, metric definition, sample, tracking quality, and whether the conclusion is confirmed or directional.
5. Business impact: what changes for revenue, conversion, retention, cost, efficiency, operations, customer experience, or risk.
6. Recommendation: what action to take, what to test, what to stop, what to monitor, or what decision is needed.
7. Next step or ask: owner, deadline, missing data, permission, metric alignment, stakeholder decision.

Use a progress-led structure only when there is not enough evidence yet. Even then, name the business decision at risk and what evidence is still missing.

## What To Emphasize

- Business question: what decision or business problem the analysis supports.
- Key finding: the one thing the recipient should remember.
- Confidence: data coverage, sample size, time window, caveats, metric definition, and whether the conclusion is confirmed or directional.
- Impact: revenue, conversion, retention, efficiency, cost, risk, user behavior, or operational bottleneck.
- Action: recommended experiment, dashboard change, metric definition, data fix, follow-up analysis, or stakeholder decision.
- Data dependency: missing table, data quality issue, tracking gap, permission, owner, and deadline.
- Decision readiness: whether the current evidence is enough to act, enough to prioritize, or only enough to investigate further.

## Avoid

- Listing SQL, charts, or data pulls as the main achievement.
- Saying only "数据还在看" without naming the decision risk.
- Overstating precision when the data is incomplete.
- Asking vaguely for "数据支持"; name the dataset, permission, owner, and deadline.
- Burying the insight under process details such as extraction, cleaning, meetings, or dashboard formatting.
- Reporting a metric movement without explaining whether it matters and what should change.
- 反向硬推结论。证据只支持到哪一步,结论就只说到哪一步;不要为了给领导一个"说法"就从弱证据推出强结论。常见两种反向硬推:
  - **不显著 → 说成"有提升/有效"**:没过显著就是没测出差异,不能当成正向结论。
  - **不显著 → 说成"效果很小/没用"**:没过显著也**不能**反推效果一定小。能不能排除"有个小效应只是没跑够",取决于实验的 MDE / 检验功效(power)。没看到 MDE 或功效之前,只说"未测出显著差异",并把"是真没效果还是功效不足"列为待确认。
- 把相关当因果。两个指标同向变动、某分群表现更好,只能说"相关",不能直接说"X 导致 Y"。详见下面的 Causal Rigor。

## Causal Rigor — 相关不等于因果

数据分析师**可以**做因果推断,但因果是一个比相关强得多的论断,必须由方法或设计撑得起。结论的强度,只能等于证据/设计的强度。

**三类证据,对应能下的三种结论:**

1. **干净的随机实验**(A/B、RCT;随机分组、无串扰、无选择性流失)→ 可以下因果结论:"X 使 Y 变化了 Z"。
2. **准实验 / 因果推断设计**(双重差分 DiD、断点回归 RDD、工具变量 IV、合成控制、倾向得分匹配 PSM 等)→ 可以下**有条件的**因果结论,但必须写明关键识别假设(平行趋势、外生性、可忽略性等)以及它们是否站得住;假设垮了,因果结论就垮了。
3. **纯观测 / 相关数据**(同期涨跌、分群对比、漏斗相关)→ **只能**说"X 与 Y 相关 / 同向变动",不能说"X 导致 Y"。要点名主要混淆因素(季节、同期活动、选择偏差、反向因果),并说清要确证因果还差什么(上实验,还是用哪种识别策略)。

**措辞要和证据对齐:**
- 只到相关:"X 与 Y 同向变动""高活用户更倾向用该功能",**别用**"带来、驱动、导致、提升了"。
- 实验级因果:"X 使 Y 提升 {幅度}(实验已随机分组)"。
- 准实验因果:"在 {识别假设} 成立的前提下,X 对 Y 的影响约为 {幅度}"。

**两类最容易翻车,下任何因果结论前先自查:**
- **反向因果**:是用了功能所以更活跃,还是本来就活跃的人才会用这功能?
- **选择偏差 / 混淆**:是干预真有效,还是高意愿用户恰好落在了这组 / 这个渠道本身用户质量就更高?

竞争性解释没排除掉,就不要把相关升级成因果;能排除哪些、还剩哪些没排除,都要写清楚。

## Report Types

Use `insight update` when the analysis has a finding:

```text
业务问题：{这次分析支持什么决策/判断}
结论：{最重要发现 + 对业务的含义}
关键依据：
- {指标/分层/对比1}
- {指标/分层/对比2}
可信度：{已验证/方向性判断/仍需补充验证}，限制是{口径/样本/时间窗/埋点/权限}
建议动作：{业务动作/实验/监控/资源调整/停止或继续}
需要支持：{如果需要，写清楚谁在何时做什么}
```

Use `analysis progress` when the work is not ready for a conclusion:

```text
业务问题：{这次分析要回答什么}
当前进展：{已经完成哪些数据准备/口径确认/初步探索}
初步信号：{如果有，写方向性发现；如果没有，说明原因}
当前卡点：{缺数据/口径未定/埋点异常/权限/样本不足}，影响是{会影响什么决策或时间点}
下一步：{何时补齐什么证据，何时给出结论}
需要支持：{请+1或老板协调的具体动作}
```

Use `decision recommendation` when the analysis should drive a decision:

```text
需要决策：{决策项}
我的建议：{推荐选项}
数据依据：
- {最关键证据1}
- {最关键证据2}
收益与风险：{推荐动作的收益、代价、风险}
可信度：{证据强度与限制}
下一步：{决策后动作 + owner + date}
```

## 向+1汇报 Pattern

```text
结论：{分析事项}目前能支持{明确结论/方向性判断/暂不建议下结论}。核心发现是{一句话发现}，对{业务决策}的影响是{影响}。我建议{下一步分析或业务动作}。

业务问题：
- {这次分析在回答什么问题，服务什么决策}

关键发现：
- {发现1：指标 + 幅度 + 时间范围 + 对比对象}
- {发现2：分层/渠道/用户群/路径/漏斗中的关键差异}

可信度与限制：
- {数据窗口/样本/口径/埋点/权限/异常值情况}
- {哪些结论可以先用于判断，哪些还需要补证据}

我的建议：
- {建议的业务动作/实验/监控/补数/口径确认}

下一步：
- {我会在何时完成什么补充分析/看板/验证}
- {需要谁补充什么数据、确认什么口径或给什么权限}

需要您支持：
- {请+1帮忙确认分析优先级/判断是否先按方向性结论推进/协调数据权限/统一指标口径}
```

## 向老板汇报 Pattern

```text
结论：从{时间范围/样本}数据看，{业务问题}的主要变化来自{核心原因}，对{业务目标}的影响是{影响}。我的建议是{业务动作/决策}。

关键发现：
- {指标变化 + 幅度 + 时间范围 + 对比基准}
- {最关键的分层结果：渠道/用户群/地区/商品/路径/场景}
- {已排除或仍待验证的因素}

可信度：
- {已验证/方向性判断/需要补充验证}。主要限制是{口径/样本/埋点/数据覆盖}。

业务影响：
- {这个发现会影响什么目标、资源分配、优先级、收入/转化/留存/成本/风险}

建议动作：
- {推荐动作}，预期作用是{结果}。
- {需要补充验证的事项}，最晚{日期}给出下一版结论。

需要您：
- {确认是否按建议推进/授权拿数据/决定是否调整目标、资源或优先级}
```

## Common Scenarios

Metric abnormality:
- Lead with what moved, how much, when, and whether it is real or caused by tracking/data issues.
- Separate "business change" from "data quality issue".

Dashboard/reporting progress:
- Do not report only dashboard completion. State what decision the dashboard enables, what metrics are aligned, and what adoption or operating rhythm it supports.

Experiment/A-B test:
- Lead with whether the result is actionable. Include sample, lift, confidence, guardrail metrics, and recommendation.
- 显著性是结论的硬约束。先判定"能不能下结论",再说方向。一句话口径:
  - 过了显著且方向正 → "测出了正向影响,建议……"。
  - 过了显著且伤护栏 → "有正向但伤了 {护栏指标},不建议上 / 需权衡"。
  - 没过显著 → "未测出显著差异,据此不能判定有效",紧接着把"是真没效果还是功效不足(看 MDE / power)"标为待确认,**不要**替领导猜是哪一种。
- 把"业务结论"和"统计结论"分开说:统计上未显著,业务上可以给"不亏不赚、单看数据没有上线理由"这种判断,再交回决策取舍,而不是用业务话术盖掉统计事实。

Data quality or tracking issue:
- Lead with decision impact. Name broken event/table/field, affected metrics, owner, fix date, and temporary workaround.

Ad hoc analysis request:
- State the business answer, then put methodology in caveats. Avoid turning the update into a methods report.
