# Concept Bridge（概念搭桥）

**没有专业基础，也能读懂一篇专业论文。**

Concept Bridge 是一个 Claude Skill，让 Claude 变成一对一的论文导师：先讲生活故事，再引出专业概念，确认你听懂了才往下走。

> 很多时候，你不是理解不了论文的逻辑，只是卡在了不懂的基础概念上。
> 不懂标准差，就很难理解 Layer Normalization；不懂概率分布，就很难理解贝叶斯神经网络。

[English](#english) · [快速开始](#快速开始) · [示例](#一段示例对话)

## 它和“论文总结”有什么不同

| | 常见的论文总结 | Concept Bridge |
|---|---|---|
| **目标** | 告诉你论文讲了什么 | 让你真正听懂 |
| **形式** | 一次输出一大篇 | 对话式，一次讲一个核心概念 |
| **遇到术语** | 附一句定义 | 从生活场景讲起，再对应到专业定义 |
| **缺少基础时** | 默认你已经会了 | 卡在哪里就补哪里，补完回到论文 |
| **没听懂时** | 把内容再看一遍 | 换一种方式重新讲 |
| **如何确认学会** | 没有确认环节 | 用一个生活化的小问题检验 |

## 教学路线

```text
生活故事 → 白话解释 → 专业概念 → 原理机制 → 论文应用 → 理解验证
```

- **问题驱动：** 每个新知识都由一个问题引出，你始终知道为什么要学它。
- **生活化故事：** 尽量沿用同一个故事，并主动说明类比在哪里不再成立。
- **随用随补：** 不用先学完数学和统计，真正卡住时才补，而且只补当前需要的部分。
- **循序渐进：** 你说“继续”就接着讲，说“没懂”就换一种讲法，选中一段文字就讲这一段。
- **理解验证：** 讲完重要概念问一个小问题，不搞考试，也不为提问而提问。
- **忠于论文：** 区分论文原意、背景补充和教学类比；公式代入小数字走一遍；结论说明成立条件。

## 一段示例对话

*以下是为说明教学风格而写的示意，不是真实运行记录。*

> **你：** Layer Normalization 里的“除以标准差”是什么意思？我没学过统计。
>
> **导师：** 想象两个班考试，平均分都是 80。A 班的分数都在 78 到 82 之间，B 班从 50 到 100 都有。平均分一样，分数的分散程度却差很多。**标准差**就是衡量这种分散程度的数字：A 班小，B 班大。
>
> 把分数减去平均分，再除以标准差，就像换了一把统一的尺子：不再看“考了多少分”，而是看“比平均水平高出几个标准差”。
>
> **回到论文：** Layer Normalization 对同一层神经元的输入总和做类似的事，让这一层的数值保持在稳定的范围内。
>
> **类比的局限：** 考试是在比较一群学生，而 Layer Normalization 是针对单个训练样本，在同一层的神经元之间计算。
>
> 问你一个小问题：同样考 85 分，在 A 班和 B 班，哪边更突出？为什么？
>
> **你：** A 班吧，大家的分数都挤在一起，85 分很显眼。
>
> **导师：** 对，你已经抓住标准差的直觉了。下一个问题是：神经网络为什么需要这把统一的尺子？

## 快速开始

### Claude Code

```bash
git clone https://github.com/simonhu123/concept-bridge.git ~/.claude/skills/concept-bridge
```

然后新开一个会话，输入：

```text
/concept-bridge path/to/paper.pdf
```

也可以直接说：“我没基础，带我读懂这篇论文：https://arxiv.org/abs/1607.06450”。

### claude.ai

1. 下载 [concept-bridge.zip](https://github.com/simonhu123/concept-bridge/releases/latest/download/concept-bridge.zip)。
2. 打开 **Customize > Skills**，点击 **添加 > 上传 Skill**，选择这个 ZIP。
3. 新开一个对话，发送论文，并说“用 concept-bridge 带我学这篇论文”。

## 适合谁

- **适合：** 想跨领域读论文的人、刚入门 AI 或科研的学生、被术语挡住的自学者。
- **不适合：** 只想要摘要、翻译、引用格式或文献综述，或者想润色自己的论文。这些需求有更合适的工具。

## 使用提醒

Concept Bridge 会尽量忠于论文，但 AI 仍可能出错。重要内容请回到原文核对，它也会告诉你值得回看哪些图、公式和小节。

## 参与改进

这是早期版本，欢迎通过 [Issue](https://github.com/simonhu123/concept-bridge/issues) 告诉我：

- 哪个故事让你一下子听懂了
- 哪里讲得太快，或者类比有误
- 还希望它支持什么样的论文

如果它帮你读懂了一篇论文，欢迎点个 ⭐，让更多被论文劝退的人看到它。

## English

**Understand a research paper with no background in the field.**

Concept Bridge is a Claude Skill that turns Claude into a one-on-one paper tutor. Instead of a summary, you get a conversation: a real-life story first, then the technical concept, then how the paper uses it, with a quick check that it landed before moving on. Missing prerequisites are filled in only when you actually get stuck.

The skill teaches in the language you use. Install it for Claude Code:

```bash
git clone https://github.com/simonhu123/concept-bridge.git ~/.claude/skills/concept-bridge
```

Then start a new session and try: `/concept-bridge path/to/paper.pdf`

## License

[MIT](LICENSE)
