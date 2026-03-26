# recipe-organizer

**从小红书、哔哩哔哩、YouTube 食谱视频一键生成结构化 Markdown 笔记的 Agent Skill。**

> 遵循 [Agent Skills 规范](https://agentskills.io/specification)，支持 Claude Code、Codex CLI 及所有兼容 skills 的 agent。

[English](README.md)

---

## Skills

| Skill | 描述 |
|-------|------|
| [recipe-organizer](skills/recipe-organizer) | 从小红书、YouTube、哔哩哔哩抓取食谱，提取食材与步骤，保存为本地 Markdown 笔记——自动识别中英文 |

---

## 安装

### Claude Code

```
/plugin marketplace add zeshuochen/recipe-organizer
/plugin install cooking@recipe-organizer
```

### 手动安装

克隆此仓库，将 `skills/` 目录复制到你的 agent 的 skills 路径下。

---

## 快速上手

1. **配置**保存路径，编辑 `skills/recipe-organizer/SKILL.md`：

```
SAVE_PATH=     # 笔记保存文件夹的绝对路径
```

2. **分享链接**，让 agent 整理食谱：

```
https://www.bilibili.com/video/...   整理食谱
```

3. 自动识别语言——中文链接输出中文笔记，英文链接输出英文笔记。

---

## 支持平台

| 平台 | 语言 | 备注 |
|------|------|------|
| 小红书 | 中文 | 步骤常在图片中，从评论和正文推断 |
| 哔哩哔哩 | 中文 | 简介和置顶评论为主要来源 |
| YouTube | 英文 | 简介栏通常含完整食材和时间戳 |

---

## 工作原理

1. **抓取** — 在 Chrome 中打开链接，提取正文、简介和评论
2. **分类** — 区分食谱帖与技巧视频（如去骨、切法），技巧内容合并为相关食谱的步骤或贴士
3. **写入** — 用对应语言的模板，在配置的文件夹中创建结构化 Markdown 笔记

---

## 输出示例

### 中文

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

---

## License

MIT © [zeshuochen](https://github.com/zeshuochen)
