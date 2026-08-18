# Functional-equivalent System Prompt mode

Use only for a named target Agent after its complete evidence set and I/O contract have been assembled. The goal is reproducible observable behavior under equivalent inputs, tools, and context—not recovery of an official prompt.

## 1. Pre-prompt contract

Deliver before writing the prompt:

1. target Agent evidence scope and ten-question boundary;
2. six-source input contract;
3. five-class output contract;
4. tool contract;
5. observable state machine;
6. fact, inference, suggestion, and unknown rule lists.

Do not proceed if the target Agent name is still a placeholder or multiple roles remain indistinguishable. Ask for a target only when evidence cannot resolve it safely.

## 2. State machine

Use only evidenced states plus clearly labeled robustness recommendations. Consider:

- `waiting_input`
- `planning`
- `waiting_confirm`
- `executing`
- `validating`
- `completed`
- `failed`
- `interrupted`
- `retrying`
- `handoff`

For each state specify entry condition, allowed action, forbidden action, exit condition, and evidence level. Output a Mermaid state diagram; label branches with explicit conditions.

Do not infer that a task was `executing` solely because the Agent described a plan. If only “规划完成” is visible, the execution transition remains unknown until a result/state/asset appears.

## 3. Rule derivation

Tag every rule:

- `【事实规则】`: directly supported by page behavior;
- `【推断规则】`: necessary or reasonable to reproduce observed behavior;
- `【建议规则】`: a hardening improvement not evidenced in the source product;
- `【未知】`: cannot currently be determined.

Cover at least identity, objective, boundary, input checks, context reads/writes, workflow, tool selection and prerequisites, confirmation gates, validation, edits/rollback, failure/retry, interruption, handoff, completion, and output format.

## 4. Prompt structure

Use this exact structure unless the user specifies another:

```text
Agent名称
1. 角色
2. 核心目标
3. 任务边界
4. 输入契约
5. 全局上下文协议
6. 工作流程
7. 工具调用规范
8. 用户确认机制
9. 结果验证
10. 修改与回退
11. 异常处理
12. 状态机
13. 下游交接
14. 完成条件
15. 输出格式
```

### Required prompt behaviors

- Separate required and optional inputs across all six source categories.
- State readable, writable, and forbidden global fields. When actual names are absent, use semantic placeholders and mark them `推导设计`.
- Identify producers, consumers, update timing, versioning, and downstream invalidation.
- For every workflow step define entry conditions, inputs, judgment, tool use, state write, confirmation, and next state.
- Use `<功能名称工具>` placeholders for unofficial tool names.
- For each tool define required parameters, prechecks, success/failure, validation, retries, retry limit, idempotency, and post-call state writes.
- Confirmation must be a recorded state/event, not merely natural-language “你满意吗”.
- Do not trust a tool's `success` alone. Verify asset existence, task/global/page consistency, and task-specific quality constraints that can actually be inspected.
- Preserve versions and avoid overwriting confirmed assets. Define downstream invalidation for upstream edits as fact, inference, or recommendation.
- Handle missing input, tool failure, safety blocking, insufficient credits, write failure, interruption, duplicates, and failed handoff without inventing error causes.
- Handoff only after completion conditions; include confirmed inputs, asset references, status, unresolved issues, and confirmation record.
- Completion requires the asset/state/validation/confirmation/handoff conditions relevant to this Agent, not the Agent's own claim.
- If the real output schema is unknown, propose a clearly labeled semantic format rather than pretending it is official.

## 5. Rule-evidence traceability

After the prompt, map every material rule:

| Rule ID | Prompt section | Rule summary | Rule type | Evidence IDs | Evidence or rationale | Confidence |
|---|---|---|---|---|---|---|

A suggestion rule may cite a failure/conflict that motivates it, but the table must say the behavior itself is proposed.

## 6. Minimum test set

Include at least these six behavioral tests:

1. complete normal input;
2. missing required input;
3. localized user modification;
4. tool failure;
5. user interruption;
6. global context/page-state conflict.

Use columns:

| Test | Input | Initial state | Expected judgment | Expected tool calls | Expected state changes | Forbidden behavior |
|---|---|---|---|---|---|---|

Add tests for credit shortage, duplicate request/idempotency, safety blocking, or state-write failure when they are material to the Agent.

Test outcomes should evaluate observable behavior and state invariants, not exact wording.

## 7. Final order and stopping point

1. 目标 Agent 的证据范围
2. 输入契约
3. 输出契约
4. 工具契约
5. 状态机
6. 事实规则、推断规则、建议规则
7. 功能等价 System Prompt
8. 规则—证据追溯表
9. 最小测试集
10. 仍然无法确认的问题

Stop. Do not continue to other Agents or claim the result is the product's official System Prompt.

