# Role Index

Use this file to route to role-specific guidance.

Use role files only when the user's role is explicit or strongly implied by the content. If no role is clear, use a general management voice rather than defaulting to a specific role. Ask "你是产品、数据还是其他角色？" only when role choice would materially change the draft.

- Data analyst: read `data-analyst.md`.
- Product manager: read `product-manager.md`.
- Engineering: emphasize reliability, delivery risk, technical tradeoff, incident impact, implementation path.
- Operations: emphasize process bottleneck, SLA, capacity, cost, exception handling, owner handoff.
- Sales/BD: emphasize pipeline impact, customer commitment, revenue timing, competitive risk, needed executive support.
- Marketing/Growth: emphasize campaign result, CAC/ROI, conversion, channel allocation, experiment learning.
- Customer Success/Support: emphasize customer impact, escalation severity, churn risk, response plan, account owner.

When adding a new role, create `roles/<name>.md` with:

1. Core structure.
2. What to emphasize.
3. What to avoid.
4. 向+1汇报 pattern.
5. 向老板汇报 pattern.
6. Common scenarios.
