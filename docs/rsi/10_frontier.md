# 10｜2026 年前沿与综述入口

[返回总览](README.md) · 本章收录 P51–P54、P58、P62–P64。2025 首稿、2026 会议版本的 HGM 放在 [代码 RSI 章](07_recursive_agents.md#p61)。

以下是截至 2026-11-09 本次检索核实的近期工作，不是“已被时间检验的经典”，也不是 2026 年全部新论文。会议状态不明确时仅按预印本标注；论文结果不等于独立复现结果。

<a id="p51"></a>
## P51｜Hyperagents

**文献**：Jenny Zhang、Bingchen Zhao、Wannan Yang、Jakob Foerster、Jeff Clune、Minqi Jiang、Sam Devlin、Tatiana Shavrina，2026-03 首稿，2026-11 有 v2。[当前摘要页](https://arxiv.org/abs/2603.19461) · [本笔记核对的方法正文 v1](https://arxiv.org/html/2603.19461v1)。以下实验细节按 v1 说明，未逐项对比 v2 全文。

**问题**：DGM 依赖“更会写代码可能也更会改自己”的任务重合；如果目标是评审或机器人奖励设计，任务得分与自改能力未必一致。

**方法**：把 task agent 与 meta agent 放进同一个可编辑程序。元智能体不仅修改任务智能体，也可以修改产生后续改进的元程序；DGM-H 用开放式档案组织候选，研究跨领域元能力迁移。

**评价贡献**：improvement@k 衡量给定初始智能体与有限候选数时，元智能体能生成多好的后代。v1 §5.2 中冻结被测元智能体，以分离“当前元能力”与评估过程中继续变化的元能力；候选依据验证分数选择，再看测试收益。

**证据边界**：论文报告元改进策略的迁移与继续改进；但 v1 §5.3 中，从迁移智能体继续演化相对从初始智能体演化的一个比较，作者明确指出差异未达统计显著。不能概括为所有跨域累积比较都显著，更不能写成已证明无限加速。[相关实验正文](https://arxiv.org/html/2603.19461v1#S5.SS3)。

**连接**：是 [P33 DGM](07_recursive_agents.md#p33) 的明确扩展；与 [P29 STOP](07_recursive_agents.md#p29)、[P59 Promptbreeder](06_scaffolds.md#p59) 同样关注元机制；与 [P04 MAML](03_foundations.md#p04) 在“评估适应后的表现”上有概念关联。

**研究启发**：把候选数预算进一步换成总 token、评价成本或 GPU 时间预算；检验元能力迁移是否依赖共享底座、语言、工具和评价风格。

<a id="p52"></a>
## P52｜Generalized Agent Iteration: One Formal Framework for Iterative Policy Improvement and Recursive Self-Improvement

**文献**：Hongyao Tang、Yi Ma、Pengyi Li、Yifu Yuan，2026-09 首稿，2026-10 v2；形式框架预印本。[原文](https://arxiv.org/abs/2609.13406)。

**问题与框架**：RSI 是机制、现象还是未来展望？GAI 将智能体看作可修改组件的配置，把评价与改进组织成循环；重点区分改进机制是否属于智能体内部、评价标准是否保持外部锚定。

**贡献**：这两个维度有助于比较固定更新规则的策略迭代、机制可变的 RSI，以及目标漂移/完全自指的情况。其价值在于把混杂的主张拆成可讨论条件。

**边界**：统一表达不是所有系统都收敛或获得加速的证明。本文主要依据摘要核对，不转述未逐条核验的定理假设。

**连接**：重新组织 [P02 Gödel Machine](03_foundations.md#p02)、[P13 Self-Rewarding](04_self_training.md#p13) 与 [P51](#p51) 的边界问题；[P48](09_evaluation.md#p48) 解释为何内部目标变好未必代表外部质量提高。

**研究启发**：在自己的论文中显式列出可改组件、固定目标与外部审计器，比仅自称“完全自主 RSI”更容易形成可验证贡献。

<a id="p53"></a>
## P53｜Reflections on Trusting Trust, Revisited: Contaminating Self-Modifying AI Coding Agents with Poisoned Benchmarks

**文献**：Franziska Roesner、Tadayoshi Kohno，2026-09；预印本。[原文](https://arxiv.org/abs/2609.17817)。

**问题与实验**：若自修改智能体把有偏或恶意评测反馈写进自身实现，这种污染能否迁移到之后的正常任务？论文在 DGM 的实验修改版本、SICA 和 Hyperagents 上做概念验证，并研究污染在后续干净评测演化中的保留。

**贡献**：把风险位置从单次输出提升到“生成后代的软件机制”。这与普通提示错误不同，因为错误行为可能进入后续版本。

**边界**：证据针对指定实验、系统和污染条件；不能推断所有自修改系统都同等脆弱，或干净评测一定无法修复。

**连接**：与 [P48 奖励过优化](09_evaluation.md#p48) 共同说明反馈不等于真值；直接关联 [P32](07_recursive_agents.md#p32)、[P33](07_recursive_agents.md#p33)、[P51](#p51) 的持久更新链。

**研究启发**：可在隔离的玩具环境中研究错误反馈检测、版本溯源、独立测试与回滚有效性；衡量异常行为是否在干净任务上持续，而不是只看当前开发分数。

<a id="p54"></a>
## P54｜Recursive Self-Improvement in AI: From Bounded Self-Refinement to Autonomous Research Loops

**文献**：Mingguang Chen、Licheng Wang、Bo Qu，2026-07 首稿；综述预印本。[原文](https://arxiv.org/abs/2607.07663)。

**问题与框架**：self-refine、self-reward、self-play、self-evolve 容易把不同强度的目标混在一起。该综述按改进对象与闭环程度整理文献，并把评价器作为重要维度。

**用途**：适合从本笔记继续扩展检索，尤其是评价、验证与开放式研究循环的连接。摘要自述覆盖的论文数量是作者的检索规模，本笔记没有独立审计该数量，不将其作为本次覆盖率的分母。

**边界**：综述中的分类和判断属于作者框架，不是统一共识。它给出的验证层级应结合具体任务和规范质量理解，不能机械化为所有场景的绝对排名。

**连接**：横跨 [P22](06_scaffolds.md#p22)、[P13](04_self_training.md#p13)、[P33](07_recursive_agents.md#p33)、[P36](08_automated_science.md#p36)；与 [P58](#p58) 的系统组件分类互补。

**研究启发**：用它检索相邻研究，再回到被引用的原始论文核验结论，避免二手摘要层层放大。

<a id="p58"></a>
## P58｜Self-Improvements in Modern Agentic Systems: A Survey

**文献**：Zhe Ren 等，2026-07；综述预印本。[原文](https://arxiv.org/abs/2607.13104)。

**问题与框架**：现代智能体不只是模型权重。综述将基础模型与提示、记忆、工具、控制逻辑放进统一系统配置，并按更新对象与反馈来源整理自改进。

**用途**：适合检查自己的选题是否过度集中在参数更新或代码改写，遗漏记忆和工具等能力载体。

**边界**：其“自改进”范围比严格的元机制递归更广；被收录不意味着每个方法都已经实现 RSI。分类是一种分析工具，不能代替实验比较。

**连接**：可把 [P08–P20](04_self_training.md) 的模型学习与 [P21–P33](06_scaffolds.md) 的支架学习放在同一图中；与 [P52](#p52) 的系统边界讨论互补。

**研究启发**：写 related work 时先按“改什么”分类，再按“谁改、谁评、是否递归”比较，避免按论文年份罗列。

<a id="p62"></a>
## P62｜AgentStream: How Well Do Self-Evolving LLM Agents Perform Under Streaming Tasks?

**文献**：Dong Yan 等，2026；评估预印本。[原文](https://arxiv.org/abs/2608.00155)。

**问题与方法**：独立单任务评价无法体现经验不断积累时的影响。AgentStream 把任务组织成孤立、顺序和交错场景，比较不同自演化机制与模型的交互。

**证据与边界**：作者发现收益随模型和任务流变化，某种方法没有在所有组合上占优；这针对所研究配置，不是所有自演化方法的普遍排名。

**连接**：拓展 [P46 AgentBench](09_evaluation.md#p46) 的交互评估视角；直接关联 [P23 Reflexion](06_scaffolds.md#p23)、[P24 Voyager](06_scaffolds.md#p24) 的持久经验问题。

**研究启发**：把记忆污染、负迁移与任务顺序作为显式变量；新基准不能只声称“第一次评价任务流”，应说明相对 AgentStream 的新问题。

<a id="p63"></a>
## P63｜Self-Evolving Agents Can Repair Failures but Struggle to Generalize from Them

**文献**：Weixiang Zhao 等，2026-10；实证预印本。[原文](https://arxiv.org/abs/2610.22984)。

**问题与方法**：在没有积累经验、没有特权指导且只看到失败交互时，智能体是否能得到可迁移能力？论文通过 Cold-Start Failure-Only Evolution 设置研究这一问题。

**证据**：在多种方法、模型和环境上，修复已失败任务与改善未见任务存在差距。作者还讨论失败解释与正确经验迁移的困难。

**边界**：限制条件排除了很多常见正反馈来源，因此不能扩大为“任何经验学习都无法泛化”。加入成功轨迹、外部反馈后需要重新比较。

**连接**：为 [P23 Reflexion](06_scaffolds.md#p23) 的经验机制提供近期对照；与 [P41](09_evaluation.md#p41) 区分当前问题纠错与更广泛泛化。

**研究启发**：构造原失败题、同机制新题、不同机制新题三个测试层次，测量经验抽象的有效范围。

<a id="p64"></a>
## P64｜When Do Agent Loops Mistake Stagnation for Progress? Self-Evaluation Bias and Externally Grounded Verification in Long-Running Autonomous LLM Agent Loops

**文献**：Hyundoo Park、Byungho Choi，2026；预注册试点测量研究/预印本。[原文](https://arxiv.org/abs/2607.25152)。

**问题与方法**：系统反复声称“有所改善”时，外部状态是否真的变好？论文固定智能体与工具面，改变评价门控的信息渠道，比较自评、文本内裁判与访问外部状态的评价。

**证据与边界**：试点显示某些任务中自评接受的改动与真实进步分离；当成功标准可从产物本身验证时，情况不同。应保留这种任务边界，不将试点推断为所有任务上的结构性不可能结论。

**连接**：把 [P44](09_evaluation.md#p44) 的裁判偏差与 [P48](09_evaluation.md#p48) 的代理目标问题带入长循环；为 [P52 GAI](#p52) 的外部锚定提供相关实验问题。

**研究启发**：记录每次“接受更新”的真实净效果，测错误接受和错误拒绝率；分开评价门控信号与反馈解释内容的作用。

## 近期工作对选题的实际影响

到本次检索为止，“让智能体修改自身代码”或“让任务智能体与元智能体一起变化”已经有直接先例。若把这两个想法本身作为创新点，论证会很薄弱。更值得验证的是：如何以更低总成本获得可迁移元能力，如何识别真的有潜力的父代，以及怎样防止反馈偏差在代际间累积。

这不是新颖性检索的完成结论。具体选题仍应围绕方法关键词、指标和任务做进一步针对性检索；[11 研究议程](11_research_agenda.md) 给出可证伪的初始设计。
