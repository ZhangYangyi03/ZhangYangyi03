### Yangyi Zhang · 张洋溢

> **A number is not a result until it has passed its own verification.**
> **一个数字，在它没通过自己的验证之前，不算结果。**

LLM agent tool-use safety · chip EDA orchestration · chemical kinetics reduction · ML evaluation auditing · verifiable sovereign-debt covenants<br>
LLM agent 的工具调用安全验证 · 芯片 EDA 编排 · 化学动力学约简 · 机器学习评测审计 · 主权债务条款的可验证执行

**Featured / 代表作** · [autoforge](https://github.com/ZhangYangyi03/autoforge) · [agentic-eda](https://github.com/ZhangYangyi03/agentic-eda) · [unifolm-wla-toolkit](https://github.com/ZhangYangyi03/unifolm-wla-toolkit) · [debt-verify](https://github.com/ZhangYangyi03/debt-verify) · [agent-os](https://github.com/ZhangYangyi03/agent-os) · [robot-spine](https://github.com/ZhangYangyi03/robot-spine)

---

#### Main line / 主线

| Project | The number it refuses to accept | 它不接受的那个数字 |
|---|---|---|
| **[debt-verify](https://github.com/ZhangYangyi03/debt-verify)** | Whether a debt covenant *was triggered*. Point estimates answer all 84 adjudicable units — but once each answer must still hold against the published amendment record, **75% become unsupportable**. Kleene K3 three-valued logic + distributed free conformal intervals + P/NP-hard / PSPACE-hard trichotomy; the 3-SAT reduction is cross-checked against z3, 120/120. | 一条债务条款"是否被触发"的结论——点值判定在 84 个可判单元全部有答案，但要求答案在已公布修订记录上仍成立之后，**75% 变得无法支持**。三值逻辑 (Kleene K3) + 分布式自由 conformal 区间 + P/NP-hard/PSPACE-hard 三分，3-SAT 归约与 z3 对拍 120/120 |
| **[autoforge](https://github.com/ZhangYangyi03/autoforge)** | A tool's own fitness score. An independent validity gate takes the right to define the oracle and the fitness function away from the tool under test. Clean ablation on a real model: gate on, intact rate stays 3/3; gate off, it degrades to 0/3 within 4 generations. On PyPI, 1,176 tests. | 一个工具自己的适应度——独立 validity gate 把 oracle 和 fitness 定义权从被测工具手里收回。真模型干净消融：gate 开则完好率恒 3/3，关掉 4 代内退化到 0/3。已发布 PyPI，1176 项测试 |
| **[agentic-eda](https://github.com/ZhangYangyi03/agentic-eda)** | A circuit's area. Equivalence to the reference netlist must be proven first (`abc cec` returns counterexamples / `yosys equiv` requires 0 unproven). 13 strategies × 11 benchmarks, best −30.1% area / −61.2% depth, full flow down to sky130 layout. | 一个电路的面积——必须先证明与参考网表等价（abc cec 给反例 / yosys equiv 要求 0 unproven）。13 策略 × 11 基准，最优 -30.1% 面积 / -61.2% 深度，全链路到 sky130 版图 |
| **[evidence-gate](https://github.com/ZhangYangyi03/evidence-gate)** | A model's AUC. Same code, two public targets: EGFR passes every gate, hERG is rejected (0.453 across eras). Label-permutation negative controls run first to falsify the pipeline, before any score is quoted. | 一个模型的 AUC——同一份代码两个公共靶点，EGFR 全门通过，hERG 被驳回（换年代 0.453）。先跑标签置换阴性对照证伪管线，再谈分数 |
| **[tool-market](https://github.com/ZhangYangyi03/tool-market)** | Whether a tool is *alive*. A two-axis orthogonal state machine decouples "can it be called" from "which version is in effect"; append-only log with a SHA-256 hash chain. | 一个工具"活着"这件事——双轴正交状态机解耦"能否调用"与"哪个版本生效"，append-only 日志 + SHA-256 哈希链 |

#### The same skeleton, tested again in another domain / 同一套骨架，换一个领域再测一遍

[eda-spine](https://github.com/ZhangYangyi03/eda-spine) chains qoragent / assertforge / covagent into one pipeline: the post-synthesis gate-level netlist **must still satisfy** the properties already proven at RTL.

[kinetics-spine](https://github.com/ZhangYangyi03/kinetics-spine) points the same four stages (search / prove / perturb / cover) at a domain with no EDA in it, using conservation laws as the gate — to answer a measurable question: **is this four-stage shape the shape of EDA, or the shape of any trustworthy search?**

[eda-spine](https://github.com/ZhangYangyi03/eda-spine) 把 qoragent / assertforge / covagent 串成一条链：综合后的门级网表**必须仍满足**在 RTL 上已证的性质。

[kinetics-spine](https://github.com/ZhangYangyi03/kinetics-spine) 把这四段 (search / prove / perturb / cover) 指向一个完全不含 EDA 的领域，用守恒量当门——用来回答一个可测量的问题：**这四段是 EDA 的形状，还是任何可信搜索的形状。**

[**robot-spine**](https://github.com/ZhangYangyi03/robot-spine) — FK / IK / capsule collision / safety gate, with zero-dependency verification. The number it refuses to accept is "my dynamics equations are correct", so the arm is handed to an engine I did not write: across 49 poses, `G(q)` differs from MuJoCo's `qfrc_bias` by **1.8e-15 N·m**; the same PD controller reaches identical endpoints on both plants with **max deviation 8.0e-3 rad** en route (different integrators, reported separately). Single-start IK reaches only **57%** — printed next to the 100% from multi-start, and asserted in CI so it is not allowed to look better.

[**robot-spine**](https://github.com/ZhangYangyi03/robot-spine) 把同一副骨架指向运动：FK / IK / 胶囊碰撞 / 安全门，验证路径零依赖。它不接受的那个数字是「我的动力学方程是对的」——所以把这台臂交给**不是自己写的**引擎去算：49 个位姿上 `G(q)` 与 MuJoCo 的 `qfrc_bias` 差 **1.8e-15 N·m**，同一 PD 在两套 plant 上终点完全相同、**途中最大差 8.0e-3 rad**（积分器不同，如实分开报告）。单起点 IK 只到 **57%**，在多起点 100% 旁边一起印着，并在 CI 里断言它不许变好看。

#### Desktop & system / 桌面与系统那一侧（2026-10 新增）

Same thesis, moved to "can an AI actually take over your own machine".

同一个主张，换到"AI 能不能接管你自己的机器"这一层。

| Repo | The number it refuses to accept | 它不接受的那个数字 |
|---|---|---|
| **[agent-os](https://github.com/ZhangYangyi03/agent-os)** | The sentence "AI can get into everything" — split into nine layers from L0 microcode to L8 cloud, each answering who is in charge, how far the local machine actually reaches, and why it cannot. L0 measured on Update Revision `0541400a`: **cannot write**, with the reason recorded as a physical fact rather than a to-do. | "AI 打通一切"这句话——拆成 L0 微码到 L8 云端九层，每层回答谁说了算、本机碰得到哪、碰不到的原因。L0 实测 Update Revision `0541400a`，**写不了**，理由写成物理事实而不是待办 |
| **[agent-anyapp](https://github.com/ZhangYangyi03/agent-anyapp)** | "This software can be taken over by an AI" — three channels (official-api / local-db / client-drive) converge on one `{name,args,returns,channel}` contract. WeChat is the measured counterexample: 28 libraries, 124,383,232 bytes, **zero plaintext**; process holds **zero listening ports**; the tool returns `unsupported` instead of reporting success. | "这个软件能被 AI 接管"——三条通道（official-api / local-db / client-drive）收敛成同一个 `{name,args,returns,channel}` 契约；微信实测是反例：28 个库 124,383,232 字节**零明文**、进程**零监听端口**，工具如实返回 unsupported 而不是报成功 |
| **[kernel-lab](https://github.com/ZhangYangyi03/kernel-lab)** | "I can get into the kernel" — KMDF driver skeleton + test signing + VM debugging, entirely through Microsoft's official signing path; the driver's only IOCTL returns the caller's PID, so it cannot hide anything. | "我能进内核"——KMDF 驱动骨架 + 测试签名 + VM 调试，全程走微软官方签名路；驱动的唯一 IOCTL 只返回调用者 PID，故意藏不住 |

Together, these three say one thing: **turn black boxes into contracts with safety boundaries that an AI can drive — and record what is unreachable as "unreachable", not as "not done yet".**

这三条线合起来的一句话：**把黑箱变成有契约、有安全边界、可被 AI 驱动的接口，并且把够不到的地方写成"够不到"，不是写成"还没做"。**

#### Data side / 数据侧

- **[unifolm-wla-toolkit](https://github.com/ZhangYangyi03/unifolm-wla-toolkit)** — a data pipeline implementing Unitree UnifoLM-WLA-1.0's official spec: 54-D action / 60-D state unified representation, SE(3) relative poses, zero-dependency URDF forward kinematics. No GPU, no real robot, no weights. All 15 self-checks pass in one command. The 7 places where the spec is undefined are written up as [a note to Unitree](https://github.com/ZhangYangyi03/unifolm-wla-toolkit/blob/main/docs/note_to_unitree.md).<br>
  按宇树 UnifoLM-WLA-1.0 官方规范实现的数据管线：54 维动作 / 60 维状态统一表示、SE(3) 相对位姿、零依赖 URDF 正运动学。不需要 GPU、真机、权重。15 步自检一条命令全过。规范里 7 处未定义的地方写成了[给宇树的说明](https://github.com/ZhangYangyi03/unifolm-wla-toolkit/blob/main/docs/note_to_unitree.md)。
- **[llm-safety-eval-audits](https://github.com/ZhangYangyi03/llm-safety-eval-audits)** — every recomputable number behind three manuscripts under review. Recomputing found: the grading script's fallback branch fired silently 28 times out of 120 trials; the rule classifier treated as ground truth is only 53% correct against human labels, and agrees with the LLM judge at 61.6% raw but **kappa 0.115**.<br>
  三篇在审稿件的全部可重算数据。重算发现：被打分脚本的回退分支在 120 次试验里悄悄触发了 28 次；被当作真值的规则分类器在人工标注上只有 53% 正确，与 LLM 裁判原始一致率 61.6% 但 **kappa 仅 0.115**。
- **[craftagent](https://github.com/ZhangYangyi03/craftagent)** — machine-tool condition data to anomaly attribution, standard library only (on that factory machine, one missing dependency is one more thing that cannot be installed). Synthetic data with planted ground truth; all 5 acceptance checks pass.<br>
  机床工况数据到异常归因，只用 Python 标准库（工厂那台机器上少一个依赖就少一个装不上的理由）。合成数据埋真值，5 项验收全过。

#### Research / 研究向

- **[swpl](https://github.com/ZhangYangyi03/swpl)** — Skew-Phase Law: data-structure selection under Zipf load, a phase transition at α = 1, ζ-Trie.
- **[agent-safety-bench](https://github.com/ZhangYangyi03/agent-safety-bench)** — a multi-step agent safety-compliance benchmark; it measures *critical depth*, not single-turn refusals.
- **[benign-rag-trap](https://github.com/ZhangYangyi03/benign-rag-trap)** — how benign queries amplify risk through out-of-distribution retrieval paths.

---

#### Contact / 怎么找我

Questions about agent tool governance, verification pipelines, or robot data formats — open an issue; I read every issue on the main repos.

有关于 agent 工具治理、验证流水线、或者机器人数据格式的问题，开 issue 就行——主仓库的 issue 我都会看。

Every project documents **what it does not do**. debt-verify detects "a conclusion unsupported by the published record", not "the sovereign is lying"; agentic-eda tells you 11/11 benchmarks still carry sign-off violations it cannot fix. That boundary is mine, not a disclaimer.

每个项目都写了**它不做的那件事**（debt-verify 检出的是"结论不被公布记录支持"，不是"债务国造假"；agentic-eda 会告诉你 11/11 基准仍带它修不了的签核违规）。这条边界是我的，不是免责声明。

<sub>Python · verification pipelines · LLM agent systems · EDA orchestration · numerical reproducibility</sub>
