---
name: ui-clarity
description: "Simplify existing UI by removing redundant copy, repeated information, and unnecessary containers while preserving essential states and accessible interactions. Use for UI cleanup, reducing explanatory text, clarifying visual hierarchy, and progressive disclosure; not for framework migrations or a new visual identity."
---

# UI Clarity

Make the information people need to decide or act easier to find in an existing interface. Fewer words or cards are not an end in themselves.

## Scope

- For a review request, provide recommendations. For an implementation request, make the changes. Follow the scope and authorization established in the conversation; invoking this skill alone does not authorize commits, pushes, or deployments.
- Start with the existing components, design tokens, authentication, and data flow. Do not introduce packages or architecture changes solely to simplify the UI.
- Preserve the product's language, terminology, and translation keys. Respond in the user's language. Verify inaccurate terminology before correcting it.
- When the user applies this skill to a document or spreadsheet, use the same criteria for its sections, tables, rows, and columns. Keep the existing artifact workflow and format; this skill guides clarity, not file authoring mechanics.

## Understand the reader and task

Identify the intended reader, the decision or action they need to take, and the information they need for it. Infer these from the request and existing context before asking questions. Inspect the screen or artifact and relevant implementation. Do not infer data semantics or behavior from appearance alone.

For each explanation, ask: **Would removing this make the reader misjudge the result or prevent their next action?** If not, remove it. If it is necessary, keep it once, where it is most useful.

Classify each piece of copy or container by its purpose:

| Purpose | Treatment |
| --- | --- |
| Information needed to decide or act | Keep it readable where the decision happens. |
| Repetition of the same meaning and scope | Keep the most useful instance and remove the others. |
| Definitions or formulas needed occasionally | Move them into nearby help or an expandable section. |
| Internal commentary or material outside the reader's task | Remove it unless it changes the reader's decision or next action. |
| Explanation that contradicts behavior | Verify the data and behavior before correcting the wording. |

Do not remove a number merely because it appears in both a summary and a detail view. Keep both when they serve different purposes, such as comparison, navigation, or identifying the current scope.

Simplify the content selection before shortening sentences. Within the requested scope, remove unrelated items and group similar ones when their procedures and outcomes remain clear. Do not impose a fixed item count, merge independently meaningful results into one passing status, or treat a past user's preferred layout as a universal rule.

## Copy and interaction

- Name the content or action directly. Check whether decorative subtitles, repeated page names, and explanations that restate button labels add useful information.
- Let clear column headers, field labels, and controls explain familiar actions. Remove prose that only narrates them, such as where to enter a result, when the entry fields already make this clear. Keep instructions for unfamiliar steps.
- Do not add lists of excluded conditions, verification boundaries, or internal reasons merely to defend the work. If the task and labels already establish what is being assessed, omit those lists. Keep a qualification only when its absence would make a claim false or materially mislead the reader.
- Before removing instructions such as "Click a number to see details," make the interaction discoverable through link styling, button shape, or an appropriate icon. Do not rely on color alone.
- Keep guidance needed for unfamiliar steps, input formats, password requirements, or error recovery. Do not replace input labels with placeholders alone.
- Place reference material such as formulas, deduplication rules, and terminology near the relevant metric, available on demand. Group shared definitions under a clear label such as "How metrics are calculated."
- Help must not depend on hover alone. Support touch and keyboard access, provide an accessible trigger name, and verify closing behavior and focus return. Reuse suitable existing help components.

## Preserve meaning

- Errors, loading, pending results, partial aggregation, missing data, and zero are different states. Never present a failed or missing measurement as zero.
- Distinguish successful requests from successful outcomes. For example, an accepted message request is not a confirmed delivery.
- Separate the outcome from the method. Prefer a short result such as "Pass" over "Pass (automated)" when the method can be recorded once in the relevant evidence or method field. Never turn partial, pending, or unexecuted work into a pass by shortening its label.
- If a section's data scope differs from the active filter, say so in that section. Do not make all-time figures appear to describe the selected period.
- Distinguish refresh time from the time through which data is available. Keep delays and provisional states visible when they affect interpretation; do not bury them in help.
- Preserve units, ratio denominators, and deduplication rules. Do not turn distinct-user counts into a simple sum when those counts can overlap.
- Preserve the meaning of access requirements, required inputs, and consequential outcomes or costs even when shortening their descriptions.

## Visual hierarchy

- Remove nested cards or outer borders where headings and spacing already separate content. Keep table boundaries and grouping that aid comparison.
- Use existing typography, color, and spacing tokens. Do not hide visual clutter by making meaningful text smaller or lower contrast.
- Keep status colors consistent. Retain decorative colors and badges only when they communicate additional information.

## Examples of judgment

| Existing UI | Possible improvement | What must remain |
| --- | --- | --- |
| A table caption says "Click a number" | Style the numbers as links and remove the caption | Keyboard access and accessible names |
| Title, sidebar, and KPI repeat the same total | Keep it where it best supports comparison | Distinctions between totals with different scopes |
| A long formula precedes a chart | Move it into nearby help or collapsed metric definitions | Current delays and errors remain visible |
| One card ignores the selected period | Label that card "All time" | The difference between filter and data scope |
| Cards contain several more cards | Simplify with spacing and headings | Meaningful grouping and table readability |
| A customer test sheet lists every internal regression case | Keep task-relevant scenarios and place useful edge cases in reference data | Distinct outcomes and traceable verification results |
| Every result says "Pass (automated)" | Use "Pass" and record the method once in the verification record | The actual result and how it was established |
| Instructions repeat obvious table headers and already-clear task boundaries | Remove the repeated instructions and exclusion lists | Information needed to perform the task or interpret the result correctly |

## Verify the change

Check the affected screens with representative data and relevant states. Use viewport sizes supported by the project to inspect wrapping, truncated numbers, and primary actions. If filters, detail navigation, or help changed, verify their behavior and keyboard access.

For documents and spreadsheets, review the changed pages or ranges as the intended reader. Confirm that the next action remains clear, distinct results remain distinguishable, and necessary data and controls are preserved. Removing explanatory copy must not change underlying values or calculations.

If an existing test depends on removed explanatory text, update it to check the behavior or meaning that text supported. Do not introduce a new test framework for simple copy edits. Run relevant existing checks and builds, and state which conditions you could not verify directly.

Report what was simplified, what meaning was preserved, and what was verified.

## Inspiration

[Comwit's design methodology](https://library.comwit.io/template/llms.txt) informed the approach to reducing unnecessary explanation and visual repetition. Package installation and framework migration are outside this skill's scope. These instructions are self-contained; the reference does not need to be fetched on every use.
