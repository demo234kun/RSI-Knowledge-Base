# 💻 代码区 · 开源项目索引

> **2025–2026 年与 RSI 直接相关的开源项目**，分三个子区：自参考/自修改框架、自进化智能体、基础设施/安全/资源。
> 星级与创建时间为检索当日（2026-09）快照。所有仓库均已用 `gh repo view` 核验元数据。

## 文件索引

| 子区 | 内容 | 入口 |
|---|---|---|
| [01_自参考与自修改框架.md](01_自参考与自修改框架.md) | 智能体重写自身代码/策略/改进算法的框架（Gödel Agent、HyperAgents、DGM…） | 入门首选 |
| [02_自进化智能体.md](02_自进化智能体.md) | 通过经验/演化世界/技能池自进化的智能体与训练框架 | 数量最多 |
| [03_基础设施安全与资源.md](03_基础设施安全与资源.md) | 闭环传感器、红队/安全、可复现 AI4AI、资源大全 | 安全与研究 |

## 总览表（按星级排序）

| 项目 | ★ | 创建 | 语言 | 定位 | 子区 |
|---|---|---|---|---|---|
| sentrux/sentrux | 3.3k | 2026-03 | Rust | 实时架构传感器：帮智能体闭环代码质量 | [03](03_基础设施安全与资源.md) |
| facebookresearch/HyperAgents | 2.7k | 2026-03 | Python | 自我指涉自改进智能体（Meta AI，可优化任意可计算任务） | [01](01_自参考与自修改框架.md) |
| jennyzzt/dgm | 2.3k | 2025-05 | Python | Darwin Gödel Machine：开放式演化自改进智能体 | [01](01_自参考与自修改框架.md) |
| zhengkid/Dream-RSI | 846 | 2026-09 | Python | Dream-RSI：演化世界中的递归自改进 | [02](02_自进化智能体.md) |
| FrontisAI/OpenRSI | 719 | 2026-07 | Python | 可执行/可测量/可复现的 AI4AI（OpenMLE、Frontis-MA1） | [03](03_基础设施安全与资源.md) |
| TokenRhythm/NeoHorse | 625 | 2026-09 | Python | NeoHorse-1：路由 harness 的智能体后训练 RSI（arXiv:2609.08183，[P12](../论文/cards/P12_NeoHorse1_2609.08183.md)；模型：[ModelScope](https://www.modelscope.cn/models/TokenRhythm/NeoHorse-1-4B)） | [02](02_自进化智能体.md) |
| HITsz-TMG/KnowAct | 485 | 2026-07 | Python | RSI 个人助理 | [02](02_自进化智能体.md) |
| selfimproving-agent/Awesome-Self-Improving-Agents | 493 | 2025-12 | TeX | 基础模型智能体自改进论文清单（Nick/ThingumaJig 等学术路线） | [03](03_基础设施安全与资源.md) |
| AetherLabsAI/RSIAgent | 349 | 2026-09 | Python | 免训练多智能体 RSI：广-深自主探索 + 可复用记忆 | [02](02_自进化智能体.md) |
| lobehub/awesome-rsi | 270 | 2026-08 | — | RSI 研究地图：模型/智能体/harness/具身/自动研究/基准/安全 | [03](03_基础设施安全与资源.md) |
| Arvid-pku/Godel_Agent | 223 | 2024-10 | Python | **Gödel Agent 官方实现**（ACL 2025，P03） | [01](01_自参考与自修改框架.md) |
| KnowledgeXLab/EvolveR | 120 | 2025-09 | Python | (ICML 2026) 经验驱动生命周期的自进化 LLM 智能体 | [02](02_自进化智能体.md) |
| ShaoShuai0605/Misevolution | 98 | 2025-09 | Python | "Your Agent May Misevolve"官方实现：自进化涌现风险 | [03](03_基础设施安全与资源.md) |
| Gen-Verse/ScienceBuddy | 68 | 2026-09 | Python | 递归-内-递归自改进的科学交互智能体 | [02](02_自进化智能体.md) |
| keskival/recursive-self-improvement-suite | 55 | — | Python | AGI 无歧义基准：开放端非模仿任务套件 | [03](03_基础设施安全与资源.md) |
| lihouwenbin/ai-redteam-recursive-self-improvement | 35 | — | Python | RSI 治理的中立红队框架 | [03](03_基础设施安全与资源.md) |

## 快速上手建议

- **想看懂"智能体重写自己"** → 先跑 `Arvid-pku/Godel_Agent`（最简入口，论文 P03 的官方代码）
- **想看工程级 RSI 演化** → `jennyzzt/dgm`（Darwin Gödel Machine 2.3k★）
- **想研究安全风险** → `ShaoShuai0605/Misevolution` + `lihouwenbin/ai-redteam-recursive-self-improvement`
- **想找全量论文/项目地图** → `lobehub/awesome-rsi`（270★ 维护活跃）
- **想做可复现 AI4AI 研究** → `FrontisAI/OpenRSI`

## 说明

- 评分仅展示当日本快照；创建时间早于 2025 的项目（如 Godel_Agent 2024-10）因其论文发表于 2025（ACL 2025）且为方法源头而保留。
- 更多关联：基础知识/02 的方法族 ↔ 论文卡片 ↔ 本项目三列对照表。