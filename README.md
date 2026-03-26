# recipe-organizer

**Agent Skill for turning recipe videos and posts into structured Markdown notes.**

> Follows the [Agent Skills specification](https://agentskills.io/specification) — works with Claude Code, Codex CLI, and any skills-compatible agent.

[中文](README.zh.md)

---

## Skills

| Skill | Description |
|-------|-------------|
| [recipe-organizer](skills/recipe-organizer) | Fetch recipes from Xiaohongshu, YouTube, or Bilibili, extract ingredients & steps, and save clean notes to a local folder — in English or Chinese |

---

## Installation

### Claude Code

```
/plugin marketplace add zeshuochen/recipe-organizer
/plugin install cooking@recipe-organizer
```

### Manual

Clone this repo and copy the `skills/` directory to your agent's skills path.

---

## Quick start

1. **Configure** your save path in `skills/recipe-organizer/SKILL.md`:

```
SAVE_PATH=     # absolute path to the folder where notes will be saved
```

2. **Share a link** and ask your agent to organize the recipe:

```
https://www.youtube.com/watch?v=...   organize recipe
```

3. The skill auto-detects language — share a Chinese link and get a Chinese note; share an English link and get an English note.

---

## Supported platforms

| Platform | Language | Notes |
|----------|----------|-------|
| Xiaohongshu (小红书) | Chinese | Steps often in images; inferred from comments |
| Bilibili (哔哩哔哩) | Chinese | Description + pinned comments |
| YouTube | English | Description box + pinned comments |

---

## How it works

1. **Fetch** — open each link in Chrome and extract the post body, description, and comments
2. **Classify** — distinguish recipe posts from technique videos (e.g. deboning demos); merge techniques as steps into the related recipe
3. **Write** — create a structured Markdown note in the configured folder using the matching language template

---

## Output examples

### English

```markdown
# Cola Chicken Legs

> **Description**: Sweet, sticky, and deeply savoury — a crowd-pleasing one-pan rice topper.
> **Prep time**: 15 min | **Cook time**: 20 min | **Serves**: 2

## Ingredients
- [ ] Chicken legs: 2
- [ ] Cola: 330 ml
- [ ] Light soy sauce: 1 tbsp
- [ ] Dark soy sauce: ½ tbsp
- [ ] Oyster sauce: 1 tbsp
- [ ] Starch: 1 tsp
- [ ] White sesame seeds: to garnish

## Steps
1. **Marinate**: Slice deboned chicken into 2 cm pieces, pat dry. Mix with soy sauces, oyster sauce, starch and a little oil. Rest 10 min.
2. **Sear**: Heat a little oil over medium heat. Stir-fry chicken until the surface is lightly charred.
3. **Braise**: Pour in cola (use half cola, half water if you prefer less sweet). Bring to a boil, then simmer 10 min.
4. **Finish**: Reduce the sauce slightly, sprinkle with white sesame seeds. Serve over rice.

## Tips
- Pat chicken dry before searing — it browns better and won't splatter.
- Half cola + half water gives a less sweet, more savoury result.

## Source
- [可乐鸡腿饭](https://www.xiaohongshu.com/explore/67e0ef8e000000001e00b1f8)
```

### Chinese

```markdown
# 菜名：可乐鸡腿饭

> **描述**：香甜浓郁的拌饭神器，鸡腿肉焦香入味，可乐赋予独特甜香，厨房小白也能轻松搞定。
> **准备时间**：15分钟 | **烹饪时间**：20分钟 | **份量**：1-2人份

## 食材清单
- [ ] 鸡腿：2个
- [ ] 可乐：1罐（330ml）
- [ ] 生抽：1汤匙
- [ ] 老抽：半汤匙
- [ ] 蚝油：1汤匙
- [ ] 淀粉：1茶匙
- [ ] 白芝麻：适量（装饰用）
- [ ] 食用油：少许

## 制作步骤
1. **去骨切块**：鸡腿去骨后切成约2cm小块，用厨房纸擦干水分。
2. **腌制**：加入生抽、老抽、蚝油、淀粉，抓匀后喷少许油，腌制10分钟。
3. **煎制**：锅中少量油热后，中火下入鸡腿肉，翻炒至表面微焦上色。
4. **焖煮**：倒入可乐（怕太甜可半可乐半开水），大火烧开后转小火焖煮10分钟。
5. **收汁**：开盖略微收汁，撒上白芝麻，浇在米饭上即可。

## 小贴士
- 鸡腿肉一定要擦干水分，煎时不溅油、更容易上色。
- 半可乐半开水口味更清爽，不那么甜腻。

## 来源
- [可乐鸡腿饭](https://www.xiaohongshu.com/explore/67e0ef8e000000001e00b1f8)
- [30秒鸡腿去骨技巧](https://www.xiaohongshu.com/explore/67518a240000000002029feb)
```

---

## License

MIT © [zeshuochen](https://github.com/zeshuochen)
