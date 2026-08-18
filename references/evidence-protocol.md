# Evidence protocol

Use this protocol for every teardown mode.

## 1. Scope inventory

Create a source register before analysis:

| Source ID | File/page | Apparent stage | Readability | Access status | Notes |
|---|---|---|---|---|---|

Use stable source IDs (`S01`, `S02`) and event IDs (`E001`, `E002`). When filenames already carry meaningful screenshot numbers, retain both.

Do not assume lexical filename order equals event order. Establish order from visible timestamps, preceding/following content, task progress, asset appearance, and other state transitions. If order remains uncertain, state the competing possibilities.

## 2. Atomic evidence ledger

Record observations at the smallest useful unit:

| Event ID | Time/order | Actor/Agent | Visible user action | Visible product response | UI component | Asset/state delta | Evidence level | Source and exact evidence |
|---|---|---|---|---|---|---|---|---|

The evidence cell should include whichever are visible:

- page wording or short exact quote;
- button, menu, form, option, card, tab, or badge name;
- displayed Agent identity;
- visible asset and its state/version;
- task or generation status;
- exact error and offered next action;
- source/screenshot ID.

Keep quotations short and use transcription brackets for uncertain characters.

## 3. Evidence levels

### `【页面事实】`

Directly visible in an in-scope page, image, video frame, or exported UI. State only what is visible.

Examples:

- `【页面事实】按钮“继续生成”可见。`
- `【页面事实】聊天显示“已完成”，但画布中未见视频资产。`

### `【合理推断】`

Supported by two or more compatible facts, or by a necessary relationship between visible states. Cite the supporting facts and make the inference explicit.

Example: a confirmed script is followed by a character-generation task using the same named characters, so the script likely became an upstream input. The exact field schema remains unknown.

### `【尚未确认】`

Evidence is absent, cropped, illegible, ambiguous, or only described by the Agent. Unknown is not failure and should not be converted into a recommendation unless the user asks for product improvements.

### `【建议】`

A proposed product or implementation improvement. Keep it visually distinct from observed behavior.

## 4. Surface reconciliation

For each important state, compare these surfaces when present:

| Surface | What to verify |
|---|---|
| Chat | Agent claim, requested confirmation, error explanation |
| Task list | current task, success/failure/interrupted state, retry |
| Canvas | node/card existence, connectivity, asset status |
| Asset library/history | actual file, version, stable reference, timestamp |
| Preview/editor | playable/viewable result and edit entry |
| Account/credits | balance, plan restriction, cost warning |

Classify reconciliation as `一致`, `冲突`, or `无法比较`. A conflict row must show both claims without selecting a winner.

## 5. Completion verification

Do not mark a stage complete from chat alone. Check, as applicable:

- required asset exists and is viewable;
- task status is success rather than queued/running/failed/interrupted;
- global/canvas state reflects the asset;
- references from downstream cards resolve to the current version;
- confirmation state is visible when the flow requires user approval;
- preview/editor entry is present for a final media output;
- the visible result can be compared with material user constraints.

When result quality cannot be inspected, say that compliance is unverified.

## 6. Error and recovery capture

For each failure or interruption, record:

- where it appears;
- exact error text;
- affected operation/asset;
- whether credits may have been consumed;
- offered recovery actions (retry, change input/model, recharge, return, cancel);
- whether execution visibly continued after interruption;
- whether duplicate assets or stale status appeared after retry.

Absence of an error screenshot does not prove failure handling exists.

## 7. Evidence gap section

Always list:

- sources not accessible or unreadable;
- cropped controls or hidden panels;
- stages with only Agent narration and no result surface;
- unknown official Agent/tool/field names;
- missing failure, credit, interruption, or retry examples;
- quality attributes that cannot be judged from still images.
