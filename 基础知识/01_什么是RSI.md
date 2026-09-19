# 01 · 什么是 RSI（Recursive Self-Improvement）

## 1. 定义

**RSI（递归自我改进）** 指一个系统**不仅改进自身，还改进"改进自身的能力"**——改进过程本身成为被改进对象的一部分，形成正反馈加速回路。

> The concept of recursive self-improvement (RSI)—a system that not only improves itself but improves its capacity to improve itself—has been a central idea in the theory of artificial general intelligence. （[P09](cards/../论文/cards/P09_内省阈值_2607.04277.md)，arXiv:2607.04277 原句）

与普通"系统更新"的本质区别：**改进者与被改进者重合**（self-referential）。普通训练是一次性改进；RSI 中"改进算法"自身也在被递归重写。

## 2. 起源与因果链

理论源头（三个里程碑）：

| 时间 | 人物/文献 | 贡献 |
|---|---|---|
| 1965 | I. J. Good | "智能爆炸"假说：超智能机器能设计出更好的机器，形成正反馈 → `intelligence explosion` |
| 2003 | Jürgen Schmidhuber | **Gödel Machine**：可证明最优的自我改进通用问题求解器（RSI 的第一个形式化原型） |
| 2007 | Eliezer Yudkowsky | **Seed AI**：将 RSI 形式化为"改进自身"与"改进自身改进能力"两个层次 |

**因果链**（P09 论文的归纳）：

```
奇点(singularity) ←— 智能爆炸(intelligence explosion) ←— RSI ←— 自我指涉(self-reference)
```

即：自我指涉是 RSI 的底层机制，RSI 是智能爆炸的驱动机制，智能爆炸通往奇点。**这一链条中每一步的可靠性都是可质疑的**（见第 4 节与 03 篇）。

## 3. 与易混淆概念的区别

| 概念 | 是否 RSI | 区别 |
|---|---|---|
| **自精修**（Self-Refine / Reflexion） | ❌ 只是 RS 的片段 | 在推理时自我批评、自我修正输出，**不改进改进器的能力**，仍依赖外部评估 |
| **自我博弈**（Self-Play RL / SPIN / LSP） | ⚠️ 训练期片段 | 模型与自己对战生成训练信号；改进的是策略，改进算法通常固定 |
| **自我奖励**（Self-Rewarding LM） | ⚠️ 评估期片段 | 模型自己给回复打标生成偏好数据；本质是**把评估器也交给模型**，已接近闭环 |
| **持续学习**（Continual Learning） | ❌ | 学习新任务但通常不重写学习算法本身 |
| **自动化 AI 研究**（AI Scientist） | ⚠️ 研究过程闭环 | AI 做科研闭环（想idea→实验→写论文→评审），最接近"研究过程"轴上的开放端 |
| **真正 RSI**（开放端） | ✅ | 闭环内**连评估器/目标/改进算法一起改**（见 02 篇与 P09 的"内省阈值"） |

## 4. 2026 现状：从理论到工程的转变

**核心观点（P01 综述 + Anthropic 专题文章）：** RSI 的碎片已经成为工程实践，学界用"**AI 参与 AI 改进的自主度连续谱**"来描述：

```
人类写全部代码(2023前) → 聊天机器人辅助编码 → 自主编码智能体 → 智能体委派给智能体 → [全闭环]
                                                                           ↑ 现阶段最前沿
```

**标志性事件（2025–2026）：**

- **2026-02-05**：OpenAI 发布 GPT-5.3-Codex，发布说明首次明确承认"早期版本模型对创造自身起到了作用"（instrumental in creating itself）——AI 实质性参与了训练、部署、评估它自己后继版本的工程回路。
- **2026-05**：IEEE Spectrum 专题《Recursive Self-Improvement Edges Closer In AI Labs》——前沿实验室已出现自我改进雏形，但人类仍在环内。
- **2026-07**：CACM《Is Recursive Self-Improvement Really Here?》——对"前沿实验室自我改进是否为营销话术"的质疑与检验。
- **2026 学术爆发**：arXiv 上 2026 Q2 单季度约 500 篇自改进论文；ICLR 2026 设立 **"AI with Recursive Self-Improvement"** workshop。

**关键分层（P01，1250 篇综述）：** 绝大多数工作仍是"有界自精修"（人在环内）；**开放端 RSI（闭环连评估器一起改）才是安全风险集中点**。

## 5. 一句话总结

> RSI = 改进自身 + 改进"改进自身的能力"。2025–2026 年，它从 Good/Schmidhuber 的纯理论构想，变成了一半工程事实、一半安全争论的焦点领域。

---
**衔接**：方法体系见 [02_方法体系与分类.md](02_方法体系与分类.md)；退化/爆炸边界见 [03_理论边界与安全.md](03_理论边界与安全.md)