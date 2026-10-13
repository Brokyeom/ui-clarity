# UI Clarity

An agent skill for simplifying existing product interfaces. Remove redundant copy and visual clutter while preserving information people need to act: errors, data scope, accessible controls, and meaningful states.

## Use it

```text
Use $ui-clarity to remove unnecessary explanations and repeated information from this dashboard.
```

```text
Use $ui-clarity to review this login screen and suggest improvements. Do not edit it yet.
```

The skill refines an existing UI. It does not prescribe a new brand, framework migration, or component library. Instructions are maintained in English; the agent should preserve the product's language and respond in the user's language.

## Install

This repository is a single skill folder. Clone it as `ui-clarity` into your agent's skill directory. Check any existing folder with that name before installing.

For Codex:

```sh
git clone https://github.com/Brokyeom/ui-clarity.git "${CODEX_HOME:-$HOME/.codex}/skills/ui-clarity"
```

Start a new session and invoke `$ui-clarity`. For other agents, use their supported skill discovery location.

## Files

- [SKILL.md](SKILL.md): decision rules, workflow, examples, and verification guidance
- [agents/openai.yaml](agents/openai.yaml): Codex display metadata and example prompt

## Inspiration

Inspired by [Comwit's design methodology](https://library.comwit.io/template/docs/migrate) and refined through UI cleanup work. This is an independent skill, not an official Comwit package. It requires no Comwit installation or architecture migration and contains no client-specific code, data, or credentials.
