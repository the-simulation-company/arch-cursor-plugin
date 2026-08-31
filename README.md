# Arch PR Authoring for Cursor

A Cursor plugin that helps authors write PR descriptions with enough grounded product context for Arch to turn the description into useful goals later.

Built by [Foothill Labs](https://foothill.sh).

It combines an always-applied standing order with a narrowly scoped skill. The rule routes PR-authoring work to the skill.

## Install

Clone the plugin into Cursor's local plugin directory:

```bash
git clone https://github.com/the-simulation-company/arch-cursor-plugin.git \
  ~/.cursor/plugins/local/arch-cursor-plugin
```

Restart Cursor or run **Developer: Reload Window**, then confirm the plugin under **Customize**.

## What it adds

The skill grounds PR descriptions in the diff, relevant tests, and repository template, then captures:

- the user-visible change;
- affected pages and components;
- how to reach the behavior;
- required setup or state; and
- evidenced behavioral variants.

Human-authored and template sections are preserved. The skill traces relevant repository evidence before asking the author for context that is genuinely unavailable.
