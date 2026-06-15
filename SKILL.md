---
name: upward-reporting
description: >-
  Create, rewrite, polish, or structure workplace upward communication for direct managers (+1), bosses, executives, sponsors, or other decision-makers. Use for natural-language requests like "这段怎么跟领导说", "帮我写给老板", "帮我汇报一下", "整理成向上汇报", "写周报/项目进展/风险升级/资源申请/决策请求", "润色成更适合领导看的版本", "生成向+1和老板两个版本", "按数据分析师/产品经理口径写", or similar Chinese/English status-update requests. Important: when the user says only "领导" and does not specify whether it is direct manager (+1) or big boss/high-level leader, ask them to choose before drafting; do not silently default to +1. Supports audience, scenario, and role-specific variants such as data analyst and product manager.
---

# Upward Reporting

## Overview

Turn raw notes into decision-friendly workplace communication. The core job is a perspective translation: from the reporter's view ("what I did") to the recipient's view ("what state is this in, do I need to decide anything"). Treat this skill as a router: choose the audience, scenario, role lens, and channel, then draft a concise report with clear impact and an executable ask.

## Quick Flow (read this first)

For most requests, this is the whole job:

1. **Audience?** If the user said only "领导" and the level is unclear -> ask "直属上级（+1）还是更高层老板？" and stop until answered (unless they asked for both). Otherwise infer +1 / boss / cross-functional / external.
2. **Role + scenario?** Infer from content: metrics/口径/埋点 -> data analyst; roadmap/需求/上线 -> product manager. If no role is clear, use a general management voice or ask "你是产品、数据还是其他角色？" when role materially changes the draft. Pick the scenario (weekly / risk / decision / resource / readout / insight).
3. **Extract the signal:** outcome, current judgment, evidence, risk(+mitigation), ask(owner+action+deadline), next step. Do not invent facts; mark gaps `待确认`. 引用数据时:相关不当因果,没显著不当有效(细则见 references/roles/data-analyst.md 的 Causal Rigor)。
4. **Draft inverted-pyramid:** BLUF -> minimal context -> smallest evidence -> risk/tradeoff -> ask/next. 长度随渠道(IM 一屏 / 邮件带主题分段 / 口头短句),详见 Medium And Length。
5. **Self-check, then output** (see Quality Bar — actually run it on your own draft).

See `references/examples.md` for full raw-notes -> polished-draft worked examples. Read the deeper reference files only when a step needs more than the above.

## Routing Workflow

For everyday natural-language requests, infer the route from wording and content. Do not require the user to name this skill, provide a path, or use formal prompt syntax.

Audience selection is mandatory when the wording is ambiguous. If the user says only "领导", stop and ask: "是给直属上级（+1），还是给更高层老板/大老板？" Do not draft before this choice unless the user explicitly asks for both versions.

0. Normalize the user's natural language:
   - Treat casual text, rough notes, pasted drafts, half-formed complaints, and "我想跟领导说一下..." as raw material.
   - First translate it into professional intent: what happened, why it matters, what judgment is implied, what action is needed, and who should act.
   - Do not expose this intermediate analysis unless useful. Use it to produce a polished workplace version.
   - Read `references/natural-language-intake.md` when the user writes casually, pastes messy notes, or asks "这段怎么说/怎么汇报/帮我润色".

1. Identify the report job:
   - `inform`: share progress with no requested action.
   - `decide`: ask for a decision between options.
   - `escalate`: surface a risk/blocker early.
   - `ask`: request resources, alignment, access, or approval.
   - `align`: make scope, priorities, or expectations explicit.

