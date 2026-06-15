# Natural Language Intake

Use this file when the user writes casually, pastes rough notes, or asks "这段怎么说", "怎么跟领导讲", "帮我润色", "帮我汇报一下", or similar.

The user should not need to write a prompt. Treat their text as raw material and convert it into a professional reporting draft.

## Intake Pipeline

1. Separate facts from interpretation.
   - Facts: dates, deliverables, metrics, existing features, blockers, owners, decisions, dependencies.
   - Interpretation: "很乱", "比较麻烦", "不清楚", "效率低", "需要统一", "后面想做".

2. Translate casual wording into management signals.
   - "现在比较乱" -> definitions are fragmented, ownership is unclear, and change history is hard to trace.
   - "不好查" -> discovery efficiency is low; users cannot quickly locate objects or understand dependencies.
   - "容易影响别的地方" -> impact assessment is weak; changes may affect related events, properties, modules, or downstream analysis.
   - "后面想做" -> next-stage roadmap or phased plan.
   - "需要领导看一下" -> needs alignment, prioritization, resource support, or decision.

3. Infer the likely route.
   - Mentions only "领导" -> audience is ambiguous. Ask whether it is for direct manager (+1) or big boss/high-level leader before drafting. Provide both versions only when the user explicitly asks for both.
   - Mentions "老板/高层/管理层" -> boss/executive version.
   - Contains metrics, analysis, tracking, data quality, dashboards, funnels, warehouses, metadata -> data analyst lens.
   - Contains requirements, roadmap, launch, product workflow, user feedback -> product manager lens.
   - If no role is clear, use a general management voice. Ask "你是产品、数据还是其他角色？" only when the role would materially change the framing.

4. Rebuild the message into a professional structure.
   - Conclusion: one-sentence judgment.
   - Context: why this matters.
   - Current progress: what is already done.
   - Gap/risk: what remains unclear or unsolved.
   - Plan: what happens next and in what order.
   - Ask: what the recipient should confirm, decide, coordinate, or know.

5. Preserve uncertainty.
   - If the user did not provide metrics, do not invent metrics.
   - Use "当前判断", "建议先", "需要进一步确认" when evidence is incomplete.
   - If there are missing owners/dates, either omit them or mark as "待确认"; do not fabricate.

## Casual To Professional Phrases

Use these as transformations, not as fixed phrases.

```text
原来都在 Excel、文档、飞书里
-> 埋点定义散在 Excel、文档、飞书里，没有一个统一的地方管。

字段含义不清
-> 字段口径不统一，别人复用或者解释数据时经常要反复确认。

负责人不明确
-> 对象没有明确的 owner，出了问题不好追到人，改动也没人能拍板确认。

历史变更难追溯
-> 没有变更记录，一次调整为什么改、改了哪些、影响多大，事后都查不清。

字段复用和影响范围不好判断
-> 事件、属性、模块之间的依赖看不清，改字段之前判断不了会牵连到哪里。

想做搜索和知识图谱
-> 下一阶段想在“能统一管”的基础上再进一步，让人能快速查到字段、看懂相互关系、估出改动的影响范围。

自动化埋点设计
-> 想根据 PRD 和已有的埋点规范自动生成埋点方案，省掉重复的人工设计，也减少各人标准不一致的问题。

数仓口径对齐
-> 把埋点定义和下游的分析口径对齐，避免采集、加工、分析这几环口径对不上。
```

## Default Drafting Behavior

When the user provides a long rough description and asks generally:

- If audience level is ambiguous, ask the user to choose `向+1汇报版` or `大老板/高层版` before drafting.
- Produce both labeled versions only when the user explicitly requests both.
- If the user is a data analyst or the text is data-heavy, apply `roles/data-analyst.md`.
- If the text is pure roadmap/product delivery and no data lens is implied, do not apply `roles/data-analyst.md`; use product-manager when implied, otherwise use a general management voice.
- If role is unclear and important, ask one short role question instead of guessing.
- Keep the first output ready to send. Put assumptions after the draft, not before it.

## Output Style

Prefer:
- "当前已经完成..."
- "下一阶段建议..."
- "核心问题是..."
- "这会影响..."
- "需要确认..."

Avoid:
- "我觉得这个东西..."
- "大概就是..."
- "可能有点乱..."
- "领导看看..."
- "希望支持一下..."
- Excessive politeness, flattery, or apology.
