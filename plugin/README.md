# First Principles plugin for Claude Code

Adds a `/first-principles` command and a skill that breaks an idea down to first principles:
facts vs assumptions, a block diagram, market/product/customer checks marked for verification,
RICE scoring, a verdict, and a Markdown report saved to `first-principles/` in your project.

## Install from GitHub

```
/plugin marketplace add jayasaagar21/first-principles-studio
/plugin install first-principles@first-principles-studio
```

## Try a local copy

```
claude --plugin-dir ./plugin
```

Then:

```
/first-principles a solar-powered cold box for street vendors
```

The plugin only writes files into a `first-principles/` folder in the project you run it from.