2. Choose the audience:
   - `向+1汇报`: direct manager. Include working context, judgment, blockers, next steps, and the specific support needed.
   - `向老板汇报`: boss, senior leader, skip-level manager, sponsor, or executive. Start with business impact, recommendation, decision point, or risk exposure.
   - Cross-functional stakeholder or external recipient: state shared goal, dependency, owner, date, and low-friction ask.
   - If the user says only "领导" and the audience level is unclear, do not silently choose and do not draft yet. Ask one short question: "是给直属上级（+1），还是给更高层老板/大老板？" Only provide both versions if the user explicitly asks for both or says "都给我".
   - If the user says "老板", "高层", "大老板", "汇报会上", or "给管理层看", use `向老板汇报`.
   - Read `references/audience-modes.md` when audience-specific variants are needed.

3. Choose the scenario:
   - Weekly/project update, risk escalation, resource ask, decision request, executive one-pager, meeting readout, launch update, insight update, analysis progress, or another concrete scenario.
   - If the user pasted a long project description and asks "怎么汇报/怎么跟领导说", default to project update with next-step and ask.
   - If the text contains metrics, analysis findings, funnels, attribution, data quality, dashboards, or tracking events, prefer data analyst scenarios.
   - Read `references/scenario-templates.md` for scenario-specific structures.

4. Choose the role lens:
   - Use a role lens only when the user explicitly names a role or the content strongly implies one.
   - Use `data-analyst` when the user says they are a data analyst, or when the content involves metrics, data quality, tracking, attribution, dashboards, funnels, experiments, data warehouses, metadata, or analysis conclusions.
   - Use `product-manager` when the user asks for PM/product manager/product owner language or the raw notes involve roadmap, requirements, launch, user feedback, experiments, or cross-functional delivery.
   - If the role cannot be inferred and the user did not specify one, do not force `data-analyst`. Use a general management voice without loading a role-specific template. If the role would materially change the wording, ask one short question: "你是产品、数据还是其他角色？"
   - Read the matching role file: `references/roles/data-analyst.md`, `references/roles/product-manager.md`, or the closest role notes in `references/roles/index.md`.

5. Extract the management signal:
   - Outcome: what changed, shipped, learned, or became possible.
   - Current judgment: on track, delayed, blocked, at risk, newly unblocked, or needs decision. Do not use traffic-light style status labels.
   - Evidence: metrics, facts, deliverables, dates, examples, customer signals, or analysis findings.
   - Risk: probability, impact, earliest warning sign, mitigation.
   - Ask: exact action needed from the recipient, with deadline.
   - Next: owners and dates for the next visible milestone.

6. Draft in an inverted-pyramid structure:
   - BLUF: bottom line up front, 1-2 sentences.
   - Context: only the background needed to understand the point.
   - Evidence: the smallest proof set that supports the judgment.
   - Risk/tradeoff: what could go wrong or what was sacrificed.
   - Ask/next step: decision, support, or FYI closure.

7. Tighten the output:
   - Replace activity with impact: not "held meetings", but "unblocked vendor contract by aligning legal and procurement".
   - Replace vague asks with executable asks: owner, decision, deadline, consequence.
   - Keep uncertainty visible without sounding helpless.
   - Make bad news early, specific, and paired with mitigation.

## Reference Map

- `references/examples.md`: end-to-end worked examples (raw casual notes -> route decision -> polished draft). Read this when you want a concrete pattern to imitate.
- `references/audience-modes.md`: audience framing for +1, boss, cross-functional, and external recipients.
- `references/natural-language-intake.md`: convert casual notes and rough wording into professional reporting intent before drafting.
- `references/scenario-templates.md`: scenario templates for weekly updates, risks, resources, decisions, one-pagers, meeting readouts, launches, and analysis updates.
- `references/templates.md`: base templates, rewrite heuristics, and tone variants.
- `references/roles/`: role-specific reporting structures. `index.md` routes and documents the extension pattern; `data-analyst.md` (includes Causal Rigor) and `product-manager.md` are the built-in roles. Use a general management voice when no role is clear.
- `references/source-patterns.md`: method background and principles.

## Question Policy

Ask at most three clarifying questions only when required. Prefer drafting with explicit assumptions when the missing details are not risky.

High-value missing details:

