# cooking-skills

**Agent Skills for turning Xiaohongshu recipe videos into structured Obsidian notes.**

> Follows the [Agent Skills specification](https://agentskills.io/specification) — works with Claude Code, Codex CLI, and any skills-compatible agent.

---

## Skills

| Skill | Description |
|-------|-------------|
| [recipe-organizer](skills/recipe-organizer) | Fetch recipes from Xiaohongshu links, extract ingredients & steps, and save clean notes to your Obsidian vault |

---

## Installation

### Claude Code

```
/plugin marketplace add zeshuochen/cooking-skills
/plugin install cooking@cooking-skills
```

### Manual

Clone this repo into your Claude plugins cache, or copy the `skills/` directory to your agent's skills path.

---

## How it works

Just share one or more Xiaohongshu links and say "organize recipe" (or "整理食谱"). The skill will:

1. **Fetch** — open each link in Chrome and extract the post body and comments
2. **Classify** — distinguish recipe posts from technique videos (e.g. deboning demos); merge techniques as steps into the related recipe
3. **Write** — create a structured Markdown note in your Obsidian vault
4. **Index** — append a wikilink to your recipe index file

### Output format

```markdown
# 菜名：Cola Chicken Legs

> **描述**：Sweet, sticky, and deeply savoury — a crowd-pleasing one-pan rice topper.
> **准备时间**：15 min | **烹饪时间**：20 min | **份量**：2 servings

## 食材清单
- [ ] Chicken legs: 2
- [ ] Cola: 330 ml
...

## 制作步骤
1. **Marinate**: ...
2. **Sear**: ...

## 小贴士
- Pat the chicken dry before searing for a better crust.

## 来源
- [可乐鸡腿饭](https://www.xiaohongshu.com/...)
```

---

## Configuration

Edit `skills/recipe-organizer/SKILL.md` to set your own vault path and folder structure:

```
Vault path:    E:\Obsidian\ob库\电脑仓库
Recipes folder: Atlas-Knowledge/厨艺/
Index file:    Atlas-Knowledge/厨艺/0 食谱.md
```

---

---

## 简介（中文）

**从小红书食谱视频一键生成结构化 Obsidian 笔记的 Agent Skill。**

只需发送小红书链接并说"整理食谱"，Claude 会自动：

1. 用浏览器打开链接，提取正文和评论区内容
2. 区分食谱帖和技巧视频（如去骨教程），将技巧合并进对应食谱步骤
3. 按统一格式写入 Obsidian vault
4. 更新食谱索引文件

### 安装

```
/plugin marketplace add zeshuochen/cooking-skills
/plugin install cooking@cooking-skills
```

### 配置

编辑 `skills/recipe-organizer/SKILL.md`，将 vault 路径改为你自己的路径即可。

---

## License

MIT © [zeshuochen](https://github.com/zeshuochen)
