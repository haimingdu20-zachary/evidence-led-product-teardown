# Agent contract mode

Use when the goal is to identify observable Agents and define their inputs, decisions, tools, outputs, context access, and handoffs. This is behavioral reverse engineering, not recovery of hidden implementation.

## 1. Discover the actual Agent roster

Start from explicit Agent labels attached to responses, task nodes, or cards. Do not assume a standard number or conventional roster.

For every candidate record:

| Agent/candidate | First appearance | Trigger | Replaces/follows | Downstream handoff | Re-entry evidence | Confidence | Evidence |
|---|---|---|---|---|---|---|---|

If a label may be a UI role, task category, or orchestrator rather than an independent Agent, retain the ambiguity. Record normally expected but absent Agents as omissions, not as discovered Agents.

## 2. Six input sources

For each Agent, check all six categories and mark each item as fact, inference, or unknown:

1. `用户当前输入`: requirement, script, choices, feedback, modification, confirm/continue, interrupt, uploads.
2. `用户长期信息`: language, plan, balance, asset library, saved characters, Face ID, voice, preferences, permissions, project history.
3. `项目全局上下文`: project parameters, current script/style/ratio/language, character/scene/prop/storyboard lists, references, model/resolution, status, confirmations, errors, versions, generated assets.
4. `上游 Agent 输出`: producer, transferred fields/assets, usage, required start conditions, rerun consequences.
5. `平台公共资产`: style/model libraries, templates, professional knowledge, model limits, safety/copyright/billing rules.
6. `工具或运行时结果`: generated media, error/interruption/insufficient balance, write result, retry result, asset reference/version.

Page visibility is required to mark long-term information or platform rules as fact. Avoid exposing credentials or sensitive identity data.

## 3. Observable decisions

Summarize functional judgments, never hidden reasoning:

- problem the Agent solves;
- required information and completeness checks;
- automatic-continuation and user-confirmation conditions;
- stop conditions;
- modification scope and invalidation behavior;
- failure/retry behavior;
- completion criteria;
- whether result quality was actually verified.

The visible labels “思考完成/规划完成” may support that a summary was exposed, not how the model reasoned.

## 4. Tool contract

Never invent official function names. Use placeholders or functional names and label them `功能命名，非官方工具名`.

| Tool | Evidence level | Trigger | Required inputs | Confirmation gate | Observable success | Validation | Failure/retry | State write | Evidence |
|---|---|---|---|---|---|---|---|---|---|

An intention such as “我将生成角色图” is not a tool call. Confirm the action through a result, asset, status transition, or tool result surface.

## 5. Five output classes

Check:

1. `用户回复`: natural language, plan summary, result, error, suggestion.
2. `页面组件`: button, form, choice, confirmation card, error, preview/editor entry.
3. `资产`: text, image, Face ID, multiview, scene, prop, storyboard, video, audio, history/version.
4. `全局上下文写入`: field, state, asset reference, relationship, confirmation, success/failure.
5. `下游交接`: recipient, fields/assets, start condition, confirmation dependency, unresolved items.

## 6. I/O contract card

Use this fixed card for each evidenced Agent:

```text
Agent：名称
1. 核心目标
2. 触发条件
3. 输入信息（逐项标记六类来源）
4. 可观察判断
5. 调用工具
6. 输出信息（逐项标记五类输出）
7. 全局上下文读写
   字段或对象｜读取/写入｜生产者｜消费者｜更新时机｜证据等级｜证据
8. 完成条件
9. 异常与重试
10. 尚未确认的问题
```

## 7. Global data flow

After all cards, produce:

- tool master table;
- global context field table;
- producer-consumer table;
- Agent input → judgment → tool → output → handoff diagram;
- fact/inference/unknown register.

Explicitly examine:

- multiple versions of the same data;
- chat/task/canvas/asset inconsistencies;
- stable IDs/URIs between character, scene, prop, and storyboard;
- downstream invalidation after upstream edits;
- read-only or write-only fields;
- Agent claims of completion without matching global state.

## 8. Single-Agent boundary interview

Before drafting a prompt for one Agent, answer with evidence:

1. What problem does it solve?
2. When does it take over?
3. Who/what triggers it?
4. Who receives its output?
5. What belongs to it?
6. What does not belong to it?
7. Can user edits retrigger it?
8. When must it stop?
9. When may it auto-continue?
10. Must it await user confirmation?

Then read [functional-equivalent-prompt.md](functional-equivalent-prompt.md).

