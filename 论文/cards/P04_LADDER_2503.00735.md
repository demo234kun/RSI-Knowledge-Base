# P04 · LADDER: Self-Improving LLMs Through Recursive Problem Decomposition

## 元信息

| 字段 | 内容 |
|---|---|
| 标题 | LADDER: Self-Improving LLMs Through Recursive Problem Decomposition |
| 作者 | Toby Simonds, Akira Yoshiyama |
| 出处 | arXiv:2503.00735 (cs.LG/cs.AI)，v1 2025-03-02，v3 2025-03-05 |
| 类型 | 方法（自引导学习 + 测试时 RL, TTRL） |
| 链接 | [arXiv](https://arxiv.org/abs/2503.00735) |

---

## 一句话结论

> 提出 **LADDER**（Learning through Autonomous Difficulty-Driven Example Recursion）：LLM 通过**递归生成并求解越来越简单的原问题变体**来自主学习，无需人工标注/精选数据集——把 Llama 3.2 3B 的本科积分准确率从 **1% 提升到 82%**；配套的 **TTRL（测试时 RL）** 让 Qwen2.5-7B-R1 蒸馏版在 MIT Integration Bee 资格赛达到 **90%**，超越 OpenAI o1。

## 问题背景

- 传统自改进需要"精选数据 + 人工反馈"，是规模化的瓶颈。
- 关键洞察：**难度是天然的课程信号**——模型的"近端发展区"（能解但费劲）附近的变体可以自生成，不依赖外部标注。

## 方法

1. **递归问题分解（LADDER）**：
   - 给定难题 h，LLM 自生成一系列更简单的变体 h'（"把 x 换成更简单的形式"等），直到变体可解
   - 用"生成→解→回带（back-substitute）"链：解出简单变体的方法，逐步用于解决原题
   - 全程**自引导**：难度信号由模型自身产生，无人工参与
2. **TTRL（Test-Time RL）**：
   - 推理时对**测试题自身的变体**做强化学习（异于常见的训练期 RL）
   - 动态地"为当前题目现场自我打磨"

## 关键结果

| 实验 | 结果 |
|---|---|
| Llama 3.2 3B · 本科级积分 | 1% → **82%** |
| Qwen2.5-7B-DeepSeek-R1-Distill · MIT Integration Bee 资格赛 | **73%**（LADDER 后） |
| 同上 + TTRL | **90%**（SOTA，超过 OpenAI o1） |

- 结论定位："**不依赖架构扩展或人工监督的自导向策略学习**也能带来显著能力提升"——直击 RSI 的数据瓶颈论。

## 与 RSI 知识库的关系

- **"部署期自演化 + 测试时训练"方法族的强证据**（P01 分类：393 篇部署期类别；TTRL 是测试时训练子线索的代表）。
- 是"零/低人工数据自改进"路线的实证担当，与 P06（LSP 零数据）互为表里：LSP 拿掉数据，LADDER 拿掉难度标注。

## 解读与批判

- ✅ **优点**：a) 教学法直觉强（难度课程 + 近端发展区）且数据令人印象深刻（1%→82%）；b) TTRL 是"把自改进搬到推理时"的清新视角，有独立价值；c) 无需人工反馈，工程门槛低。
- ⚠️ **局限**：a) 领域集中在数学积分（可形式验证、变体生成容易），通用性未知；b) 变体生成质量依赖基础模型，弱模型先验差时"变体污染"风险未系统分析；c) 对比基线与超参细节论文报告有限，复现建议直接跑官方代码。

---

**相关卡片**：[P01 综述](P01_RSI综述_2607.07663.md) · [P06 LSP](P06_LSP_2509.07414.md) · [P11 反思RL](P11_ReflectRetryReward_2505.24726.md) · [返回目录](../README.md)