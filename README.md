# Arch PR Authoring for Cursor

A Cursor plugin that helps authors write PR descriptions with enough grounded product context for Arch to turn the description into useful goals later.

Built by [Foothill Labs](https://foothill.sh).

It combines an always-applied standing order with a narrowly scoped skill. The rule routes PR-authoring work to the skill.

## Install manually from GitHub

This installs the plugin for the current Cursor user and makes it available across all projects and repositories.

1. Clone the plugin into Cursor's local plugin directory:

```bash
mkdir -p ~/.cursor/plugins/local
git clone https://github.com/the-simulation-company/arch-cursor-plugin.git \
  ~/.cursor/plugins/local/arch-cursor-plugin
```

2. Restart Cursor or run **Developer: Reload Window**.
3. Open **Customize** and confirm that `arch-cursor-plugin` is available.

On managed Team or Enterprise workspaces, an administrator may need to enable **Allow Local Plugin Imports** first.

## What it adds

The skill grounds PR descriptions in the diff, relevant tests, and repository template, then captures:

- the user-visible change;
- affected pages and components;
- how to reach the behavior;
- required setup or state; and
- evidenced behavioral variants.

Human-authored and template sections are preserved. The skill traces relevant repository evidence before asking the author for context that is genuinely unavailable.
