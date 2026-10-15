# knows-you

> 越用越懂你 —— 但每一条关于你的结论，都必须可以被推翻。

An Agent Skill that builds a **revisable model of you** instead of a pile of remembered facts.
Plain Markdown, your machine, no database, no service.

Works with Codex, Claude Code, Cursor, OpenCode — any agent that reads the
[Agent Skills](https://agentskills.io/specification) format.

---

## 它跟别的记忆方案有什么不一样

大部分记忆项目回答的是"**记住什么**"：偏好、事实、项目背景，存进向量库或者数据库，下次检索出来。

这个 skill 回答的是另一个问题："**关于你的判断，凭什么成立？**"

它会给你维护一份可读的档案，但里面每一条关于你的结论都必须带着四样东西：

| 必须写 | 为什么 |
| --- | --- |
| **证据** | 至少两个独立观察，不能因为一句话就下结论 |
| **置信度** | `tentative` / `probable` / `confirmed`，明确知道自己有多确定 |
| **替代解释** | 至少一个。这条最关键 —— 它让条目保持可被推翻，而不是变成自我强化的故事 |
| **复查日期** | 到期重新看，不合的就改掉或删掉 |

再加上一条总则：**你的自我描述永远覆盖它的推断。** 你说不是，就是它错了。

## 为什么需要"替代解释"这一栏

一个安静描摹你的系统，最大的风险不是冒犯，是**自我强化**：它越用假设去解释你，
就越觉得假设是对的，最后你得到的不是一个懂你的助手，而是一个固执的印象。

所以这个 skill 不允许写"结论"，只允许写"目前最合理的猜测，以及它可能错在哪"。

## 四个 skill

| Skill | 作用 |
| --- | --- |
| `memory-recall` | 开始任务前读档案，只读需要的那几页，不加载整个库 |
| `memory-save` | 判断什么值得长期留下、什么绝对不能记，然后写进库里 |
| `memory-maintain` | 定期整理：去重、合并、退休过时条目、修正被推翻的假设 |
| `memory-uninstall` | 干净的卸载路径 |

## 库长什么样

一个 Obsidian 兼容的 Markdown 文件夹。纯文本，你能随时用任何编辑器打开、手改、删掉。

```
vault/
├── INDEX.md                     # 索引，一行一条
├── open-loops.md                # 没闭环的事
├── preferences/
│   ├── user-profile.md          # 短档案：沟通、工作方式、工具、期待
│   └── pref-psychological-hypotheses.md   # 关于你的假设（本项目的重点）
├── projects/
├── decisions/
└── lessons/
```

两条设计原则：

1. **档案必须短。** 它每次任务开始都会被读，塞满会拖累每一次对话。细节放在别的笔记里，档案只留一行摘要和链接。
2. **一切都可读可改。** 没有黑盒。你能看到它记住了什么，也能直接划掉。

## 心理侧写模块

这是它跟普通记忆工具差别最大的地方，也是需要你自己想清楚要不要开的部分。

默认行为：**主动记录，不逐条征求同意**（否则永远攒不出一个连贯的你），但受五条约束：

- 证据来自至少两个独立观察
- 每条必须写替代解释
- 每条带复查日期
- 不做诊断、不贴标签、不碰受保护特征
- 你的自述永远优先

### 伦理边界（请认真读这一节）

这套东西是给"**本人授权 agent 记录本人**"设计的。默认假设是：库的主人就是被记录的人。

请不要拿它给**第三方**建模 —— 你的同事、家人、客户、用户。那不是这个项目想做的事，
而且很容易变成"悄悄给人建模再拿捏他"的工具。技术上门是开着的，但请你自己关好它。

## 安装

```bash
# Codex
cp -R skills/* ~/.codex/skills/

# Claude Code
cp -R skills/* ~/.claude/skills/
```

或者用 skills CLI：

```bash
npx skills add <owner>/knows-you
```

然后告诉你的 agent 你的库放在哪，让它写进 `vault-path.txt`；或者直接建一个空文件夹，
让它按 `memory-save/references/memory-format.md` 里的规范初始化。

**重启 agent 之后生效。**

## 它不会做什么

- **不是数据库。** 没有向量检索、没有嵌入、没有云同步。就是文件和索引。
- **不记敏感信息。** 凭据、密钥、私聊内容、完整转录、原始日志，明确禁止入库。
- **不假装懂你。** 它保存的是标注了置信度的猜测，不是事实。

## 卸载

删掉 skill 文件夹即可。你的库是你自己的，它不会跟着走，也不会被删。

## License

MIT
