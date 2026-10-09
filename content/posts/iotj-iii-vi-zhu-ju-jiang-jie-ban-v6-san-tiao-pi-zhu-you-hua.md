---
title: IoT-J 论文逐句讲解版（本轮 3 条批注优化 v6 · 可批注版）
subtitle: ''
date: '2026-10-09T19:45:57+08:00'
lastmod: '2026-10-09T19:45:57+08:00'
draft: false
authors: []
description: ''
tags: []
categories: []
series: []
hiddenFromHomePage: false
hiddenFromSearch: false
featuredImage: ''
featuredImagePreview: ''
toc:
  enable: true
math:
  enable: false
lightgallery: true
license: 本文采用 <a rel="license" href="https://creativecommons.org/licenses/by-nc/4.0/"
  target="_blank">CC BY-NC 4.0</a> 许可协议，转载请注明出处。
---

# IoT-J 论文逐句讲解版（本轮 3 条批注优化 v6 · 可批注版）

批注说明：每个逐句讲解单元和公式卡的末尾均留有“我的意见”空栏，请直接在该栏填写疑问或修改建议。本轮更新了三条批注对应的正文释义及讲解；原有公式和未涉及批注的单元保留，既有 S/E 定位号不变。

III 系统模型 — VI 优化问题表述

英文对照 · 中文释义 · 数学拆解 · 原批注回应

