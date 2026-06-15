# References Index

These are the deep references for the `upward-reporting` skill. They are loaded **on demand** — `SKILL.md` stays thin and only pulls in a file when the current routing step needs it. You normally don't read these top-to-bottom; you jump to the one your situation calls for.

Files are organized along the skill's routing dimensions: **intake → audience → scenario → role → format**, plus examples and method background.

| 路由维度 | 文件 | 什么时候读 |
|---|---|---|
| 0. 口语归一 | [natural-language-intake.md](natural-language-intake.md) | 用户给的是吐槽/笔记/草稿,要先翻译成专业意图 |
| 1. 受众 | [audience-modes.md](audience-modes.md) | 需要 +1 / 老板 / 跨部门 / 外部 的不同框架 |
| 2. 场景 | [scenario-templates.md](scenario-templates.md) | 周报、风险升级、决策、资源、一页纸、纪要、上线、数据洞察等场景结构 |
| 3. 角色 | [roles/](roles/) | 按职业口径写;见下方 roles/ 小节 |
| 4. 渠道/格式 | [templates.md](templates.md) | 快聊/邮件/口头基础模板、改写启发、语气变体(更强/更软/更高管/更短) |
| 范例 | [examples.md](examples.md) | 想要可直接照抄的端到端范例(含数据严谨的正反对照) |
| 方法论 | [source-patterns.md](source-patterns.md) | 用户问"为什么用这套结构"或想要替代方案 |

## roles/ — 角色口径(可扩展)

| 文件 | 说明 |
|---|---|
| [roles/index.md](roles/index.md) | 角色路由 + 扩展规范(加新角色就在此目录放一个 `<name>.md`) |
| [roles/data-analyst.md](roles/data-analyst.md) | 数据分析师口径,含 Causal Rigor:相关≠因果、没显著不下结论 |
| [roles/product-manager.md](roles/product-manager.md) | 产品经理口径 |

当上下文无法推断角色、用户也没有说明时,使用通用管理层口径,不要默认套用数据分析师模板。只有角色会明显影响表达时,再追问"你是产品、数据还是其他角色?"。

> 扩展更多角色(engineering / operations / sales / marketing / CS 等)的强调点和模板规范,见 [roles/index.md](roles/index.md)。

## 加载关系

```
SKILL.md ──按需读──▶ references/*.md
                      │
                      └─ roles/ ──内部互引──▶ data-analyst.md 是显著性/因果纪律的单一事实源,
                                              product-manager.md 等其它角色引用它,不重复写。
```
