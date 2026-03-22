---
name: recipe-organizer
description: Fetch recipes from Xiaohongshu (小红书) links, extract ingredients and steps, and save structured notes to an Obsidian vault. Use when the user shares Xiaohongshu links and asks to organize recipes.
---

# Recipe Organizer

Fetch recipes from Xiaohongshu (小红书) posts, extract structured content, and save clean recipe notes to an Obsidian vault.

## Configuration

Update these paths to match your vault before using:

- **Vault path**: `E:\Obsidian\ob库\电脑仓库`
- **Recipes folder**: `Atlas-Knowledge/厨艺/`
- **Index file**: `Atlas-Knowledge/厨艺/0 食谱.md`

## Workflow

### Step 1 — Fetch page content

Use `mcp__claude-in-chrome__tabs_context_mcp` to get the current tab, create a new tab per link (`mcp__claude-in-chrome__tabs_create_mcp`), and navigate (`mcp__claude-in-chrome__navigate`).

- Try `mcp__claude-in-chrome__get_page_text` first for the main body text
- Fall back to `mcp__claude-in-chrome__read_page` (depth=5) if content is insufficient
- Note: Xiaohongshu video posts often have steps only in images — infer from comments and any visible text

### Step 2 — Analyse and consolidate

- Classify each link as a **recipe** or a **technique** (e.g. deboning, knife skills). Technique videos are not saved as separate notes; instead, merge their content as steps or tips into the related recipe.
- Extract: dish name, ingredients + quantities, steps, prep/cook time, serving size, tips
- Multiple links may combine into one dish (e.g. technique video + recipe video)

### Step 3 — Write the note

Use the `Write` tool to create `<vault>\Atlas-Knowledge\厨艺\<dish name>.md` in this format:

```markdown
# 菜名：[Dish Name]

> **描述**：[One-line description highlighting the dish's character]
> **准备时间**：[X min] | **烹饪时间**：[X min] | **份量**：[X servings]

## 食材清单
- [ ] [Ingredient]: [Quantity]

## 制作步骤
1. **[Step name]**: [Instructions]

## 小贴士
- [Key tips or cautions]

## 来源
- [Post title](xiaohongshu link)
```

### Step 4 — Update the index

`Read` the index file first, then use `Edit` to append at the end:

```markdown
## [[Dish Name]]
```

## Notes

- If quantities are not stated in the video, use reasonable estimates and add "adjust to taste" in tips
- Bold every step name for scannability
- Always keep the original Xiaohongshu link in the source section
- If multiple videos support one dish, list all links in the source section