依据：2026-10-09 修改、回读及编译核对的 [Overleaf 线上稿](https://www.overleaf.com/project/6ac73b6b2b7ae56343f5e414)。本轮按 3 条新批注局部澄清 III 章；此前 v5 的 VI 章节顺序及 f/p、分区优化展开式完整保留。未运行实验、改实验协议、换目标模型或引入提前讨论的解法概念。

覆盖：298 个当前线上阅读单元，另保留 S11、S54 两个删除标记；29 张公式卡。原 S/E 阅读编号稳定保留，章节按新的线上顺序排列，所以分区的 S245–S259 会先于请求资源的 S224–S244。S/E 是讲解定位号，不是论文自动编号。

v5 已有、此次保留的关键内容：

- VI-A：请求准入与可行性。
- VI-B：部署分区优化，完整展开为式 (27a–27g)，在本讲解中仍为 E27。
- VI-C：固定分区下的请求级 GPU 频率与设备 Wi-Fi 功率分配。E28 显式列出 z 的两阶段分量；E29 完整展开式 (28a–28f) 的 f/p 目标及约束。
- A 的简式现为论文式 (29)，只命名展开问题的最优向量，不再是唯一展示资源优化的地方。连续参考现为式 (31a–31e)，不替换实际有限等级策略。

原 32 条批注的回应全部保留。v4 的符号定义、用词修订、参数化模型、长度分工、两跳 Wi-Fi、保守内存界、统一控制能量、合法资源等级及确定性平局规则均保留。原分区式和其他既有公式的数学表达未改；新增请求式是对同一目标与可行集合的等价展开。

此次章节移动及插入导致部分论文自动公式编号变化；源文引用标签保留，编译后的交叉引用随之更新。讲解中的论文式号同步调整，不把旧编号当成新版本位置。

原批注文件、v3、v4 和 v5 均保留，本版另存。可以继续使用 S207c、E28、E29 等编号提出意见。

线上编译：0 个 LaTeX 错误，无 Overfull 公式溢出、无 PDF 渲染错误。参考文献末页仍有 1 个列平衡警告及普通 Underfull 排版提示；未修改范围外的平衡命令，不表示整篇完成投稿终检。

## 本轮 3 条批注的处理（v6）

依据你在《IoT-J 论文逐句讲解版（new）》中的 S8、E3、S51 批注，对 Overleaf 最新稿做局部修订。只改 III 章相应文字和图注；IV–VI、所有既有公式、分区/请求优化展开式以及 VII 之后的内容保持原样。用户批注文件与旧版另行保留，本文件是新的阅读副本。

- **S7–S8a / E9：内存额度。** 总服务额度包含运行时开销，运行时预留计在需求式左侧；不是不占内存，也不是必须在右侧再减一遍。S8 保留你的原批注与一个等价记账示例。
- **S28–S28d / E3：步数与 token 长度。** 明确 $t$ 是 decode 步序号，第 $t$ 步输入第 $t$ 个输出并生成第 $t+1$ 个。每步被处理的上下文为 $P+t$，最终完整序列为 $P+G$；没有增加额外 decode 步。
- **S51–S51a / S62：请求内固定。** 写明到达时选择的两阶段资源向量直到请求结束都不重新优化，保留两阶段可采用不同 f/p 的设定。若你本意是“两阶段也必须相同”，那是另一项建模改动，本轮未增加这种相等约束。

**原意核对：** 此轮遵循 latex-paper-en 的原意与符号保护原则。没有新增文献、实证结果、预测器创新声明或实验动作。原来的三条批注在对应单元以“本轮批注（已处理）”保留，并留出新的“我的意见”空栏；其他单元的空栏也保留。新增句子使用 S8a、S28a–S28d、S51a，不重排既有定位号。

**线上核对：** 回读确认保存内容与修订稿完全一致；III 章以外源文及所有既有显示公式逐字保持不变。编译 0 错误、1 个原有参考文献列平衡警告，无 Overfull 提示；仍有普通 Underfull 信息，不表示整篇投稿终检完成。

## v5 保留的章节顺序与公式展开说明

**章节目的：** 让读者先看到部署时选择的固定分区，再明确该分区如何作为请求资源问题的给定输入。

| 位置 | 给定信息 | 决策或输出 | 长度的作用 |
| --- | --- | --- | --- |
| VI-A 准入定义 | 设备、候选分区、P、预算及合法等级 | 是否存在可行资源 | cap 检查预算 |
| VI-B 分区部署 | 历史请求及同一个到达信息资源规则 A | 固定分区 c* | 各请求先按预测选资源，再按真实长度评分 |
| VI-C 请求控制 | 已部署 c*、当前 P 与预测 G | 两阶段 f/p，合为 z | 预测比较时延；cap 检查能量和内存 |

**两个顺序不能混淆。** 实际服务时先部署 c*，新请求到达后才选 f/p。校准时则必须给定一个候选 c，为历史请求用同一规则选资源，按真实长度评价，才能知道应选择哪个分区。因此分区章节放在前面，需要先介绍 A 的输入/输出，并指向后文的完整定义；不是取消分区对资源策略的依赖。

**f/p 展开没有改变优化问题。** 给定 c、P、预测长度，优化器共同选择两阶段频率与设备 Wi-Fi 功率。展开的时延是原 T；能量、内存、合法等级是原 Z 的条件。AP 功率仍固定，cap 控制可行性，历史真实 G 不进入当前请求决策。目标相同、可行集合相同，平局规则也相同，故仍选择原来的资源策略。

**内存与能量约束的区别。** 固定 c/P 后，内存需求不含 f/p，是准入门槛；能量含两阶段 f/p，限制计算与 Wi-Fi 的共同配置。不能为了看起来“可优化”而把频率加入原本不含频率的容量式。

**z 不是单阶段配置。** 它含 2N 个频率和 2N−1 个功率，共 4N−1 个分量；没有 p_N^pre，因为末设备在 prefill 中不发送层间激活，但有用于 token 反馈的 p_N^dec。两阶段设置在到达时一起选定，所选资源向量直到请求结束都不重新优化；两阶段可以使用不同值。

v5 采用 latex-paper-en 的模块输入/输出衔接与原意保护原则、math-reasoning 的符号/单位/代入核对。证据是已有定义和等价代入，不是新的实证效果或创新性声明。

## v4 批注修订：继续保留的理由与影响

1. **容量预算不等于权重。** $\bar M_i$ 是可用容量，$W_\ell$ 是层权重需求，$M_i$ 是权重、状态、缓冲和运行时预留组成的保守需求。准入式没有改变，也没有把保守容量界写成实测峰值。
2. **单请求能量额度。** 同一设备额度对每个评价请求适用，不按预测长度临时制造预算；它是任务级约束，不是连续服务的电池动态模型。“增量”指核算的推理相关组成，不是相邻步骤间能量差。
3. **三种输出长度分工。** 预测 $\widehat G$ 用于候选资源的时延排序；强制上限 $G_{\mathrm{cap}}$ 用于预算检查；历史真实 $G_r$ 用于评分和选择分区。历史请求也先按到达信息选资源，再按真实长度评分，保留因果信息边界。
4. **通用理论与固定部署。** 理论以架构/运行时需求量为参数，不先限定某个模型名；每次部署则须给定这些参数。模型选择不是优化变量，实验目标仍为 Qwen3.5-4B，未正式采用任何候选替换方案。
5. **Wi‑Fi 两跳与访存。** 设备发送功率是可调 Wi‑Fi 射频功率，AP 下行功率是预设基础设施参数。固定内存时钟不等于忽略访存；时间中的 $D/\beta$ 和能量中的 $\epsilon D$ 均保留。没有增加 AP 能量到设备预算，也没有改成直连设备通信。
6. **分区式等价展开。** 将 $J,T,E,h,R,n,S_{\mathrm{air}}$ 的定义代入最终式，并把原来藏在非空可行集合条件中的内存、能量约束列明。请求资源仍由同一到达信息策略确定，不变成利用真实长度任意优化的离线变量。频率/功率上下界显式列出，但合法等级已在这些界内，因此不增加新限制。展开式的形状参数是恢复原来省略的依赖，不是增加新成本项。
7. **此前优化保留。** 保守内存界、固定形状下有效系数近似、统一控制能量预留、确定性平局规则、独立合法资源等级和单请求串行执行设定均保留。承诺的生成上限可行性是模型内结论，仍依赖这些假设，不能解释成真实硬件测量或对未知参数误差的无条件保证。

应用学术写作技能的影响：按 latex-paper-en 的原意保护原则做定点修改，按 math-reasoning 检查单位、索引和代入关系；没有为润色改变公式含义，没有新增文献、结果或已完成事项。

阅读方式：先看每小节概览，再读“英文原句 → 中文意思 → 讲解/作用”。最后的 [32 条批注回应索引](#annotation-responses) 保留你的问题及处理结果。数学采用 Markdown 的 LaTeX 语法；英文中的引用键用于定位原引用，不是新的参考文献结论。

## 目录

- [先看整条论证链](#reading-map)
- [III 系统模型](#section-1)
  - [III-A 设备、模型与执行顺序](#section-3)
  - [III-B token 计数与到达信息](#section-24)
  - [III-C 控制与模型假设](#section-40)
- [IV 分层计算与内存模型](#section-64)
  - [IV-A 层级与算子级量](#section-67)
  - [IV-B 架构和运行时相关需求](#section-85)
  - [IV-C 准入内存需求](#section-113)
- [V 时延与增量能量模型](#section-124)
  - [V-A 计算时延与增量能量](#section-126)
  - [V-B 无线时延与增量能量](#section-153)
  - [V-C 请求总时延和设备能量](#section-194)
- [VI 优化问题表述](#section-205)
  - [VI-A 请求准入与可行性](#section-214)
  - [VI-B 部署分区优化](#section-245)
  - [VI-C 请求级频率与 Wi-Fi 功率分配](#section-224)
- [读完后的自检与定位](#self-check)
- [32 条批注回应索引](#annotation-responses)

<a id="reading-map"></a>

## 先看整条论证链

### III 系统是什么

设备及顺序给定；部署选连续分区，请求到达时只知道输入和预测。

### IV 要多少资源

F 是操作数、D 是执行访存量、W/S 是存储容量、V 是边界载荷、U 是同时活跃的临时峰值。

### V 转成什么代价

按设备系数与所选 f/p 算组级时间和能量，再按串行执行汇总为 T 与各设备 E。

### VI 优化什么

准入约束使用 G_cap；在线时延目标使用 G_hat；历史分区评分使用 G，但不向在线策略泄漏 G。

### 四类长度切勿混淆

- P：到达时已知的模板后输入 token 数。
- G_hat：预测器给出的估计输出长度，优化时延代理用它。
- G：某一次请求真实停止后才知道的输出长度，历史评价可以用它。校准请求 r 对应各自的 G_r；不是把历史输出长度的平均值当作每个请求的 G。分区目标平均的是逐请求时延，而不是先平均长度再代入一次时延模型。
- G_cap：强制执行的服务生成上限，可行性检查用它。

### 输入/决策/输出

给定设备、执行顺序、模型与运行路径、预算、合法资源等级、服务上限和固定预测器。部署变量是整数切点 c；请求变量是阶段频率 f 与发送者功率 p，统一记为 z。输出是固定部署分区和每个准入请求的配置，不是预测器本身的新方法。

<a id="section-1"></a>

## III 系统模型

回答设备如何连接、模型怎样分配、什么信息在何时可用。

<a id="s1"></a>

#### S1

> This section describes the participating devices, model partition, and information available at request arrival.

**中文意思：** 本节介绍参与设备、模型分区和请求到达时可获得的信息。

**讲解 / 作用：** 这是章节导语：先规定系统里有什么、模型放在哪里、控制器何时知道哪些信息，再建立代价模型。

**我的意见：**


<a id="s2"></a>

#### S2

> These definitions provide the basis for the computation, memory, and communication models and the joint partitioning and resource-allocation problem.

**中文意思：** 这些定义是计算、内存、通信模型以及分区与资源分配联合优化问题的基础。

**讲解 / 作用：** 本句说明章节依赖：先定义系统和到达信息，再计算代价，最后建立联合优化问题。联合性在于分区改变各设备需求，从而影响其可选资源；这里没有预先规定求解方法，也没有宣称效果已经验证。

**我的意见：**


<a id="section-3"></a>

### III-A 设备、模型与执行顺序

先读设备和预算，再理解整数切点与状态归属。

<a id="s3"></a>

#### S3

> Let $N\geq2$ be the number of participating home-edge devices, and let $\mathcal{N}=\{1,\ldots,N\}$ denote their index set.

**中文意思：** N≥2 是参与推理的设备数量，花体 N 是由编号 1 至 N 组成的集合。

**讲解 / 作用：** N 是数字，花体 N 是集合。例如三台设备时，N=3，编号集合为 {1,2,3}；这只是讲解示例。设备数量在本问题中给定。

**我的意见：**


<a id="s4"></a>

#### S4

> The devices communicate through a Wi-Fi access point (AP) and execute the model in the fixed order $1,\ldots,N$.

**中文意思：** 设备经一个 Wi‑Fi 接入点 AP 通信，按给定的 1 至 N 顺序执行模型。

**讲解 / 作用：** AP 是网络中的转发基础设施，不属于参与计算的 N 台设备；设备数量及顺序是输入，优化器不挑选或重排设备。

**我的意见：**


<a id="s5"></a>

#### S5

> For computation modeling, device $i\in\mathcal{N}$ is represented by one graphics processing unit (GPU) with specified computation and memory-bandwidth characteristics.

**中文意思：** 在计算建模中，设备 i 以一块具有指定计算和内存带宽特性的 GPU 表示。

**讲解 / 作用：** 补出“计算建模”限定：不是宣称设备只包含 GPU，也不代表进行了真实测量；ρf 表示这一计算抽象的吞吐。

**我的意见：**


<a id="s6"></a>

#### S6

> Other accelerator types require corresponding device parameters.

**中文意思：** 若采用其他类型的加速器，需要相应的设备参数。

**讲解 / 作用：** 不能把 GPU 的频率、吞吐或能耗系数原封不动地套到另一种加速器上。这里限定抽象的适用方式。

**我的意见：**


<a id="s7"></a>

#### S7

> Let $\bar M_i$ denote the memory-capacity budget, in bytes, allocated to the inference service on device $i$ after excluding operating-system and other non-service allocations.

**中文意思：** $\bar M_i$ 表示设备 $i$ 分配给推理服务的总内存容量额度，单位字节；操作系统和其他非服务占用已排除。

**讲解 / 作用：** “额度”回答允许推理服务用多少，“需求”回答推理服务实际需要多少。它不是只给模型权重的额度，也不是硬盘容量；服务内部的各类内存都要在这个总额度内安排。

**我的意见：**


<a id="s8"></a>

#### S8

> This budget must accommodate the model weights, inference state, temporary buffers, and the service's runtime reserve.

**中文意思：** 这个总额度必须同时容纳模型权重、推理状态、临时缓冲以及服务自身的运行时预留内存。

**讲解 / 作用：** 运行服务的内存需求没有被排除，恰恰包含在推理服务总需求中。正式需求式 E9 的最后一项 $M_{\mathrm{rt},i}$ 就是运行时预留；左边合计服务要用的内存，右边 $\bar M_i$ 是允许服务用的总内存。

**本轮批注（已处理，保留原文）：** 看不懂这句话说的是啥，服务运行的内存需求为什么不在服务额度M_bar,i里面扣除？M_bar,i不是允许使用的存储量吗？运行服务的内存需求不在这里面在哪里？

**本轮回应：** 你的疑问来自原句只说“不再扣除”，却没说明这笔内存记在哪里。线上现在先列出总额度要容纳的内容，再指向内存需求式。运行时占用要计入，但只能计一次。

**容量口径示例（仅用于讲解）：** 假设服务总额度为 6 GB，运行时预留为 0.5 GB，权重、状态及临时缓冲合计 5.4 GB，则总需求为 5.9 GB，满足 5.9≤6。也可以先扣运行时预留，再比较其余需求，即 5.4≤5.5；两种写法等价。不能先把右边减到 5.5 GB，又在左边保留已含运行时的 5.9 GB，否则同一笔 0.5 GB 被重复收费。本文采用“左边计全服务需求、右边保留总额度”的口径。

**我的意见：**


<a id="s8a"></a>

#### S8A

> These components, including the runtime reserve, are counted in the total memory requirement in (11), rather than subtracted from $\bar M_i$.

**中文意思：** 这些组成，包括运行时预留，都计入式 (11) 的总内存需求，而不是从 $\bar M_i$ 中扣除。

**讲解 / 作用：** 对应 E9：层权重与端点权重、状态与临时缓冲峰值、最后的 $M_{\mathrm{rt},i}$ 相加，与 $\bar M_i$ 比较。这是记账方式，不是免除运行时占用。若以后改用“扣掉运行时后的剩余额度”，必须同时从左边移除该项，才能保持同一可行集合。

**我的意见：**


<a id="s9"></a>

#### S9

> Let $\bar E_i>0$ denote a prescribed per-request energy allowance, in joules, for the inference-related components defined below.

**中文意思：** E_bar,i>0 是预先规定的单请求推理相关能量额度，单位焦耳。

**讲解 / 作用：** “每请求”指预算适用的任务单位，不是每次都重新估计一个预算。此模型用同一个设备额度比较不同请求的执行配置；为何合理与它不涵盖什么，见下一句。

**我的意见：**


<a id="s9a"></a>

#### S9a

> The same allowance is applied to each evaluated request; it is not recomputed from the predicted output length.

**中文意思：** 每个评价请求采用同一额度，不按预测输出长度重新制定预算。

**讲解 / 作用：** 这是服务任务级约束，适合研究一次请求内计算与 Wi‑Fi 如何分配有限能量。它不是完整的剩余电池动态模型，也不保证连续很多次请求的累计电量不超电池容量；没有修改实验协议或预算数值。

**我的意见：**


<a id="s10"></a>

#### S10

> The participating devices and their execution order are given inputs, rather than optimization variables.

**中文意思：** 参与设备及其执行顺序是给定输入，不是优化变量。

**讲解 / 作用：** 按你的意见去掉 host–accelerator co-scheduling：本文不研究 CPU/GPU 工作分配，没必要引入这一不参与优化的术语。保留设备集合与顺序固定的必要设定。

**我的意见：**


<a id="s11"></a>

#### S11 · 已从线上删除

按你的意见删除“单设备基线没有设备间通信”的显然说明。它不是当前线上原句；N≥2 的系统设定保留。

**我的意见：**


<a id="s12"></a>

#### S12

> Let $L\geq N$ be the number of ordered decoder-layer blocks in the autoregressive model, indexed by $\ell\in\{1,\ldots,L\}$.

**中文意思：** L≥N 是模型按顺序排列的解码层块数量，ℓ 是 1 至 L 中的层编号。

**讲解 / 作用：** 每台设备至少分到一层，所以层数不能少于设备数。L 和 N 是给定整数；这里的 decoder layer 不等于 decode 阶段。

**我的意见：**


<a id="s13"></a>

#### S13

> Define the partition vector as $\mathbf{c}=(c_1,\ldots,c_{N-1})$, where $c_i$ is the index of the last layer assigned to device $i$, with $c_0=0$ and $c_N=L$.

**中文意思：** 分区向量 c 由 N−1 个内部切点组成；c_i 是设备 i 所分最后一层的编号，端点约定 c_0=0、c_N=L。

**讲解 / 作用：** 优化 N−1 个内部边界即可，两个端点不必优化。例如 L=8、N=3、c=(2,5)，各设备层数为 2、3、3；仅为讲解。

**我的意见：**


<a id="s14"></a>

#### S14

> To assign each device a nonempty block of consecutive layers, the boundaries satisfy

**中文意思：** 要让每台设备获得一个非空连续层块，边界必须满足下式。

**讲解 / 作用：** 这是一句公式引导语，与 E1 连起来读。严格递增同时保证非空、连续、不重叠，并覆盖全部层。

**我的意见：**


<a id="e1"></a>

#### E1 · 对应原稿式 1 · 连续非空分区

$$
0=c_0<c_1<\cdots<c_N=L
$$

**符号与单位：** c_i：设备 i 的最后层编号；c_0=0 和 c_N=L 固定；N 为设备数，L 为层数，内部边界为整数。

**为什么这样写：** 严格递增表示每台设备至少获得一层。切点确定后，各层不重叠也不遗漏。这里没有容量或能量条件，后面还要再筛可行性。

**用途 / 条件 / 示例：** 定义部署变量的结构可行域。讲解例：L=8、N=3、c=(2,5)，分配 1–2、3–5、6–8 层。

**我的意见：**


<a id="s15"></a>

#### S15

> and the layer-index set assigned to device $i$ is

**中文意思：** 而设备 i 被分配的层编号集合为下式。

**讲解 / 作用：** 这是 E2 的引导片段：把边界变量转换成设备实际负责的层集合，便于随后求和。

**我的意见：**


<a id="e2"></a>

#### E2 · 对应原稿式 2 · 切点到设备层集合

$$
\mathcal{L}_i(\mathbf{c})=\{c_{i-1}+1,\ldots,c_i\}
$$

**符号与单位：** 花体 L_i 是层编号集合，不是层数；它由相邻两切点给出。

**为什么这样写：** 设备 i 从前一设备末层之后开始，到自身末层结束；层数为 c_i−c_{i-1}。

**用途 / 条件 / 示例：** 权重、状态和计算需求都按这个集合求和。集合内每项只计到所属设备。

**我的意见：**


<a id="s16"></a>

#### S16

> Let $\mathcal{C}$ denote the set of integer partition vectors satisfying 1.

**中文意思：** 花体 C 表示满足层边界约束的所有整数分区向量的集合。

**讲解 / 作用：** 切点必须落在层与层之间，不能为 2.5 层。后面的部署优化在这个有限候选空间中选择分区。

**我的意见：**


<a id="s17"></a>

#### S17

> The input embedding is placed on device 1; final normalization, the language-model head, and token selection are placed on device $N$.

**中文意思：** 输入嵌入放在设备 1；最终归一化、语言模型输出头和 token 选择放在设备 N。

**讲解 / 作用：** 端点操作也占计算、内存和能量。只核算中间解码层，会低估首尾设备的负载。

**我的意见：**


<a id="s18"></a>

#### S18

> Only the assigned model weights and required runtime data are stored in GPU-accessible memory during inference.

**中文意思：** 推理期间，GPU 可访问的内存中保存本设备分到的权重和必要运行数据。

**讲解 / 作用：** GPU 是用于执行模型计算的硬件。加速器是更宽泛的称呼，这里直接写 GPU 更容易读；GPU-accessible 包括被当前 GPU 使用的内存，不强行认定所有设备都采用同一种独立显存体系。各设备不保存全部模型权重。

**我的意见：**


<a id="s19"></a>

#### S19

> Checkpoint storage is a deployment prerequisite, and model loading is excluded from per-request latency and energy.

**中文意思：** 检查点存储是部署前提，模型加载不计入单请求时延和能量。

**讲解 / 作用：** 假定模型已经装载并就绪。每次请求重新加载完整权重，是不同的执行契约，不能混进当前公式。

**我的意见：**


<a id="s20"></a>

#### S20

> During each forward pass, device $i<N$ sends the intermediate activation at its partition boundary to device $i+1$ through the AP.

**中文意思：** 每次前向执行中，除末设备外的设备 i，把切点处中间激活经 AP 发给设备 i+1。

**讲解 / 作用：** 传的是层输出激活，不是模型权重。每个前向 pass 在每个分区边界上发生一次这样的传输。

**我的意见：**


<a id="s21"></a>

#### S21

> After device $N$ selects an output token, the token identifier and control metadata are returned to device 1 if another forward pass is required.

**中文意思：** 末设备选出 token 后，若还需下一次前向计算，就把 token 编号和控制元数据返回设备 1。

**讲解 / 作用：** 这形成自回归反馈环。最后一个输出 token 后不再计算，因此不需要为继续执行而反馈一次。

**我的意见：**


<a id="s22"></a>

#### S22

> Each layer's inference state, including its key-value (KV) cache or recurrent state, is retained on the device executing that layer throughout the request.

**中文意思：** 每层的 KV 缓存或循环状态等推理状态，在整个请求中保留于执行该层的设备。

**讲解 / 作用：** 状态归属随层放置而确定。每步不把整份 KV 或循环状态搬到下一台设备；传输与状态内存因此要分开建模。

**我的意见：**


<a id="s23"></a>

#### S23

> The partition is selected at deployment and remains fixed across requests and across the prefill and decode phases; no model weights or inference states are migrated during a request.

**中文意思：** 分区在部署时选择，在多个请求以及 prefill/decode 两阶段之间保持不变；请求内不迁移权重或状态。

**讲解 / 作用：** 这是分区保持不变的系统假设。请求到达后改变频率和功率，不等于重新分区；本句界定允许的决策行为，并不规定怎样求解。

**我的意见：**


<a id="section-24"></a>

### III-B token 计数与到达信息

确认第一个 token 属于 prefill；把预测与硬上限严格分开。

<a id="s24"></a>

#### S24

> Let $P$ denote the token count of the complete model input after formatting and tokenization, including any tokens inserted by the chat template.

**中文意思：** P 是完整模型输入经过格式化与分词后的 token 数，包括聊天模板插入的 token。

**讲解 / 作用：** 输入不是只把用户汉字直接交给模型：模板还可能插入用户/助手角色标记、分隔或结束标记，以及等待助手继续生成的起始标记。这些也是模型处理的序列内容，故要计入 P。本文不指定某种模板实际插入了多少个 token。

**我的意见：**


<a id="s25"></a>

#### S25

> Let ${G_{\mathrm{cap}}}\geq1$ be the service's enforced integer upper limit on the number of generated tokens, and let $G\in\{1,\ldots,{G_{\mathrm{cap}}}\}$ denote the realized output length.

**中文意思：** G_cap≥1 是服务强制执行的整数生成上限；G 是 1 至 G_cap 中的实际输出 token 数。

**讲解 / 作用：** 明确生成上限是整数，不更改上限数值或生成过程；G_cap 仍不等于长度预测。

**我的意见：**


<a id="s25a"></a>

#### S25a

> Generation stops when the model terminates normally or reaches the cap, whichever occurs first.

**中文意思：** 生成在正常结束或达到上限时停止，以先发生者为准。

**讲解 / 作用：** G_cap 是允许最多生成多少，不是每次必须生成多少；G 是这次实际生成多少。例如上限 100、正常生成 40 时 G=40，不会补齐到 100。示例仅为讲解。

**我的意见：**


<a id="s25b"></a>

#### S25b

> The cap bounds the decode steps and context lengths that must be checked for energy and memory feasibility.

**中文意思：** 该上限限制需要进行能量及内存检查的 decode 步数和上下文长度。

**讲解 / 作用：** 只知道预测长度无法保证不低估。若预测 40、实际生成 80，按 40 检查可能漏掉后半程成本；按强制上限 100 检查则覆盖允许范围中的 80。保证仍依赖本文能量/内存模型及运行时真的强制停止，不是对现实参数误差的保证。

**我的意见：**


<a id="s26"></a>

#### S26

> The prefill phase processes the prompt and produces the first output token.

**中文意思：** prefill 处理输入，并产生第一个输出 token。

**讲解 / 作用：** 本文把生成第一个 token 的模型计算算在 prefill 中，所以后续 decode 步数不是 G，而是 G−1。

**我的意见：**


<a id="s27"></a>

#### S27

> If $G>1$, the decode phase contains $G-1$ sequential steps.

**中文意思：** 当输出不止一个 token 时，decode 包含 G−1 个串行步骤。

**讲解 / 作用：** 例如输出 4 个 token，需要 prefill 产生第 1 个，decode 再产生 3 个；这是讲解计数，不是实验数据。

**我的意见：**


<a id="s28"></a>

#### S28

> Let $t\in\{1,\ldots,G-1\}$ denote the decode-step index.

**中文意思：** $t$ 是 decode 步的序号，取值从 1 到 $G-1$。

**讲解 / 作用：** $G$ 表示本次请求最终生成多少个输出 token；$t$ 表示当前在第几个 decode 步。两者不是同一种量。prefill 已生成第一个输出 token，所以只剩 $G-1$ 个 decode 步；若 $G=1$，没有 decode，$t$ 的集合为空。

**我的意见：**


<a id="s28a"></a>

#### S28A

> At step $t$, the model consumes output token $t$ and generates output token $t+1$.

**中文意思：** 第 $t$ 个 decode 步输入第 $t$ 个输出 token，并生成第 $t+1$ 个输出 token。

**讲解 / 作用：** 例如，第 1 个 decode 步输入 prefill 生成的第 1 个 token，生成第 2 个；第 2 个 decode 步再输入第 2 个，生成第 3 个。因此步序号也恰好等于该步开始前已有的输出 token 数，但它仍是步序号，不是最终输出长度。

**我的意见：**


<a id="s28b"></a>

#### S28B

> The context processed in this step consists of the $P$ prompt tokens and the first $t$ output tokens, so its length $q_t$ is

**中文意思：** 这一步处理的上下文由 $P$ 个输入 token 和前 $t$ 个输出 token 构成，所以上下文长度 $q_t$ 如下式所示。

**讲解 / 作用：** decode 本步新增输入只有 1 个 token，但该 token 的注意力计算可涉及全部已有上下文。$q_t$ 包含本步输入的第 $t$ 个输出 token，不包含本步即将生成的第 $t+1$ 个。因而是 $P+t$，不是 $P+t+1$；后者是这一步生成结束后的完整序列长度。

**我的意见：**


<a id="e3"></a>

#### E3 · 对应原稿式 3 · decode 步序号与上下文长度

$$
q_t=P+t
$$

**符号与单位：** $P$：输入 token 数；$G$：实际输出 token 数；$t\in\{1,\ldots,G-1\}$：decode 步序号；$q_t$：第 $t$ 个 decode 步处理的上下文 token 数。$t$ 是整数序号，$P$、$G$、$q_t$ 是 token 计数。

**为什么引入 $t$：** 各个 decode 步的上下文逐步增长。只知道最终输出 $G$，不能区分第 1 步与最后一步的计算、状态和访存需求。$t$ 用来逐步索引；后文 $\sum_{t=1}^{G-1}$ 正是把这些不同上下文的成本加起来。

**与 $G$ 的数学关系：** decode 共 $G-1$ 步，第 $t$ 步生成第 $t+1$ 个输出。若 $G>1$，最后一步 $t=G-1$，故最后一次被处理的上下文长度为 $q_{G-1}=P+G-1$；该步输出完成后的完整序列长度为 $P+G$。若 $G=1$，只有 prefill，不存在 $q_{G-1}$ 对应的 decode 步。

**讲解例（不是实验数据）：** 取 $P=5$、$G=3$。

| 模型执行 | 本步处理的上下文长度 | 本步生成的输出 token | 生成结束后的完整序列长度 |
| --- | --- | --- | --- |
| prefill | 5 | 第 1 个 | 6 |
| decode 第 1 步：$t=1$ | $q_1=6$ | 第 2 个 | 7 |
| decode 第 2 步：$t=2$ | $q_2=7$ | 第 3 个（最终） | 8，即 $P+G$ |

**公式处理与影响：** 保留 $q_t=P+t$ 原式，只补清 $t$ 的定义和它与 $G$ 的关系。计算/通信仍是一个 prefill 加 $G-1$ 个 decode，不新增额外步骤，不改变能量、内存或优化式的求和上限。最后一个输出不再输入模型；内存约束依然要求覆盖整个前向执行所需的状态、输出及临时缓冲，不能据此漏记输出缓冲。

**本轮批注（已处理，保留原文）：** 这里逻辑怪怪的，t是步数还是token长度？上文不是规定了G代表输出token长度吗？总的token长度不应该是P+G吗？只不过这G个token是通过G-1个解码步骤得来的，因为prefill生成第一个token。所以这里引入t的目的是什么？这里t和G有什么数学关系，是不是要进一步说明一下？

**本轮回应：** 你的 $P+G$ 是最终完整序列长度，正确。原文没有把它与“第 $t$ 次前向的上下文”区分清楚，因此容易让人以为 $t$ 是另一个输出长度。现在上线补充 decode 步序号、输入/输出 token 编号，以及最终上下文与完整序列的关系；原式无需改成 $P+G$。

**我的意见：**


<a id="s28c"></a>

#### S28C

> For $G>1$, the last decode step processes a context of length $q_{G-1}=P+G-1$ and produces the final output token, bringing the completed prompt-plus-output sequence to $P+G$ tokens.

**中文意思：** 当 $G>1$ 时，最后一个 decode 步的上下文长度是 $P+G-1$；它生成最后一个输出 token 后，完整输入加输出序列长度才达到 $P+G$。

**讲解 / 作用：** 这句话直接回应“总长度应该是 $P+G$”：你对完整序列的判断是对的；但式 (3) 描述的是每次前向计算处理的上下文，而不是该步输出完成后的序列长度。两者相差本步刚生成的 1 个 token。

**我的意见：**


<a id="s28d"></a>

#### S28D

> The final token is not fed back for another forward pass because generation has ended.

**中文意思：** 生成已经结束，最后一个输出 token 不再反馈给模型进行下一次前向计算。

**讲解 / 作用：** 因此不能额外计一次处理 $P+G$ 上下文的 decode。若需要继续生成，就属于新的准入/继续服务问题，不是本次已停止请求多算一步。本句不否认最终文本含最后一个 token，只说明它没有再作为本次请求的模型输入。

**我的意见：**


<a id="s29"></a>

#### S29

> We use $q$ as a phase-dependent sequence-length argument: $q=P$ for prefill and $q=q_t$ for decode.

**中文意思：** q 是随阶段确定含义的序列长度参数：prefill 为 P，decode 为 q_t。

**讲解 / 作用：** decode 本步只输入一个 token，但其上下文长度为 q_t；因此把 q 称为“本步执行长度”容易误读。后面的函数需要同时看 s 和 q。

**我的意见：**


<a id="s30"></a>

#### S30

> A request therefore requires one prefill pass, $G-1$ decode passes, one activation message per partition boundary in each pass, and $G-1$ token-feedback messages.

**中文意思：** 一次请求有一个 prefill pass、G−1 个 decode pass；每个 pass 的每个边界传一次激活，并有 G−1 条反馈消息。

**讲解 / 作用：** 模型前向执行总次数是 G。激活消息总数为 G(N−1)，反馈为 G−1；两种消息内容和方向不同。

**我的意见：**


<a id="s31"></a>

#### S31

> At request arrival, the controller observes the prompt and its token count $P$, whereas the realized output length $G$ is unknown.

**中文意思：** 到达时控制器看到输入和 P，但不知道实际输出长度 G。

**讲解 / 作用：** 这是信息时序约束，防止把事后才知道的长度偷偷作为在线输入。

**我的意见：**


<a id="s32"></a>

#### S32

> Let $g_\theta$ denote an output-length predictor with parameters $\theta$ fixed before partition calibration and testing.

**中文意思：** g_θ 表示输出长度预测器，其参数 θ 在分区校准和测试之前固定。

**讲解 / 作用：** 它是资源决策的一个输入模块；本文不以预测器架构创新为主张。固定参数使不同候选分区使用同一个预测规则。

**我的意见：**


<a id="s33"></a>

#### S33

> Its integer prediction, denoted by $\widehat{G}$, is

**中文意思：** 预测器处理后得到的整数长度记为 G_hat，其定义如下。

**讲解 / 作用：** 与 E4 一起读。帽子表示估计值，不表示实际 G，也不是硬上限。

**我的意见：**


<a id="e4"></a>

#### E4 · 对应原稿式 4 · 整数化与裁剪预测

$$
\widehat{G}=\Pi_{[1,G_{\mathrm{cap}}]}(\mathrm{round}(g_\theta(\mathrm{prompt})))
$$

**符号与单位：** g_θ：固定参数预测器；round：取最近整数；Π：裁剪；G_hat：预测长度；G_cap：硬上限。

**为什么这样写：** 估计值先整数化，再压到服务允许范围。这里 round 后不会凭空获知真实 G。

**用途 / 条件 / 示例：** 候选配置的时延式代入预测 G_hat，预算检查代入 G_cap。讲解例：预测 12.4、上限 10，最终估计为 10，并非保证真实长度恰为 10。

**“进入时延目标”的具体意思：** 原时延式是 $T(\mathbf c,\mathbf z;P,G)$。请求到达时不知道 $G$，于是候选资源配置按 $T(\mathbf c,\mathbf z;P,\widehat G)$ 比较，而不是把 $\widehat G$ 直接加到秒数上。它确定预计会有多少个 decode 步及对应上下文长度。能量和内存检查始终使用 $G_{\mathrm{cap}}$。

**仅用于讲解的简化例，不是实验结果：** 假定 A、B 两个配置都通过同一 cap 约束，A 的 prefill 为 0.2 s、每个 decode 步为 0.02 s，B 分别为 0.4 s 和 0.01 s。当 $\widehat G=5$ 时，A 估计为 $0.2+4\times0.02=0.28$ s，B 为 0.44 s；当 $\widehat G=50$ 时，A 为 1.18 s，B 为 0.89 s。这个例子说明预测怎样改变候选配置的排序。真实模型的 decode 单步成本可随上下文变化，并不统一为例中的常数。

**我的意见：**


<a id="s34"></a>

#### S34

> where $\operatorname{round}(\cdot)$ rounds to the nearest integer and $\Pi_{[1,{G_{\mathrm{cap}}}]}(\cdot)$ clips the result to $[1,{G_{\mathrm{cap}}}]$.

**中文意思：** round 四舍五入到最近整数，Π 把结果截断到 [1,G_cap]。

**讲解 / 作用：** 先整数化，再限制合法范围。下限保证至少一个输出，上限保证预测服务长度不超过服务硬上限。

**回应你的长度疑问：**

| 量 | 到达时是否知道 | 用途 | 不代表什么 |
| --- | --- | --- | --- |
| $G_{\mathrm{cap}}$ | 知道，服务预设并强制执行 | 检查内存与能量能否覆盖允许的最长生成 | 不是实际长度，也不是预测结果 |
| $\widehat G$ | 知道，固定预测器给出 | 比较候选 $f/p$ 的估计时延 | 不能单独提供不超预算保证 |
| $G$ / $G_r$ | 新请求结束后知道；历史请求已知 | 评价选定配置；以历史请求时延选择分区 | 不交给当前请求的资源策略 |

预测被裁剪到 cap 内，是因为服务不允许生成更长；裁剪并不说明预测必然准确。

**我的意见：**


<a id="s35"></a>

#### S35

> Predictor training uses data separate from the partition-calibration and test sets.

**中文意思：** 预测器训练使用与分区校准及测试集合分离的数据。

**讲解 / 作用：** 这声明信息隔离要求：不能用测试结果训练预测器或选择部署分区。本讲解不展开范围外的具体数据协议。

**我的意见：**


<a id="s36"></a>

#### S36

> Each request is represented by its complete input token sequence and the output sequence generated from that input.

**中文意思：** 每个请求由完整输入 token 序列及其生成的输出序列表示。

**讲解 / 作用：** 原句“每个会话首次用户轮次取一个请求”是数据取样限定，不是通用理论建模的必要条件。这里改为请求的输入/输出定义；实验如何取样保持原样，没有改实验章节或数据协议。

**我的意见：**


<a id="s37"></a>

#### S37

> The controller substitutes $\widehat{G}$ for the unknown output length when estimating latency for candidate resource configurations, while energy and memory feasibility are checked at ${G_{\mathrm{cap}}}$.

**中文意思：** 比较候选资源配置的时延时，用 G_hat 替代未知的实际输出长度；能量和内存可行性按 G_cap 检查。

**讲解 / 作用：** “进入时延目标”就是把 T(c,z;P,G) 中的未知 G 换成预测 G_hat，再比较不同 z 的估计秒数。它不会把预测值直接当作预算或实际生成长度。G_cap 只确定约束检查的最远执行范围。

**我的意见：**


<a id="s37a"></a>

#### S37a

> The realized length $G$ is used to evaluate the selected resources after generation and to score historical requests during partition selection.

**中文意思：** 实际长度 G 用于生成结束后的资源评价，也用于选择分区时对历史请求评分。

**讲解 / 作用：** 三者职责：G_hat 排序候选频率/功率；G_cap 检查配置能否覆盖所有允许输出；G_r 是某个历史请求真实输出长度，用于计算历史实际长度下的时延评分。G_r 不是所有历史长度的平均值。

**我的意见：**


<a id="s38"></a>

#### S38

> Historical requests with known realized lengths are used to select the partition by their mean inference latency under the arrival-time resource policy.

**中文意思：** 利用已知真实长度的历史请求，按到达信息资源策略产生的平均推理时延来选择分区。

**讲解 / 作用：** 接受你补充的主线：大量历史真实 G_r 参与选择分区；当前请求用预测长度选择 f/p。为忠实评价将来会运行的策略，每个历史请求也先按 P_r、G_hat,r 选资源，再用真实 G_r 打分，不让在线策略预知真实长度。

**我的意见：**


<a id="s38a"></a>

#### S38a

> For each candidate partition, resources are first selected from each historical request's prompt length and predicted output length and are then evaluated at its realized output length.

**中文意思：** 对每个候选分区，先按每个历史请求的输入长度和预测输出长度选资源，再按其真实输出长度计算时延。

**讲解 / 作用：** 真实历史长度直接决定每个候选分区的评分；区别只是不能把它提前交给请求资源策略。VI-C 用 P_r、G_hat,r、G_r 分别记每个历史请求的三个长度。

**我的意见：**


<a id="s39"></a>

#### S39

> Thus, the online resource decision does not use the realized output length.

**中文意思：** 因此在线资源决策不使用实际输出长度。

**讲解 / 作用：** 这就是本文 causal 的含义：没有未来信息。不是统计学中的因果效应识别。

**我的意见：**


<a id="section-40"></a>

### III-C 控制与模型假设

哪些变量可调、何时选择、哪些执行与能量组件不在边界内。

<a id="s40"></a>

#### S40

> Let $s\in\{\mathrm{pre},\mathrm{dec}\}$ denote the inference phase, where $\mathrm{pre}$ and $\mathrm{dec}$ refer to prefill and decode, respectively.

**中文意思：** 阶段 s 取 pre 或 dec，分别指 prefill 和 decode。

**讲解 / 作用：** 上标 s 常表示阶段标签，不是把变量乘方。相同设备可以在两阶段采用不同设置。

**我的意见：**


<a id="s41"></a>

#### S41

> The control variables in phase $s$ are the GPU core frequency $f_i^s$, in hertz, and the Wi-Fi radio transmit power $p_i^s$ of device $i$, in watts.

**中文意思：** 阶段 s 的控制变量是设备 i 的 GPU 核心频率 f_i^s（Hz）和 Wi‑Fi 无线电发射功率 p_i^s（W）。

**讲解 / 作用：** 按你的意见明确 Wi‑Fi。p_i^s 是向 AP 发无线信号的射频输出功率，不是 GPU 功率、整机功率或 AP 功率；发送电路与功放效率的耗电另在无线能量式中计入。

**我的意见：**


<a id="s42"></a>

#### S42

> Their operating limits are $f_{i,\min}$ and $f_{i,\max}$ for frequency, and $p_{i,\min}$ and $p_{i,\max}$ for transmit power.

**中文意思：** 频率上下界为 f_i,min、f_i,max，发射功率上下界为 p_i,min、p_i,max。

**讲解 / 作用：** 这些界是给定参数，不是待学习结果；设备间可以不同。有限合法等级和连续参考区间要区别看。

**我的意见：**


<a id="s43"></a>

#### S43

> All allowed discrete resource levels lie within these bounds and are specified as hardware-supported values or simulation assumptions.

**中文意思：** 允许的离散资源等级在上下界内，并明确属于硬件支持值或模拟假设。

**讲解 / 作用：** 离散等级并不自动意味着真实设备可配置。此句要求透明说明来源，不声称已经部署这些控制。

**我的意见：**


<a id="s44"></a>

#### S44

> Frequencies are positive, and the allowed transmit powers yield positive modeled link rates.

**中文意思：** 频率为正，允许的发射功率对应正的模型链路速率。

**讲解 / 作用：** 时延公式要除以吞吐或速率，因此分母不能为零。这里是数学定义域条件。

**我的意见：**


<a id="s45"></a>

#### S45

> The memory clock is not optimized; memory-access time and energy remain included through the effective bandwidth and traffic terms.

**中文意思：** 不优化内存时钟，但仍通过有效带宽和访存量计入访存时间与能量。

**讲解 / 作用：** 你指出得对：Roofline 用 max(F/(ρf),D/β) 包含访存瓶颈，能量式还含 εD。固定内存时钟仅说明它不是决策变量，绝不等于 D=0 或访存免费。只调整 GPU 核心 f，β 对固定形状按既定近似处理。

**我的意见：**


<a id="s46"></a>

#### S46

> The devices transmitting during prefill are indexed by $\mathcal{I}_{\mathrm{pre}}=\{1,\ldots,N-1\}$, while $\mathcal{I}_{\mathrm{dec}}=\mathcal{N}$ includes device $N$ for token feedback.

**中文意思：** prefill 发送者集合为 1 至 N−1；decode 发送者集合包含所有设备，末设备负责 token 反馈。

**讲解 / 作用：** 末设备没有 prefill 激活要发给下一设备。第一条用于启动 decode 的反馈也按 decode 阶段计费，后文会解释。

**我的意见：**


<a id="s47"></a>

#### S47

> Thus, $p_i^s$ is defined only for $i\in\mathcal{I}_s$.

**中文意思：** 只有该阶段会发送的设备才定义发射功率变量。

**讲解 / 作用：** 不应给不存在的发送事件增加无意义变量，例如末设备的 prefill 发射功率。

**我的意见：**


<a id="s48"></a>

#### S48

> Let $\mathbf{z}$ denote the resource vector containing all phase-specific frequencies and the applicable transmit powers.

**中文意思：** z 把所有阶段频率和有效的发射功率变量收集成一个资源向量。

**讲解 / 作用：** 写 A(c,P,G_hat) 返回 z，就是一次性返回这些配置，不是只返回某台设备一个频率。

**我的意见：**


<a id="s48a"></a>

#### S48a

> For lexicographic tie-breaking, frequency components are ordered first by phase ($\mathrm{pre}$ before $\mathrm{dec}$) and then by increasing device index, followed by transmit-power components in the same phase and index order.

**中文意思：** 为定义字典序，先排列频率分量：prefill 在前、decode 在后，每阶段按设备编号递增；再按同样顺序排列存在的发射功率分量。

**讲解 / 作用：** 这是本轮补全的确定性约定，不增加控制变量。具体顺序为 prefill 的 N 个 f、decode 的 N 个 f、prefill 的 N−1 个 p、decode 的 N 个 p。平局时它会影响选定配置，进而可能影响历史评分；不宣称任何一种排列更优。

**我的意见：**


<a id="s49"></a>

#### S49

> The AP uses the prescribed Wi-Fi transmit power $p_{\mathrm{AP}}$ for its downlinks to the devices; this infrastructure parameter is not optimized.

**中文意思：** AP 向设备转发数据的 Wi‑Fi 发射功率 p_AP 是预设基础设施参数，不参与优化。

**讲解 / 作用：** 同一条消息有两次不同发送：设备 i→AP 使用待选 p_i^s；AP→设备 j 使用预设 p_AP。两者属于不同发送端，所以可调设备功率与固定 AP 功率不矛盾。AP 耗能不计入设备预算，但它的下行速度与接收设备耗能仍必须计入。

**我的意见：**


<a id="s50"></a>

#### S50

> At arrival, the controller selects the resource vector for both phases using $(P,\widehat{G})$.

**中文意思：** 请求到达时，控制器用 P 和 G_hat 同时选择两阶段资源。

**讲解 / 作用：** 不是完成 prefill 后重新观察真实输出长度再决策，也不是每生成一个 token 重算一次资源。

**我的意见：**


<a id="s51"></a>

#### S51

> The selected phase-specific frequencies and transmit powers remain fixed until the request is completed; no resource re-optimization is performed during that request.

**中文意思：** 选定的两阶段频率和发射功率配置直到本次请求完成都不再修改；请求执行中不重新优化资源。

**讲解 / 作用：** “保持不变”指到达时选好的资源向量 $\mathbf z$ 保持不变，不是要求两阶段共用同一组数值。切换到 decode 时，使用的是到达时已经选好的 decode 配置，不是重新运行优化器。

**本轮批注（已处理，保留原文）：** 改成选定频率和功率在本次请求服务结束前保持不变

**本轮回应：** 已按你的意见明确写成“直到本次请求完成”。为了保留此前联合选择两阶段 f/p 的模型，增加 phase-specific，并由 S51a 说明两阶段可以不同；没有把 $f_i^{\mathrm{pre}}=f_i^{\mathrm{dec}}$ 或 $p_i^{\mathrm{pre}}=p_i^{\mathrm{dec}}$ 加成新约束。

**我的意见：**


<a id="s51a"></a>

#### S51A

> The two phases may use different values, but all decode steps share the selected decode configuration.

**中文意思：** prefill 与 decode 可以使用不同数值，但所有 decode 步都使用同一个选定的 decode 配置。

**讲解 / 作用：** 例如，某设备可以在到达时选定 prefill 频率为 $f_i^{\mathrm{pre}}$、decode 频率为另一个 $f_i^{\mathrm{dec}}$。请求中不重新选值，只按阶段使用已选值。每步上下文 $q_t$ 可以增长，但 decode 的频率和发射功率不随 $t$ 变化。

**我的意见：**


<a id="s52"></a>

#### S52

> The model considers one request at batch size one, with sequential computation and communication and no overlap between devices.

**中文意思：** 模型考虑 batch=1 的单请求，计算和通信串行，设备间不重叠执行。

**讲解 / 作用：** 因此端到端时间可以累加。算子内部计算与访存的重叠是另一层级，不与这个假设冲突。

**我的意见：**


<a id="s53"></a>

#### S53

> Requests are evaluated independently.

**中文意思：** 各请求独立评价。

**讲解 / 作用：** 模型不引入跨请求排队、竞争或流水线；共享的只是部署分区，不是请求间联合调度。

**我的意见：**


<a id="s54"></a>

#### S54 · 已从线上删除

按你的意见删除冗长的排除项清单。批大小为一、逐请求独立评价、串行执行和无重叠的必要假设仍保留。

**我的意见：**


<a id="s55"></a>

#### S55

> Let $E_i^{\mathrm{acct}}$ denote the modeled energy attributed to executing a request on device $i$ within the accounting boundary specified below.

**中文意思：** E_i^acct 是设备 i 在下述核算边界内执行一次请求所对应的模型能量。

**讲解 / 作用：** 避免只说难懂的“模型增量能量”。它将模型计算、访存、控制和 Wi‑Fi 活动归到这个请求，并不是设备整个时间段的所有耗电。acct 是 accounted（已核算组成）的标签。

**我的意见：**


<a id="s55a"></a>

#### S55a

> Here, incremental refers to the inference-related energy components, not to an increase from one token or request to the next.

**中文意思：** 这里 incremental 指归属于推理的能量组成，不是相邻 token 或相邻请求之间的能量差。

**讲解 / 作用：** 不要理解为 E(第2步)−E(第1步) 这样的差分。本文把指定推理活动的能量加起来，排除基础系统、等待、显示等项；所以它也不等于整机电表或电池读数。公式仍是既有核算模型，没有新增实测声明。

**我的意见：**


<a id="s56"></a>

#### S56

> It includes computation, memory access, control, and radio operation, measured in joules.

**中文意思：** 它包括计算、访存、控制和无线操作，单位焦耳。

**讲解 / 作用：** GPU 能耗只是其中一部分。预测、优化和同步控制也在核算边界内，不能把它们一律当免费。

**我的意见：**


<a id="s57"></a>

#### S57

> Base system power, accelerator idle/waiting power, display power, unrelated workloads, and AP energy are excluded.

**中文意思：** 基础系统功率、加速器空闲或等待、显示、其他负载和 AP 能量不计入。

**讲解 / 作用：** 这些排除项不是说现实中不存在，而是当前预算只约束指定的增量组成。

**我的意见：**


<a id="s58"></a>

#### S58

> The budget $\bar E_i$ therefore constrains these specified request components; it does not represent a whole-device electricity or battery-lifetime limit.

**中文意思：** E_i 的预算因此只约束指定请求组件，不表示整机电量或电池寿命上限。

**讲解 / 作用：** 模型内满足预算，不等于真实整机一定满足同样的电池限制。所有保证都必须沿用这个边界。

**我的意见：**


<a id="s59"></a>

#### S59

> Figure 1 summarizes the execution order and the partition and resource decisions, with $\mathbf{c}^\star$ denoting the partition selected at deployment.

**中文意思：** 系统图概括执行顺序、分区决策和资源决策，c* 表示部署选定分区。

**讲解 / 作用：** 星号在此表示最终选出的解，不自动意味着对所有未来请求或所有可能策略全局最优。

**我的意见：**


<a id="s60"></a>

#### S60

> FIGURE: System architecture and resource decisions.

**中文意思：** 图注标题：系统架构与资源决策。

**讲解 / 作用：** Partition selection 表示由历史请求和固定预测器选跨请求共用分区；Request control 表示依据当前 P 和预测长度选资源。新版图下半部分的 Adjacent-device transfer 描述任意 1≤i<N 的 i→AP→i+1 传输，而非列出三台不同设备，因此也适用于 N=2。Token feedback 仅在还需要下一次前向时从 N 返回 1。输入 embedding 在设备 1，最终 normalization、head 和 token selection 在设备 N；图示不引入额外计算节点。

**我的意见：**


<a id="s61"></a>

#### S61

> The deployment partition is fixed across requests.

**中文意思：** 部署分区在各请求间固定。

**讲解 / 作用：** 这是跨请求保持不变，不是只在某一次请求内固定。

**我的意见：**


<a id="s62"></a>

#### S62

> The controller selects phase-specific GPU frequencies and device Wi-Fi transmit powers from arrival-time information; the selected resource vector remains fixed until the request is completed.

**中文意思：** 控制器根据请求到达时的信息选择两阶段 GPU 频率和设备 Wi-Fi 发射功率；所选资源向量直到请求完成都保持不变。

**讲解 / 作用：** 图注同步采用 S51 的口径：到达时一次选定两阶段配置，请求内不重新优化；阶段切换使用对应的已选值，不能理解为两阶段必须相同。AP 下行功率仍固定。

**我的意见：**


<a id="s63"></a>

#### S63

> The AP downlink uses a prescribed transmit power that is not optimized.

**中文意思：** AP 下行采用预设而非优化的发射功率。

**讲解 / 作用：** 图中的设备传输通过 AP 中转，不是设备 i 直接发到 i+1。源设备 Wi‑Fi 功率可调，路由器/AP 的转发功率固定；接收者和目的链路不同，下行时延仍会不同。请与 E14 两个分式一起读。

**我的意见：**


<a id="section-64"></a>

## IV 分层计算与内存模型

从层放置得到需求量，区分运算、访存和容量。

<a id="s64"></a>

#### S64

> The partition determines which layer and endpoint operators each device executes.

**中文意思：** 分区决定设备负责哪些层和端点算子。

**讲解 / 作用：** 这是从 III 的放置决策进入 IV 的资源需求。端点放置固定，层集合由切点决定。

**我的意见：**


<a id="s65"></a>

#### S65

> We first specify their computation, memory-access, and storage requirements, then derive a conservative memory requirement for admission.

**中文意思：** 先规定计算、访存和存储需求，再给出准入使用的保守内存需求。

**讲解 / 作用：** 不再把由分项容量合成的需求无条件称为精确峰值。F/D/W/S/V 的含义不变，原内存公式也保留。

**我的意见：**


<a id="s66"></a>

#### S66

> These quantities enter the latency and energy models in the next section.

**中文意思：** 这些量会进入下一节的时延和能量模型。

**讲解 / 作用：** IV 回答需要执行或存储多少，V 回答在给定设备和资源下需要多久、消耗多少能量。

**我的意见：**


<a id="section-67"></a>

### IV-A 层级与算子级量

F/D/W/S/V 的职责及组级核算的重要性。

<a id="s67"></a>

#### S67

> For layer $\ell$, let $F_\ell^{\mathrm{pre}}(P)$ denote the number of floating-point operations (FLOP) required to process a prompt of length $P$, and let $D_\ell^{\mathrm{pre}}(P)$ denote its effective memory traffic in bytes.

**中文意思：** 层 ℓ 的 prefill 计算量记为 F_ℓ^pre(P)，单位 FLOP；有效访存量记为 D_ℓ^pre(P)，单位 byte。

**讲解 / 作用：** FLOP 是操作次数，FLOP/s 才是吞吐。F 和 D 是需求量，不包含设备执行速度。

**我的意见：**


<a id="s68"></a>

#### S68

> For one decode step at context length $q$, the corresponding quantities are $F_\ell^{\mathrm{dec}}(q)$ and $D_\ell^{\mathrm{dec}}(q)$.

**中文意思：** 上下文为 q 的一个 decode 步对应 F_ℓ^dec(q)、D_ℓ^dec(q)。

**讲解 / 作用：** 不是整段响应的 decode 总量；总量还要对 G−1 个不同 q_t 的步骤求和。

**我的意见：**


<a id="s69"></a>

#### S69

> Memory traffic quantifies data transfers during execution, including repeated accesses and cache reuse under the specified runtime model; it is not the memory capacity occupied by the tensors.

**中文意思：** 访存量描述执行期间的数据传输，包括声明路径中的重复访问和缓存复用，不等于张量占据的容量。

**讲解 / 作用：** 同一份权重存一次，却可能被读很多次；缓存又可能避免部分外层传输，因此只知道权重大小不能确定 D。

**我的意见：**


<a id="s70"></a>

#### S70

> Memory traffic and the bandwidth and per-byte energy coefficients are defined at the same interface of the memory hierarchy.

**中文意思：** 访存量、带宽和每字节能量系数，都按同一存储层级的接口定义。

**讲解 / 作用：** 例如若 D 统计 GPU 主存到执行单元的数据量，β 和 ε 也应代表这些传输；不能把主存字节量除以某个缓存层的速度，更不能除以 Wi‑Fi 速度。所谓“边界”是计数从哪个内存层级到哪个层级，不是层分区边界 c_i。

**我的意见：**


<a id="s71"></a>

#### S71

> Let $W_\ell$ denote the storage required by layer $\ell$'s trained parameters, and let $S_\ell(q)$ denote the storage required for its inference-state tensors to continue generation at context length $q$.

**中文意思：** W_ℓ 是第 ℓ 层已训练参数所需容量；S_ℓ(q) 是在上下文长度 q 时，继续生成所需推理状态张量的容量。

**讲解 / 作用：** 权重是模型训练后给定的参数，不随这次生成逐 token 重训练；状态是这次推理产生并留到下一步使用的数据，如 KV 缓存或循环状态。W/S 都是存多少字节，D 则是执行期间累计搬多少字节，不能混为一谈。

**我的意见：**


<a id="s72"></a>

#### S72

> The inference state is retained between forward passes and comprises the KV cache for a full-attention layer or the state and convolutional cache for a recurrent layer.

**中文意思：** 状态在前向 pass 之间保留：全注意力层是 KV，循环层是循环状态和卷积缓存。

**讲解 / 作用：** 不能把所有层都套成随 q 线性增长的 KV。目标模型的两类层需要不同核算。

**我的意见：**


<a id="s73"></a>

#### S73

> Let $V_\ell^s(q)$ denote the size of the intermediate activation transmitted at a partition boundary after layer $\ell$ in phase $s$.

**中文意思：** V_ℓ^s(q) 是阶段 s 在层 ℓ 后切分时需要传输的中间激活字节数。

**讲解 / 作用：** 层是否成为边界由 c 决定，边界载荷大小由 V 给出。后面乘 8 换成 bit。

**我的意见：**


<a id="s74"></a>

#### S74

> All three quantities are measured in bytes.

**中文意思：** W、S 和 V 三种量都用字节计。

**讲解 / 作用：** 此处 three 指上一组权重、状态、激活，不包含 FLOP。明确单位有助于检查通信中的 8 倍换算。

**我的意见：**


<a id="s75"></a>

#### S75

> Their values depend on the model architecture, numerical precision, and runtime implementation.

**中文意思：** 这些量随模型架构、数值精度和运行时实现而变。

**讲解 / 作用：** 不能把某模型的层成本或 BF16 大小当成所有模型的常数；本模型需匹配当前目标和路径。

**我的意见：**


<a id="s76"></a>

#### S76

> The latency and energy models also include the input embedding, final normalization, output projection, and token selection.

**中文意思：** 时延和能量还计入输入嵌入、最终归一化、输出投影和 token 选择。

**讲解 / 作用：** 不仅统计解码层。尤其词表投影可能较大，端点设备的成本不能忽略。

**我的意见：**


<a id="s77"></a>

#### S77

> Let $\mathcal{O}_i^s(\mathbf{c},q)$ denote the ordered collection of operator groups executed by device $i$ in phase $s$ at length $q$.

**中文意思：** O_i^s(c,q) 是设备 i 在给定分区、阶段、长度下按顺序执行的算子组集合。

**讲解 / 作用：** 它把解码层和端点算子统一起来。ordered 表示执行有序，后续时间按组累加。

**我的意见：**


<a id="s77a"></a>

#### S77a

> An operator group is one modeled execution unit and may contain a single operation or several operations executed together by the runtime.

**中文意思：** 算子组是模型中一次核算的执行单元，可以是一个运算，也可以是运行时合并执行的多个运算。

**讲解 / 作用：** “算子”可理解为一个计算步骤，如矩阵乘法、归一化、注意力更新；“组”用于匹配运行时的执行单元，未规定所有模型都用一样分组。每组有自己的 F、D、时间和能量，再按顺序累加。

**我的意见：**


<a id="s77b"></a>

#### S77b

> Examples include a linear projection, an attention computation, or a fused normalization-and-elementwise kernel.

**中文意思：** 例子包括线性投影、注意力计算，或融合执行的归一化与逐元素运算。

**讲解 / 作用：** 这些只是分组例子，不声称当前虚拟测试床已测量这些内核。O_i^s(c,q) 列出设备 i 在该分区、阶段、形状下要执行哪些组，包含层内运算和 embedding/head 等端点；它不是设备集合或层集合。

**我的意见：**


<a id="s78"></a>

#### S78

> For operator group $o\in\mathcal{O}_i^s$, let $F_{io}^s(q)$ and $D_{io}^s(q)$ denote its FLOP count and effective memory traffic, and let $t_{io}^s$ and $e_{io}^s$ denote its execution time in seconds and incremental energy consumption in joules.

**中文意思：** 对于组 o，F、D 分别是计算和访存量，t、e 分别是执行秒数和增量焦耳数。

**讲解 / 作用：** 把需求 F、D 与代价 t、e 分开：代价需要进一步结合设备参数及所选频率。

**我的意见：**


<a id="s78a"></a>

#### S78a

> The duration $t_{io}^s$ is distinct from the integer decode-step index $t$ in (3).

**中文意思：** 执行时长 t_io^s 与上下文计数式中的整数 decode 步编号 t 不同。

**讲解 / 作用：** 确实复用了字母形状，但两个带完整记号的数学对象不同：无下标 t 是第几步，单位无；t_io^s 是该设备该组的秒数，单位 s；t_0 是每帧协议时间，单位 s。为不破坏既有公式及解法符号，本轮明确区分而不只为换字母进行全局重命名。

**我的意见：**


<a id="s79"></a>

#### S79

> For an operator group within decoder layer $\ell$, $r$ indexes the group, and $F_{\ell r}^s(q)$ and $D_{\ell r}^s(q)$ denote its FLOP count and memory traffic.

**中文意思：** 若组位于解码层 ℓ 内，r 是该层的组编号，F_ℓr 和 D_ℓr 表示其需求。

**讲解 / 作用：** o 是统一设备级算子编号，(ℓ,r) 是层内编号。两种写法不是两套重复计算。

**我的意见：**


<a id="s80"></a>

#### S80

> Operators outside the decoder layers are included as separate entries in the operator specification.

**中文意思：** 解码层之外的算子作为单独条目列入算子说明。

**讲解 / 作用：** 例如 embedding、head 不必强行归到某个解码层，仍可进入统一总和。

**我的意见：**


<a id="s81"></a>

#### S81

> Operator groups within a layer can have different ratios of computation to memory access.

**中文意思：** 同一层内不同算子组的计算量与访存量之比可能不同。

**讲解 / 作用：** 有的组偏计算密集，有的偏访存密集；一个层的平均比值可能掩盖这些差异。

**我的意见：**


<a id="s82"></a>

#### S82

> We therefore estimate each sequential group's execution time from its computation and memory-access requirements and then sum the group times.

**中文意思：** 因此先按每个串行算子组的需求估时，再把各组时间相加。

**讲解 / 作用：** 计算 max 的层级必须正确：每组先取瓶颈，再跨组求和。

**我的意见：**


<a id="s83"></a>

#### S83

> Applying a single maximum to aggregated FLOP counts and memory-traffic quantities would allow different groups' bottlenecks to overlap, contrary to the assumed sequential execution.

**中文意思：** 若把所有组的需求先相加再取一次 max，会让不同组的瓶颈互相重叠，与串行设定不符。

**讲解 / 作用：** 例如两个串行组各需 max(10,1) 和 max(1,10)，正确共 20，而汇总后 max(11,11)=11；数字仅作讲解。

**我的意见：**


<a id="s84"></a>

#### S84

> The Roofline model provides the compute-bound and memory-bound interpretation [cite: williams2009roofline,nvidia_gpu_performance]; effective throughput, bandwidth, and execution overheads specify the latency model used here.

**中文意思：** Roofline 提供计算受限与访存受限的解释；本文由有效吞吐、带宽和开销确定具体时延。

**讲解 / 作用：** 引用提供建模思想，不代表任何引用已经测量了本虚拟设备。系数仍须明确来源或假设。

**我的意见：**


<a id="section-85"></a>

### IV-B 架构和运行时相关需求

共同投影、两类层及输入输出端点要匹配实际路径。

<a id="s85"></a>

#### S85

> Tensor dimensions, layer types, weight and inference-state sizes, temporary-buffer lifetimes, and boundary activations are inputs supplied by the model architecture and runtime configuration.

**中文意思：** 张量维度、层类型、权重和状态大小、临时缓冲生命周期及边界激活，由模型架构和运行时配置提供，作为理论模型输入。

**讲解 / 作用：** 理论不是先规定必须用 Qwen 才成立，而是以这些需求量为参数。一次部署/求解需给定它们，才能评价分区；更换模型可改变输入量，但不把选择模型本身加入本文优化变量。

**我的意见：**


<a id="s85a"></a>

#### S85a

> The formulation is parameterized by these inputs and does not require a particular model name, although the architecture and runtime are fixed for each deployment.

**中文意思：** 该公式体系由这些输入参数化，不要求某个特定模型名称；但每次部署的架构和运行时是给定的。

**讲解 / 作用：** “通用参数化”与“求解时输入固定”可以同时成立。通用接口不意味着每个模型有相同层成本，也不意味着已证明任何硬件/架构都满足这里的有效系数近似。实验目标仍是 Qwen3.5-4B，未作更换。

**我的意见：**


<a id="s86"></a>

#### S86

> Architecture-dependent operation counts follow from tensor dimensions, while effective memory traffic and workspace requirements are supplied by the runtime model.

**中文意思：** 架构相关的运算计数可由张量维度确定；有效访存量和工作区需求由运行时模型提供。

**讲解 / 作用：** 按你的意见去掉正文中的清单式要求，改为说明这些量从何处进入模型。来源透明和假设说明仍保留在参数说明处，不把缺乏依据的量写成测量结果。

**我的意见：**


<a id="s87"></a>

#### S87

> Full-attention and recurrent layers are modeled separately because their inference-state structures and non-projection operations differ.

**中文意思：** 全注意力层和循环层分别建模，因为它们的推理状态结构及非投影运算不同。

**讲解 / 作用：** 不在通用理论段落先绑定 Qwen。全注意力层需要 KV 状态，循环层的状态结构由具体实现给出；两类层共用 F/D/S 接口，但不共用全部成本公式。具体目标的说明放在原有附录引用语境中。

**我的意见：**


<a id="s88"></a>

#### S88

> Appendix A gives the corresponding model-specific accounting details [cite: qwen35_4b_config,qwen35_hf_docs].

**中文意思：** 附录给出对应的模型专属核算细节。

**讲解 / 作用：** 原有 Qwen 文献键移到具体模型明细的附录指引处，没有新增或伪造文献。正文保持参数化理论，目标模型的配置例仍在既有附录和实验范围；本轮不修改那些章节。

**我的意见：**


<a id="s89"></a>

#### S89

> Let $d$ denote the model's hidden dimension and $v$ its vocabulary size.

**中文意思：** d 是隐藏维度，v 是词表大小。

**讲解 / 作用：** 它们是架构给定尺寸，不是设备频率或预测输出长度；后续投影成本用到二者。

**我的意见：**


<a id="s90"></a>

#### S90

> We distinguish the projection operations shared by the layer types from their attention or recurrent operations and retained inference states.

**中文意思：** 把层类型共有的投影，与各自的注意力/循环操作及保留状态分开核算。

**讲解 / 作用：** 投影公式可共用，不表示完整层计算相同。先讲共有部分，再讲类型专属部分。

**我的意见：**


<a id="s91"></a>

#### S91

> Consider a linear projection with input dimension $a$ and output dimension $b$.

**中文意思：** 考虑输入维度 a、输出维度 b 的线性投影。

**讲解 / 作用：** 这是为矩阵乘法计数建立小模型；a、b 都是维度数量，没有 Hz 或 byte 单位。

**我的意见：**


<a id="s92"></a>

#### S92

> Multiplying a $P\times a$ activation matrix by an $a\times b$ weight matrix requires $2Pab$ FLOP under the convention that a multiply-accumulate counts as two operations.

**中文意思：** P×a 的激活乘 a×b 的权重，在乘加算两次操作的约定下需要 2Pab FLOP。

**讲解 / 作用：** 每个 P×b 输出元素累计 a 次乘加，共 Pab 个乘加，再乘 2。FLOP 约定必须与吞吐系数一致。

**我的意见：**


<a id="s93"></a>

#### S93

> Let $\mathcal{A}_\ell$ denote the set of linear-projection weight matrices in layer $\ell$, and let $A\in\mathcal{A}_\ell$ denote one such matrix.

**中文意思：** A_ℓ 集合包含层 ℓ 的所有线性投影权重矩阵，普通 A 表示其中一块矩阵。

**讲解 / 作用：** 集合与单个矩阵不同。后面遍历集合累加各投影，不能只算 QKV 中某一块。

**我的意见：**


<a id="s94"></a>

#### S94

> The functions $\operatorname{rows}(A)$ and $\operatorname{cols}(A)$ give its row and column counts.

**中文意思：** rows(A)、cols(A) 分别取矩阵行数和列数。

**讲解 / 作用：** 行列数量的乘积给出矩阵权重元素数，也是每位置投影乘加的主要计数依据。

**我的意见：**


<a id="s95"></a>

#### S95

> The prefill and one-step decode FLOP counts for these projections, denoted by $F_{\mathrm{proj},\ell}^{\mathrm{pre}}(P)$ and $F_{\mathrm{proj},\ell}^{\mathrm{dec}}$, are

**中文意思：** 所有这些投影的 prefill 与单步 decode 计算量分别记为两个 F_proj，并由下式给出。

**讲解 / 作用：** prefill 有 P 个位置，而 batch=1 的单步 decode 只处理一个新位置，所以 E5 两式相差 P 因子。

**我的意见：**


<a id="e5"></a>

#### E5 · 对应原稿式 5–6 · 共同线性投影计算量

$$
F_{\mathrm{proj},\ell}^{\mathrm{pre}}(P)=2P\sum_{A\in\mathcal{A}_\ell}\mathrm{rows}(A)\mathrm{cols}(A)
$$

$$
F_{\mathrm{proj},\ell}^{\mathrm{dec}}=2\sum_{A\in\mathcal{A}_\ell}\mathrm{rows}(A)\mathrm{cols}(A)
$$

**符号与单位：** A_ℓ：本层所有投影矩阵；rows/cols：行列数；F 的单位 FLOP；乘加计两次操作。

**为什么这样写：** prefill 对 P 个位置投影，单步 decode 对一个新位置投影，因而相差 P 因子。

**用途 / 条件 / 示例：** 这是投影部分，不是整层全部 FLOP；注意力、循环更新及逐元素算子须另列。讲解例：单矩阵 2×3，P=4 时 48 FLOP，单步 12 FLOP。

**我的意见：**


<a id="s96"></a>

#### S96

> Let $d_{\mathrm{ff}}$ denote the intermediate dimension of a gated feed-forward block.

**中文意思：** d_ff 表示门控前馈块的中间维度。

**讲解 / 作用：** 采用该符号避免与消息编号 m 混淆。它是宽度参数，不是层数或消息长度。

**我的意见：**


<a id="s97"></a>

#### S97

> Its two $d\times d_{\mathrm{ff}}$ projections and one $d_{\mathrm{ff}}\times d$ projection require $6Pd d_{\mathrm{ff}}$ FLOP in prefill and $6d d_{\mathrm{ff}}$ FLOP per decode step.

**中文意思：** 两个 d×d_ff 和一个 d_ff×d 投影，prefill 共需 6Pdd_ff FLOP，单步 decode 需 6dd_ff FLOP。

**讲解 / 作用：** 三次投影各有 2dd_ff 的每位置成本，所以出现 6；此数不含随后列出的非矩阵算子。

**我的意见：**


<a id="s98"></a>

#### S98

> Normalization, nonlinearities, elementwise products, and residual operations are recorded separately; any omitted contribution must be identified as a modeling approximation.

**中文意思：** 归一化、非线性、逐元素乘法和残差单列；若省略某项，必须说明它是近似。

**讲解 / 作用：** 不能把主矩阵 FLOP 直接说成全部成本。是否近似属于模型说明，不凭讲解替作者决定省略。

**我的意见：**


<a id="s99"></a>

#### S99

> For a full-attention layer, let $h_q$ be the number of query heads and $d_h$ the dimension of each head.

**中文意思：** 全注意力层中 h_q 是查询头数，d_h 是每头维度。

**讲解 / 作用：** 这些决定 QKᵀ 和注意力加权 V 的矩阵乘法规模；与 KV 头数 h_kv 不一定相等。

**我的意见：**


<a id="s100"></a>

#### S100

> The approximate FLOP counts of the two attention matrix products, denoted by $F_{\mathrm{attn}}^{\mathrm{dec}}(q)$ and $F_{\mathrm{attn}}^{\mathrm{pre}}(P)$, are

**中文意思：** 两次注意力矩阵乘法的近似计算量分别记为 decode 和 prefill 的 F_attn，下式给出。

**讲解 / 作用：** 只计这两次主要乘法，不把 softmax 等自动算进去。prefill 的二次长度项与逐步 decode 的 q 项不同。

**我的意见：**


<a id="e6"></a>

#### E6 · 对应原稿式 7–8 · 全注意力主要矩阵乘法

$$
F_{\mathrm{attn}}^{\mathrm{dec}}(q)=4qh_qd_h
$$

$$
F_{\mathrm{attn}}^{\mathrm{pre}}(P)=4P^2h_qd_h\quad(\mathrm{dense})
$$

$$
F_{\mathrm{attn}}^{\mathrm{pre}}(P)=2P(P+1)h_qd_h\quad(\mathrm{triangular})
$$

**符号与单位：** h_q：查询头数；d_h：每头维度；dense 为完整矩阵乘法，triangular 为利用因果三角结构的内核。

**为什么这样写：** QKᵀ 和注意力乘 V 各产生一个 2 倍乘加成本，因此有 4。三角核只处理 P(P+1)/2 个因果位置对。

**用途 / 条件 / 示例：** 三行中后两行是二选一，不能相加；计数须与吞吐系数对应的内核匹配，不适用于循环层。

**我的意见：**


<a id="s101"></a>

#### S101

> The dense or triangular counting convention is used consistently for both the FLOP count and the effective-throughput coefficient.

**中文意思：** 密集或三角运算的计数口径，必须在 FLOP 数和有效吞吐系数中一致使用。

**讲解 / 作用：** F 是需要多少操作，ρf 是按同一口径每秒做多少操作。若 F 采用三角有效运算数，却直接混用按另一计数口径得到的吞吐，就不能保证 F/(ρf) 表示正确时间。也可以使用等效 FLOP 口径，但分子与吞吐必须成对转换，不是只改其中一项。

**我的意见：**


<a id="s102"></a>

#### S102

> Let $h_{kv}$ denote the number of key/value heads, $b_{kv}$ the number of bytes per KV-state element, and $S_{\mathrm{full}}(q)$ the memory occupied by the principal KV state of one full-attention layer.

**中文意思：** h_kv 是 KV 头数，b_kv 是每状态元素的字节数，S_full(q) 是一层主要 KV 状态占用。

**讲解 / 作用：** 这是容量计数；头数乘头维度、上下文长度和精度，不能使用查询头数代替 KV 头数。

**我的意见：**


<a id="s103"></a>

#### S103

> Then

**中文意思：** 于是得到下式。

**讲解 / 作用：** 此短语连接前述符号定义与 E7。应与公式一起读，不是独立技术断言。

**我的意见：**


<a id="e7"></a>

#### E7 · 对应原稿式 9 · 一层 KV 状态容量

$$
S_{\mathrm{full}}(q)=2qh_{kv}d_hb_{kv}
$$

**符号与单位：** h_kv：KV 头数；b_kv：每状态元素 byte；q：上下文长度；结果 byte。

**为什么这样写：** 前面的 2 来自 K、V 两份；每份 q×h_kv×d_h 个元素。这里的 2 不是 FLOP 乘加约定。

**用途 / 条件 / 示例：** 进入内存容量约束，不自动等于每步 D。讲解例：q=10、h_kv=2、d_h=4、b_kv=2，共 320 byte；不代替目标模型实际参数。

**我的意见：**


<a id="s104"></a>

#### S104

> For a recurrent layer, the non-projection operations and the retained recurrent state and convolutional cache are specified by the selected implementation.

**中文意思：** 循环层的非投影操作、循环状态和卷积缓存由所选实现规定。

**讲解 / 作用：** 循环层不仅有线性投影，还可能有状态更新和卷积；其确切张量不能通过 KV 公式猜测。

**我的意见：**


<a id="s105"></a>

#### S105

> Their computation, memory traffic, and state-memory requirements enter the same operator-level specification; the full-attention FLOP and KV-state expressions do not apply to them.

**中文意思：** 这些计算、访存和状态量进入同一算子说明，但不套用全注意力 FLOP 与 KV 状态式。

**讲解 / 作用：** 通用的是接口 F、D、S，不是类型专属公式。这里保护混合架构的核算正确性。

**我的意见：**


<a id="s106"></a>

#### S106

> Appendix A provides the model-specific tensor details.

**中文意思：** 附录给出具体目标模型的张量细节。

**讲解 / 作用：** 这句只是指向具体实现的明细。循环层不必保存随上下文线性增长的 KV 缓存，而是保存其实现规定的循环状态与卷积缓存；计算和容量须按这些实际张量定义。通用正文用 F、D、S 接口接收它们，不把全注意力的 4qh_qd_h 或 2qh_kvd_hb_kv 公式直接套到循环层。原讲解中的“不假造”是编辑者的工作原则，不是论文模型内容，本版删去该措辞。

**我的意见：**


<a id="s107"></a>

#### S107

> Endpoint operators are accounted for separately from the decoder layers.

**中文意思：** 端点算子在解码层之外单独核算。

**讲解 / 作用：** 这承接共有投影和类型专属层，最后补齐输入/输出两端，避免漏项。

**我的意见：**


<a id="s108"></a>

#### S108

> Let $n_{\mathrm{head}}^s$ denote the number of positions projected by the language-model head in phase $s$.

**中文意思：** n_head^s 是阶段 s 在语言模型头中实际进行词表投影的位置数。

**讲解 / 作用：** 重点是实际做了多少位置的矩阵乘法，不是最终保留了多少行输出。

**我的意见：**


<a id="s109"></a>

#### S109

> The principal matrix-multiplication cost is $2n_{\mathrm{head}}^sdv$ FLOP.

**中文意思：** 输出头主要矩阵乘法成本为 2n_head^s d v FLOP。

**讲解 / 作用：** 每位置从 d 维映射至 v 个词表分数；乘加两次，因此乘 2。

**我的意见：**


<a id="s110"></a>

#### S110

> Prefill may project the final position or all $P$ positions, depending on the execution path.

**中文意思：** prefill 可能只投影最后一个位置，也可能投影全部 P 个位置，取决于执行路径。

**讲解 / 作用：** 这不是优化器随便选的开关，而是已声明运行时行为。不同路径的 F 必须分别正确计数。

**我的意见：**


<a id="s111"></a>

#### S111

> Retaining only the final logits row after an all-position projection does not reduce the operations already performed [cite: hf_qwen35_implementation,hf_transformers_generation].

**中文意思：** 全位置投影做完后只保留最后一行 logits，不能减少已经发生的计算。

**讲解 / 作用：** 丢弃结果不等于没做计算。必须区分投影前切片与投影后取最后行。

**我的意见：**


<a id="s112"></a>

#### S112

> When the embedding and output head share parameters but are stored on different devices, the memory model includes each physical copy.

**中文意思：** 输入嵌入与输出头虽共享参数，但若分存在不同设备，内存模型计入每份物理副本。

**讲解 / 作用：** 模型唯一参数量不等于各设备实际存储之和。跨设备相同数值也可能需要两份存储。

**我的意见：**


<a id="section-113"></a>

### IV-C 准入内存需求

把权重、状态、同时存在的缓冲和运行时预留一次性核清。

<a id="s113"></a>

#### S113

> Let $U_i(\mathbf{c},s,q)$ denote the peak memory required for simultaneously allocated workspace and temporary buffers on device $i$ in phase $s$ at length $q$.

**中文意思：** U_i(c,s,q) 是设备在指定分区、阶段和长度下同时分配的工作区及临时缓冲峰值。

**讲解 / 作用：** 同时存在才需一起占内存；先后使用并可复用的缓冲不能全部相加。

**我的意见：**


<a id="s114"></a>

#### S114

> Let $M_{\mathrm{rt},i}$ denote the memory reserved by the inference service for its runtime, and let $W_{\mathrm{extra},i}$ denote the memory for embedding, final normalization, output-head parameters, and any required weight copies outside its assigned decoder layers.

**中文意思：** M_rt,i 是服务运行时预留；W_extra,i 是所分解码层之外的嵌入、末归一化、输出头和必要权重副本。

**讲解 / 作用：** 区分模型端点权重与运行时内存，也不要与 U 的临时缓冲重复核算。

**我的意见：**


<a id="s115"></a>

#### S115

> These quantities are measured in bytes.

**中文意思：** 这些量都以字节计。

**讲解 / 作用：** 与服务额度 M_bar 使用相同单位，才能直接比较。

**我的意见：**


<a id="s116"></a>

#### S116

> For an output length $G$, the set of phase-length pairs executed by a request is

**中文意思：** 输出长度为 G 的请求所执行的阶段-长度对组成下式集合。

**讲解 / 作用：** E8 枚举本次会经历的执行形状，为内存容量检查和逐步求和提供索引。

**我的意见：**


<a id="e8"></a>

#### E8 · 对应原稿式 10 · 请求经历的阶段与形状

$$
\mathcal{Q}(P,G)=\{(\mathrm{pre},P)\}\cup\{(\mathrm{dec},P+t):1\leq t<G\}
$$

**符号与单位：** 每个元素是一对 (阶段,执行长度)。Q 是形状集合，不是计算量或资源集合。

**为什么这样写：** 一次 prefill 加 G−1 个 decode 形状。G=1 时只有第一项。

**用途 / 条件 / 示例：** 内存检查代入 G_cap，实际代价汇总代入真实 G 或预测 G_hat。

**从一次生成理解集合：** $P=5,G=3$ 时，
$$
\mathcal Q(5,3)=\{(\mathrm{pre},5),(\mathrm{dec},6),(\mathrm{dec},7)\}.
$$

| 执行事件 | 集合元素 | 这次执行产生 |
| --- | --- | --- |
| 一次 prefill | $(\mathrm{pre},5)$ | 第 1 个输出 token |
| 第 1 次 decode | $(\mathrm{dec},6)$ | 第 2 个输出 token |
| 第 2 次 decode | $(\mathrm{dec},7)$ | 第 3 个输出 token |

decode 每步输入一个上次生成的 token，但其注意力可能面对多个上下文位置，所以第二坐标是上下文长度，不是本步新输入 token 数。$\cup$ 把 prefill 与 decode 的两类元素合在一起；冒号后列出整数步编号的范围。

在时延/能量式中，对这个集合求和意味着计入每次执行；在内存式中取最大意味着容量必须装得下每次执行中的最大需求。把 $G$ 换成 $G_{\mathrm{cap}}$，就是检查服务允许的完整范围。

**我的意见：**


<a id="s117"></a>

#### S117

> where the decode set is empty for $G=1$.

**中文意思：** G=1 时 decode 集合为空。

**讲解 / 作用：** 只有 prefill；空求和为零。这是重要边界情形，不能再计一次 decode。

**我的意见：**


<a id="s118"></a>

#### S118

> To test memory feasibility for all permitted output lengths, we evaluate the largest memory requirement over $\mathcal Q(P,{G_{\mathrm{cap}}})$.

**中文意思：** 检查所有允许输出长度的内存可行性时，在 Q(P,G_cap) 中取最大内存需求。

**讲解 / 作用：** 这里检查的是各阶段/长度对应的容量要求的最大值，不把整个生成过程的存储量累加，也不暗示该保守式等于实测瞬时峰值。

**我的意见：**


<a id="s119"></a>

#### S119

> The resulting conservative memory requirement, denoted by $M_i(\mathbf{c};P,{G_{\mathrm{cap}}})$, is

**中文意思：** 得到的保守内存需求记为 M_i(c;P,G_cap)，如下定义。

**讲解 / 作用：** M_i 是模型准入容量要求，不是实测瞬时峰值。状态所需容量与临时缓冲峰值相加可以保守计费；只有各项峰值同时出现时，才等于实际峰值。

**我的意见：**


<a id="e9"></a>

#### E9 · 对应原稿式 11 · 设备保守内存需求

$$
M_i=\sum_{\ell\in\mathcal{L}_i(\mathbf{c})}W_\ell+W_{\mathrm{extra},i}
$$

$$
\quad+\max_{(s,q)\in\mathcal{Q}(P,G_{\mathrm{cap}})}\left[\sum_{\ell\in\mathcal{L}_i(\mathbf{c})}S_\ell(q)+U_i(\mathbf{c},s,q)\right]+M_{\mathrm{rt},i}
$$

**符号与单位：** 为简洁展示省略 M_i 的参数；完整参数为 (c;P,G_cap)。W：层权重；W_extra：端点及副本；S：状态；U：临时缓冲峰值；M_rt：服务运行时预留。均为 byte。

**为什么这样写：** 权重与运行时预留计一次；每个合法形状的状态容量与临时缓冲峰值相加，再对形状取最大。不同阶段和长度不是同时执行，不能累计全部容量。如果状态与临时缓冲峰值不同步，这个和是保守上界，而不是精确瞬时峰值。

**用途 / 条件 / 示例：** 要求 $M_i\leq\bar M_i$。状态容量项必须覆盖该前向执行全过程所需分配，临时缓冲项不能重复包含同一状态。$\bar M_i$ 是整个推理服务的总额度，已经排除非服务占用；服务自己的运行时预留 $M_{\mathrm{rt},i}$ 仍是额度内的开销，计在本式左边最后一项，而不是被忽略。也可等价地把运行时预留移到右边，但必须同时从左边移除，不能重复扣除。此式可能保守地缩小准入空间；只有证明单调后，才能简化形状遍历。

**我的意见：**


<a id="s120"></a>

#### S120

> The memory constraint is $M_i(\mathbf{c};P,{G_{\mathrm{cap}}})\leq\bar M_i$, where $\bar M_i$ is the service allocation introduced in Section III.

**中文意思：** 内存需求必须不超过 III 定义的服务额度 M_bar,i。

**讲解 / 作用：** 左边是要用多少，右边是允许用多少；可行性判断不能调换角色。

**我的意见：**


<a id="s121"></a>

#### S121

> The runtime reserve $M_{\mathrm{rt},i}$ is charged once in the requirement on the left-hand side.

**中文意思：** 运行时预留只在左侧需求中计一次。

**讲解 / 作用：** 额度已经排除了非服务占用，但未再次扣掉同一服务预留。

**我的意见：**


<a id="s122"></a>

#### S122

> The maximum checks every executed phase–length pair, while $U_i$ accounts for simultaneous workspace and temporary-buffer allocations rather than summing reusable buffers across layers.

**中文意思：** 最大值检查每个执行的阶段—长度组合；U_i 按同时分配的工作区和临时缓冲计费，不逐层累加可复用缓冲。

**讲解 / 作用：** 区分两种最大值：外层 max 检查不同形状，U_i 内部的峰值检查同一形状下同时存活的临时内存。状态容量另计，不能据此声称各项峰值必然同时发生。

**我的意见：**


<a id="s122a"></a>

#### S122a

> The state-memory term must cover the state allocations throughout the corresponding forward pass; adding this capacity requirement to the temporary-buffer peak gives a conservative bound when their peaks do not coincide.

**中文意思：** 状态内存项必须覆盖相应前向执行全过程的状态分配；若它与临时缓冲峰值不同步，将两者相加得到保守上界。

**讲解 / 作用：** 这是内存式保守解释成立的条件，不声称已测到这样的上界。S_ℓ(q) 需包含该形状下状态分配所需容量，U_i 不再重复计同一状态。可能高估需求、缩小准入空间，但不能凭这种保守性保证现实参数误差也被覆盖。

**我的意见：**


<a id="s123"></a>

#### S123

> Every execution length through the cap is checked unless monotonicity of the memory requirement has been established.

**中文意思：** 除非证明内存需求单调，否则检查到硬上限为止的每个执行长度。

**讲解 / 作用：** 不能仅凭 KV 增长就断言总峰值单调，工作区可能随形状变化。

**我的意见：**


<a id="section-124"></a>

## V 时延与增量能量模型

把需求转换成秒和焦耳，再汇总请求成本。

<a id="s124"></a>

#### S124

> Using the operator and storage requirements defined above, this section models computation and wireless communication separately and aggregates their costs over the request.

**中文意思：** 本节依据前面的需求，分别建模计算和无线通信，再汇总请求代价。

**讲解 / 作用：** IV 给需求，V 把需求变成秒和焦耳；不是重新定义分区。

**我的意见：**


<a id="s125"></a>

#### S125

> The resulting latency and per-device incremental energy determine the objective and energy constraints of the optimization problem.

**中文意思：** 得到的时延和各设备增量能量分别用于优化目标及能量约束。

**讲解 / 作用：** 最小化时延，不是最小化能量；能量是必须遵守的上限。

**我的意见：**


<a id="section-126"></a>

### V-A 计算时延与增量能量

组内 max、组间 sum；四项能量必须互不重复。

<a id="s126"></a>

#### S126

> For operator group $r$ in layer $\ell$ on device $i$, let $\rho_{i\ell r}^s$ denote the effective FLOP count per cycle of the GPU core clock and $\beta_{i\ell r}^s$ the effective memory bandwidth in bytes per second.

**中文意思：** 设备 i、层 ℓ、组 r 的 ρ 是每个 GPU 核心时钟周期的有效 FLOP 数；β 是有效字节每秒内存带宽。

**讲解 / 作用：** ρ 是整个所建模算子组的有效系数，不是某个单独计算核心的吞吐；不能在 ρf 上再额外乘一次核心数量。单位与原式相同。

**我的意见：**


<a id="s127"></a>

#### S127

> At frequency $f_i^s$, the effective compute throughput is $\rho_{i\ell r}^s f_i^s$ FLOP/s.

**中文意思：** 频率 f 下，有效计算吞吐为 ρf FLOP/s。

**讲解 / 作用：** 每周期操作数乘每秒周期数，单位变为每秒操作数。

**我的意见：**


<a id="s128"></a>

#### S128

> These positive coefficients are specified for each device, operator group, phase, and tensor shape, rather than taken as universal hardware constants.

**中文意思：** 这些正系数按设备、算子组、阶段和张量形状规定，而不是一组普遍适用的硬件常数。

**讲解 / 作用：** ρ、β 是给定形状下的有效计算/访存能力；同一 GPU 上，大矩阵、小矩阵、prefill 与 decode 的利用率可能不同，因此要说明参数对应的执行对象。不同对象也可以恰好使用相同参数，但不能无依据地宣称一个参数普遍精确。

**我的意见：**


<a id="s128b"></a>

#### S128b

> Execution shape refers to tensor dimensions, such as prompt-position count in a prefill projection or context length in a decode attention computation.

**中文意思：** 执行形状指张量的尺寸，例如 prefill 投影处理多少个输入位置，或 decode 注意力面对多长的上下文。

**讲解 / 作用：** 不是设备外形。prefill 投影输入可为 P×a；单步 decode 投影输入是 1×a；decode 全注意力的一行查询会与 q 个上下文位置交互。这些尺寸影响 F、D 以及所采用的有效系数。

**我的意见：**


<a id="s128a"></a>

#### S128a

> The shape dependence of these coefficients is suppressed in the notation; for each fixed shape, both are treated as independent of the selected frequency within the declared operating bounds.

**中文意思：** 符号省略了系数对执行形状的依赖；给定形状后，在声明的频率范围内，将两系数视为不随所选频率变化。

**讲解 / 作用：** 这是有效计算模型的固定系数近似，不是真实硬件规律。允许不同 q 的系数不同；对固定 q，ρf 才是线性频率吞吐，D/β 才不随 f 变化。不会把厂家峰值自动当作应用系数。

**我的意见：**


<a id="s129"></a>

#### S129

> The bytes counted by $D_{\ell r}^s$ and the bandwidth $\beta_{i\ell r}^s$ refer to the same memory interface.

**中文意思：** D_ℓr^s 计数的字节量与 β_iℓr^s 的带宽，对应同一个内存接口。

**讲解 / 作用：** “同一传输边界”就是同一条数据搬运路径。教学例：若该接口要搬 100 MB，有效带宽为 50 GB/s，按十进制单位 D/β=2 ms；不能用另一缓存或 Wi‑Fi 的带宽来除。例子不是设备测量或参数设定。

**我的意见：**


<a id="s130"></a>

#### S130

> Let $\tau_{i\ell r}^s\geq0$ denote a fixed execution overhead in seconds.

**中文意思：** τ≥0 是该组固定执行开销，单位秒。

**讲解 / 作用：** 固定 launch 等时间不随计算量除以吞吐自动消失。

**我的意见：**


<a id="s131"></a>

#### S131

> The group's execution time is modeled as

**中文意思：** 该组执行时间用下式建模。

**讲解 / 作用：** E10 是声明的分析近似，不是未经说明的真实硬件计时结果。

**我的意见：**


<a id="e10"></a>

#### E10 · 对应原稿式 12 · 算子组瓶颈时延

$$
t_{i\ell r}^s=\max\left(\frac{F_{\ell r}^s}{\rho_{i\ell r}^sf_i^s},\frac{D_{\ell r}^s}{\beta_{i\ell r}^s}\right)+\tau_{i\ell r}^s
$$

**符号与单位：** ρf：FLOP/s；β：byte/s；τ：s；F、D 的 q 参数在原文中省略。

**为什么这样写：** 计算秒数 F/(ρf) 与访存秒数 D/β 取较大者，表示组内理想化重叠，再加固定开销。

**用途 / 条件 / 示例：** 跨组再求和。讲解例：两种时间为 3、5 ms，开销 1 ms，组时延为 6 ms，不是 9 ms。改变 f 对访存受限组可能无时延收益。

**我的意见：**


<a id="s132"></a>

#### S132

> where the length argument $q$ of the FLOP count and memory traffic is omitted for readability.

**中文意思：** 为了简洁，省略 F 和 D 的长度参数 q。

**讲解 / 作用：** 省略记号不等于不依赖长度；读每个 decode 步时应代入 P+t。

**我的意见：**


<a id="s133"></a>

#### S133

> The maximum models overlap between computation and memory transfers within an operator group, while distinct operator groups execute sequentially.

**中文意思：** max 表示组内计算与访存重叠，而不同组串行。

**讲解 / 作用：** 组内瓶颈取较慢一项；组间则累加，不能跨组抵消瓶颈。

**我的意见：**


<a id="s134"></a>

#### S134

> It does not introduce overlap between devices or between model execution and wireless communication.

**中文意思：** 这不引入设备间、或模型计算与无线通信之间的重叠。

**讲解 / 作用：** 区分不同层次的 overlap，避免与 III 的串行假设矛盾。

**我的意见：**


<a id="s135"></a>

#### S135

> Effective coefficients must be specified for the declared execution path using public information or explicit assumptions, rather than equating advertised peak values with application performance.

**中文意思：** 有效系数须匹配声明路径，以公开信息或明确假设规定，而非把广告峰值当应用性能。

**讲解 / 作用：** 这是参数依据要求，不暗示已经实测或完成校准。

**我的意见：**


<a id="s136"></a>

#### S136

> The incremental energy consumption of the same operator group is

**中文意思：** 同一算子组的增量能量如下。

**讲解 / 作用：** E11 将运算、搬运、残余活跃和启动能量分开。

**我的意见：**


<a id="e11"></a>

#### E11 · 对应原稿式 13 · 组级增量能量四项

$$
e_{i\ell r}^s=\kappa_{i\ell r}^sF_{\ell r}^s(v_{0,i}^s+v_{1,i}^sf_i^s)^2+\epsilon_{i\ell r}^sD_{\ell r}^s
$$

$$
\quad+P_{\mathrm{act},i\ell r}^st_{i\ell r}^s+e_{\mathrm{launch},i\ell r}^s
$$

**符号与单位：** κ：J/(FLOP·V²)；ε：J/byte；P_act：W；t：s；e_launch：J。v_0+v_1f 是电压。

**为什么这样写：** 四项各为焦耳：开关、访存、残余活跃、启动。残余功率必须排除已由前两项表示的组件，不能用总额定功率代替。

**用途 / 条件 / 示例：** 进入设备总能量。频率升高可能缩短 P_act·t，却增加电压平方项；能耗不等于简单功率或固定每层常数。

**我的意见：**


<a id="s137"></a>

#### S137

> where $\kappa_{i\ell r}^s$ is the switching-energy coefficient in $\mathrm{J}/(\mathrm{FLOP}\cdot\mathrm{V}^2)$, $\epsilon_{i\ell r}^s$ is the memory-access energy per byte, $P_{\mathrm{act},i\ell r}^s$ is the residual active power in watts after excluding the switching and memory-access components, and $e_{\mathrm{launch},i\ell r}^s$ is the fixed launch energy in joules.

**中文意思：** κ 是每 FLOP 每电压平方的开关能耗系数；ε 是每字节访存能量；P_act 是排除前两项后的残余活跃功率；e_launch 是固定启动焦耳数。

**讲解 / 作用：** 残余功率不是整机或整个 GPU 总功率，否则再加开关和访存会重复计费。V 在单位中表示伏特。

**我的意见：**


<a id="s138"></a>

#### S138

> The voltage model is $V_i^s(f)=v_{0,i}^s+v_{1,i}^sf$, with nonnegative intercept $v_{0,i}^s$ and slope $v_{1,i}^s$, measured in volts and volts per hertz.

**中文意思：** 电压用仿射式 V(f)=v_0+v_1f 表示；非负截距单位 V，非负斜率单位 V/Hz。

**讲解 / 作用：** 斜率乘频率后才成为电压。这里的电压 V_i 与边界张量大小 V_ℓ 要按下标和上下文区分。

**我的意见：**


<a id="s139"></a>

#### S139

> For fixed operation counts, CMOS switching energy depends on the squared voltage [cite: chandrakasan1992lowpower]; the affine voltage model specifies its dependence on frequency.

**中文意思：** 固定操作数量时，CMOS 开关能量与电压平方相关；仿射电压式进一步建立与频率的关系。

**讲解 / 作用：** 不是直接套 CPU 每样本周期公式。频率改变电压，也改变时间。

**我的意见：**


<a id="s140"></a>

#### S140

> The four terms account for switching, memory access, residual active operation, and launch overhead, respectively.

**中文意思：** 四项依次表示开关、访存、残余活跃和启动开销。

**讲解 / 作用：** 理解每项的物理解释，比记住一长串下标更重要。

**我的意见：**


<a id="s141"></a>

#### S141

> The memory-access coefficient must use the same traffic definition as $D_{\ell r}^s$, and the four components must be parameterized without overlap.

**中文意思：** 访存系数须匹配 D 的定义，四项参数不能重复覆盖同一能量。

**讲解 / 作用：** “分别相加”成立的前提是核算项互不重叠，而不只是每项单位对。

**我的意见：**


<a id="s142"></a>

#### S142

> All energy coefficients and additive energy terms are nonnegative.

**中文意思：** 所有能耗系数和附加能量项非负。

**讲解 / 作用：** 这支撑后面的长度上限保证：额外 decode 步不能带来负能量。

**我的意见：**


<a id="s142a"></a>

#### S142a

> For a fixed operator group and execution shape, the energy coefficients are also treated as frequency independent; frequency dependence enters through the affine voltage model and the execution time.

**中文意思：** 给定算子组和执行形状后，能量系数也按不随频率变化处理；频率影响通过仿射电压模型和执行时间进入。

**讲解 / 作用：** 明确 κ、ε、P_act 和固定启动能量在频率优化中的口径。能量仍随 f 变化，只是变化由原式中电压平方和 t(f) 两条路径表达。这是分析假设，不是已验证的硬件拟合结论。

**我的意见：**


<a id="s143"></a>

#### S143

> Equations 12 and 13 also apply to operators outside the decoder layers by replacing $(\ell,r)$ with $o$.

**中文意思：** 把层内索引 (ℓ,r) 换为统一算子索引 o，这两式也用于层外算子。

**讲解 / 作用：** 输入嵌入和输出头通过相同代价接口纳入，不另造不一致总和。

**我的意见：**


<a id="s144"></a>

#### S144

> Each coefficient must have a stated source, derivation, or simulation assumption.

**中文意思：** 每个系数必须说明来源、推导或模拟假设。

**讲解 / 作用：** must 是规范要求，不等于来源表已经全部完成。

**我的意见：**


<a id="s145"></a>

#### S145

> If a voltage model is fitted, its approximation error must be reported over the specified operating levels; assumed coefficients require explicit uncertainty ranges.

**中文意思：** 若拟合电压模型，应报告工作等级内误差；假设系数应给出明确不确定范围。

**讲解 / 作用：** 条件句不宣称已有拟合结果，本讲解也不替作者虚构误差值。

**我的意见：**


<a id="s146"></a>

#### S146

> Rated device power alone does not determine operator-level energy coefficients.

**中文意思：** 仅靠设备额定功率无法确定算子级能耗系数。

**讲解 / 作用：** 额定 W 不能唯一反推出每 FLOP 的 κ 和每 byte 的 ε。

**我的意见：**


<a id="s147"></a>

#### S147

> A non-affine voltage table can be evaluated on the finite resource grid, but the continuous convexity result in Section VII requires the stated affine model.

**中文意思：** 非仿射电压表可用于有限网格评价，但后面的连续凸性结论要求当前仿射模型。

**讲解 / 作用：** 离散枚举能处理表格，不意味着同一个连续证明仍适用。

**我的意见：**


<a id="s148"></a>

#### S148

> Prior DVFS studies motivate frequency control without providing directly transferable coefficients for different hardware [cite: zhang2023dvfo].

**中文意思：** 已有 DVFS 研究支持频率控制的动机，但不能直接提供可跨硬件搬用的系数。

**讲解 / 作用：** 引用方法思想与转移数值参数是两件事。DVFS 指动态电压与频率调节。

**我的意见：**


<a id="s149"></a>

#### S149

> Let $E_{\mathrm{ctrl},i}\geq0$ denote a specified per-request control-energy reserve on device $i$ for prediction, optimization, synchronization, and phase transitions.

**中文意思：** E_ctrl,i≥0 是设备 i 为每次请求的预测、优化、同步和阶段切换规定的控制能量预留。

**讲解 / 作用：** 本轮将含糊的“控制能量”明确为保守预留，按控制操作的声明执行位置分配到各设备；不是假定每台设备都运行预测器。此项计入同一增量能量预算。

**我的意见：**


<a id="s150"></a>

#### S150

> The reserve is assumed to cover these operations uniformly over the permitted prompt domain and legal resource configurations, independently of the predicted and realized output lengths.

**中文意思：** 假定该预留覆盖允许输入域和合法配置中的这些控制操作，并且不依赖预测或实际输出长度。

**讲解 / 作用：** 这是本轮明确加入的统一上界假设，必须以参数来源或明确假设支持，不能当作已完成测量。它使固定 P,c 下的准入集合不因 G_hat 改变，也让不同停止长度共享同一固定控制项。若现实控制消耗超过预留，模型保证就不能直接作为现实保证。

**我的意见：**


<a id="s151"></a>

#### S151

> Both the executable policy and the continuous reference charge this same reserve; any transition-dependent accounting requires a bound that preserves the stated admission guarantee.

**中文意思：** 可执行策略与连续参考计入同一个预留；若使用依赖切换配置的核算方式，必须有保持既定准入保证的界。

**讲解 / 作用：** 本文主模型统一使用预留，避免有限策略与连续参考采用不同约束口径。配置相关切换能量只有被统一预留覆盖时，才不破坏所述保证；不在这里实施或修改实验核算。

**我的意见：**


<a id="s152"></a>

#### S152

> A lower-bound comparison using different control-energy accounting requires the feasible-set inclusion condition stated in Section VII.

**中文意思：** 如果比较双方采用不同控制能量核算，连续参考作为下界还需满足解法章节所述可行集合包含条件。

**讲解 / 作用：** 控制开销核算不同，不能仅因变量连续就宣称最优值是下界；必须检查有限合法可行点是否包含在所比较的连续可行集合中。这里只说明适用条件，不展开求解方法。

**我的意见：**


<a id="section-153"></a>

### V-B 无线时延与增量能量

两跳经 AP、分帧与 ACK、设备收发能量和消息枚举。

<a id="s153"></a>

#### S153

> Let $R_i(p)$ denote the modeled single-hop Wi-Fi transmission rate, in bits per second, between device $i$ and the AP at radio-frequency output power $p$ watts.

**中文意思：** R_i(p) 是设备 i 与 AP 之间一跳 Wi‑Fi 链路在射频功率 p W 下的模型速率，单位 bit/s。

**讲解 / 作用：** 它只是某一跳的速度，不是设备 i 到设备 j 的全程有效吞吐。设备间消息需两跳，上行由源设备功率决定，下行由 AP 功率与目的设备链路决定，完整时间在 E14 相加。

**我的意见：**


<a id="s153a"></a>

#### S153a

> A device-to-device transfer comprises a device-to-AP uplink followed by an AP-to-device downlink, rather than a direct device-to-device link.

**中文意思：** 设备间传输由设备→AP 的上行和 AP→设备的下行组成，不是直接设备对设备传输。

**讲解 / 作用：** 你理解的“上传和下载”对应这两段无线转发，不是把模型或请求上传云服务器处理。源发给 AP，AP 再发给目标设备；AP 不执行 LLM 层。两跳顺序传输，不能只计一段时间。

**我的意见：**


<a id="s154"></a>

#### S154

> Let $B>0$ be the channel bandwidth in hertz, $\xi>0$ a dimensionless effective-rate factor, $\gamma_i>0$ the effective channel gain-to-noise ratio per watt, and $R_{\max}>0$ the rate ceiling in bits per second.

**中文意思：** B 为信道带宽 Hz；ξ 为正的无量纲有效速率因子；γ_i 为每瓦有效增益噪声比；R_max 为速率上限 bit/s。

**讲解 / 作用：** 保留 ξ>0 的原域，改称 effective-rate factor，避免称“效率”却未规定不超过 1 的歧义。没有把 ξ 的范围缩小，也没有改变速率公式或系数值。γp 必须无量纲。

**我的意见：**


<a id="s155"></a>

#### S155

> The rate model is

**中文意思：** 速率模型如下。

**讲解 / 作用：** E12 同时体现随功率增长和饱和上限。

**我的意见：**


<a id="e12"></a>

#### E12 · 对应原稿式 14 · 功率到无线速率

$$
R_i(p)=\min\{R_{\max},\xi B\log_2(1+\gamma_i p)\}
$$

**符号与单位：** p：射频 W；γ：W⁻¹；B：Hz；ξ：无量纲；R：bit/s。

**为什么这样写：** γp 是线性信噪比；对数体现边际收益递减；min 加入速率上限。

**用途 / 条件 / 示例：** 给出两跳中的各链路速度。饱和后继续增 p 不加快速率，却仍可能增加功放能量。这是有效速率近似，不是物理验证。

**我的意见：**


<a id="s156"></a>

#### S156

> which uses the logarithmic signal-to-noise relationship of a wireless link [cite: tse2005wireless].

**中文意思：** 该式采用无线速率与信噪比的对数关系。

**讲解 / 作用：** 是建模依据，不是说家用 Wi-Fi 实测等于 Shannon 容量。

**我的意见：**


<a id="s157"></a>

#### S157

> The effective-rate factor and rate ceiling specify a link-rate approximation; framing and protocol overheads are accounted for separately below.

**中文意思：** 有效速率因子和速率上限构成链路速率近似；成帧和协议开销在下文另计。

**讲解 / 作用：** ξ 不能无说明地包含随后 H、C、t_0 再次计入的协议开销，否则重复计算。这里仍是链路模型，而不是两跳载荷 goodput。

**我的意见：**


<a id="s158"></a>

#### S158

> Let $p_{\mathrm{ref}}>0$ denote a reference transmit power and $\mathrm{SNR}_{\mathrm{ref},i}$ the corresponding signal-to-noise ratio in decibels.

**中文意思：** p_ref 是正参考发射功率，SNR_ref,i 是对应 dB 信噪比。

**讲解 / 作用：** dB 是对数单位，不能直接当线性 γp 代入。

**我的意见：**


<a id="s159"></a>

#### S159

> Then $\gamma_i=10^{\mathrm{SNR}_{\mathrm{ref},i}/10}/p_{\mathrm{ref}}$.

**中文意思：** 因此 γ_i 等于 10 的 SNR_dB/10 次方，再除以参考功率。

**讲解 / 作用：** 先把 dB 转成线性比值，再按功率归一化，得到每瓦系数。

**我的意见：**


<a id="s160"></a>

#### S160

> The nominal model assumes reciprocal effective client-AP link coefficients, so the fixed-power AP downlink to device $j\in\mathcal{N}$ has rate $R_j(p_{\mathrm{AP}})$.

**中文意思：** 标称模型假设客户端与 AP 的有效链路系数互易，所以到设备 j 的下行速率为 R_j(p_AP)。

**讲解 / 作用：** 互易是声明假设；下行由固定 AP 功率决定，不由发送设备 i 的功率决定。

**我的意见：**


<a id="s161"></a>

#### S161

> Consider a message from device $i$ to device $j$ with payload size $S$ bits.

**中文意思：** 考虑设备 i 发给 j 的消息，有效载荷 S bit。

**讲解 / 作用：** S 是这条消息的位数，不是层状态字节量 S_ℓ(q)。看下标区分。

**我的意见：**


<a id="s162"></a>

#### S162

> The uplink and downlink are sequential, so both airtimes contribute to the message delay.

**中文意思：** 上行与下行顺序发生，两段空口时间都计入这条消息的时延。

**讲解 / 作用：** 完整 h_ij = 上行数据时间 + 下行数据时间 + 合并协议时间。E14 的两个分母分别是 R_i(p_i) 和 R_j(p_AP)，因此设备与 AP 的两个功率不能混用。

**我的意见：**


<a id="s163"></a>

#### S163

> Let $L_{\mathrm{pay}}>0$ denote the maximum payload bits per frame, $H\geq0$ the per-frame header and padding bits, and $C(S)\geq0$ the same-direction control bits.

**中文意思：** L_pay 是每帧最大载荷 bit，H 是每帧头部和填充 bit，C(S) 是同方向控制 bit，均按声明条件取值。

**讲解 / 作用：** 分帧头开销乘帧数；C 的具体形式仍需给定，不由这一式自动决定。

**我的意见：**


<a id="s164"></a>

#### S164

> The number of frames $n(S)$ and the total transmitted data-direction bits $S_{\mathrm{air}}(S)$ are

**中文意思：** 帧数 n(S) 和数据方向总空口位数 S_air(S) 如下。

**讲解 / 作用：** E13 把有效载荷转为实际需发送的位数。

**我的意见：**


<a id="e13"></a>

#### E13 · 对应原稿式 15 · 载荷、帧数与空口位数

$$
n(S)=\lceil S/L_{\mathrm{pay}}\rceil
$$

$$
S_{\mathrm{air}}(S)=S+n(S)H+C(S)
$$

**符号与单位：** S：有效载荷 bit；L_pay：bit/frame；n：整数帧数；H：每帧头/填充 bit；C：同方向控制 bit。

**为什么这样写：** 先上取整确定帧数，再把帧头和控制开销加入。反向 ACK 不在 S_air 内。

**用途 / 条件 / 示例：** 时延和数据空口能量使用 S_air，不只用 S。讲解例：S=2500、L_pay=1000、H=100、C=0，需 3 帧、2800 bit。

**我的意见：**


<a id="s165"></a>

#### S165

> where $\lceil\cdot\rceil$ denotes rounding upward to an integer.

**中文意思：** 上取整符号表示向上取最近整数。

**讲解 / 作用：** 不足一整帧的最后一部分也需要一帧，不能用小数帧数计头部开销。

**我的意见：**


<a id="s166"></a>

#### S166

> Reverse-direction acknowledgment (ACK) bits are excluded from $S_{\mathrm{air}}$.

**中文意思：** 反方向 ACK 位不包含在 S_air 中。

**讲解 / 作用：** 并非不计 ACK：其时间进 t_0、能量进固定帧项，避免在两处重复算。

**我的意见：**


<a id="s167"></a>

#### S167

> With the same aggregate frame format on both hops, the message delay is

**中文意思：** 两跳采用同样汇总帧格式时，消息时延如下。

**讲解 / 作用：** 这是 E14 的适用条件。若两跳帧格式不同，不能不改参数就复用同一 S_air。

**我的意见：**


<a id="e14"></a>

#### E14 · 对应原稿式 16 · 经 AP 的两跳消息时延

$$
h_{ij}(S,p_i)=\frac{S_{\mathrm{air}}(S)}{R_i(p_i)}+\frac{S_{\mathrm{air}}(S)}{R_j(p_{\mathrm{AP}})}+n(S)t_0
$$

**符号与单位：** 首项源上行，第二项 AP 下行，末项两跳合并每帧协议开销；单位均 s。

**为什么这样写：** 两跳串行，所以相加。设备 i 的可变功率只影响上行；下行由目的 j 的链路及固定 AP 功率决定。

**用途 / 条件 / 示例：** 每条消息进入总时延一次。t_0 已包括声明的反向回复时间，但不再包含这两项数据空口时间。

**我的意见：**


<a id="s168"></a>

#### S168

> where $h_{ij}$ is measured in seconds and $p_i$ is the source device's Wi-Fi transmit power for the applicable phase.

**中文意思：** h_ij 以秒计，p_i 是源设备在对应阶段的 Wi‑Fi 发射功率。

**讲解 / 作用：** 根据消息的源设备和阶段，从 z 中取 p_i^pre 或 p_i^dec；不是接收设备的功率，也不是 AP 功率。

**我的意见：**


<a id="s169"></a>

#### S169

> The nonnegative constant $t_0$ is the combined per-frame protocol time across the two hops, including interframe intervals and reverse ACK airtime at fixed reply rates and powers.

**中文意思：** 非负 t_0 是两跳合并的每帧协议时间，包括帧间间隔和固定回复速率/功率下的反向 ACK 时间。

**讲解 / 作用：** 它是每帧开销，不是整条消息总开销，所以乘 n(S)。

**我的意见：**


<a id="s170"></a>

#### S170

> It excludes the data airtime already represented by the first two terms.

**中文意思：** t_0 不含前两项已经计入的数据传输时间。

**讲解 / 作用：** 否则发送同一数据的时间会重复累加。

**我的意见：**


<a id="s171"></a>

#### S171

> Hop-specific framing, asymmetric links, or variable reply controls require separate parameters.

**中文意思：** 不同跳分帧、非对称链路或可变回复控制需要单独参数。

**讲解 / 作用：** 当前公式不自动覆盖这些拓展；不要在理解时偷偷引入额外决策。

**我的意见：**


<a id="s172"></a>

#### S172

> The payload goodput is $S/h_{ij}$, which differs from the link rate because the delay includes both hops and protocol overheads.

**中文意思：** 有效载荷吞吐为 S/h_ij，因包含两跳与开销而不同于链路速率。

**讲解 / 作用：** R 是单链路模型速率；goodput 是最终有效载荷除以完整消息时间。

**我的意见：**


<a id="s173"></a>

#### S173

> The transmitting and receiving devices consume

**中文意思：** 发送设备和接收设备的能量由下两式给出。

**讲解 / 作用：** E15 的两行针对不同参与设备；AP 能量不在当前预算内。

**我的意见：**


<a id="e15"></a>

#### E15 · 对应原稿式 17–18 · 发送与接收能量

$$
e_{\mathrm{tx},i}=\left(p_i/\eta_i+P_{\mathrm{tx,c},i}\right)\frac{S_{\mathrm{air}}(S)}{R_i(p_i)}+n(S)\chi_{\mathrm{tx},i}+e_{\mathrm{tail},i}
$$

$$
e_{\mathrm{rx},j}=P_{\mathrm{rx},j}\frac{S_{\mathrm{air}}(S)}{R_j(p_{\mathrm{AP}})}+n(S)\chi_{\mathrm{rx},j}+e_{\mathrm{wake},j}
$$

**符号与单位：** 省略左侧参数：发送为 (S,p_i)，接收为 (S)。η 为效率；电路 P 为 W；χ 为 J/frame；tail/wake 为 J/message。

**为什么这样写：** 功率乘空口秒数，加每帧处理和每消息状态费用。ACK 能量在 χ 中计一次。AP 自身耗电不在此预算内。

**用途 / 条件 / 示例：** 各设备分别累计自己的发送与接收。低 p 可能使发送时间变长，电路项增大，因此不能假设降低 p 总能省电。

**我的意见：**


<a id="s174"></a>

#### S174

> respectively, in joules.

**中文意思：** 两式分别以焦耳计。

**讲解 / 作用：** respectively 对应发送与接收的顺序；这是公式后的单位说明片段。

**我的意见：**


<a id="s175"></a>

#### S175

> Here $0<\eta_i\leq1$ is the source power-amplifier efficiency, $P_{\mathrm{tx,c},i}$ the incremental transmit-circuit power, and $P_{\mathrm{rx},j}$ the incremental receive-circuit power.

**中文意思：** η 是 0 到 1 的功放效率；P_tx,c 是增量发送电路功率；P_rx 是增量接收电路功率。

**讲解 / 作用：** 射频输出 p 需要耗电 p/η，再加电路功率；η 越低，同样 p 的输入耗电越大。

**我的意见：**


<a id="s176"></a>

#### S176

> The per-frame energies $\chi_{\mathrm{tx},i}$ and $\chi_{\mathrm{rx},j}$ include host and network-interface processing and the participant's fixed ACK-related energy.

**中文意思：** 每帧 χ_tx、χ_rx 包括主机/网卡处理及参与设备固定 ACK 相关能量。

**讲解 / 作用：** 这些项按帧数累加，不按载荷字节数直接累加。

**我的意见：**


<a id="s177"></a>

#### S177

> The per-message terms $e_{\mathrm{tail},i}$ and $e_{\mathrm{wake},j}$ represent the transmit-tail and receiver-wake energies.

**中文意思：** 每消息的 e_tail、e_wake 表示发送尾态和接收唤醒能量。

**讲解 / 作用：** 是状态相关固定开销，不是数据发送功率乘空口时间的重复项。

**我的意见：**


<a id="s178"></a>

#### S178

> The incremental radio circuit powers and the per-frame and per-message energy terms are nonnegative.

**中文意思：** 增量无线电路功率、每帧和每消息能量非负。

**讲解 / 作用：** 再次给出能量单调论证的组成条件，不允许人为用负项抵消预算。

**我的意见：**


<a id="s179"></a>

#### S179

> The model assigns one tail and wake charge to each directed message; it does not infer these charges from a physical radio-state trace.

**中文意思：** 模型为每条有向消息计一次尾态和唤醒，不声称由真实无线状态轨迹推断。

**讲解 / 作用：** 这是会计假设。真实状态可能跨多条消息持续，当前讲解不把该模型写成硬件测量。

**我的意见：**


<a id="s180"></a>

#### S180

> Reverse ACK energy is included in the fixed frame terms rather than in data-direction amplifier energy.

**中文意思：** 反向 ACK 能量包含于固定帧项，而非数据方向的功放能量。

**讲解 / 作用：** ACK 与主数据方向相反，不能不区分地都乘源设备可变功率。

**我的意见：**


<a id="s181"></a>

#### S181

> Published Wi-Fi measurements motivate the separate airtime, frame-processing, and state-transition components [cite: garcia2012wifi,xiao2014wifi].

**中文意思：** 已有 Wi-Fi 测量文献支持分开考虑空口、帧处理和状态转换的动机。

**讲解 / 作用：** 文献支持组成结构，不意味着本文设备系数已经由这些文献直接确定。

**我的意见：**


<a id="s182"></a>

#### S182

> Reducing transmit power can increase airtime and therefore does not necessarily reduce transmit energy.

**中文意思：** 降低发射功率可能延长空口时间，因此并不必然降低发送能量。

**讲解 / 作用：** 修正原英语的方向歧义，没有改变能量式。发送电路功率乘以空口时间；省下的射频功率可能被更长的持续耗能抵消。

**我的意见：**


<a id="s183"></a>

#### S183

> For the boundary after layer $c_i$, the prefill activation payload is $8V_{c_i}^{\mathrm{pre}}(P)$ bits, and the payload at decode step $t$ is $8V_{c_i}^{\mathrm{dec}}(P+t)$ bits.

**中文意思：** c_i 层后边界的 prefill 载荷为 8V^pre(P) bit，decode 第 t 步为 8V^dec(P+t) bit。

**讲解 / 作用：** V 定义用 byte，通信模型用 bit，因此必须乘 8。

**我的意见：**


<a id="s184"></a>

#### S184

> For example, a single bfloat16 (BF16) activation of hidden width $d$ occupies $16Pd$ bits in prefill and $16d$ bits in decode.

**中文意思：** 例如，隐藏宽度 d 的单个 BF16 激活，在 prefill 为 16Pd bit，在 decode 为 16d bit。

**讲解 / 作用：** 增加“例如”，明确这是特定格式和单张量结构的说明，不把所有理论模型固定为 BF16。通用载荷仍由 V_ℓ^s(q) 给出；若精度、张量数量或边界格式不同，应使用相应输入量。

**我的意见：**


<a id="s185"></a>

#### S185

> Additional boundary tensors are included if required by the specified model execution path.

**中文意思：** 若执行路径需要其他边界张量，也必须计入。

**讲解 / 作用：** 不能把 16Pd 或 16d 当成任意运行路径的全部载荷。

**我的意见：**


<a id="s186"></a>

#### S186

> To enumerate communication events, represent a directed message by $m=(a_m,b_m,s_m,q_m,S_m)$, where $a_m$ and $b_m$ are its source and destination indices, $s_m$ its phase, $q_m$ its phase-dependent sequence length, and $S_m$ its payload size in bits.

**中文意思：** 每条有向消息 m 记录源 a、目的 b、阶段 s、阶段相关序列长度 q 和载荷 S bit。

**讲解 / 作用：** 与 III 的 q 定义统一，避免把 decode 的上下文长度说成本步输入 token 数。消息不是一个未解释的常数项：后面会按这些字段调用两跳时延与各设备收发能量。

**我的意见：**


<a id="s187"></a>

#### S187

> The message multiset $\mathcal{M}(P,G)$ retains one entry for each transmitted message; its dependence on $\mathbf{c}$ is suppressed for brevity in the following definition:

**中文意思：** 消息多重集合 M(P,G) 为每次传输保留一个条目；下式为简洁省略它对分区 c 的依赖。

**讲解 / 作用：** M(P,G) 不是与分区无关：边界载荷仍由 c_i 决定。保持原消息集合公式，避免外层换分区时被误读为消息内容固定。多重集合不能去重后少计成本。

**我的意见：**


<a id="e16"></a>

#### E16 · 对应原稿式 19 · 枚举所有通信事件

$$
\mathcal{M}(P,G)=\{(i,i+1,\mathrm{pre},P,8V_{c_i}^{\mathrm{pre}}(P)):i<N\}
$$

$$
\quad\cup\{(i,i+1,\mathrm{dec},P+t,8V_{c_i}^{\mathrm{dec}}(P+t)):i<N,1\leq t<G\}
$$

$$
\quad\cup\{(N,1,\mathrm{dec},P+t,S_{\mathrm{tok}}):1\leq t<G\}
$$

**符号与单位：** 五元组为源、目的、阶段、形状长度、载荷 bit；S_tok 为反馈编号和元数据位数。

**为什么这样写：** 三行分别是 prefill 激活、decode 激活、启动下一 decode 的 token 反馈。按多重集合语义保留每一次事件。

**用途 / 条件 / 示例：** 激活共 G(N−1) 条、反馈 G−1 条。第一反馈虽然在 prefill 后发送，但按启动的 decode 阶段标记；最终无需继续计算就不再反馈。

**我的意见：**


<a id="s188"></a>

#### S188

> where $S_{\mathrm{tok}}$ is the number of bits used for the token identifier and its control metadata.

**中文意思：** S_tok 是 token 编号及控制元数据的位数。

**讲解 / 作用：** 反馈的是编号等少量信息，不是完整词表 logits 或 KV 状态。

**我的意见：**


<a id="s189"></a>

#### S189

> The feedback entry indexed by $t$ is the message needed to initiate decode step $t$; its phase label therefore refers to the receiving decode step.

**中文意思：** 第 t 条反馈用于启动第 t 个 decode 步，阶段标签按接收后要执行的 decode 归类。

**讲解 / 作用：** 第一条反馈在 prefill 产生 token 后发生，但本文仍用 decode 功率计费，这是明确的标签约定。

**我的意见：**


<a id="s190"></a>

#### S190

> For each $m\in\mathcal{M}(P,G)$, define its delay $h_m$ as

**中文意思：** 对多重集合中的每条消息，定义其时延 h_m。

**讲解 / 作用：** E17 把五元组映射到前面通用两跳公式。

**我的意见：**


<a id="e17"></a>

#### E17 · 对应原稿式 20 · 消息记录调用通用延迟式

$$
h_m(\mathbf{z})=h_{a_mb_m}(S_m,p_{a_m}^{s_m})
$$

**符号与单位：** a_m、b_m 给出方向；S_m 给出载荷；s_m 选择发送者在 z 中对应阶段功率。

**为什么这样写：** 只是把消息五元组逐项送入两跳公式，不增加新通信路径。

**用途 / 条件 / 示例：** 总时延对所有消息 h_m 求和。

**我的意见：**


<a id="s191"></a>

#### S191

> The transmit and receive message multisets of device $i$ are $\mathcal{M}_i^{\mathrm{tx}}=\{m\in\mathcal{M}:a_m=i\}$ and $\mathcal{M}_i^{\mathrm{rx}}=\{m\in\mathcal{M}:b_m=i\}$.

**中文意思：** 设备 i 的发送集合筛出源为 i 的消息，接收集合筛出目的为 i 的消息。

**讲解 / 作用：** 同一消息会进入源设备发送能量和目的设备接收能量，但端到端时延只计一次。

**我的意见：**


<a id="s192"></a>

#### S192

> For these messages, $e_{\mathrm{tx},i,m}=e_{\mathrm{tx},i}(S_m,p_i^{s_m})$ and $e_{\mathrm{rx},i,m}=e_{\mathrm{rx},i}(S_m)$ denote the corresponding energies from 17 and 18.

**中文意思：** 按消息载荷和所属阶段功率代入通用收发式，得到设备-消息能量 e_tx,i,m 与 e_rx,i,m。

**讲解 / 作用：** 接收式不含源设备可变功率，因为 AP 下行功率固定；发送式则读取自己的 p。

**我的意见：**


<a id="s193"></a>

#### S193

> Device $N$ has a decode transmit-power variable for feedback and no prefill transmit-power variable, consistent with the sender sets defined in Section III.

**中文意思：** 末设备有反馈用 decode 发射功率，没有 prefill 发射功率，与 III 发送者集合一致。

**讲解 / 作用：** 检查变量数量与消息事件是否对应，避免无发送变量或漏掉反馈能量。

**我的意见：**


<a id="section-194"></a>

### V-C 请求总时延和设备能量

时延跨设备求和，能量逐设备约束；端点和控制时间范围要明确。

<a id="s194"></a>

#### S194

> For an executed phase-length pair $(s,q)\in\mathcal{Q}(P,G)$, let $T_i^s(\mathbf{c},f_i^s;q)$ denote device $i$'s computation latency and $E_{\mathrm{comp},i}^s(\mathbf{c},f_i^s;q)$ its incremental computation and memory-access energy.

**中文意思：** 对执行形状 (s,q)，T_i^s 为设备计算时延，E_comp,i^s 为计算和访存的增量能量。

**讲解 / 作用：** comp 不是仅指算术开关项，它汇总该组计算模型中的多项能量；无线另算。

**我的意见：**


<a id="s195"></a>

#### S195

> Summing over its sequential operator groups gives

**中文意思：** 对该设备串行算子组求和，得到下式。

**讲解 / 作用：** E18 是从组级代价到设备级代价的汇总接口。

**我的意见：**


<a id="e18"></a>

#### E18 · 对应原稿式 21 · 组级汇总到设备级

$$
T_i^s(\mathbf{c},f_i^s;q)=\sum_{o\in\mathcal{O}_i^s(\mathbf{c},q)}t_{io}^s
$$

$$
E_{\mathrm{comp},i}^s(\mathbf{c},f_i^s;q)=\sum_{o\in\mathcal{O}_i^s(\mathbf{c},q)}e_{io}^s
$$

**符号与单位：** O 是设备负责的有序算子组，包含层内及端点；T 为 s，E 为 J。

**为什么这样写：** 各组串行执行，先算每组瓶颈及能量，再相加。comp 能量包括组模型中的访存等项，不仅算术开关。

**用途 / 条件 / 示例：** 随后再把 prefill 与每个 decode 步汇总为请求成本。

**我的意见：**


<a id="s196"></a>

#### S196

> Let $T(\mathbf{c},\mathbf{z};P,G)$ denote the total inference latency of a request.

**中文意思：** T(c,z;P,G) 是请求的总推理时延。

**讲解 / 作用：** 分区 c 和资源 z 都会影响它；P、G 给出要执行多少计算和消息。

**我的意见：**


<a id="s197a"></a>

#### S197a

> The communication sum includes prefill activation transfers, decode activation transfers, and the token-feedback messages that initiate subsequent decode steps.

**中文意思：** 通信求和包含 prefill 激活、decode 激活，以及启动后续 decode 步的 token 反馈。

**讲解 / 作用：** 不是云上传时间。每条激活或反馈都经 AP 两跳，h_m 已包含该消息的上行、下行与协议开销；总式对每条消息仅加一次。详见 E19 的三类通信展开。

**我的意见：**


<a id="s197"></a>

#### S197

> The total inference latency comprises one prefill pass, all decode passes, and their communication delays:

**中文意思：** 它包括一次 prefill、所有 decode 及对应通信时延。

**讲解 / 作用：** E19 把三类时间合成总目标，不能漏掉 AP 两跳或反馈。

**我的意见：**


<a id="e19"></a>

#### E19 · 对应原稿式 22 · 端到端推理时延

$$
T=\sum_{i=1}^{N}T_i^{\mathrm{pre}}(\mathbf{c},f_i^{\mathrm{pre}};P)
$$

$$
\quad+\sum_{t=1}^{G-1}\sum_{i=1}^{N}T_i^{\mathrm{dec}}(\mathbf{c},f_i^{\mathrm{dec}};P+t)+\sum_{m\in\mathcal{M}(P,G)}h_m(\mathbf{z})
$$

**符号与单位：** T 左侧完整参数为 (c,z;P,G)；三项单位 s；decode 空求和在 G=1 时为零。

**为什么这样写：** 先一个 prefill 的全部设备，再 G−1 次 decode 的全部设备，再所有消息。无跨设备、计算通信重叠，因此可直接累加。

**用途 / 条件 / 示例：** 选资源时用 G_hat；历史评分或实际长度评价时用 G。起终点为开始 prefill 到末设备最后 token 就绪，不自动包含控制时间与用户交付。

**通信项不是一个未知常数。** 将消息集合按三类拆开，它等价于：
$$
\begin{aligned}
&\sum_{m\in\mathcal M(P,G)}h_m(\mathbf z)\\
={}&\sum_{i=1}^{N-1}
 h_{i,i+1}\!\left(8V_{c_i}^{\mathrm{pre}}(P),p_i^{\mathrm{pre}}\right)\\
&+\sum_{t=1}^{G-1}\sum_{i=1}^{N-1}
 h_{i,i+1}\!\left(8V_{c_i}^{\mathrm{dec}}(P+t),p_i^{\mathrm{dec}}\right)\\
&+\sum_{t=1}^{G-1}h_{N,1}\!\left(S_{\mathrm{tok}},p_N^{\mathrm{dec}}\right).
\end{aligned}
$$

第一项是 prefill 的相邻设备激活，第二项是所有 decode 的相邻设备激活，第三项是启动下一步所需的 token 反馈。每个 $h$ 已含“设备→AP + AP→目标设备 + 协议时间”，不能再额外加一遍下行。

**讲解计数例：** $N=3,G=4$ 时，有 $4(3-1)=8$ 条激活消息和 $4-1=3$ 条反馈，共 11 条有向消息，每条含两跳数据传输。协议 ACK 已按 E14/E15 的固定项计入，不能作为又一条数据消息重复计数。此处是对原消息集合的教学展开，没有修改线上时延式。

**我的意见：**


<a id="s198"></a>

#### S198

> where computation and communication times are added because execution is sequential and no cross-device overlap is modeled.

**中文意思：** 由于串行且不考虑跨设备重叠，计算和通信时间直接相加。

**讲解 / 作用：** 若将来改为流水线，这个总和形式不能不加修改地使用。

**我的意见：**


<a id="s199"></a>

#### S199

> The corresponding incremental request energy on device $i$ is

**中文意思：** 设备 i 对应的请求增量能量如下。

**讲解 / 作用：** E20 是设备本地预算左侧，不是所有设备能量的总和。

**我的意见：**


<a id="e20"></a>

#### E20 · 对应原稿式 23 · 设备请求级核算能量

$$
E_i^{\mathrm{acct}}=E_{\mathrm{ctrl},i}+E_{\mathrm{comp},i}^{\mathrm{pre}}(\mathbf{c},f_i^{\mathrm{pre}};P)
$$

$$
\quad+\sum_{t=1}^{G-1}E_{\mathrm{comp},i}^{\mathrm{dec}}(\mathbf{c},f_i^{\mathrm{dec}};P+t)
$$

$$
\quad+\sum_{m\in\mathcal{M}_i^{\mathrm{tx}}}e_{\mathrm{tx},i,m}+\sum_{m\in\mathcal{M}_i^{\mathrm{rx}}}e_{\mathrm{rx},i,m}
$$

**符号与单位：** 左侧完整参数 (c,z;P,G)；消息集合完整参数 (P,G)，其中对 c 的依赖在集合符号中省略。E_ctrl,i 是统一控制能量预留；prefill、decode、发送、接收为该设备的模型能量项，单位均为 J。

**为什么这样写：** 时延跨设备汇总，能量却分别检查各设备。接收端也耗能，但 AP 能量及基础系统等排除项不在这里。

**用途 / 条件 / 示例：** 准入代入 G_cap，与 E_bar,i 比较；请求评价代入真实 G，但控制项仍采用同一预留。这是本文核算口径，不是对真实控制消耗或整机电量的直接测量。不能跨设备用总富余抵消某一台超支。

**我的意见：**


<a id="s200"></a>

#### S200

> This quantity is evaluated at $G={G_{\mathrm{cap}}}$ for admission and at the realized $G$ for request-level evaluation.

**中文意思：** 准入时以 G_cap 核算，事后请求评价以真实 G 核算。

**讲解 / 作用：** 同一个函数两种用途：安全可行性看上限，实际长度成本看停止时刻。

**我的意见：**


<a id="s201"></a>

#### S201

> The latency interval begins with prefill on device 1 and ends when the final output token is ready on device $N$.

**中文意思：** 时延从设备 1 开始 prefill，到设备 N 最后输出 token 就绪为止。

**讲解 / 作用：** 这是 T 的精确服务端点，不是从用户按发送到屏幕完整显示的全过程。

**我的意见：**


<a id="s202"></a>

#### S202

> Delivery to a user-facing client lies outside this interval.

**中文意思：** 向用户客户端交付不在该区间内。

**讲解 / 作用：** 不能把 T 与包含网络回传和显示的用户感知响应时间无条件等同。

**我的意见：**


<a id="s203"></a>

#### S203

> Prediction and optimization times are reported separately and enter response-time totals only when their execution location and timing are explicitly specified.

**中文意思：** 预测与优化用时单列，只有明确执行位置和时序后才加入响应时间总量。

**讲解 / 作用：** 能量模型含控制项，并不自动意味着 T 已含控制时间；两种会计边界需分别读。

**我的意见：**


<a id="s204"></a>

#### S204

> NOTATION TABLE

**中文意思：** 核心符号表。

**讲解 / 作用：** 此条是图表定位项，不是英文句子；讲解版附快速符号对照，方便返回定义。原表的 N/L、c、四类长度、f/p、F/D、W/S/V、预算与总成本均已逐句讲到。

| 符号 | 对应原稿核心符号表的含义 |
| --- | --- |
| N / L | 设备数量 / 解码层块数量，给定整数。 |
| c / 花体 C | 整数层切点向量 / 所有合法分区候选集合。 |
| P / G / G_hat / G_cap | 输入 / 真实输出 / 预测输出 / 强制生成上限，单位 token。 |
| f_i^s / p_i^s | 设备阶段 GPU 核心频率 Hz / 射频输出功率 W；仅发送者有 p。 |
| F_ℓ^s / D_ℓ^s | 计算操作数 FLOP / 与声明传输边界一致的访存量 byte。 |
| W_ℓ / S_ℓ(q) / V_ℓ^s(q) | 权重 / 保留推理状态 / 边界激活大小，单位 byte。 |
| E_bar,i / M_bar,i | 设备请求级核算能量预算 J / 服务内存额度 byte。 |
| T / E_i^acct / M_i | 请求总时延 s / 设备核算能量 J / 设备准入用保守内存需求 byte。 |

**我的意见：**


<a id="section-205"></a>

## VI 优化问题表述

先准入，再定义主有限策略和辅助连续参考，最后历史评分选分区。

<a id="s205"></a>

#### S205

> The objective is to minimize inference latency under each device's memory and incremental-energy budgets.

**中文意思：** 目标是在每台设备内存及增量能量预算下最小化推理时延。

**讲解 / 作用：** 约束是逐设备预算，不能把一台设备富余能量直接借给另一台；也不是能量-时延加权目标。

**我的意见：**


<a id="s206"></a>

#### S206

> The deployment decision selects one partition for multiple requests; the request-level decision selects phase-specific frequencies and transmit powers from arrival-time information.

**中文意思：** 部署为多个请求选一个分区，请求级则用到达信息选两阶段频率和发射功率。

**讲解 / 作用：** 分区跨请求保持不变，资源向量依据当前请求的到达信息选择。评价一个分区时，必须考虑该分区对应的资源选择行为，而不能只比较层数；本句定义决策关系，不是在介绍求解算法。

**我的意见：**


<a id="s207"></a>

#### S207

> We first define cap-based admission, then formulate the deployment partition problem, and finally present the expanded request-level frequency and Wi-Fi power problem.

**中文意思：** 先定义 cap 准入条件，再给出部署分区问题，最后给出展开的请求级频率与 Wi-Fi 功率问题。

**讲解 / 作用：** 按部署后服务请求的顺序安排两个决策章节，但分区评价仍依赖将要执行的请求资源规则，不变成独立的层数均分。

**我的意见：**


<a id="s207a"></a>

#### S207a

> Let $\mathcal A(\mathbf c,P,\widehat{G})$ denote the deterministic arrival-time resource rule for an admitted request, which minimizes predicted inference latency over the cap-feasible legal resource set.

**中文意思：** A(c,P,G_hat) 表示确定性的到达信息资源规则：在满足 cap 预算的合法配置中，最小化预测推理时延。

**讲解 / 作用：** 先定义这个资源映射的输入、输出和目标，避免前面的分区问题用到一个尚未介绍的符号。精确问题和同分选择规则在 VI-C 给出；它不是另一种提前知道真实 G 的策略。

**我的意见：**


<a id="s207b"></a>

#### S207b

> Its optimization problem and tie rule are specified in Section VI-C.

**中文意思：** 其优化问题及平局选择规则在 VI-C 规定。

**讲解 / 作用：** 这是指向后续详细定义的导航句，不引入具体求解算法。这里介绍映射，后面将目标和约束全部展开。

**我的意见：**


<a id="s207c"></a>

#### S207c

> The deployment partition is selected before serving requests, but each candidate partition is evaluated using the same resource rule that will subsequently be executed.

**中文意思：** 正式服务前先选分区，但每个候选分区都通过同一个之后会执行的资源规则来评价。

**讲解 / 作用：** 区分两个顺序：服务时先部署 c*，请求到达后才选 f/p；校准时先给定候选 c，为历史请求按预测长度选 f/p，再用真实长度评分，最后选 c*。所以“分区在前”不等于校准时完全不考虑 f/p。

**我的意见：**


<a id="s208"></a>

#### S208

> Changing a partition reallocates the FLOP counts, weight storage, and inference-state memory among devices.

**中文意思：** 改变分区会在设备之间重新分配计算量、权重和状态存储。

**讲解 / 作用：** 即使总层数不变，每台设备预算占用也会变，因此好分区不是只看层数均衡。

**我的意见：**


<a id="s209"></a>

#### S209

> It also changes the energy remaining for communication after computation and control, and may change the activation payload at a boundary.

**中文意思：** 分区还会改变计算和控制之后可供通信使用的剩余能量，并可能改变边界激活载荷。

**讲解 / 作用：** 变化的是预算的使用分配，不是给定预算 E_bar 本身；若所有边界宽度相同，仍可能通过计算能量改变可选发射功率。

**我的意见：**


<a id="s210"></a>

#### S210

> Even if all boundary activations have the same width, computation and transmission share each device's request-level energy budget, and prefill and decode share that same budget.

**中文意思：** 即使各边界激活同宽，计算与发送、prefill 与 decode 仍共用设备的请求级预算。

**讲解 / 作用：** 因此通信载荷相同不意味着分区与资源无关；共享能量约束就是耦合渠道。

**我的意见：**


<a id="s211"></a>

#### S211

> The resource vector returned by $\mathcal A$ therefore depends on the partition.

**中文意思：** A 返回的资源向量因此依赖分区。

**讲解 / 作用：** 分区决定各设备 F/D、状态和权重需求，进而改变可行频率/功率及最优选择。改用已经介绍的 A 名称，避免在开头依赖后置公式编号。

**我的意见：**


<a id="s212"></a>

#### S212

> A deployment partition must be evaluated through the causal policy it induces.

**中文意思：** 部署分区应通过其诱导的因果在线策略来评价。

**讲解 / 作用：** 不能用事后已知真实 G 的理想配置来给在线分区打分。

**我的意见：**


<a id="s213"></a>

#### S213

> This dependence is compatible with the fixed-partition device-wise decomposition established in Section VII.

**中文意思：** 这种依赖与后文固定分区下按设备分解并不矛盾。

**讲解 / 作用：** 外层分区与内层策略耦合，不等于固定分区后所有设备的资源变量还必须互相耦合。

**我的意见：**


<a id="section-214"></a>

### VI-A 请求准入与可行性

合法等级不等于预算可行；可行集合不能依赖预测长度。

<a id="s214"></a>

#### S214

> Let $P_{\min}$ and $P_{\max}$ be integers with $1\leq P_{\min}\leq P_{\max}$ denoting the minimum and maximum permitted prompt lengths, and let $\mathcal{P}=[P_{\min},P_{\max}]\cap\mathbb{Z}$ be the admissible prompt-length set, where $\mathbb{Z}$ denotes the integers.

**中文意思：** P_min 和 P_max 是满足 1≤P_min≤P_max 的整数输入长度界；花体 P 是该区间内的整数集合。

**讲解 / 作用：** 补出计数域和界的顺序，不填实际长度数值。输入域合法是准入必要条件，不代表能源或内存可行。

**我的意见：**


<a id="s214a"></a>

#### S214a

> The prompt range is chosen so that every pair in $\mathcal{Q}(P,{G_{\mathrm{cap}}})$ is supported by the specified model and runtime for all $P\in\mathcal{P}$.

**中文意思：** 选择输入范围时，要保证每个允许 P 对应的 Q(P,G_cap) 中所有阶段—长度组合均被指定模型和运行时支持。

**讲解 / 作用：** 最晚的前向长度是 P+G_cap−1；最后输出 token 不再被前向消费。若存在最大支持长度 q_max，应满足 P_max+G_cap−1≤q_max；这里只解释条件，不新增一个未经确认的 q_max 数值，也不假定内存足够就代表模型支持。

**我的意见：**


<a id="s215"></a>

#### S215

> Let $\mathcal{Z}_{\mathrm{legal}}$ denote the finite set of valid frequency and transmit-power vectors for the specified devices.

**中文意思：** Z_legal 是各设备允许的有限频率/功率配置向量集合。

**讲解 / 作用：** legal 表示等级合法，不表示一定满足请求能量或内存预算。

**我的意见：**


<a id="s216"></a>

#### S216

> Resource levels are identified as supported hardware values or simulation assumptions.

**中文意思：** 资源等级须区分硬件支持值和模拟假设。

**讲解 / 作用：** 再次明确配置来源，不把假设等级说成已经能在实物上执行。

**我的意见：**


<a id="s216a"></a>

#### S216a

> The legal operating levels are specified independently for each device, without cross-device restrictions on their selection.

**中文意思：** 每台设备的合法工作等级独立规定，不对不同设备的等级选择施加跨设备限制。

**讲解 / 作用：** 这是明确的模型设定，使合法向量由各设备合法配置组合得到。设备内部的两阶段预算仍耦合；AP 功率固定、串行通信也保持不变。并非声称所有现实硬件或协议天然满足这种独立性。

**我的意见：**


<a id="s217"></a>

#### S217

> For partition $\mathbf{c}$ and prompt length $P$, the feasible resource set is

**中文意思：** 给定分区 c 与输入长度 P，可行资源集合如下。

**讲解 / 作用：** E21 在合法等级中再筛选满足设备预算的点。

**我的意见：**


<a id="e21"></a>

#### E21 · 对应原稿式 24 · 合法等级中的可行子集

$$
\mathcal{Z}(\mathbf{c},P)=\{\mathbf{z}\in\mathcal{Z}_{\mathrm{legal}}:E_i^{\mathrm{acct}}(\mathbf{c},\mathbf{z};P,G_{\mathrm{cap}})\leq\bar{E}_i,
$$

$$
\qquad M_i(\mathbf{c};P,G_{\mathrm{cap}})\leq\bar{M}_i,\ \forall i\}
$$

**符号与单位：** Z_legal 只定义合法配置；Z(c,P) 再施加每设备能量和内存限制；∀i 表示每台都须通过。

**为什么这样写：** 计算与通信在 G_cap 检查，控制项采用与预测无关的统一预留，所以集合不依赖 G_hat，预测不会改变准入空间。内存与 z 无关；若分区不满足本文保守容量检查，仅调整频率和功率不能让它通过该检查，但这不等于证明所有其他内存管理方式也不可行。

**用途 / 条件 / 示例：** P 在允许域且该集合非空才准入；内层在集合内排序，外层要求每校准请求集合非空。

**我的意见：**


<a id="s218"></a>

#### S218

> With both constraints evaluated at the enforced output cap and the control-energy reserve independent of the prediction, the feasible set depends on $P$ and $\mathbf{c}$, but not on the output-length prediction.

**中文意思：** 两约束在强制生成上限检查，且控制预留不依赖预测，因此可行集合依赖 P 和 c，而不依赖预测输出长度。

**讲解 / 作用：** 把原来省略的控制能量条件写出来。G_hat 改变可行点的目标排名，不放宽准入预算；这个结论仅适用于本文规定的固定预留口径。

**我的意见：**


<a id="s219"></a>

#### S219

> A request is admitted if and only if $P\in\mathcal{P}$ and $\mathcal{Z}(\mathbf{c},P)\neq\varnothing$.

**中文意思：** 当且仅当 P 在允许范围内且可行资源集合非空时准入。

**讲解 / 作用：** if and only if 是充要条件；至少存在一个合法可行配置才可开始。

**我的意见：**


<a id="s220"></a>

#### S220

> Otherwise, it is rejected before model execution and the failed feasibility test is recorded.

**中文意思：** 否则执行前拒绝，并记录可行性检查失败。

**讲解 / 作用：** 拒绝不等于软件求解失败；后者可能只是没找到或来不及找到配置。

**我的意见：**


<a id="s221"></a>

#### S221

> The runtime enforces max_new_tokens$={G_{\mathrm{cap}}}$; any continuation requires a separate admission decision.

**中文意思：** 运行时强制 max_new_tokens=G_cap；继续生成需另一次准入。

**讲解 / 作用：** 否则超出上限后，前面的能量和内存保证不再覆盖延长部分。

**我的意见：**


<a id="s222"></a>

#### S222

> The prompt domain and generation cap specify the permitted workload, while admission additionally requires a feasible resource vector.

**中文意思：** 输入域和生成上限定义服务允许负载，准入还需可行资源。

**讲解 / 作用：** 请求形式合法不代表设备一定承受得住。

**我的意见：**


<a id="s223"></a>

#### S223

> Memory feasibility uses the complete set of execution lengths defined in 10.

**中文意思：** 内存检查使用前面定义的完整执行长度集合。

**讲解 / 作用：** 不能只查最后 decode 长度而漏掉可能更大的 prefill 工作区。

**我的意见：**


<a id="section-245"></a>

### VI-B 部署分区优化

先因果选资源、再用历史真实长度评分；最优性范围是指定策略的校准目标。

<a id="s245"></a>

#### S245

> Let $K\geq1$ denote the number of historical calibration requests, and let $\mathcal{D}_{\mathrm{cal}}=\{1,\ldots,K\}$ be their index set.

**中文意思：** K≥1 为历史校准请求数，D_cal={1,…,K} 为其编号集合。

**讲解 / 作用：** K 是数量，D_cal 是索引。均值分母不能为零；这里 r 将表示请求编号。

**我的意见：**


<a id="s246"></a>

#### S246

> For request $r\in\mathcal{D}_{\mathrm{cal}}$, let $P_r\in\mathcal{P}$, $\widehat{G}_r$, and $G_r$ denote its prompt length, prediction from the fixed predictor, and realized output length, respectively.

**中文意思：** 校准请求 r 的 P_r、G_hat,r、G_r 分别为输入长度、固定预测器预测和真实输出长度。

**讲解 / 作用：** 三者不可混用。校准历史可以事后知道 G_r，但内层仍只看前两者。

**我的意见：**


<a id="s247"></a>

#### S247

> For each candidate partition that admits every calibration request, let $\mathbf{z}_r(\mathbf{c})$ be the resource vector selected by the same causal policy:

**中文意思：** 对能准入全部校准请求的候选分区，以 z_r(c) 表示同一个因果策略选定的资源。

**讲解 / 作用：** 先筛出有定义的可行候选，再调用策略；不对拒绝请求凭空指定时延。

**我的意见：**


<a id="e25"></a>

#### E25 · 对应原稿式 25 · 历史请求的因果资源选择

$$
\mathbf{z}_r(\mathbf{c})=\mathcal{A}(\mathbf{c},P_r,\widehat{G}_r)
$$

**符号与单位：** r 为校准请求编号；z_r(c) 是该分区下该请求的资源；预测器固定。A 的输入/输出已在 S207a 介绍，完整 f/p 问题见 E29。

**为什么这样写：** 不同分区会诱导不同资源，所以资源要写成 c 的函数；选择不读取 G_r。

**用途 / 条件 / 示例：** 这是评分前的步骤。必须先选 z_r，再在 E26 使用真实长度。

**我的意见：**


<a id="s248"></a>

#### S248

> The calibration objective $J_{\mathrm{cal}}(\mathbf{c})$ is the mean inference latency obtained with these selected resources at the historical realized output lengths:

**中文意思：** J_cal(c) 是采用这些选定资源、按历史真实输出长度评价得到的平均推理时延。

**讲解 / 作用：** 明确被平均的是请求时延，而不是资源向量或输出长度；每个 G_r 只进入评分，不进入该请求的资源选择。

**我的意见：**


<a id="e26"></a>

#### E26 · 对应原稿式 26 · 历史真实长度下评分

$$
J_{\mathrm{cal}}(\mathbf{c})=\frac{1}{K}\sum_{r\in\mathcal{D}_{\mathrm{cal}}}T(\mathbf{c},\mathbf{z}_r(\mathbf{c});P_r,G_r)
$$

**符号与单位：** K 为正历史请求数；D_cal 为索引集合；J 的单位 s；G_r 是事后真实长度。

**为什么这样写：** 平均的是已经因果选定资源在真实历史长度下的时延，不是内层预测目标的平均，也不是 oracle 资源的平均。

**用途 / 条件 / 示例：** 部署比较候选分区。讲解例：两个请求在其选定配置下为 2、4 秒，评分为 3 秒；不是论文结果。

**我的意见：**


<a id="s249"></a>

#### S249

> We next express the deployment problem directly in terms of operator costs, Wi-Fi airtimes, and memory allocations.

**中文意思：** 下面直接用算子成本、Wi‑Fi 空口时间和内存分配，写出展开后的部署问题。

**讲解 / 作用：** 按你的要求展开原来的 J_cal、T、E、h、R、n 和 S_air；只保留已定义的结构索引集合和模型/运行时输入。新写法与原问题等价，不把历史真实长度放进在线资源选择。

**我的意见：**


<a id="s249a"></a>

#### S249a

> For calibration request $r$, let $f_{i,r}^s$ and $p_{i,r}^s$ denote the components of $\mathbf z_r(\mathbf c)$ selected by (29) from $(P_r,\Ghat_r)$.

**中文意思：** 校准请求 r 的 f_i,r^s、p_i,r^s 是由 P_r、G_hat,r 通过同一请求策略得到的 z_r(c) 分量。

**讲解 / 作用：** 增加 r 下标仅为了在总式中区分各历史请求的配置，不增加离线自由决策变量。分区候选改变时，策略重新选择各请求资源；控制仍不知道 G_r。

**我的意见：**


<a id="s249b"></a>

#### S249b

> These resources are functions of the candidate partition, not free offline variables optimized with knowledge of the realized lengths.

**中文意思：** 这些资源随候选分区而定，不是利用已知真实长度自由优化的离线变量。

**讲解 / 作用：** 这是展开总式必须保留的关键约束语义。若直接同时最小化 c 与任意 f_i,r/p_i,r 的真实历史时延，会把问题改成预知长度的离线优化，不再评价现有因果策略。

**我的意见：**


<a id="s249c"></a>

#### S249c

> The shape arguments of the operator coefficients are shown explicitly, and each message set is evaluated at the output length indicated in its arguments.

**中文意思：** 把算子系数的形状参数显式写出；消息集合按其参数中标注的输出长度生成。

**讲解 / 作用：** 算子统一用 o 代替层内 (ℓ,r) 索引；这些是同一套系数，不是新增能量项。目标的 Q/M 用真实 G_r，约束的 Q/M 用 G_cap，所以执行次数、上下文和消息数可不同。

**我的意见：**


<a id="s249d"></a>

#### S249d

> Substituting the computation, framing, and link-rate expressions yields the expanded objective and constraints below.

**中文意思：** 代入计算、成帧和链路速率表达后，得到下面展开的目标与约束。

**讲解 / 作用：** 合法等级集合只列出允许的离散配置，不隐藏能量或内存约束；约束已逐项展开。F/D/W/S/U 和边界载荷仍是模型/运行时输入，不能为追求“再展开”而凭空套成同一种模型公式。

**我的意见：**


<a id="e27"></a>

#### E27 · 对应原稿式 27a–27g · 展开后的总体部署优化问题

**先看变量：** 外层只选切点 $\mathbf c$。这里的 $f_{i,r}^s,p_{i,r}^s$ 已由 E25 的 $\mathbf z_r(\mathbf c)=\mathcal A(\mathbf c,P_r,\widehat G_r)$ 确定，不是在看见 $G_r$ 后自由选择。下列七部分对应同一个问题；为方便 Markdown 阅读，将线上连续长公式分成七个展示块。

**(27a) 目标：历史真实长度下的平均总时延。**

$$
\begin{aligned}
\min_{\mathbf c}\quad
&\frac1K\sum_{r\in\mathcal D_{\mathrm{cal}}}\Biggl[
\sum_{(s,q)\in\mathcal Q(P_r,G_r)}\sum_{i=1}^{N}
\sum_{o\in\mathcal O_i^s(\mathbf c,q)}
\left(\max\!\left\{\frac{F_{io}^s(q)}{\rho_{io}^s(q)f_{i,r}^s},\frac{D_{io}^s(q)}{\beta_{io}^s(q)}\right\}+\tau_{io}^s(q)\right)\\
&+\sum_{m\in\mathcal M(P_r,G_r)}\Biggl(
\frac{S_m+\lceil S_m/L_{\mathrm{pay}}\rceil H+C(S_m)}{\min\{R_{\max},\xi B\log_2(1+\gamma_{a_m}p_{a_m,r}^{s_m})\}}\\
&\qquad+\frac{S_m+\lceil S_m/L_{\mathrm{pay}}\rceil H+C(S_m)}{\min\{R_{\max},\xi B\log_2(1+\gamma_{b_m}p_{mathrm{AP}})\}}
+\lceil S_m/L_{\mathrm{pay}}\rceil t_0\Biggr)\Biggr].
\end{aligned}
$$

第一大项逐阶段、逐设备、逐算子组求计算时延。每组中，计算时间 $F/(\rho f)$ 与访存时间 $D/\beta$ 取最大，再加固定执行开销 $\tau$。第二大项逐消息加上行、下行与协议时间；帧数、空口比特和链路速率均已代入，不再以 $h_m$、$R_i$ 或 $S_{\mathrm{air}}$ 隐藏成本。外层平均的单位是秒。

**(27b) 连续非空层分区。**

$$
0=c_0<c_1<\cdots<c_N=L,\qquad c_i\in\mathbb Z,\quad i=0,\ldots,N.
$$

切点是整数，端点固定，中间严格递增。每台给定设备至少得到一层，设备顺序不变。

**(27c) 每个历史请求、每台设备的内存约束。**

$$
\begin{aligned}
&\sum_{\ell\in\mathcal L_i(\mathbf c)}W_\ell
 +W_{\mathrm{extra},i}+M_{\mathrm{rt},i}\\
&+\max_{(s,q)\in\mathcal Q(P_r,G_{\mathrm{cap}})}
 \left\{\sum_{\ell\in\mathcal L_i(\mathbf c)}S_\ell(q)
 +U_i(\mathbf c,s,q)\right\}
 \leq\bar M_i,\\
&\hspace{2em}\forall i\in\mathcal N,\ r\in\mathcal D_{\mathrm{cal}}.
\end{aligned}
$$

左侧是分到该设备的层权重、端点/副本权重、运行时预留，再加 cap 范围内最大“状态容量 + 同时活跃临时缓冲”需求。右侧是该服务允许使用的容量。所有项均为字节。原保守容量界保留，不改成实测峰值，也不只检查预测长度。

**(27d) 每个历史请求、每台设备的能量约束。**

$$
\begin{aligned}
&E_{\mathrm{ctrl},i}
+\sum_{(s,q)\in\mathcal Q(P_r,G_{\mathrm{cap}})}
 \sum_{o\in\mathcal O_i^s(\mathbf c,q)}\Biggl[
 \kappa_{io}^s(q)F_{io}^s(q)(v_{0,i}^s+v_{1,i}^sf_{i,r}^s)^2\\
&\qquad+\epsilon_{io}^s(q)D_{io}^s(q)
 +P_{\mathrm{act},io}^s(q)
 \left(\max\!\left\{\frac{F_{io}^s(q)}{\rho_{io}^s(q)f_{i,r}^s},\frac{D_{io}^s(q)}{\beta_{io}^s(q)}\right\}+\tau_{io}^s(q)\right)
 +e_{\mathrm{launch},io}^s(q)\Biggr]\\
&+\sum_{m\in\mathcal M_i^{\mathrm{tx}}(P_r,G_{\mathrm{cap}})}\Biggl[
 \left(\frac{p_{i,r}^{s_m}}{\eta_i}+P_{\mathrm{tx,c},i}\right)
 \frac{S_m+\lceil S_m/L_{\mathrm{pay}}\rceil H+C(S_m)}{\min\{R_{\max},\xi B\log_2(1+\gamma_{i}p_{i,r}^{s_m})\}}\\
&\qquad+\lceil S_m/L_{\mathrm{pay}}\rceil\chi_{\mathrm{tx},i}
 +e_{\mathrm{tail},i}\Biggr]\\
&+\sum_{m\in\mathcal M_i^{\mathrm{rx}}(P_r,G_{\mathrm{cap}})}\Biggl[
 P_{\mathrm{rx},i}\frac{S_m+\lceil S_m/L_{\mathrm{pay}}\rceil H+C(S_m)}{\min\{R_{\max},\xi B\log_2(1+\gamma_{i}p_{mathrm{AP}})\}}\\
&\qquad+\lceil S_m/L_{\mathrm{pay}}\rceil\chi_{\mathrm{rx},i}
 +e_{\mathrm{wake},i}\Biggr]\leq\bar E_i,\\
&\hspace{2em}\forall i\in\mathcal N,\ r\in\mathcal D_{\mathrm{cal}}.
\end{aligned}
$$

从上到下依次是：统一控制能量预留；所有算子组的开关、访存、剩余活动和启动能量；本设备发送消息的功放/电路、逐帧和尾部能量；本设备接收消息的电路、逐帧和唤醒能量。所有项为焦耳。发送项使用设备可调 Wi‑Fi 功率，接收项的下行速率使用 AP 固定功率。AP 本身耗能不计入任何设备的额度。

**(27e) 合法离散资源等级。**

$$
\mathbf z_r(\mathbf c)\in\mathcal Z_{\mathrm{legal}},
 \qquad\forall r\in\mathcal D_{\mathrm{cal}}.
$$

这只是给定设备允许的离散频率/功率组合，预算约束已在前两块明确列出。“合法”等级不等于已满足这个请求的预算。没有具体等级表就不能把这个集合列成确定数值，否则会编造参数。

**(27f) 频率范围。**

$$
f_{i,\min}\leq f_{i,r}^s\leq f_{i,\max},
\quad\forall i\in\mathcal N,\ s\in\{\mathrm{pre},\mathrm{dec}\},\
r\in\mathcal D_{\mathrm{cal}}.
$$

每台设备、每个阶段、每个请求都受同一给定的频率界限制。合法离散等级已落在这些界内，所以在此显式列出是说明运行范围，不增加新的可行性要求。

**(27g) 发送者 Wi‑Fi 功率范围。**

$$
p_{i,\min}\leq p_{i,r}^s\leq p_{i,\max},
\quad\forall s\in\{\mathrm{pre},\mathrm{dec}\},\
i\in\mathcal I_s,\ r\in\mathcal D_{\mathrm{cal}}.
$$

只有实际需要发送的设备有对应功率变量。prefill 的发送者为 $1,\ldots,N-1$；decode 还包含末设备的 token 反馈，因此可有 $p_N^{\mathrm{dec}}$，没有 $p_N^{\mathrm{pre}}$。

**为什么与旧式等价？** 旧式要求 $\mathcal Z(\mathbf c,P_r)\neq\varnothing$。按其定义，这就是存在合法资源满足 cap 内存与能量约束。策略 $\mathcal A$ 在这个非空有限集合里按预测时延选一个满足约束的资源，因此显式约束它实际返回的 $\mathbf z_r(\mathbf c)$ 与旧式的存在条件等价。反过来，返回向量满足这些条件就说明集合非空。目标则只是把 E26 中的 $T$ 及其各成本定义代入。没有新增可调 AP 功率，没有删掉控制能量，没有改成 oracle 优化。

**展开到哪里为止？** $\mathcal Q$、$\mathcal O$、$\mathcal M$ 是前文已列明的执行/消息索引，决定对哪些对象求和；$\mathcal L_i$ 是已定义的层分配集合。它们不是未解释的成本函数。$F,D,W,S,U,V$ 是模型与运行时提供的需求量，投影和全注意力部分已有具体公式，循环层、有效访存和工作区还依赖实现。不能把所有层统一套为某个固定目标模型，否则会改变理论含义。系数显式写出 $q$，只是恢复原文已声明省略的形状依赖。

**我的意见：**


<a id="s250"></a>

#### S250

> A solution is denoted by $\mathbf{c}^\star$ and is held fixed for subsequent requests.

**中文意思：** 得到的分区解记为 c*，后续请求保持使用它。

**讲解 / 作用：** 请求级资源仍变化；星号不表示对所有未来流量必然最优。

**我的意见：**


<a id="s251"></a>

#### S251

> The first constraint assigns consecutive nonempty layer blocks in the specified device order.

**中文意思：** 第一条约束按照固定设备顺序分配连续非空层块。

**讲解 / 作用：** 它是可部署分区结构，不包含设备挑选或重排序。

**我的意见：**


<a id="s252"></a>

#### S252

> The energy, memory, and legal-level constraints require every calibration request to receive a valid resource vector satisfying the cap-based budgets.

**中文意思：** 能量、内存和合法等级约束要求每个校准请求都获得满足上限预算的合法资源配置。

**讲解 / 作用：** 总式已不再把预算条件藏在 Z(c,P)≠空中，因此不再说“第二条约束”涵盖所有准入要求。约束的意义不变：每个请求可用自己的资源配置，但所有请求共用同一分区。

**我的意见：**


<a id="s253"></a>

#### S253

> Thus, candidate partitions are scored on the same calibration workload, and the objective is defined only for feasible candidates.

**中文意思：** 因此候选都在同一校准负载上评分，目标仅对可行候选定义。

**讲解 / 作用：** 避免只服务容易请求的分区获得较小均值；也避免对不存在的策略输出计算 T。

**我的意见：**


<a id="s254"></a>

#### S254

> Equal-score partitions are ordered lexicographically by their boundary vectors.

**中文意思：** 评分相同的分区按边界向量字典序排序。

**讲解 / 作用：** 先比第一个切点，再比后续切点，保证确定性选择。

**我的意见：**


<a id="s255"></a>

#### S255

> If no candidate is feasible, the deployment problem is infeasible for the specified workload and parameters.

**中文意思：** 如果无候选可行，该负载与参数下的部署问题不可行。

**讲解 / 作用：** 不能把不可行包装成算法失败或偷偷删请求使问题变得可行。

**我的意见：**


<a id="s256"></a>

#### S256

> The historical length $G_r$ is used only to score the vector already selected from $(P_r,\widehat{G}_r)$.

**中文意思：** 历史真实长度只用于给已按 P_r、预测长度选好的配置打分。

**讲解 / 作用：** 重复强调信息边界，因为这里最容易把离线已知信息泄漏给在线策略。

**我的意见：**


<a id="s257"></a>

#### S257

> Allowing the inner optimizer to observe $G_r$ would define a different, oracle-based deployment objective.

**中文意思：** 若允许内层看到真实 G_r，就会形成另一种预知真实长度的 oracle 部署目标。

**讲解 / 作用：** oracle 是不可在线获得的参考信息，不能给这种问题的最优结果冠以当前因果策略保证。

**我的意见：**


<a id="s258"></a>

#### S258

> The stated formulation selects a partition for the specified causal policy rather than jointly optimizing over all possible policies.

**中文意思：** 当前公式为指定因果策略选择分区，不是在全部可能策略空间中联合寻优。

**讲解 / 作用：** “联合”指分区通过资源策略评价、计算与无线共用预算，不意味着证明所有可设计策略中最优。

**我的意见：**


<a id="s259"></a>

#### S259

> Calibration feasibility does not guarantee feasibility for every future prompt; each new request still undergoes the admission test in 24.

**中文意思：** 校准可行不保证所有未来输入可行，新请求仍须逐次准入检查。

**讲解 / 作用：** 历史优化目标与未来服务保证不同：固定的是分区，不是自动准入所有未来请求。

**我的意见：**


<a id="s259a"></a>

#### S259a

> Operation counts, memory traffic, storage sizes, and buffer requirements remain model-and-runtime inputs because no single architecture-independent expression represents all of them.

**中文意思：** 运算量、访存量、存储量和缓冲需求仍作为模型与运行时输入，因为它们不存在一条适用于所有架构的统一表达式。

**讲解 / 作用：** “展到最开”的合理终点是：目标/预算式展开到这些需求量与设备系数。投影和全注意力计数已在 IV 给出；循环状态、有效访存与内核工作区取决于实现。继续统一展开成某个固定模型表达，反而会违背通用理论的定位。

**我的意见：**


<a id="section-224"></a>

### VI-C 请求级频率与 Wi-Fi 功率分配

预测影响目标，硬上限保护模型预算；理解命题前提及连续参考地位。

<a id="s224"></a>

#### S224

> After deployment, the partition is fixed at $\mathbf c^\star$, and each admitted request is assigned its own resource vector.

**中文意思：** 部署后分区固定为 c*，每个准入请求获得各自的资源配置。

**讲解 / 作用：** 这一节的部署分区来自前一节；不是在每个请求到达时再选择一次切点。不同请求可选不同 f/p，层分区保持不变。

**我的意见：**


<a id="s224a"></a>

#### S224a

> For the request-level problem, $\mathbf c$, $P$, and $\widehat{G}$ are given inputs; only the phase-specific GPU frequencies and device Wi-Fi transmit powers are optimized.

**中文意思：** 请求问题的 c、P、预测 G 已给定，只优化阶段 GPU 频率和设备 Wi-Fi 发射功率。

**讲解 / 作用：** 明确哪些是输入、哪些才是决策变量。c 在正式服务中为已部署 c*，G_cap 是既定上限，AP 功率不加入优化。

**我的意见：**


<a id="s224b"></a>

#### S224b

> During calibration, the same problem is evaluated at each candidate partition to define $\mathcal A(\mathbf c,P,\widehat{G})$.

**中文意思：** 校准时，同一个请求问题在各候选分区下评价，以定义 A(c,P,G_hat)。

**讲解 / 作用：** 确保离线评分与将来运行的请求规则一致；不是为了先写分区就把历史真实 G 当作请求优化输入。

**我的意见：**


<a id="s224c"></a>

#### S224c

> The resource vector defined in Section III contains both phases, with ordered components

**中文意思：** III 中的资源向量包括两个阶段，其有序分量如下。

**讲解 / 作用：** 下面显式列出 prefill/decode 的频率和 Wi-Fi 功率，回答 z 是否包含两阶段资源。

**我的意见：**


<a id="e28"></a>

#### E28 · 线上未编号 · z 明确包含两个阶段的资源

$$
\begin{aligned}
\mathbf z=(&f_1^{\mathrm{pre}},\ldots,f_N^{\mathrm{pre}},
f_1^{\mathrm{dec}},\ldots,f_N^{\mathrm{dec}},\\
&p_1^{\mathrm{pre}},\ldots,p_{N-1}^{\mathrm{pre}},
p_1^{\mathrm{dec}},\ldots,p_N^{\mathrm{dec}}).
\end{aligned}
$$

**四组分量：** prefill 的 N 个频率、decode 的 N 个频率、prefill 的 N−1 个设备 Wi-Fi 功率、decode 的 N 个设备 Wi-Fi 功率。排列与 III 的字典序规则一致，没有新增决策量，也没有改变平局规则。

**为什么最后设备的两阶段功率不同？** prefill 末设备生成首 token，不向“下一台设备”发激活，所以没有 $p_N^{\mathrm{pre}}$。若还需生成下一个 token，它要反馈给设备 1，该消息归到启动的 decode 步，使用 $p_N^{\mathrm{dec}}$。这不是 AP 功率；$p_{\mathrm{AP}}$ 仍为预设基础设施参数。

**阶段配置不相互独立：** 两阶段 f/p 在到达时一起选择，并共享本设备同一个请求能量预算，各阶段内部使用固定设置。预测为 1 时也不删除 cap 约束和既定平局规则中的 decode 分量。

**我的意见：**


<a id="s224d"></a>

#### S224d

> For each phase $s$, frequencies are selected for all $i\in\mathcal N$, while transmit powers are selected only for $i\in\mathcal I_s$.

**中文意思：** 每个阶段都为所有设备选频率，但只为发送者集合 I_s 中的设备选功率。

**讲解 / 作用：** 频率有 2N 个分量，功率有 (N−1)+N=2N−1 个分量，因此 z 共 4N−1 个分量。没有 p_N^pre，保留用于反馈的 p_N^dec。

**我的意见：**


<a id="s224e"></a>

#### S224e

> Substituting the latency and energy expressions gives the following request-level frequency and power optimization problem:

**中文意思：** 代入时延与能量表达后，得到下面的请求级频率/功率优化问题。

**讲解 / 作用：** 这个式子才直接以 f_i^s 和 p_i^s 为优化变量。它是原有限网格 A 定义的等价展开，不是新的优化策略。

**我的意见：**


<a id="e29"></a>

#### E29 · 对应原稿式 28a–28f · 完整展开的请求级 f/p 优化

给定一个合法分区 $\mathbf c$、输入长度 $P$、预测输出长度 $\widehat G$，只优化 $\{f_i^s\}$ 和 $\{p_i^s\}$；索引域见 S224d。正式服务中 $\mathbf c=\mathbf c^\star$，历史校准中则代入待评价的候选分区。不是用历史真实 $G_r$ 来选本请求资源。

**(28a) 最小化预测总时延。**

$$
\begin{aligned}
\min_{\{f_i^s\},\{p_i^s\}}\quad
&\sum_{(s,q)\in\mathcal Q(P,\widehat G)}\sum_{i=1}^{N}
\sum_{o\in\mathcal O_i^s(\mathbf c,q)}
\left(\max\!\left\{\frac{F_{io}^s(q)}{\rho_{io}^s(q)f_i^s},\frac{D_{io}^s(q)}{\beta_{io}^s(q)}\right\}+\tau_{io}^s(q)\right)\\
&+\sum_{m\in\mathcal M(P,\widehat G)}\Biggl(
\frac{S_m+\lceil S_m/L_{\mathrm{pay}}\rceil H+C(S_m)}{\min\{R_{\max},\xi B\log_2(1+\gamma_{a_m}p_{a_m}^{s_m})\}}\\
&\qquad+\frac{S_m+\lceil S_m/L_{\mathrm{pay}}\rceil H+C(S_m)}{\min\{R_{\max},\xi B\log_2(1+\gamma_{b_m}p_{mathrm{AP}})\}}
+\lceil S_m/L_{\mathrm{pay}}\rceil t_0\Biggr).
\end{aligned}
$$

第一项逐 prefill/decode 形状、设备和算子组加计算时延；第二项逐消息加设备→AP 上行、AP→目的设备下行及协议时间。$f_i^s$ 出现在计算吞吐中，$p_{a_m}^{s_m}$ 出现在设备上行速率中。目标中两类执行集合均代入预测长度。AP 下行虽不优化，仍必须计入总时间。

**(28b) 内存准入约束。**

$$
\begin{aligned}
&\sum_{\ell\in\mathcal L_i(\mathbf c)}W_\ell
 +W_{\mathrm{extra},i}+M_{\mathrm{rt},i}\\
&+\max_{(s,q)\in\mathcal Q(P,G_{\mathrm{cap}})}
 \left\{\sum_{\ell\in\mathcal L_i(\mathbf c)}S_\ell(q)
 +U_i(\mathbf c,s,q)\right\}
 \leq\bar M_i,\\
&\hspace{2em}\forall i\in\mathcal N.
\end{aligned}
$$

权重、端点权重、运行时预留以及 cap 范围内状态与临时缓冲的保守需求，不得超过服务容量。这里不含 f/p：固定分区和 P 后，调频、调 Wi-Fi 功率不能解决容量不足。

**(28c) 单设备、两阶段共用的能量约束。**

$$
\begin{aligned}
&E_{\mathrm{ctrl},i}
+\sum_{(s,q)\in\mathcal Q(P,G_{\mathrm{cap}})}
 \sum_{o\in\mathcal O_i^s(\mathbf c,q)}\Biggl[
 \kappa_{io}^s(q)F_{io}^s(q)(v_{0,i}^s+v_{1,i}^sf_i^s)^2\\
&\qquad+\epsilon_{io}^s(q)D_{io}^s(q)
 +P_{\mathrm{act},io}^s(q)
 \left(\max\!\left\{\frac{F_{io}^s(q)}{\rho_{io}^s(q)f_i^s},\frac{D_{io}^s(q)}{\beta_{io}^s(q)}\right\}+\tau_{io}^s(q)\right)
 +e_{\mathrm{launch},io}^s(q)\Biggr]\\
&+\sum_{m\in\mathcal M_i^{\mathrm{tx}}(P,G_{\mathrm{cap}})}\Biggl[
 \left(\frac{p_i^{s_m}}{\eta_i}+P_{\mathrm{tx,c},i}\right)
 \frac{S_m+\lceil S_m/L_{\mathrm{pay}}\rceil H+C(S_m)}{\min\{R_{\max},\xi B\log_2(1+\gamma_{i}p_i^{s_m})\}}\\
&\qquad+\lceil S_m/L_{\mathrm{pay}}\rceil\chi_{\mathrm{tx},i}
 +e_{\mathrm{tail},i}\Biggr]\\
&+\sum_{m\in\mathcal M_i^{\mathrm{rx}}(P,G_{\mathrm{cap}})}\Biggl[
 P_{\mathrm{rx},i}\frac{S_m+\lceil S_m/L_{\mathrm{pay}}\rceil H+C(S_m)}{\min\{R_{\max},\xi B\log_2(1+\gamma_{i}p_{mathrm{AP}})\}}\\
&\qquad+\lceil S_m/L_{\mathrm{pay}}\rceil\chi_{\mathrm{rx},i}
 +e_{\mathrm{wake},i}\Biggr]\leq\bar E_i,\\
&\hspace{2em}\forall i\in\mathcal N.
\end{aligned}
$$

一条设备预算中累计：统一控制预留；两阶段算子组的开关、访存、剩余活动和启动能量；本设备发送消息的功放/电路、逐帧和尾部能量；本设备接收消息的电路、逐帧和唤醒能量。全部按 cap 计算。不能分别给 prefill、decode 各用一次完整 E_bar，也不能把设备 i 的电量与别的设备合并为总预算。

**(28d) 合法离散配置。**

$$
\mathbf z\in\mathcal Z_{\mathrm{legal}}.
$$

频率和功率必须落在给定合法等级中，不是任意连续实数。它不隐藏预算条件，前两块已完全列出。

**(28e) 各设备、各阶段的频率界。**

$$
f_{i,\min}\leq f_i^s\leq f_{i,\max},
\quad\forall i\in\mathcal N,\ s\in\{\mathrm{pre},\mathrm{dec}\}.
$$

两阶段都必须在设备给定的工作范围内。显式列出不改变合法等级原先已在界内的规定。

**(28f) 各阶段发送者的设备 Wi-Fi 功率界。**

$$
p_{i,\min}\leq p_i^s\leq p_{i,\max},
\quad\forall s\in\{\mathrm{pre},\mathrm{dec}\},\ i\in\mathcal I_s.
$$

只约束有功率变量的发送者，没有引入 $p_N^{\mathrm{pre}}$ 或可调 AP 功率。

**与 A 简式等价的理由：** 内存、能量和合法等级条件正是原 $\mathcal Z(\mathbf c,P)$ 的定义；展开目标正是 $T(\mathbf c,\mathbf z;P,\widehat G)$。所以得到同一个最小值和同一个最优集合，之后仍用既定 cap 能量与字典序规则选定向量。只把变量和成本显式显示出来，没有更换策略、解法、设备参数或预算。

**保留的建模边界：** F/D、状态、缓冲和载荷仍是模型/运行时输入；系数形状依赖恢复为 q。收发能量仍按原两跳、ACK、逐帧、逐消息核算，保守内存界和统一控制预留均未改变。

**我的意见：**


<a id="s224f"></a>

#### S224f

> The objective counts prefill and decode computation and every two-hop message at the predicted length, whereas the constraints cover the enforced generation cap.

**中文意思：** 目标按预测长度计入两阶段计算和每条两跳消息，约束按强制生成上限覆盖允许执行范围。

**讲解 / 作用：** 两种长度的角色不交换：预测长度决定候选配置的估计时延，cap 决定准入约束。不是把两阶段分开用两个互不相关的能量预算。

**我的意见：**


<a id="s224g"></a>

#### S224g

> For fixed $\mathbf c$ and $P$, the memory inequality is a feasibility test rather than a constraint that can be relaxed by changing $f_i^s$ or $p_i^s$.

**中文意思：** c 和 P 固定后，内存不等式是可行性检查，不能靠调 f 或 p 放松它。

**讲解 / 作用：** 该内存模型由权重、状态和缓冲容量决定，不含 f/p。若需求已超预算，此分区下该请求不可准入，不能靠降低频率或无线功率把权重变小。

**我的意见：**


<a id="s225"></a>

#### S225

> The rule $\mathcal A$ returns a minimizer of this finite-grid problem:

**中文意思：** A 返回上述有限网格问题的一个最优资源向量。

**讲解 / 作用：** 前面展开了问题，这里用简式命名输出映射。后面的 cap 总能量平局规则和字典序继续决定同目标情况下的唯一选择。

**我的意见：**


<a id="e22"></a>

#### E22 · 对应原稿式 29 · 主要有限网格策略

$$
\mathcal{A}(\mathbf{c},P,\widehat{G})\in\mathrm{argmin}_{\mathbf{z}\in\mathcal{Z}(\mathbf{c},P)}T(\mathbf{c},\mathbf{z};P,\widehat{G})
$$

**符号与单位：** argmin 返回使目标最小的配置集合；A 按正文破平局规则选其中一个；min 则只返回最小值。

**为什么这样写：** 约束已藏在 Z 中，所以这并不是无约束问题。预测进入目标，硬上限进入 Z。

**用途 / 条件 / 示例：** 外层对每个 c、请求 r 调用同一个 A；不把真实 G_r 交给它。并列时先最低上限总能量，再字典序。

**现在的作用：** E29 已将 f/p 问题完整展开，本卡只是用 A 命名它的最优向量，方便分区评分引用。不是唯一展示资源优化问题的地方。

**我的意见：**


<a id="s226"></a>

#### S226

> If the feasible set is empty, the policy returns a rejection; computational failures and timeouts are recorded separately.

**中文意思：** 可行集为空返回拒绝；计算失败与超时另记。

**讲解 / 作用：** 数学不可行和求解器没完成不能混为一类。

**我的意见：**


<a id="s227"></a>

#### S227

> Among objective minimizers, it selects the one with the lowest total energy evaluated at the cap, followed by the lexicographically smallest resource vector.

**中文意思：** 时延最优点并列时，先选上限下总能量最低者，再选字典序最小向量。

**讲解 / 作用：** 这是确定性破平局规则，能量不是主要目标；字典序是按固定变量顺序逐个比较。

**我的意见：**


<a id="s228"></a>

#### S228

> Decode variables remain in the cap constraints and tie rule even when $\widehat{G}=1$.

**中文意思：** 即使预测只生成一个 token，decode 变量仍参与上限约束及破平局。

**讲解 / 作用：** 预测可能低估，所以不能删除实际可能使用的 decode 资源和预算要求。

**我的意见：**


<a id="s229"></a>

#### S229

> Section VII develops the solution method.

**中文意思：** 解法在后面的章节展开。

**讲解 / 作用：** 这里只定义策略要返回什么，不讲解范围外的算法细节。

**我的意见：**


<a id="s230"></a>

#### S230

> For a fixed partition and realized request, output-length prediction can affect modeled inference latency only through changes in the selected resources.

**中文意思：** 对固定分区和真实请求，长度预测只能通过改变所选资源来影响模型推理时延。

**讲解 / 作用：** 这是必要路径，不是收益保证。资源变化也可能得到同样时延甚至更差的真实时延；这里讨论 T，不包括另计的预测或优化时间。

**我的意见：**


<a id="s231"></a>

#### S231

> If the feasible set is unchanged and varying $\widehat{G}$ only rescales the entire resource-dependent objective by a positive factor and adds a resource-independent term, the set of minimizers is unchanged.

**中文意思：** 若可行集合不变，预测变化只让整个资源相关目标乘正系数，并加资源无关项，则最小化解集合不变。

**讲解 / 作用：** 强调“整个目标”，而非只缩放其中一个资源相关项。a(G_hat)Φ(z)+b(G_hat) 且 a>0 时排序不变；若 prefill 和 decode 各有资源相关项，而只改变其中一项权重，这个结论不能直接使用。

**我的意见：**


<a id="s232"></a>

#### S232

> Shared energy budgets across phases and context-dependent computation can make the selected vector depend on $\widehat{G}$, but the presence of a predictor alone does not imply a latency benefit.

**中文意思：** 跨阶段共享预算和上下文相关计算可能使资源依赖预测，但有预测器本身不保证时延收益。

**讲解 / 作用：** “可能”不是实证结论；收益取决于配置如何改变和真实长度下的成本。

**我的意见：**


<a id="s233"></a>

#### S233

> Section VIII specifies comparisons that evaluate this decision dependence.

**中文意思：** 后面的评价章节安排比较来检验这种决策依赖。

**讲解 / 作用：** 这是跨节指引，不是已有结果。本讲解不展开或调整实验内容。

**我的意见：**


<a id="s234"></a>

#### S234

> Proposition 1 (energy feasibility under the generation cap): Suppose that every additional decode operation and message has nonnegative modeled energy, and that the energy of an executed operation does not depend on the eventual stopping point.

**中文意思：** 命题 1 假设新增 decode 操作和消息能量非负，且已执行操作的成本不依赖最终停止位置。

**讲解 / 作用：** 需两条条件：新增项不负；相同前缀按相同成本核算，不能因较早停止而重定义先前成本。

**我的意见：**


<a id="s235"></a>

#### S235

> For fixed $(\mathbf{c},\mathbf{z},P)$, every device $i\in\mathcal{N}$, and every $1\leq G\leq{G_{\mathrm{cap}}}$,

**中文意思：** 固定 c、z、P 时，对每台参与设备 i 以及所有 1≤G≤G_cap，满足下式。

**讲解 / 作用：** 补全逐设备量词，不改变不等式。控制预留在不同停止长度下相同；额外 decode 和消息项非负，才得到逐设备单调关系。

**我的意见：**


<a id="e23"></a>

#### E23 · 对应原稿式 30 · 上限下能量覆盖较早停止

$$
E_i^{\mathrm{acct}}(\mathbf{c},\mathbf{z};P,G)\leq E_i^{\mathrm{acct}}(\mathbf{c},\mathbf{z};P,G_{\mathrm{cap}})
$$

**符号与单位：** 固定 c、z、P，且 1≤G≤G_cap。相同前缀成本一致，新增步骤和消息非负。

**为什么这样写：** 长到上限的请求包含短请求所有前缀，再加非负能量，所以不会更小。无需假设每步成本不变，也不比较不同资源向量。

**用途 / 条件 / 示例：** 上限能量通过则允许范围内任何停止长度也通过。内存另由全形状最大值覆盖。保证只针对声明核算模型，并非整机电池保证。

**我的意见：**


<a id="s236"></a>

#### S236

> Proof: The cap-length request contains the same prefill operation and the same decode and communication operations through output $G$, plus the nonnegative increments for decode steps $G,\ldots,{G_{\mathrm{cap}}}-1$.

**中文意思：** 证明：上限请求包含到第 G 个输出为止的相同前缀，并多出编号 G 至 G_cap−1 的非负步骤增量。

**讲解 / 作用：** 输出 G 对应 G−1 个 decode；下一新增 decode 的编号就是 G，索引没有差一。

**我的意见：**


<a id="s237"></a>

#### S237

> Summing these additional increments establishes the inequality.

**中文意思：** 把这些额外非负项相加即得到不等式。

**讲解 / 作用：** 这是前缀包含的直接证明，不要求每步能量相同。

**我的意见：**


<a id="s238"></a>

#### S238

> Together with the conservative memory test over $\mathcal{Q}(P,{G_{\mathrm{cap}}})$, Proposition 1 ensures that an admitted configuration satisfies the modeled budgets for every permitted stopping length, regardless of prediction error.

**中文意思：** 结合覆盖所有执行形状的保守内存检查，命题 1 保证准入配置在所有允许停止长度下满足模型预算，与预测误差无关。

**讲解 / 作用：** 把 peak-memory 改为 conservative memory，与 IV-C 的口径一致。保证依赖于状态容量和临时缓冲界、非负能量项以及固定控制预留，不是现实测量或模型失配下的无条件保证。

**我的意见：**


<a id="s239"></a>

#### S239

> The guarantee applies to the incremental-energy components and fixed accounting boundary specified in Section III.

**中文意思：** 保证适用于 III 指定的增量能量组件与固定核算边界。

**讲解 / 作用：** 不将理论模型保证扩大到真实整机、电池寿命或未建模行为。

**我的意见：**


<a id="s240"></a>

#### S240

> For complementary continuous analysis, the same latency objective and cap-based constraints can be considered with controls varying continuously within their operating bounds.

**中文意思：** 作为辅助连续分析，可让控制在上下界内连续变化，仍使用同样目标与上限约束。

**讲解 / 作用：** 真实有限等级和连续区间不同；连续参考不是直接可部署配置。

**我的意见：**


<a id="s241"></a>

#### S241

> When this reference is feasible, let $\mathcal{A}_{\mathrm{cont}}(\mathbf{c},P,\widehat{G})$ denote a resource vector solving

**中文意思：** 连续参考可行时，以 A_cont 表示下式的资源解。

**讲解 / 作用：** E24 显式列出时延目标、能量/内存约束及控制区间。

**我的意见：**


<a id="e24"></a>

#### E24 · 对应原稿式 31a–31e · 辅助连续参考

$$
\min_{\mathbf{z}}\ T(\mathbf{c},\mathbf{z};P,\widehat{G})
$$

$$
E_i^{\mathrm{acct}}(\mathbf{c},\mathbf{z};P,G_{\mathrm{cap}})\leq\bar{E}_i,\quad M_i(\mathbf{c};P,G_{\mathrm{cap}})\leq\bar{M}_i
$$

$$
f_{i,\min}\leq f_i^s\leq f_{i,\max},\quad p_{i,\min}\leq p_i^s\leq p_{i,\max}\ (i\in\mathcal{I}_s)
$$

**符号与单位：** c 固定；频率对所有设备和两阶段，功率仅对对应发送者。控制允许在界内连续变化。

**为什么这样写：** 展示时把原五条分式压为三行，约束范围未改变。与有限策略的主要区别是配置域，不是用真实 G 替换预测。

**用途 / 条件 / 示例：** 只为辅助连续性质分析；部署评分仍调用有限 A。能否成为下界取决于同口径成本和可行集包含，不在此处无条件宣称。

**与 E29 的关系：** 仅移除有限合法等级成员条件，保留同一时延、cap 内存与能量、频率/功率范围。这个连续参考不替代实际离散 A。

**我的意见：**


<a id="s242"></a>

#### S242

> The frequency and power bounds are those defined in Section III.

**中文意思：** 频率和功率界沿用 III 的定义。

**讲解 / 作用：** 不是为连续参考另造更宽的硬件范围。

**我的意见：**


<a id="s243"></a>

#### S243

> This reference treats the controls as continuous within those bounds; the deployment formulation above uses the finite-grid policy $\mathcal{A}$, not $\mathcal{A}_{\mathrm{cont}}$.

**中文意思：** 连续参考允许区间中任意值；下面部署问题使用离散 A，而不是 A_cont。

**讲解 / 作用：** 外层分区必须按主策略评分，不能拿连续理想资源代替。

**我的意见：**


<a id="s243a"></a>

#### S243a

> The continuous reference removes only the finite legal-level membership condition from (28); it is not the executable control rule.

**中文意思：** 连续参考只去掉请求问题中的有限合法等级集合条件，不是实际执行的控制规则。

**讲解 / 作用：** 时延函数、cap 内存与能量条件、f/p 范围均保持；这不是改用连续输出替换原离散策略。尚未进入求解方法章节。

**我的意见：**


<a id="s244"></a>

#### S244

> Its continuous properties are analyzed separately from executable control in Section VII.

**中文意思：** 连续性质在解法章节与可执行控制分开分析。

**讲解 / 作用：** 本范围只定义参考问题，不借讲解扩展后文证明。

**我的意见：**


<a id="self-check"></a>

## 读完后的自检与定位

- 能否分清 N 数量与花体 N 集合，以及 L 层数与花体 L_i 的设备层集合？
- 能否说出 c、z 各在何时选择，以及设备顺序为什么不是优化变量？
- 能否解释 prefill 产生第一个 token，因此只有 G-1 个 decode 和反馈？
- 能否区分 D 的传输量、S 的状态容量与 V 的通信张量大小？
- 能否解释为什么先算每组 max，再跨组求和，而非全层只取一次 max？
- 能否解释 M_rt 为什么不能在预算和需求两边重复扣除？
- 能否解释消息经过两跳、ACK 时间和能量各在哪里计？
- 能否说清楚命题 1 为什么要求固定资源、非负新增项和一致前缀成本？
- 能否指出 A 的目标使用 G_hat、Z 的约束使用 G_cap、J_cal 的评分使用真实 G？
- 能否解释外层只为指定 A 选分区，不证明所有在线策略或未来负载下最优？

### 版本与讲解边界

本版英文与公式对应本轮线上 III–VI 修订。英文中的自定义 TeX 命令、引用和附录定位已转成可读形式，未改变其含义。E27 和 E29 的换行分块只为 Markdown 阅读，完整成本项与线上式一致；额外教学展开注明为等价解释，数值例不是论文结果。

这是修改后的阅读稿，不表示论文、参数假设、长度标签或策略实验已经最终验收。虚拟测试床不能写成真实多设备测量。本轮没有提出或执行新的实验协议调整；如果后续修改需要改变参数或评价方案，应另行交实验对话处理。

<a id="annotation-responses"></a>

## 32 条批注回应索引

保留你的原问题（仅去除加粗标记），不把疑问当成已经证实的结论。点击编号可回到当前原句或公式卡。

### [S7](#s7)

你的批注：这里的mi不是模型权重吗？

回应与处理：请分清三类量：M_bar,i 是允许用多少；W_ℓ 是某层权重需要多少；M_i(c;P,G_cap) 是该设备权重、状态、临时缓冲和运行时预留的总需求。准入比较总需求 M_i≤容量预算 M_bar,i。

### [S9](#s9)

你的批注：（ 给每个请求都要建立预算合适吗 ）

回应与处理：“每请求”指预算适用的任务单位，不是每次都重新估计一个预算。此模型用同一个设备额度比较不同请求的执行配置；为何合理与它不涵盖什么，见下一句。

### [S10](#s10)

你的批注：（我们不涉及设备选择吧，执行顺序是固定的吧、加速器的协同调度是什么意思）

回应与处理：按你的意见去掉 host–accelerator co-scheduling：本文不研究 CPU/GPU 工作分配，没必要引入这一不参与优化的术语。保留设备集合与顺序固定的必要设定。

### [S11](#s11)

你的批注：这感觉是一句废话

回应与处理：已从线上删除显然的单设备通信说明，保留 N≥2 的系统设定。

### [S18](#s18)

你的批注：加速器是什么意思？大家都这么写吗？

回应与处理：GPU 是用于执行模型计算的硬件。加速器是更宽泛的称呼，这里直接写 GPU 更容易读；GPU-accessible 包括被当前 GPU 使用的内存，不强行认定所有设备都采用同一种独立显存体系。各设备不保存全部模型权重。

### [S24](#s24)

你的批注：模板中的角色和特殊token会影响输入长度，这句话是什么意思？

回应与处理：输入不是只把用户汉字直接交给模型：模板还可能插入用户/助手角色标记、分隔或结束标记，以及等待助手继续生成的起始标记。这些也是模型处理的序列内容，故要计入 P。本文不指定某种模板实际插入了多少个 token。

### [S25](#s25)

你的批注：我对G_cap还有点不知道是什么意思，有什么必要搞这个G_cap

回应与处理：G_cap 是允许最多生成多少，不是每次必须生成多少；G 是这次实际生成多少。例如上限 100、正常生成 40 时 G=40，不会补齐到 100。示例仅为讲解。 只知道预测长度无法保证不低估。若预测 40、实际生成 80，按 40 检查可能漏掉后半程成本；按强制上限 100 检查则覆盖允许范围中的 80。保证仍依赖本文能量/内存模型及运行时真的强制停止，不是对现实参数误差的保证。 线上在原定义后新增 S25a/S25b。

### [E4](#e4)

你的批注：这里的进入时延目标是什么意思？

回应与处理：已在 E4 明确：用 T(c,z;P,G_hat) 比较候选配置的估计秒数，不是把 token 数直接加到时延。补充仅供讲解的两配置排序例；预测公式未改。

### [S34](#s34)

你的批注：文中的G_cap、G_hat、G分别用来干什么，有什么用，我想我们可以再讨论一下

回应与处理：已增加三种长度的用途对照表，配合线上 S37/S37a/S38/S38a。裁剪预测不等于预测准确，公式未改。

### [S36](#s36)

你的批注：这句话不知道是什么意思

回应与处理：原句“每个会话首次用户轮次取一个请求”是数据取样限定，不是通用理论建模的必要条件。这里改为请求的输入/输出定义；实验如何取样保持原样，没有改实验章节或数据协议。

### [S37](#s37)

你的批注：这里也是，文中的G_cap、G_hat、G分别用来干什么，有什么用，我想我们可以再讨论一下

回应与处理：“进入时延目标”就是把 T(c,z;P,G) 中的未知 G 换成预测 G_hat，再比较不同 z 的估计秒数。它不会把预测值直接当作预算或实际生成长度。G_cap 只确定约束检查的最远执行范围。

### [S38](#s38)

你的批注：这里我再补充一下逻辑，利用大量已知真实的历史的G，去确定分区。利用预测G去优化方程里面针对每请求去解优化方程优化

回应与处理：接受你补充的主线：大量历史真实 G_r 参与选择分区；当前请求用预测长度选择 f/p。为忠实评价将来会运行的策略，每个历史请求也先按 P_r、G_hat,r 选资源，再用真实 G_r 打分，不让在线策略预知真实长度。

### [S41](#s41)

你的批注：这里要强调是设备wifi的发射功率，不要直接说是发射功率

回应与处理：按你的意见明确 Wi‑Fi。p_i^s 是向 AP 发无线信号的射频输出功率，不是 GPU 功率、整机功率或 AP 功率；发送电路与功放效率的耗电另在无线能量式中计入。

### [S45](#s45)

你的批注：这代表我们没有考虑访存开销吗？不对吧，我们后面的屋顶线模型里面，prefill和decoding阶段，每步延迟都是用的计算开销和访存开销的最大值，不对吗？你再斟酌一下用词

回应与处理：你指出得对：Roofline 用 max(F/(ρf),D/β) 包含访存瓶颈，能量式还含 εD。固定内存时钟仅说明它不是决策变量，绝不等于 D=0 或访存免费。只调整 GPU 核心 f，β 对固定形状按既定近似处理。

### [S49](#s49)

你的批注：没看懂，为什么又有个固定发射功率？

回应与处理：同一条消息有两次不同发送：设备 i→AP 使用待选 p_i^s；AP→设备 j 使用预设 p_AP。两者属于不同发送端，所以可调设备功率与固定 AP 功率不矛盾。AP 耗能不计入设备预算，但它的下行速度与接收设备耗能仍必须计入。

### [S54](#s54)

你的批注：这个有必要说吗？去掉这句话吧，没意义

回应与处理：已从线上删除排除项清单；批大小一、串行无重叠及请求独立评价的必要假设保留。

### [S55](#s55)

你的批注：模型的增量能量是什么意思？

回应与处理：避免只说难懂的“模型增量能量”。它将模型计算、访存、控制和 Wi‑Fi 活动归到这个请求，并不是设备整个时间段的所有耗电。acct 是 accounted（已核算组成）的标签。

### [S63](#s63)

你的批注：需要你再给我讲一下

回应与处理：图中的设备传输通过 AP 中转，不是设备 i 直接发到 i+1。源设备 Wi‑Fi 功率可调，路由器/AP 的转发功率固定；接收者和目的链路不同，下行时延仍会不同。请与 E14 两个分式一起读。

### [S71](#s71)

你的批注：这里有点看不懂

回应与处理：权重是模型训练后给定的参数，不随这次生成逐 token 重训练；状态是这次推理产生并留到下一步使用的数据，如 KV 缓存或循环状态。W/S 都是存多少字节，D 则是执行期间累计搬多少字节，不能混为一谈。

### [S77](#s77)

你的批注：算子组集合是什么意思？这个概念我有些不懂

回应与处理：“算子”可理解为一个计算步骤，如矩阵乘法、归一化、注意力更新；“组”用于匹配运行时的执行单元，未规定所有模型都用一样分组。每组有自己的 F、D、时间和能量，再按顺序累加。 这些只是分组例子，不声称当前虚拟测试床已测量这些内核。O_i^s(c,q) 列出设备 i 在该分区、阶段、形状下要执行哪些组，包含层内运算和 embedding/head 等端点；它不是设备集合或层集合。 线上新增 S77a/S77b，原集合定义保留。

### [S78](#s78)

你的批注：这里的t之前是不是出现过，是不是存在一个字母表示了两种意思的情况

回应与处理：确实复用了字母形状，但两个带完整记号的数学对象不同：无下标 t 是第几步，单位无；t_io^s 是该设备该组的秒数，单位 s；t_0 是每帧协议时间，单位 s。为不破坏既有公式及解法符号，本轮明确区分而不只为换字母进行全局重命名。 线上新增 S78a，未全局重命名。

### [S85](#s85)

你的批注：我们在建模阶段是固定的模型吗？我们实验阶段确实固定模型，但是在理论建模阶段我们是吗？可以再讨论，斟酌斟酌

回应与处理：理论不是先规定必须用 Qwen 才成立，而是以这些需求量为参数。一次部署/求解需给定它们，才能评价分区；更换模型可改变输入量，但不把选择模型本身加入本文优化变量。

### [S86](#s86)

你的批注：这是我们的目标或者是要求吧，写在正文里怪怪的

回应与处理：按你的意见去掉正文中的清单式要求，改为说明这些量从何处进入模型。来源透明和假设说明仍保留在参数说明处，不把缺乏依据的量写成测量结果。

### [S87](#s87)

你的批注：理论建模阶段不用上来就写固定模型

回应与处理：不在通用理论段落先绑定 Qwen。全注意力层需要 KV 状态，循环层的状态结构由具体实现给出；两类层共用 F/D/S 接口，但不共用全部成本公式。具体目标的说明放在原有附录引用语境中。

### [S101](#s101)

你的批注：这里有点看不懂，选用的操作计数必须匹配确定有效吞吐时所采用的注意力内核

回应与处理：F 是需要多少操作，ρf 是按同一口径每秒做多少操作。若 F 采用三角有效运算数，却直接混用按另一计数口径得到的吞吐，就不能保证 F/(ρf) 表示正确时间。也可以使用等效 FLOP 口径，但分子与吞吐必须成对转换，不是只改其中一项。

### [S106](#s106)

你的批注：正文此处明确需要实现信息，不假造新的循环层成本表达式你这句话是什么意思

回应与处理：已重写讲解，删除编辑者工作原则式的“不假造”措辞。解释循环层通过具体状态/张量提供 F/D/S，不能套用全注意力公式；线上附录指引原句无需改动。

### [E8](#e8)

你的批注：这个公式我看不懂，这代表什么？

回应与处理：已逐元素解释 Q(P,G)，增加 P=5、G=3 的三个执行事件对照；说明求和用于成本累计，最大值用于容量检查。公式未改。

### [S128](#s128)

你的批注：这里描述的不够细致，我看不懂

回应与处理：ρ、β 是给定形状下的有效计算/访存能力；同一 GPU 上，大矩阵、小矩阵、prefill 与 decode 的利用率可能不同，因此要说明参数对应的执行对象。不同对象也可以恰好使用相同参数，但不能无依据地宣称一个参数普遍精确。

### [S129](#s129)

你的批注：同一传输边界是什么意思

回应与处理：“同一传输边界”就是同一条数据搬运路径。教学例：若该接口要搬 100 MB，有效带宽为 50 GB/s，按十进制单位 D/β=2 ms；不能用另一缓存或 Wi‑Fi 的带宽来除。例子不是设备测量或参数设定。

### [S153](#s153)

你的批注：无线传输我们模拟了一个什么过程？是不是分为上传和下载两部分时间建模，还是什么？

回应与处理：它只是某一跳的速度，不是设备 i 到设备 j 的全程有效吞吐。设备间消息需两跳，上行由源设备功率决定，下行由 AP 功率与目的设备链路决定，完整时间在 E14 相加。

### [E19](#e19)

你的批注：这里的通信项是什么？

回应与处理：线上新增通信三类组成的解释；Markdown 另把消息求和等价拆成 prefill 激活、decode 激活和 token 反馈。每条消息已包括两跳，不能重复计下行。原时延式未改。

### [S259](#s259)

你的批注：还有建议，最终的优化方程以及限制条件你最后需要把每一项都展开，展到最开，不能像现在一样是简写形式

回应与处理：已在 Overleaf 完整展开分区总式 27a–27g，并在 E27 逐项解释理由和等价性。展开到模型需求量与设备系数，保留明确索引集合和合法等级输入；不编造统一的循环层、有效访存或工作区公式。


## 本次补充问题的回应

### “分区应先给出，才能优化 f/p”

线上 VI 已重排为准入、分区部署、请求资源。III 中原有连续分区及部署后固定的定义保留。分区章节提前不意味着分区完全独立于资源策略；S207a–S207c 先交代 A 的角色，VI-C 再给出其完整定义。旧顺序可以按数学依赖成立，但没有突出服务执行顺序，本版改进的是这层行文。

### “为什么 f/p 的优化方程没有展开？”

v4 只展开了分区式，未完整展开请求问题，这一缺漏已补齐。现在 VI-C 的式 (28a–28f) 直接以 f_i^s、p_i^s 为变量，展开时延、内存、能量、合法等级及工作范围；见 E29。A 简式只负责为最优资源向量命名。

### “z 是否同时包含两阶段 f/p？”

是。见 E28 的四组分量；缺少 p_N^pre 是发送者定义决定的，不是忘记 prefill。末设备 decode 的 token 反馈功率仍在 z 中。两阶段配置共同选定，仍共享同一个设备请求级能量预算。

<!--
% CONTRACT [LLM]: goal=clarity strength=minimal
% EXPRESSION [S7-S8a]: total service budget and requirement clarified
% Changed: budget components listed; runtime reserve located in eq:memory
% Protected: bar M_i; eq:memory; all original display formulas
% Meaning-Check: PRESERVED
% Risk-Flags: none
% LOGIC [S28-S28d, E3]: distinguish decode-step index, processed context, and completed sequence
% Changed: explicit token indexing and last-step relationship added; no original formula changed
% Protected: eq:context; q_t=P+t; G-1 decode steps; original memory/energy/optimization expressions
% Meaning-Check: PRESERVED
% Risk-Flags: none
% EXPRESSION [S51-S51a, S62]: fixed request resource vector clarified
% Changed: no intra-request re-optimization made explicit; phase-specific values retained
% Protected: phase-specific f/p; both-phase resource vector; all existing constraints
% Meaning-Check: PRESERVED
% Risk-Flags: none
-->
