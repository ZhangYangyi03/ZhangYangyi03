### Yangyi Zhang · 张洋溢

Robotics data infrastructure & self-evolving agent systems.
数据侧工程 + agent 基础设施。分布在芬兰（LUT），当前主线是把机器人数据接进统一动作空间。

---

#### 现在在做的三个

| 项目 | 一句话 | 状态 |
|---|---|---|
| **[unifolm-wla-toolkit](https://github.com/ZhangYangyi03/unifolm-wla-toolkit)** | 按宇树 UnifoLM-WLA-1.0 官方规范实现的数据管线：54 维动作 / 60 维状态统一表示、SE(3) 相对位姿、零依赖 URDF 正运动学。不需要 GPU、真机、权重。 | 自检 15/15，真实 G1 300 帧端到端通过 |
| **[autoforge](https://github.com/ZhangYangyi03/autoforge)** | 会自己造工具、并且让工具"证明自己值得留"的 agent 框架：创造 → 五关验证 → 生命周期；运行后用 ledger 观察、判定、隔离/康复/退役。 | 已发布到 PyPI，合入线在跑 |
| **[tool-market](https://github.com/ZhangYangyi03/tool-market)** | 面向可演化工具的协议化资源底座：每个工具是有状态、有版本、有血缘的资源；候选工具在打分之前先过不变量闸门。 | 服务在线，协议实现有据可查 |

#### 研究向

- **[swpl](https://github.com/ZhangYangyi03/swpl)** — Skew-Phase Law：Zipf 负载下的数据结构选型，附 3 张实测图与论文草稿
- **[agent-safety-bench](https://github.com/ZhangYangyi03/agent-safety-bench)** — 多步 agent 安全合规基准，测的是"关键深度"而不是单轮拒答

---

#### 怎么找我

有关于机器人数据格式、WLA 接入、或者自演化 agent 工具治理的问题，开 issue 就行——三个主仓库的 issue 我都会看。
`unifolm-wla-toolkit` 里那份 [给宇树的说明](https://github.com/ZhangYangyi03/unifolm-wla-toolkit/blob/main/docs/note_to_unitree.md) 是我和上游对话的方式，欢迎照这个格式来。

<sub>Python · PyTorch · robotics data pipelines · agent tooling</sub>
