# User journey mode

Use when the goal is to reconstruct what the user experienced from initial input to an outcome.

## 1. Required questions

Trace from the earliest event:

- What requirement, script, style, references, uploads, and form choices did the user submit?
- How did the product first respond, and what did it ask the user to confirm?
- What changed after each confirmation or modification?
- Where could the user continue, revise, choose an alternative, stop, retry, or return?
- How did normal generation, correction, failure, insufficient credits, and interruption behave?
- Did chat, task list, canvas, asset history, preview, and editor agree?

Do not force a path category to exist when no evidence supports it. Include the requested category but label it `【尚未确认】` and explain the missing evidence.

## 2. Evidence table

Use one row per meaningful stage or branch:

| 阶段 | 用户目标 | 用户动作 | 页面反馈 | 用户需要做的决定 | 页面/资产状态变化 | 问题或阻力 | 证据 |
|---|---|---|---|---|---|---|---|

Evidence must name the screenshot/source, visible wording, button, Agent, asset, status, or error. Separate facts from inferences inside each cell.

## 3. Journey diagram

Keep exactly three swimlanes when the user requests the three-lane journey format:

1. 用户
2. 产品界面
3. 系统结果

Each node should state:

- current goal;
- user action;
- page feedback;
- whether a choice is required;
- next state after each choice;
- recovery behavior after failure;
- supporting evidence ID.

Represent decisions as diamonds and label branches explicitly, for example:

- 满意 / 不满意
- 继续 / 中断
- 生成成功 / 生成失败
- 余额充足 / 余额不足

Distinguish path styles for normal flow, modification/correction, and failure/interruption. If a path is not evidenced, use a dashed “待验证” branch instead of inventing behavior.

## 4. Experience layer

For each major stage, derive a compact experience row:

| Stage | Observable emotion signal | Likely thought/feeling | Pain point | Evidence level | Product opportunity |
|---|---|---|---|---|---|

Emotion and thought are normally `【合理推断】` unless the user explicitly expressed them. Keep user-supplied annotations editable or visually marked as “待补充”.

Opportunity statements should be actionable, such as:

- synchronize chat, tasks, canvas, and assets through one status model;
- expose cost/credit and retry consequences before generation;
- show which downstream assets become stale after an upstream edit;
- provide explicit version comparison and rollback;
- make confirmation gates and edit scope unambiguous.

Do not claim the source product already implements an opportunity.

## 5. Recommended delivery order

1. 本次查看范围
2. 无法访问或无法确认的证据
3. 用户旅程证据表
4. 三泳道用户旅程图
5. 用户情绪、想法、痛点与可补充项
6. 同类产品机会点
7. 三个最值得讨论的用户体验问题

Stop after the journey deliverable unless the user explicitly asks for Agent internals.
