# P03 · Gödel Agent: A Self-Referential Agent Framework for Recursive Self-Improvement

## 元信息

| 字段 | 内容 |
|---|---|
| 标题 | Gödel Agent: A Self-Referential Agent Framework for Recursive Self-Improvement |
| 作者 | Xunjian Yin, Xinyi Wang, Liangming Pan, Li Lin, Xiaojun Wan, William Yang Wang |
| 出处 | **ACL 2025 主会长文** + arXiv:2410.04444（v4, 2025-05-31） |
| DOI | 10.18653/v1/2025.acl-long.1354 |
| 类型 | 方法（自参考智能体框架） |
| 链接 | [arXiv](https://arxiv.org/abs/2410.04444) \| [ACL Anthology](https://aclanthology.org/2025.acl-long.1354/) |
| 开源代码 | Arvid-pku/Godel_Agent（223★，见代码区） |

---

## 一句话结论

> 提出了**第一个完全自我指涉的智能体框架**：受 Gödel Machine 启发，让智能体在运行时**递归重写自己的代码**（包括自己的"改进算法"），实现自感知（self-awareness）、自修改（self-modification）、递归自改进（RSI）。

## 问题背景

- 手工设计智能体：依赖人类专家，范围受限、劳民伤财。
- 元学习优化智能体：优化算法固定，搜索空间被锁死。
- **缺口**：两类方法都把"改进算法" I 当作固定参数，无法做到真正的自参考改进。

## 方法：自我指涉学习算法

**核心记法（Gödel Agent 的递归更新）：**

```
π_{t+1}, I_{t+1} = I_t(π_t, I_t, r_t, g)
```

- `π_t`：当前策略（policy），`I_t`：当前（元）学习算法，`r_t = U(E, π_t)`：环境反馈（效用），`g`：高层目标
- **关键**：每轮更新同时产出新的策略**和新的学习算法**——即"改进者改进了改进者本身"（这就是 RSI 的定义式）。

**实现（monkey patching 方法）：**

- 用 Python 运行时"猴子补丁"实现运行时内存交互 → 自感知与自修改
- 算法骨架（Algorithm 1）：`SELF_INSPECT`（读取全部自身代码）→ 计算初始性能 `r` → `SELF_IMPROVE(π, s, r, g)` 递归调用
- `I_0 = (f_0, o_0)`：决策函数（LLM 决定动作序列）+ 执行函数（执行并更新策略）互为递归
- 四类基本动作：读取/修改自身代码、执行、记录（论文定义的 action space）

## 关键结果

- 在数学推理与复杂智能体任务上**持续自改进**（连续多轮迭代性能上升，优于随机采样基线）。
- 证明可行性：把 2003 年 Schmidhuber 的 Gödel Machine 理论在 LLM 时代"落地"为可运行的 agent 代码。

## 与 RSI 知识库的关系

- **"自我指涉/自参考重写"方法族的代表实现**（P01 分类：轴一=策略+评估器，轴二=高闭合度端）。
- 与本库 P09（内省阈值）直接咬合：Gödel Agent 的递归重写是"内省程序"的工程雏形——但按 P09 的观点，若自建模能力不足，这种递归会退化而非复合。

## 解读与批判

- ✅ **优点**：a) 形式化漂亮——`π, I` 同时递归更新的式子一句话说清了 RSI 的定义；b) 首次用 LLM 实现"自参考代理"，具有示范意义；c) ACL 长文 + 开源实现，可复现。
- ⚠️ **局限**：a) monkey patching 是"实现自修改"的方式之一，但由此引入的运行时风险/不可恢复性没有被系统评估；b) 论文报告的是持续改进，缺理论保证（对照：Schmidhuber 原始 Gödel Machine 是可证明最优的——落地方案没有保留该性质）；c) 改进的"目标 g"仍由人给定，属"评估器固定"的半闭环，非终极开放端。

---

**相关卡片**：[P01 综述](P01_RSI综述_2607.07663.md) · [P09 内省阈值](P09_内省阈值_2607.04277.md) · [返回目录](../README.md) · 代码区：[Gödel Agent 实现](../../代码/01_自参考与自修改框架.md)