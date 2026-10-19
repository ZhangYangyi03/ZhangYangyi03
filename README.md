### Yangyi Zhang · 张洋溢

一个主张，在五个领域各测一遍：**一个数字，在它没通过自己的验证之前，不算结果。**

LLM agent 的工具调用安全验证 · 芯片 EDA 编排 · 化学动力学约简 · 机器学习评测审计 · 主权债务条款的可验证执行。

---

#### 主线

| 项目 | 它不接受的那个数字 |
|---|---|
| **[debt-verify](https://github.com/ZhangYangyi03/debt-verify)** | 一条债务条款"是否被触发"的结论——点值判定在 84 个可判单元全部有答案，但要求答案在已公布修订记录上仍成立之后，**75% 变得无法支持**。三值逻辑 (Kleene K3) + 分布式自由 conformal 区间 + P/NP-hard/PSPACE-hard 三分，3-SAT 归约与 z3 对拍 120/120 |
| **[autoforge](https://github.com/ZhangYangyi03/autoforge)** | 一个工具自己的适应度——独立 validity gate 把 oracle 和 fitness 定义权从被测工具手里收回。真模型干净消融：gate 开则完好率恒 3/3，关掉 4 代内退化到 0/3。已发布 PyPI，1176 项测试 |
| **[agentic-eda](https://github.com/ZhangYangyi03/agentic-eda)** | 一个电路的面积——必须先证明与参考网表等价（abc cec 给反例 / yosys equiv 要求 0 unproven）。13 策略 × 11 基准，最优 -30.1% 面积 / -61.2% 深度，全链路到 sky130 版图 |
| **[evidence-gate](https://github.com/ZhangYangyi03/evidence-gate)** | 一个模型的 AUC——同一份代码两个公共靶点，EGFR 全门通过，hERG 被驳回（换年代 0.453）。先跑标签置换阴性对照证伪管线，再谈分数 |
| **[tool-market](https://github.com/ZhangYangyi03/tool-market)** | 一个工具"活着"这件事——双轴正交状态机解耦"能否调用"与"哪个版本生效"，append-only 日志 + SHA-256 哈希链 |

#### 同一套骨架，换一个领域再测一遍

[eda-spine](https://github.com/ZhangYangyi03/eda-spine) 把 qoragent / assertforge / covagent 串成一条链：综合后的门级网表**必须仍满足**在 RTL 上已证的性质。
[kinetics-spine](https://github.com/ZhangYangyi03/kinetics-spine) 把这四段 (search / prove / perturb / cover) 指向一个完全不含 EDA 的领域，用守恒量当门——用来回答一个可测量的问题：**这四段是 EDA 的形状，还是任何可信搜索的形状。**

[**robot-spine**](https://github.com/ZhangYangyi03/robot-spine) 把同一副骨架指向运动：FK / IK / 胶囊碰撞 / 安全门，验证路径零依赖。它不接受的那个数字是「我的动力学方程是对的」——所以把这台臂交给**不是自己写的**引擎去算：49 个位姿上 `G(q)` 与 MuJoCo 的 `qfrc_bias` 差 **1.8e-15 N·m**，同一 PD 在两套 plant 上终点完全相同、**途中最大差 8.0e-3 rad**（积分器不同，如实分开报告）。单起点 IK 只到 **57%**，在多起点 100% 旁边一起印着，并在 CI 里断言它不许变好看。

#### 数据侧

- **[unifolm-wla-toolkit](https://github.com/ZhangYangyi03/unifolm-wla-toolkit)** — 按宇树 UnifoLM-WLA-1.0 官方规范实现的数据管线：54 维动作 / 60 维状态统一表示、SE(3) 相对位姿、零依赖 URDF 正运动学。不需要 GPU、真机、权重。15 步自检一条命令全过。规范里 7 处未定义的地方写成了[给宇树的说明](https://github.com/ZhangYangyi03/unifolm-wla-toolkit/blob/main/docs/note_to_unitree.md)。
- **[llm-safety-eval-audits](https://github.com/ZhangYangyi03/llm-safety-eval-audits)** — 三篇在审稿件的全部可重算数据。重算发现：被打分脚本的回退分支在 120 次试验里悄悄触发了 28 次；被当作真值的规则分类器在人工标注上只有 53% 正确，与 LLM 裁判原始一致率 61.6% 但 **kappa 仅 0.115**。
- **[craftagent](https://github.com/ZhangYangyi03/craftagent)** — 机床工况数据到异常归因，只用 Python 标准库（工厂那台机器上少一个依赖就少一个装不上的理由）。合成数据埋真值，5 项验收全过。

#### 研究向

- **[swpl](https://github.com/ZhangYangyi03/swpl)** — Skew-Phase Law：Zipf 负载下的数据结构选型，α = 1 处相变，ζ-Trie
- **[agent-safety-bench](https://github.com/ZhangYangyi03/agent-safety-bench)** — 多步 agent 安全合规基准，测的是"关键深度"而不是单轮拒答
- **[benign-rag-trap](https://github.com/ZhangYangyi03/benign-rag-trap)** — 无害查询如何经由分布外检索路径放大风险

---

#### 怎么找我

有关于 agent 工具治理、验证流水线、或者机器人数据格式的问题，开 issue 就行——主仓库的 issue 我都会看。
每个项目都写了**它不做的那件事**（debt-verify 检出的是"结论不被公布记录支持"，不是"债务国造假"；agentic-eda 会告诉你 11/11 基准仍带它修不了的签核违规）。这条边界是我的，不是免责声明。

<sub>Python · verification pipelines · LLM agent systems · EDA orchestration · numerical reproducibility</sub>
