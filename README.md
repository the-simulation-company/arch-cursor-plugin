# Arch PR Authoring for Cursor

A Cursor plugin that helps authors write PR descriptions with enough grounded product context for Arch to turn the description into useful goals later.

Published by [Foothill Labs](https://foothill.sh).

It combines an always-applied standing order with a narrowly scoped skill. The rule routes only PR-authoring work to the skill; ordinary coding work is unaffected. The plugin does not run QA, simulations, MCP tools, or any Arch workflow.

## Install

Clone the plugin into Cursor's local plugin directory:

```bash
git clone https://github.com/the-simulation-company/arch-cursor-plugin.git \
  ~/.cursor/plugins/local/arch-cursor-plugin
```

Restart Cursor or run **Developer: Reload Window**, then confirm the plugin under **Customize**. The same native package can be installed from Cursor Marketplace after marketplace review.

## What it adds

The skill grounds PR descriptions in the diff, relevant tests, and repository template, then captures:

- the user-visible change;
- affected pages and components;
- how to reach the behavior;
- required setup or state; and
- evidenced behavioral variants.

Human-authored and template sections are preserved. Missing facts are marked for the author instead of invented.

## Local verification

Run Cursor Agent with `--plugin-dir /absolute/path/to/arch-cursor-plugin`, or symlink the repository into `~/.cursor/plugins/local/arch-cursor-plugin`. Ask it to create or edit a PR description without naming the skill. Confirm that product context is added, the repository template is preserved, and no external QA action occurs.

Use [`fixtures/pr-description-cases.md`](fixtures/pr-description-cases.md) for the shared information-level behavior checks.
