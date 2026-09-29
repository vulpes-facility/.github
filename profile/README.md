# vulpes facility

Tools that run work on GitHub, and the Claude Code plugins that drive them.

## Repositories

| Repository | What it does |
| --- | --- |
| [`gh-shapeup`](https://github.com/vulpes-facility/gh-shapeup) | Run [Shape Up](https://basecamp.com/shapeup) on GitHub Issues and Projects: a CLI for pitches, scopes, cooldowns and bugs, and an Action that draws each pitch's hill chart. |
| [`claude-plugins`](https://github.com/vulpes-facility/claude-plugins) | The `vulpes` marketplace of Claude Code plugins, such as `gh-shapeup` and `vwiki`. |

## Install

```
gh extension install vulpes-facility/gh-shapeup
claude plugin marketplace add vulpes-facility/claude-plugins
claude plugin install <plugin>@vulpes
```
