# 渐进式引导 · Stepwise Guide

一个面向 Codex 的中文引导技能：每次推进一个小步骤，解释正在解决什么、为什么这样做、结果意味着什么，等待用户理解或作出选择后再继续。

适用于知识学习、解题、论文与材料阅读、生活问题分析和旅行规划。

## 核心方式

- 先说明当前要回答的问题，再解释方法与操作。
- 每次只引入一个需要理解或决定的小步骤。
- 遇到疑问先澄清，不越过用户的卡点。
- 通过具体数据、公式解释或选项比较帮助理解。
- 用户说“下一步”后继续；说“直接给答案”“一次讲完”时调整节奏。
- 只在明确调用时启用，普通问答不自动套用。

## 安装

将本仓库中的 `SKILL.md` 和 `agents` 文件夹放入 Codex 的个人技能目录，文件夹名为 `stepwise-guide`：

```text
~/.codex/skills/stepwise-guide/
├── SKILL.md
└── agents/
    └── openai.yaml
```

Windows 默认对应 `%USERPROFILE%\.codex\skills\stepwise-guide\`；如自行设置了 `CODEX_HOME`，使用其下的 `skills/stepwise-guide/`。

也可以在尚未安装同名技能时使用 Git 克隆整个仓库：

```sh
git clone https://github.com/Doviedos316/stepwise-guide.git ~/.codex/skills/stepwise-guide
```

如已有同名技能，先检查并备份自己的修改，再更新文件。

## 使用示例

安装后，在对话中明确调用 `$stepwise-guide`，并提供目标及必要材料：

```text
使用 $stepwise-guide 带我阅读这篇论文的数据预处理部分。
先解释原始数据是什么，每次只推进一个步骤，等我理解后再继续。
```

```text
使用 $stepwise-guide 带我解这道题。
每一步说明我们要解决什么、为什么这样做，不提前给出完整答案。
```

```text
使用 $stepwise-guide 帮我规划一次三天旅行。
每次讨论一个决策，说明它怎样影响后续安排。
```

显示名称为“渐进式引导”，调用标识为 `stepwise-guide`。

## 对话节奏

| 用户回应 | 技能如何继续 |
|---|---|
| 理解了／下一步 | 推进一个新步骤 |
| 没懂／举个例子 | 缩小当前步骤或更换解释方式 |
| 理解了，但是…… | 先回答疑问 |
| 直接给答案／一次讲完 | 按最新要求调整 |
| 退出逐步模式 | 结束该模式 |

## 文件与边界

- `SKILL.md`：引导规则与使用范围。
- `agents/openai.yaml`：显示名称、默认提示词与仅明确调用的策略。
- 技能本身不附带执行脚本，也不自动创建学习记录。
- 理解确认不等于购买、预订、发消息等外部操作的授权。
- 使用效果取决于宿主对技能的支持；事实与计算仍需结合原始资料核验。

## License

[MIT](LICENSE) · Copyright (c) 2026 Doviedos316
