# 📄 论文区 · 精读卡片集

> **12 篇 2025–2026 精选论文**，每篇一张"精读卡片"：元信息 / 一句话结论 / 问题背景 / 方法要点 / 关键结果 / 与 RSI 的关系 / 解读与批判。
> 覆盖综述(1)、理论(3)、方法(7)、工程原型(1)。所有元信息均已核验（arXiv/NeurIPS/ACL/ModelScope 官方页面）。

## 精读卡片索引

| # | 论文 | 年份/venue | 主题 | 卡片 |
|---|---|---|---|---|
| P01 | **Recursive Self-Improvement in AI: From Bounded Self-Refinement to Autonomous Research Loops** | 2026-07 / arXiv:2607.07663 | 综述(1250篇) · 双轴分类 | [📄 打开](cards/P01_RSI综述_2607.07663.md) |
| P02 | **Self-Improving AI Agents through Self-Play** | 2025-12 / arXiv:2512.02731 | 理论 · GVU 统一算子 | [📄 打开](cards/P02_GVU_2512.02731.md) |
| P03 | **Gödel Agent: A Self-Referential Agent Framework for Recursive Self-Improvement** | 2024-10 / ACL 2025 (Long) + arXiv:2410.04444 | 方法 · 自参考重写 | [📄 打开](cards/P03_GoedelAgent_2410.04444.md) |
| P04 | **LADDER: Self-Improving LLMs Through Recursive Problem Decomposition** | 2025-03 / arXiv:2503.00735 | 方法 · 自引导分解+TTRL | [📄 打开](cards/P04_LADDER_2503.00735.md) |
| P05 | **Toward Training Superintelligent Software Agents through Self-Play SWE-RL (SSR)** | 2025-12 / ICML 2026 + arXiv:2512.18552 | 方法 · 自我博弈(软件) | [📄 打开](cards/P05_SSR_2512.18552.md) |
| P06 | **Language Self-Play For Data-Free Training (LSP)** | 2025-09 / arXiv:2509.07414 | 方法 · 零数据自我博弈 | [📄 打开](cards/P06_LSP_2509.07414.md) |
| P07 | **Triplets Better Than Pairs (T-SPIN)** | 2025-12 / NeurIPS 2025 + arXiv:2601.08198 | 方法 · 稳定自我博弈 | [📄 打开](cards/P07_TSPIN_2601.08198.md) |
| P08 | **Why Self-Rewarding Works: Theoretical Guarantees for Iterative Alignment** | 2026-01 / arXiv:2601.22513 | 理论 · 自我奖励 | [📄 打开](cards/P08_SelfRewardingTheory_2601.22513.md) |
| P09 | **Self-Reference in LLMs: The Introspection Threshold for RSI** | 2026-07 / arXiv:2607.04277 | 理论 · 内省阈值(退化) | [📄 打开](cards/P09_内省阈值_2607.04277.md) |
| P10 | **Will Compute Bottlenecks Prevent an Intelligence Explosion?** | 2025-07 / arXiv:2507.23181 | 理论 · 算力瓶颈 | [📄 打开](cards/P10_算力瓶颈_2507.23181.md) |
| P11 | **Reflect, Retry, Reward: Self-Improving LLMs via RL** | 2025-05 / arXiv:2505.24726 | 方法 · 自反思+GRPO | [📄 打开](cards/P11_ReflectRetryReward_2505.24726.md) |
| P12 | **NeoHorse-1: RSI via Agentic Post-Training with Routing Harness** | 2026-09 / arXiv:2609.08183 | 方法 · harness 闭环（4B:+5.93） | [📄 打开](cards/P12_NeoHorse1_2609.08183.md) |

## 阅读路径建议

- **只要时间读 1 篇** → P01（领域地图）
- **理解 RSI 统一理论** → P02（GVU）→ P08（自我奖励理论）→ P09（内省阈值）
- **看工程自改进怎么做** → P04(LADDER) → P06(LSP) → P05(SSR) → P11
- **看业界工程闭环原型** → P12（NeoHorse，harness 中介 RSI）→ 复刻解析见 [代码区 04](../代码/04_NeoHorse1_复刻与解析.md) → [金融应用](../金融应用/README.md)（怎么复刻）
- **看安全争论** → P09 + P10

## 分类速览表

| 类别(方法族) | 卡片 |
|---|---|
| 综述/分类 | P01 |
| 自我指涉/自参考重写 | P03 |
| 自精修/自引导学习 | P04, P11 |
| 自我博弈 | P05, P06, P07 |
| 自我奖励 | P08 |
| harness 闭环工程原型 | P12 |
| 理论边界 | P09(退化), P10(爆炸) |

## BibTeX

全部条目见 [references.bib](references.bib)（key 规则：`作者首姓+arXiv尾号`，可直接导入 Zotero/EndNote）。

## 引用约定

本库中引用风格：`[P0X]` 指本区卡片编号；纯 arXiv 编号直接给出（如 arXiv:2607.07663）。