- Recipient and relationship: direct manager (+1), senior executive/big boss, sponsor, client, teacher.
- Desired action: FYI, approve, choose, unblock, give resources, align expectations.
- Scenario: weekly update, risk escalation, decision request, resource ask, insight update, analysis progress, launch update, incident readout.
- Role lens: data analyst, product manager, operations, engineering, sales, marketing, or another function.
- Medium and length: WeChat/Slack, email, meeting script, one-pager, slide bullets.
- Stakes and sensitivity: bad news, conflict, budget, delay, performance, politics.
- Raw facts: timeline, metrics, blockers, owners, deadlines.

Do not ask the user to turn their notes into a prompt. If the raw material is enough to draft, draft with assumptions. The main exception is audience level: when "领导" is ambiguous, ask the user to choose +1 or big boss before drafting. Do not provide a full draft until the audience is selected, unless the user explicitly asks for both versions.

## Quality Bar

After drafting and before showing the user anything, run this checklist against your own draft and silently fix any line that fails. Do not show the checklist; show the corrected draft.

- The first sentence tells the recipient the point.
- The recipient can see whether action is needed.
- Every risk has impact and mitigation.
- Every ask has owner, action, and deadline.
- The tone is candid, calm, and capable.
- The wording does not use traffic-light style status labels.
- The role lens changes the evidence and language, not the facts.
- Casual user language has been translated into professional wording without inventing facts.
- The report avoids chronology unless chronology explains the decision.
- The report avoids empty qualifiers: "basically", "maybe", "should be okay", "as soon as possible".
- 结论强度不超过证据强度。任何引用数据的汇报都要满足:相关不写成因果(没有实验或因果推断设计就只说"相关/同向变动");没过显著不写成"有提升/有效";效果大小没被功效支撑就不下"效果小"的断言。数据岗细则见 `references/roles/data-analyst.md` 的 Causal Rigor。

## Output Defaults

When the user does not specify a format, produce:

1. A polished version ready to send.
2. A short note naming assumptions or missing facts.
3. Optional variants only when useful: `向+1汇报版`, `向老板汇报版`, `数据分析师版`, `产品经理版`, stronger, softer, shorter, or more executive.

When the user gives raw notes and asks casually ("这段怎么汇报", "帮我写一下", "怎么跟领导说") and does not specify audience level, ask the +1/big-boss choice first. Do not label one as the default unless the user chooses. Provide both versions only when explicitly requested.

For Chinese upward reporting, default to professional, direct, non-flattering language. Respect hierarchy without overusing polite filler.

## Medium And Length

渠道决定**形态和长度**,受众决定**框架**,两者独立选。"发群里给老板" = IM 形态 + 老板框架。

从措辞推断渠道:"发群里 / 微信 / Slack" -> IM;"写封邮件 / 发邮件" -> email;"汇报会 / 当面 / 口头跟领导讲" -> spoken;"一页纸 / 汇报材料 / 给管理层看 / PPT" -> one-pager。渠道不明且只是随口问,默认按 IM 快聊长度起草,不必追问。

| 渠道 | 套用模板 | 形态与长度 |
|---|---|---|
| 微信 / Slack / 群消息(IM) | `templates.md` → Fast Chat Update | 一屏看完;结论 + 3-4 条要点;不寒暄不铺垫 |
| 邮件 | `templates.md` → Email Update | 带主题行【FYI/需决策/需支持】;结论先行;分段 |
| 当面 / 电话 / 汇报会口头 | `templates.md` → 30-Second Spoken | 先说结论,口语短句,30 秒能讲完 |
| 一页纸 / 汇报材料 / 给管理层 | `scenario-templates.md` → Executive One-Pager | 一句话结论 + 关键事实 + 风险 + 选项建议 + 决策项 |
| 幻灯片要点 | 压成 bullet,每条一个判断,动词开头 | 一页一个信息,删掉过程细节 |

篇幅默认随渠道走;用户说"短一点 / 详细点"再调,不要自作主张把 IM 拉成长邮件。
