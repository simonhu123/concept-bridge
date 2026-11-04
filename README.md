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

*节选自一次真实学习记录，论文是 Hinton & van Camp（1993），“（……）”表示有省略。学习者此前被问到是否了解平均值、概率和神经网络。*

> **学习者：** 完全不清楚
>
> **导师：** 好，那我们从零开始。第一个问题是为什么神经网络会“背答案”。要回答它，得先花一分钟知道神经网络大概是个什么东西。
>
> 想象一台机器，上面有很多旋钮。你从一头喂进去一个数字（比如“今天的气温”），它从另一头吐出一个数字（比如“冰淇淋能卖几支”）。旋钮拧到不同位置，吐出来的结果就不同。（……）
>
> **生活故事：手抖的画**
>
> 回到发电报的故事。你要教朋友的那张图，是你手画的一条波浪线，然后在线上点了 20 个点。可你画的时候手有点抖，所以每个点都比真正的波浪线稍微偏高或偏低一点。
>
> 现在有两种学生在学这张图：
>
> 学生 A 把 20 个点的位置一个不差地背下来，连手抖造成的歪斜也一起背了。考他这 20 个点，他满分。
>
> 学生 B 只记住“大概是一条往上走的波浪线”。考这 20 个点，他每个都差一点点。（……）
>
> **专业定义：** 过拟合（overfitting）指模型把训练数据里的噪声也当成规律学了进去，结果在训练数据上表现很好，在新数据上表现变差。（……）
>
> **这个类比的局限：** 现实中的神经网络不是故意“背”的，它只是在调旋钮让误差变小。另外，真实数据的噪声也不一定都是“手抖”这么简单。（……）
>
> **小问题：** 一个学生把去年考卷的答案全背下来了，去年的题他门门满分。今年换了题，他考得一塌糊涂。他像故事里的学生 A 还是学生 B？为什么？
>
> **学习者：** 像故事里的a，因为他只是背答案，没有学习原理
>
> **导师：** 答对了，就是这个意思：背住了答案，没学到原理。

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

上传后，在 Claude 浏览器插件里也能用：打开论文页面，新开一个对话，说“用 concept-bridge 技能，带我学当前页面这篇论文”。

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
