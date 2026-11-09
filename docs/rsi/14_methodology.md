# 14｜检索范围、版本与证据说明

[返回总览](README.md) · [文献索引](13_bibliography.md)

## 1. 范围与纳入规则

检索核对日期为 **2026-11-09**。用户确认 RSI 指大模型与智能体的 Recursive Self-Improvement。资料覆盖概念起点、元学习、模型自训练、环境课程、支架优化、自修改代码、自动科研、评价与近期反面证据。

纳入条件是至少满足一项：提供自改进的重要机制；是理解该机制必要的基础/强基线；直接评价关键能力或失效；为文献组织提供有用框架。因而 ReAct、DPO、SWE-bench 等被纳入，但不被称为严格 RSI 算法。

本次收录 64 篇编号文献，其中 P54、P58 是综述，其余为研究论文、理论/观点文章或技术报告。没有按统一引用量门槛筛选，也没有计算文献总体中的覆盖率。“经典”是对基础性工作的阅读定位，不适用于每篇近期预印本。

## 2. 检索方法

先从 agent 与 RSI 的本地项目语境确定范围，再使用主题检索定位种子论文；核对 arXiv、会议论文页、出版社及作者/研究机构原始资料；对代码 RSI 与零数据学习重点检查正文；最后针对研究选题反向检索直接先例，补入 HGM 及近期评估论文。

实际检索词按以下主题展开，包含论文精确标题检索：

| 主题 | 代表关键词/标题 |
|---|---|
| 定义与理论 | recursive self improvement、Gödel Machines、AI-generating algorithms |
| 自训练 | STaR、Self-Instruct、Reinforced Self-Training、Self-Rewarding Language Models |
| 自课程 | Absolute Zero、R-Zero、Agent0、AgentEvolver、AgentGym |
| 支架与提示 | Reflexion、Voyager、DSPy、OPRO、TextGrad、GEPA、Promptbreeder |
| 自修改 | Self-Taught Optimizer、Automated Design of Agentic Systems、SICA、DGM、Hyperagents |
| 元能力先例 | metaproductivity、Metaproductivity-Performance Mismatch、budget matched evaluation |
| 评价与失效 | self-correction、reward overoptimization、model collapse、evaluator drift、streaming tasks |

这不是 PRISMA 式系统综述：未导出所有数据库结果、未去重统计全部候选、未做双人筛选、未获得所有论文的完整版本差异。搜索结果中的新闻、博客、论坛和聚合站仅可能作为发现线索，论文技术结论优先回到一手原文。

## 3. 阅读深度

索引使用两个标记：

- **A**：核对一手摘要/出版社概要与书目信息，必要时辅以会议页或原始研究页面。足以支持卡片的高层概述，不声称逐项审计方法与实验。
- **M**：除上述内容，还针对正文的相关方法、实验设置或局限段落作定向核对。**M 也不等于逐页全文精读或独立复现。**

| 编号 | 定向核对的重点 | 采用来源 |
|---|---|---|
| P18 | 出题/解题双角色、执行反馈、任务构造与初始化边界 | [AZR v1 正文](https://arxiv.org/html/2505.03335v1) |
| P19 | 多数票伪标签、难度筛选、质量随难度变化 | [R-Zero v1 §3 与分析](https://arxiv.org/html/2508.05004v1) |
| P32 | 父代选择、效用、50 题固定子集 | [SICA v2 §3–4](https://arxiv.org/html/2504.15228v2) |
| P33 | 档案与自修改、冻结改进器对照、分阶段子集评估 | [DGM v3 §3–4](https://arxiv.org/html/2505.22954v3) |
| P34 | 函数空间搜索、骨架、种群与评价器的适用条件 | [FunSearch 期刊正文](https://www.nature.com/articles/s41586-023-06924-6) |
| P49 | 递归数据替换/分布退化的论证范围及符号更正 | [模型坍塌正文](https://www.nature.com/articles/s41586-024-07566-y) |
| P51 | improvement@k、冻结元智能体测试、跨域继续改进的显著性 | [Hyperagents v1 §5.2–5.3](https://arxiv.org/html/2603.19461v1) |

其他卡片按 A 标记。对仅核对摘要的论文，避免引用未检查的实现细节、消融数字或理论保证。本文的研究启发和比较判断是综合分析，不能当作原作者逐字主张。

## 4. 年份与版本处理

优先记录首个公开年份，已核实的重要正式版本另注。年份排序不表示算法优先权；不同论文可能并行提出相似方法。

| 容易混淆的文献 | 处理方式 |
|---|---|
| Good | 保留常见 1965 引法与当前出版社 1966 记录的差异，不静默统一 |
| Gödel Machine | 以 2003 技术报告为主，说明存在后续章节标题 |
| AlphaZero | 采用 2017 arXiv 标题，不混入后续 Science 版标题与实验 |
| FunSearch | 2023 在线发表 / 2024 卷期 |
| TextGrad | 2024 arXiv 与 2025 Nature 题名不同 |
| Gödel Agent | arXiv 与 ACL 题名在 Recursive / Recursively 上不同 |
| STOP | 2023 首稿 / COLM 2024 |
| GEPA | 2025 首稿 / ICLR 2026 Oral |
| HGM | 2025 首稿 / ICLR 2026；human-level 的对照对象需保留 |
| Hyperagents | 当前摘要页为 v2；正文定向核对基于 v1，明确标注 |
| AgentEvolver | P55 是 arXiv:2511.10395，不混入 2026 年另一个同名系统 |

## 5. 数值与结论的使用原则

大多数卡片不列历史排行榜数字，因为模型、任务子集和预算不同，横向数值比较容易误导。保留少数直接影响理解的数字，例如 SICA 的 50 题子集、DGM 的分阶段设置，并在相关位置给出来源。

“论文报告提升”是作者实验结果的概述，不意味着本项目做过复现。这里没有运行任何模型训练、agent 搜索或论文基准，也没有验证作者发布代码能在当前环境直接运行。

理论结论要连同假设引用；摘要中出现“optimal”“zero data”“human-level”“open-ended”等词，不直接扩展成无条件结论。研究建议同样不构成新颖性保证。

## 6. 尚未系统覆盖的相邻文献

这版没有系统覆盖早期自修改策略与所有 Gödel Machine 后续理论、完整质量多样性/开放式学习史、全部 AutoML 与神经程序搜索、所有合成数据方法、形式定理证明、计算机操作/机器人基准，以及 2026 年每一篇 harness 演化预印本。

链式思考、树搜索推理、进化指令、自动工具生成和多智能体协作等大量相邻工作，可能是具体选题必需的背景，但并非仅因使用这些模块就构成 RSI。确定选题后，应按明确瓶颈补充这些文献，而不是继续无边界扩充目录。

## 7. 后续维护规则

新增论文沿用 P65 起编号，避免旧链接失效；记录首次公开时间、引用版本和阅读深度；单独写“它改变了哪一个已有结论”。发现新版本改变结果时，保留旧结果的版本说明，再更新卡片，不把不同版本的实验拼接成一个结果。

若要形成可投稿的正式综述，下一阶段应建立结构化数据库、完整检索式与筛选日志，并对核心论文逐项复核数据与实验；本套笔记可以作为这一工作的种子材料。
