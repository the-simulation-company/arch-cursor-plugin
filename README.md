# Arch PR Authoring for Cursor

A Cursor plugin that helps authors write PR descriptions with enough grounded product context for Arch to turn the description into useful goals later.

It combines an always-applied standing order with a narrowly scoped skill. The rule routes only PR-authoring work to the skill; ordinary coding work is unaffected. The plugin does not run QA, simulations, MCP tools, or any Arch workflow.

## Install

Install for one project:

```bash
mkdir -p .cursor/skills && \
  curl -sSL https://github.com/the-simulation-company/arch-cursor-plugin/archive/refs/heads/main.tar.gz \
  | tar -xz --strip-components=3 -C .cursor/skills 'arch-cursor-plugin-main/.cursor/skills'

mkdir -p .cursor/rules && \
  curl -sSL -o .cursor/rules/pr-qa-description-standing-order.mdc \
  https://raw.githubusercontent.com/the-simulation-company/arch-cursor-plugin/main/.cursor/rules/pr-qa-description-standing-order.mdc
```

For a global install, copy `.cursor/skills/pr-qa-description` into `~/.cursor/skills/`. Cursor global rules are configured in **Cursor Settings → Rules → User Rules**; paste the body of `.cursor/rules/pr-qa-description-standing-order.mdc` there.

## What it adds

The skill grounds PR descriptions in the diff, relevant tests, and repository template, then captures:

- the user-visible change;
- affected pages and components;
- how to reach the behavior;
- required setup or state; and
- evidenced behavioral variants.

Human-authored and template sections are preserved. Missing facts are marked for the author instead of invented.

## Local verification

Copy or symlink the `.cursor` contents into a test project, reload Cursor, and ask it to create or edit a PR description without naming the skill. Confirm that product context is added, the repository template is preserved, and no external QA action occurs.

Use [`fixtures/pr-description-cases.md`](fixtures/pr-description-cases.md) for the shared information-level behavior checks.
