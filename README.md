# cooking-skills

Agent Skills for organizing recipes from Xiaohongshu into an Obsidian vault.

These skills follow the [Agent Skills specification](https://agentskills.io/specification).

## Installation

### Claude Code

```
/plugin marketplace add zeshuochen/cooking-skills
/plugin install cooking@cooking-skills
```

### Manually

Clone this repo and point Claude Code to it, or copy the `skills/` directory contents into your skills path.

## Skills

| Skill | Description |
|-------|-------------|
| [整理食谱](skills/整理食谱) | 从小红书链接提取食谱，整理成标准格式保存到 Obsidian 食谱库 |

## Configuration

The skill assumes the following Obsidian vault setup:

- **Vault path**: `E:\Obsidian\ob库\电脑仓库`
- **Recipes folder**: `Atlas-Knowledge/厨艺/`
- **Index file**: `Atlas-Knowledge/厨艺/0 食谱.md`

Modify the `SKILL.md` to match your own vault path if different.
