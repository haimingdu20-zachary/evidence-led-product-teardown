# Standalone HTML report

Use when the user asks for an HTML visualization, an interface-like report, or a downloadable/openable document.

## 1. File and scope

- Create one standalone `.html` file at an authorized writable path.
- Use a descriptive product/mode/Agent filename.
- State clearly that the report is evidence-led analysis, not an official product document.
- Provide a direct clickable absolute file link in the final response.

## 2. Information architecture

Follow the user's requested section order. Recommended shell:

- title, scope badge, generated date;
- sticky table of contents;
- evidence gaps near the top;
- collapsible or scannable evidence/contract sections;
- diagrams and tables with evidence IDs adjacent to nodes/rows;
- unresolved questions and stopping point at the end.

For a long functional-equivalent prompt, provide a dedicated copy button and preserve whitespace in a readable code/prompt panel.

## 3. Visual semantics

Use consistent chips/colors for:

- 页面事实 / 事实规则;
- 合理推断 / 推断规则;
- 尚未确认 / 未知;
- 建议规则;
- conflict/error;
- normal, correction, and failure paths.

Do not rely on color alone; include visible text labels.

## 4. Diagrams

- Include evidence IDs inside or beside every substantive node.
- Use diamonds for decisions and label all branches.
- For journey maps, retain the required user/interface/system swimlanes.
- For Agent maps, show input → judgment → tool → output → handoff and note capability boundaries.
- For state machines, show failure, retry, interruption, and confirmation transitions only when evidenced or explicitly labeled as proposed.
- If Mermaid rendering depends on an external CDN, include the readable Mermaid source or an HTML fallback so the report remains understandable offline.

## 5. Usability and accessibility

- Support desktop, tablet, and mobile widths.
- Use semantic headings, tables, buttons, and adequate contrast.
- Make wide tables horizontally scrollable.
- Add print styles and a print button when useful.
- Avoid tiny text and fixed-height content that clips long evidence.
- Keep source paths readable without flooding the main narrative.

## 6. Validation

Before delivery, verify:

- file exists and is non-empty;
- required sections and evidence IDs are present;
- HTML IDs are unique;
- inline JavaScript parses;
- no scaffold TODOs remain;
- responsive/print CSS exists when promised;
- all direct local links use absolute paths;
- the page does not claim unsupported completion or official provenance.

If visual browser inspection is available and the page is complex, open the local file and check layout at representative desktop and narrow widths. Do not mutate the product under analysis during report QA.

