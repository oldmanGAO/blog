---
title: IoT-J 论文逐句讲解版（本轮优化阅读版 v3）
subtitle: ''
date: '2026-10-09T08:26:27+08:00'
lastmod: '2026-10-09T08:26:27+08:00'
draft: false
authors: []
description: 论文草稿
tags:
- 论文
categories:
- 论文
series: []
hiddenFromHomePage: false
hiddenFromSearch: false
featuredImage: ''
featuredImagePreview: ''
toc:
  enable: true
math:
  enable: true
lightgallery: true
license: 本文采用 <a rel="license" href="https://creativecommons.org/licenses/by-nc/4.0/"
  target="_blank">CC BY-NC 4.0</a> 许可协议，转载请注明出处。
---

# IoT-J 论文逐句讲解版（本轮优化阅读版 v3）

III 系统模型 - VI 总体优化问题

英文对照 · 中文释义 · 数学拆解

依据：2026-10-08 核对的 [Overleaf 线上版本](https://www.overleaf.com/project/6ac73b6b2b7ae56343f5e414)。仅讲解 System Model 到 Problem Formulation，不讲解解法、实验或附录原文。

覆盖：265 个阅读单元（沿用 S1–S259，新增 S48a、S122a、S128a、S142a、S214a、S216a；含图注、公式引导片段和符号表定位），27 个展示公式环境。沿用旧版的逐句编号及公式说明；本版已同步此次线上语言与模型说明修订，旧 PDF、旧 Markdown 和 v2 均保留，未覆盖。英文 TeX 数学和引用指令仅转换为可读排版，讲解编号 S/E 不替代论文原编号。

本次同步说明：只修改线上 III–VI。24 处句子得到修订，新增 6 句必要说明，调整内存小节标题、符号表措辞及系统图。27 个展示公式的数学表达、引用键和标签均保持不变；部分定义和适用假设得到明确，具体影响见下节。其他章节和实验内容未修改。以下讲解只解释系统与问题定义，不提前展开解法。

重要边界：Qwen3.5-4B 仍为目标模型。本文模型讨论不等于真实多设备测量，未编造实验结果。所有数值演示均明确标为讲解例。

阅读方式：先读每小节概览，再依次看“英文原句 → 中文意思 → 讲解/作用”。公式卡另说明符号、单位、项的含义、假设和后续用途。可直接用 S87 或 E19 在对话中提问。公式采用 `$...$` / `$$...$$` 的 LaTeX 数学语法。

## 本轮修改的理由与影响

这份文件是供你逐句提出意见的本轮阅读稿，不表示论文、参数验证或实验已经最终验收。

1. **内存容量口径。** 保留原式 11，把 M_i 明确为准入使用的保守需求；U_i 仍是临时缓冲的同时分配峰值。状态容量和临时缓冲峰值不同步时，二者相加可能高估容量，不能宣称等于实测峰值。需要容量界覆盖完整前向执行，模型保证才成立。
2. **固定系数近似。** 系数可以随算子和执行形状变化；但对给定形状，在频率优化范围内将计算、带宽和能量系数视为固定。频率作用仍由原有的 ρf、电压模型和 t(f) 表达。未改变公式，明确了模型分析的条件，未声称这种近似已获硬件验证。
3. **统一控制能量预留。** 可执行策略和连续参考均计入同一 E_ctrl,i；假定它覆盖允许输入域、合法配置及所有允许输出长度下的控制开销。相比使用较小的配置特定消耗，统一预留可能收紧可行空间。尚未指定新数值，也不宣称现实控制耗能已经验证满足这一界。
4. **平局选择约定。** 明确 z 的分量排列，补全字典序规则。它不改变变量或 argmin 的目标；但不同平局选择可能影响按真实长度计算的历史评分，因此此约定是模型策略的一部分，而非没有影响的排版改动。
5. **输入域与合法配置。** 输入长度界为正整数，所有 cap 内执行形状必须被指定模型与运行时支持；合法等级按设备独立选择，不引入跨设备等级限制。没有填写新的上下文长度、频率或功率参数，也没有修改实验协议。
6. **表达与图示。** 澄清 q 是阶段相关序列长度参数，降低发射功率未必降低能量，以及预测改变资源不保证收益；解释消息集合省略了分区依赖。系统图改画一般的相邻设备传输及有条件的 token 反馈，不再将 Device 2 和 Device N 当作必然不同的设备。

证据边界：定义性结论由现有公式及明确约定支持；生成上限保证依赖非负增量、固定控制预留和容量界。没有加入新的实证效果、文献或已完成事项。这里不运行实验，也不把应由实验对话核验的参数假设当成已验收结果。

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
  - [VI-B 请求资源分配](#section-224)
  - [VI-C 部署分区优化](#section-245)
- [读完后的自检与定位](#self-check)

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

<a id="s2"></a>

#### S2

> These definitions provide the basis for the computation, memory, and communication models and the joint partitioning and resource-allocation problem.

**中文意思：** 这些定义是计算、内存、通信模型以及分区与资源分配联合优化问题的基础。

**讲解 / 作用：** 本句说明章节依赖：先定义系统和到达信息，再计算代价，最后建立联合优化问题。联合性在于分区改变各设备需求，从而影响其可选资源；这里没有预先规定求解方法，也没有宣称效果已经验证。

<a id="section-3"></a>

### III-A 设备、模型与执行顺序

先读设备和预算，再理解整数切点与状态归属。

<a id="s3"></a>

#### S3

> Let $N\geq2$ be the number of participating home-edge devices, and let $\mathcal{N}=\{1,\ldots,N\}$ denote their index set.

**中文意思：** N≥2 是参与推理的设备数量，花体 N 是由编号 1 至 N 组成的集合。

**讲解 / 作用：** N 是数字，花体 N 是集合。例如三台设备时，N=3，编号集合为 {1,2,3}；这只是讲解示例。设备数量在本问题中给定。

<a id="s4"></a>

#### S4

> The devices communicate through a wireless access point (AP) and execute the model in the fixed order $1,\ldots,N$.

**中文意思：** 设备通过一个无线接入点 AP 通信，按 1 至 N 的固定顺序执行模型。

**讲解 / 作用：** 计算顺序是一条链，物理通信却经过 AP：设备 i→AP→设备 i+1。优化层边界，不优化设备顺序。

<a id="s5"></a>

#### S5

> For computation modeling, device $i\in\mathcal{N}$ is represented by one graphics processing unit (GPU) with specified computation and memory-bandwidth characteristics.

**中文意思：** 在计算建模中，设备 i 以一块具有指定计算和内存带宽特性的 GPU 表示。

**讲解 / 作用：** 补出“计算建模”限定：不是宣称设备只包含 GPU，也不代表进行了真实测量；ρf 表示这一计算抽象的吞吐。

<a id="s6"></a>

#### S6

> Other accelerator types require corresponding device parameters.

**中文意思：** 若采用其他类型的加速器，需要相应的设备参数。

**讲解 / 作用：** 不能把 GPU 的频率、吞吐或能耗系数原封不动地套到另一种加速器上。这里限定抽象的适用方式。

<a id="s7"></a>

#### S7

> Let $\bar M_i$ denote the memory allocation, in bytes, available to the inference service after excluding operating-system and non-service allocations.

***这里的mi不是模型权重吗？***

**中文意思：** 上横线 M_i 表示扣除操作系统和非本服务占用后，可分配给推理服务的内存字节数。

**讲解 / 作用：** 它是服务额度，不是设备标称总容量。上横线表示给定预算，不表示平均值；与 IV 的需求 M_i 比较。

<a id="s8"></a>

#### S8

> The service's own runtime reserve is included in its memory requirement, not deducted again from $\bar M_i$.

**中文意思：** 服务自己的运行时预留计入内存需求，不再从服务额度中重复扣除。

**讲解 / 作用：** 统一左右两边的会计口径：额度一侧只排除非服务占用，需求一侧包括服务运行时。否则会人为缩小可行空间。

<a id="s9"></a>

#### S9

> Let $\bar E_i>0$ denote the per-request budget, in joules, for the incremental energy components defined below.

**中文意思：** 上横线 E_i>0 表示设备每个请求的增量能量预算，单位焦耳。

**（ 给每个请求都要建立预算合适吗 ）**

**讲解 / 作用：** 能量 J 与功率 W 不同：能量是累计消耗，功率是消耗速度。此预算仅约束随后定义的核算项，不是整机电池电量。

<a id="s10"></a>

#### S10

> Device selection, execution order, and host-accelerator co-scheduling are fixed inputs.

**（我们不涉及设备选择吧，执行顺序是固定的吧、加速器的协同调度是什么意思）**

**中文意思：** 设备选择、执行顺序和主机与加速器的协同调度作为固定输入。

**讲解 / 作用：** 这些不属于决策变量。我们要优化的是连续层分区、两阶段频率和设备发射功率，而不是所有系统配置。

<a id="s11"></a>

#### S11

> The single-device baseline has no inter-device communication.

**这感觉是一句废话**

**中文意思：** 单设备比较情形不存在设备间通信。

**讲解 / 作用：** 移除的是跨设备激活和 token 反馈通信，不是模型内部计算。此句仅说明系统边界，不扩展或修改实验方案。

<a id="s12"></a>

#### S12

> Let $L\geq N$ be the number of ordered decoder-layer blocks in the autoregressive model, indexed by $\ell\in\{1,\ldots,L\}$.

**中文意思：** L≥N 是模型按顺序排列的解码层块数量，ℓ 是 1 至 L 中的层编号。

**讲解 / 作用：** 每台设备至少分到一层，所以层数不能少于设备数。L 和 N 是给定整数；这里的 decoder layer 不等于 decode 阶段。

<a id="s13"></a>

#### S13

> Define the partition vector as $\mathbf{c}=(c_1,\ldots,c_{N-1})$, where $c_i$ is the index of the last layer assigned to device $i$, with $c_0=0$ and $c_N=L$.

**中文意思：** 分区向量 c 由 N−1 个内部切点组成；c_i 是设备 i 所分最后一层的编号，端点约定 c_0=0、c_N=L。

**讲解 / 作用：** 优化 N−1 个内部边界即可，两个端点不必优化。例如 L=8、N=3、c=(2,5)，各设备层数为 2、3、3；仅为讲解。

<a id="s14"></a>

#### S14

> To assign each device a nonempty block of consecutive layers, the boundaries satisfy

**中文意思：** 要让每台设备获得一个非空连续层块，边界必须满足下式。

**讲解 / 作用：** 这是一句公式引导语，与 E1 连起来读。严格递增同时保证非空、连续、不重叠，并覆盖全部层。

<a id="e1"></a>

#### E1 · 对应原稿式 1 · 连续非空分区

$$
0=c_0<c_1<\cdots<c_N=L
$$

**符号与单位：** c_i：设备 i 的最后层编号；c_0=0 和 c_N=L 固定；N 为设备数，L 为层数，内部边界为整数。

**为什么这样写：** 严格递增表示每台设备至少获得一层。切点确定后，各层不重叠也不遗漏。这里没有容量或能量条件，后面还要再筛可行性。

**用途 / 条件 / 示例：** 定义部署变量的结构可行域。讲解例：L=8、N=3、c=(2,5)，分配 1–2、3–5、6–8 层。

<a id="s15"></a>

#### S15

> and the layer-index set assigned to device $i$ is

**中文意思：** 而设备 i 被分配的层编号集合为下式。

**讲解 / 作用：** 这是 E2 的引导片段：把边界变量转换成设备实际负责的层集合，便于随后求和。

<a id="e2"></a>

#### E2 · 对应原稿式 2 · 切点到设备层集合

$$
\mathcal{L}_i(\mathbf{c})=\{c_{i-1}+1,\ldots,c_i\}
$$

**符号与单位：** 花体 L_i 是层编号集合，不是层数；它由相邻两切点给出。

**为什么这样写：** 设备 i 从前一设备末层之后开始，到自身末层结束；层数为 c_i−c_{i-1}。

**用途 / 条件 / 示例：** 权重、状态和计算需求都按这个集合求和。集合内每项只计到所属设备。

<a id="s16"></a>

#### S16

> Let $\mathcal{C}$ denote the set of integer partition vectors satisfying 1.

**中文意思：** 花体 C 表示满足层边界约束的所有整数分区向量的集合。

**讲解 / 作用：** 切点必须落在层与层之间，不能为 2.5 层。后面的部署优化在这个有限候选空间中选择分区。

<a id="s17"></a>

#### S17

> The input embedding is placed on device 1; final normalization, the language-model head, and token selection are placed on device $N$.

**中文意思：** 输入嵌入放在设备 1；最终归一化、语言模型输出头和 token 选择放在设备 N。

**讲解 / 作用：** 端点操作也占计算、内存和能量。只核算中间解码层，会低估首尾设备的负载。

<a id="s18"></a>

#### S18

> Only the assigned model weights and required runtime data are stored in accelerator-accessible memory during inference.

**加速器是什么意思？大家都这么写吗？**

**中文意思：** 推理期间，加速器可访问内存中只存放该设备分到的权重和必需运行数据。

**讲解 / 作用：** 不是每台设备都保存完整模型。accelerator-accessible 说明这些数据能被建模的加速器使用，不据此断言某个具体内存体系。

<a id="s19"></a>

#### S19

> Checkpoint storage is a deployment prerequisite, and model loading is excluded from per-request latency and energy.

**中文意思：** 检查点存储是部署前提，模型加载不计入单请求时延和能量。

**讲解 / 作用：** 假定模型已经装载并就绪。每次请求重新加载完整权重，是不同的执行契约，不能混进当前公式。

<a id="s20"></a>

#### S20

> During each forward pass, device $i<N$ sends the intermediate activation at its partition boundary to device $i+1$ through the AP.

**中文意思：** 每次前向执行中，除末设备外的设备 i，把切点处中间激活经 AP 发给设备 i+1。

**讲解 / 作用：** 传的是层输出激活，不是模型权重。每个前向 pass 在每个分区边界上发生一次这样的传输。

<a id="s21"></a>

#### S21

> After device $N$ selects an output token, the token identifier and control metadata are returned to device 1 if another forward pass is required.

**中文意思：** 末设备选出 token 后，若还需下一次前向计算，就把 token 编号和控制元数据返回设备 1。

**讲解 / 作用：** 这形成自回归反馈环。最后一个输出 token 后不再计算，因此不需要为继续执行而反馈一次。

<a id="s22"></a>

#### S22

> Each layer's inference state, including its key-value (KV) cache or recurrent state, is retained on the device executing that layer throughout the request.

**中文意思：** 每层的 KV 缓存或循环状态等推理状态，在整个请求中保留于执行该层的设备。

**讲解 / 作用：** 状态归属随层放置而确定。每步不把整份 KV 或循环状态搬到下一台设备；传输与状态内存因此要分开建模。

<a id="s23"></a>

#### S23

> The partition is selected at deployment and remains fixed across requests and across the prefill and decode phases; no model weights or inference states are migrated during a request.

**中文意思：** 分区在部署时选择，在多个请求以及 prefill/decode 两阶段之间保持不变；请求内不迁移权重或状态。

**讲解 / 作用：** 这是分区保持不变的系统假设。请求到达后改变频率和功率，不等于重新分区；本句界定允许的决策行为，并不规定怎样求解。

<a id="section-24"></a>

### III-B token 计数与到达信息

确认第一个 token 属于 prefill；把预测与硬上限严格分开。

<a id="s24"></a>

#### S24

> Let $P$ denote the number of prompt tokens after applying the target model's chat template.

**模板中的角色和特殊token会影响输入长度，这句话是什么意思？**

**中文意思：** P 是应用目标模型聊天模板后的输入 token 数。

**讲解 / 作用：** 应数实际进入模型的序列，而不是原始文本字符数。模板中的角色和特殊 token 会影响输入长度。

<a id="s25"></a>

#### S25

> Let ${G_{\mathrm{cap}}}\geq1$ be the service's enforced integer upper limit on the number of generated tokens, and let $G\in\{1,\ldots,{G_{\mathrm{cap}}}\}$ denote the realized output length.

**我对G_cap还有点不知道是什么意思，有什么必要搞这个G_cap**

**中文意思：** G_cap≥1 是服务强制执行的整数生成上限；G 是 1 至 G_cap 中的实际输出 token 数。

**讲解 / 作用：** 明确生成上限是整数，不更改上限数值或生成过程；G_cap 仍不等于长度预测。

<a id="s26"></a>

#### S26

> The prefill phase processes the prompt and produces the first output token.

**中文意思：** prefill 处理输入，并产生第一个输出 token。

**讲解 / 作用：** 本文把生成第一个 token 的模型计算算在 prefill 中，所以后续 decode 步数不是 G，而是 G−1。

<a id="s27"></a>

#### S27

> If $G>1$, the decode phase contains $G-1$ sequential steps.

**中文意思：** 当输出不止一个 token 时，decode 包含 G−1 个串行步骤。

**讲解 / 作用：** 例如输出 4 个 token，需要 prefill 产生第 1 个，decode 再产生 3 个；这是讲解计数，不是实验数据。

<a id="s28"></a>

#### S28

> At decode step $t\in\{1,\ldots,G-1\}$, the model consumes the preceding output token, and the context length $q_t$, including that token, is

**中文意思：** 第 t 个 decode 步输入此前产生的 token；包含这个输入 token 的上下文长度 q_t 由下式定义。

**讲解 / 作用：** t 从 1 开始。上下文长度不是仅缓存中的旧 token 数，而是按本文计数包含本步输入后的长度。

<a id="e3"></a>

#### E3 · 对应原稿式 3 · decode 的上下文计数

$$
q_t=P+t
$$

**符号与单位：** P：模板后输入长度；t：第 1 至 G−1 个 decode 步；q_t：包含本步输入 token 的上下文长度。

**为什么这样写：** prefill 产生第一个输出，第一次 decode 再输入它，故 q_1=P+1。

**用途 / 条件 / 示例：** 把各步的 q_t 代入注意力 FLOP、状态、访存、边界张量。讲解例：P=5、G=3，两个 decode 形状为 q=6、7。

<a id="s29"></a>

#### S29

> We use $q$ as a phase-dependent sequence-length argument: $q=P$ for prefill and $q=q_t$ for decode.

**中文意思：** q 是随阶段确定含义的序列长度参数：prefill 为 P，decode 为 q_t。

**讲解 / 作用：** decode 本步只输入一个 token，但其上下文长度为 q_t；因此把 q 称为“本步执行长度”容易误读。后面的函数需要同时看 s 和 q。

<a id="s30"></a>

#### S30

> A request therefore requires one prefill pass, $G-1$ decode passes, one activation message per partition boundary in each pass, and $G-1$ token-feedback messages.

**中文意思：** 一次请求有一个 prefill pass、G−1 个 decode pass；每个 pass 的每个边界传一次激活，并有 G−1 条反馈消息。

**讲解 / 作用：** 模型前向执行总次数是 G。激活消息总数为 G(N−1)，反馈为 G−1；两种消息内容和方向不同。

<a id="s31"></a>

#### S31

> At request arrival, the controller observes the prompt and its token count $P$, whereas the realized output length $G$ is unknown.

**中文意思：** 到达时控制器看到输入和 P，但不知道实际输出长度 G。

**讲解 / 作用：** 这是信息时序约束，防止把事后才知道的长度偷偷作为在线输入。

<a id="s32"></a>

#### S32

> Let $g_\theta$ denote an output-length predictor with parameters $\theta$ fixed before partition calibration and testing.

**中文意思：** g_θ 表示输出长度预测器，其参数 θ 在分区校准和测试之前固定。

**讲解 / 作用：** 它是资源决策的一个输入模块；本文不以预测器架构创新为主张。固定参数使不同候选分区使用同一个预测规则。

<a id="s33"></a>

#### S33

> Its integer prediction, denoted by $\widehat{G}$, is

**中文意思：** 预测器处理后得到的整数长度记为 G_hat，其定义如下。

**讲解 / 作用：** 与 E4 一起读。帽子表示估计值，不表示实际 G，也不是硬上限。

<a id="e4"></a>

#### E4 · 对应原稿式 4 · 整数化与裁剪预测

$$
\widehat{G}=\Pi_{[1,G_{\mathrm{cap}}]}(\mathrm{round}(g_\theta(\mathrm{prompt})))
$$

**符号与单位：** g_θ：固定参数预测器；round：取最近整数；Π：裁剪；G_hat：预测长度；G_cap：硬上限。

**为什么这样写：** 估计值先整数化，再压到服务允许范围。这里 round 后不会凭空获知真实 G。

**用途 / 条件 / 示例：** G_hat 进入时延目标；G_cap 进入约束。讲解例：预测 12.4、上限 10，最终估计为 10，并非保证真实长度恰为 10。

<a id="s34"></a>

#### S34

> where $\operatorname{round}(\cdot)$ rounds to the nearest integer and $\Pi_{[1,{G_{\mathrm{cap}}}]}(\cdot)$ clips the result to $[1,{G_{\mathrm{cap}}}]$.

**中文意思：** round 四舍五入到最近整数，Π 把结果截断到 [1,G_cap]。

**讲解 / 作用：** 先整数化，再限制合法范围。下限保证至少一个输出，上限保证预测服务长度不超过服务硬上限。

<a id="s35"></a>

#### S35

> Predictor training uses data separate from the partition-calibration and test sets.

**中文意思：** 预测器训练使用与分区校准及测试集合分离的数据。

**讲解 / 作用：** 这声明信息隔离要求：不能用测试结果训练预测器或选择部署分区。本讲解不展开范围外的具体数据协议。

<a id="s36"></a>

#### S36

> The workload includes one request from the initial user turn of each conversation.

**中文意思：** 所考虑的负载从每个会话的首次用户轮次取一个请求。

**讲解 / 作用：** 替换不自然的 first-user prompt；请求输入仍按目标聊天模板处理，P 包括模板处理后的全部输入 token。没有改动数据或实验协议。

<a id="s37"></a>

#### S37

> The prediction determines the latency estimate used for resource allocation, while ${G_{\mathrm{cap}}}$ determines the energy and memory requirements used for admission.

**中文意思：** 预测长度用于资源优化的时延估计，硬上限用于准入所需的能量和内存检查。

**讲解 / 作用：** 记住分工：目标看预测，约束看上限。不能为了更好时延把预算检查也换成预测长度。

<a id="s38"></a>

#### S38

> Historical values of $G$ are used during partition calibration only to evaluate resources already selected from arrival-time information.

**中文意思：** 历史真实 G 仅在分区校准时评价已经依据到达信息选定的资源。

**讲解 / 作用：** 先按 P、G_hat 选资源，再用历史 G 算实际长度下的代价，顺序不能反过来。

<a id="s39"></a>

#### S39

> Thus, the online resource decision does not use the realized output length.

**中文意思：** 因此在线资源决策不使用实际输出长度。

**讲解 / 作用：** 这就是本文 causal 的含义：没有未来信息。不是统计学中的因果效应识别。

<a id="section-40"></a>

### III-C 控制与模型假设

哪些变量可调、何时选择、哪些执行与能量组件不在边界内。

<a id="s40"></a>

#### S40

> Let $s\in\{\mathrm{pre},\mathrm{dec}\}$ denote the inference phase, where $\mathrm{pre}$ and $\mathrm{dec}$ refer to prefill and decode, respectively.

**中文意思：** 阶段 s 取 pre 或 dec，分别指 prefill 和 decode。

**讲解 / 作用：** 上标 s 常表示阶段标签，不是把变量乘方。相同设备可以在两阶段采用不同设置。

<a id="s41"></a>

#### S41

> The control variables are the GPU core frequency $f_i^s$ and the device transmit power $p_i^s$ in phase $s$, measured in hertz and watts, respectively.

**中文意思：** 控制变量是设备 i 在阶段 s 的 GPU 核心频率 f_i^s 和发射功率 p_i^s，单位分别为 Hz 与 W。

**讲解 / 作用：** f 控制计算资源，p 控制无线发送。功率 p 是射频输出功率，后面还要考虑放大器效率和电路功率。

<a id="s42"></a>

#### S42

> Their operating limits are $f_{i,\min}$ and $f_{i,\max}$ for frequency, and $p_{i,\min}$ and $p_{i,\max}$ for transmit power.

**中文意思：** 频率上下界为 f_i,min、f_i,max，发射功率上下界为 p_i,min、p_i,max。

**讲解 / 作用：** 这些界是给定参数，不是待学习结果；设备间可以不同。有限合法等级和连续参考区间要区别看。

<a id="s43"></a>

#### S43

> All allowed discrete resource levels lie within these bounds and are specified as hardware-supported values or simulation assumptions.

**中文意思：** 允许的离散资源等级在上下界内，并明确属于硬件支持值或模拟假设。

**讲解 / 作用：** 离散等级并不自动意味着真实设备可配置。此句要求透明说明来源，不声称已经部署这些控制。

<a id="s44"></a>

#### S44

> Frequencies are positive, and the allowed transmit powers yield positive modeled link rates.

**中文意思：** 频率为正，允许的发射功率对应正的模型链路速率。

**讲解 / 作用：** 时延公式要除以吞吐或速率，因此分母不能为零。这里是数学定义域条件。

<a id="s45"></a>

#### S45

> Memory frequency is fixed.

**中文意思：** 内存频率固定。

**讲解 / 作用：** 只优化 GPU 核心频率，不优化内存时钟；这不表示内存访存没有成本。

<a id="s46"></a>

#### S46

> The devices transmitting during prefill are indexed by $\mathcal{I}_{\mathrm{pre}}=\{1,\ldots,N-1\}$, while $\mathcal{I}_{\mathrm{dec}}=\mathcal{N}$ includes device $N$ for token feedback.

**中文意思：** prefill 发送者集合为 1 至 N−1；decode 发送者集合包含所有设备，末设备负责 token 反馈。

**讲解 / 作用：** 末设备没有 prefill 激活要发给下一设备。第一条用于启动 decode 的反馈也按 decode 阶段计费，后文会解释。

<a id="s47"></a>

#### S47

> Thus, $p_i^s$ is defined only for $i\in\mathcal{I}_s$.

**中文意思：** 只有该阶段会发送的设备才定义发射功率变量。

**讲解 / 作用：** 不应给不存在的发送事件增加无意义变量，例如末设备的 prefill 发射功率。

<a id="s48"></a>

#### S48

> Let $\mathbf{z}$ denote the resource vector containing all phase-specific frequencies and the applicable transmit powers.

**中文意思：** z 把所有阶段频率和有效的发射功率变量收集成一个资源向量。

**讲解 / 作用：** 写 A(c,P,G_hat) 返回 z，就是一次性返回这些配置，不是只返回某台设备一个频率。

<a id="s48a"></a>

#### S48a

> For lexicographic tie-breaking, frequency components are ordered first by phase ($\mathrm{pre}$ before $\mathrm{dec}$) and then by increasing device index, followed by transmit-power components in the same phase and index order.

**中文意思：** 为定义字典序，先排列频率分量：prefill 在前、decode 在后，每阶段按设备编号递增；再按同样顺序排列存在的发射功率分量。

**讲解 / 作用：** 这是本轮补全的确定性约定，不增加控制变量。具体顺序为 prefill 的 N 个 f、decode 的 N 个 f、prefill 的 N−1 个 p、decode 的 N 个 p。平局时它会影响选定配置，进而可能影响历史评分；不宣称任何一种排列更优。

<a id="s49"></a>

#### S49

> The AP transmit power, denoted by $p_{\mathrm{AP}}$, is fixed.

**中文意思：** AP 发射功率 p_AP 固定。

**讲解 / 作用：** AP 不是待优化设备。这个设定使下行速率和设备接收能量不随其他设备的发射功率改变。

<a id="s50"></a>

#### S50

> At arrival, the controller selects the resource vector for both phases using $(P,\widehat{G})$.

**中文意思：** 请求到达时，控制器用 P 和 G_hat 同时选择两阶段资源。

**讲解 / 作用：** 不是完成 prefill 后重新观察真实输出长度再决策，也不是每生成一个 token 重算一次资源。

<a id="s51"></a>

#### S51

> Each selected frequency and power is held constant during its phase.

**中文意思：** 选定频率和功率在各自阶段内保持不变。

**讲解 / 作用：** prefill 一组、decode 一组；decode 内所有步骤共享该组控制，但每步上下文 q_t 会变化。

<a id="s52"></a>

#### S52

> The model considers one request at batch size one, with sequential computation and communication and no overlap between devices.

**中文意思：** 模型考虑 batch=1 的单请求，计算和通信串行，设备间不重叠执行。

**讲解 / 作用：** 因此端到端时间可以累加。算子内部计算与访存的重叠是另一层级，不与这个假设冲突。

<a id="s53"></a>

#### S53

> Requests are evaluated independently.

**中文意思：** 各请求独立评价。

**讲解 / 作用：** 模型不引入跨请求排队、竞争或流水线；共享的只是部署分区，不是请求间联合调度。

<a id="s54"></a>

#### S54

> Concurrent request scheduling, inter-device pipelining, speculative decoding, prefix reuse, dynamic quantization, and routing are outside this setting.

**中文意思：** 并发请求调度、设备间流水线、推测解码、前缀复用、动态量化和路由不在当前设定内。

**讲解 / 作用：** 这是问题边界。不能在解释或比较中悄悄利用这些机制来改变原公式的执行次数和消息量。

<a id="s55"></a>

#### S55

> Let $E_i^{\mathrm{acct}}$ denote the modeled incremental energy consumed by device $i$ for a request.

**中文意思：** E_i^acct 表示设备 i 执行一个请求的模型增量能量。

**讲解 / 作用：** acct 是 accounted 的核算标签，提醒它不是全设备总能量；V 节会展开具体项。

<a id="s56"></a>

#### S56

> It includes computation, memory access, control, and radio operation, measured in joules.

**中文意思：** 它包括计算、访存、控制和无线操作，单位焦耳。

**讲解 / 作用：** GPU 能耗只是其中一部分。预测、优化和同步控制也在核算边界内，不能把它们一律当免费。

<a id="s57"></a>

#### S57

> Base system power, accelerator idle/waiting power, display power, unrelated workloads, and AP energy are excluded.

**中文意思：** 基础系统功率、加速器空闲或等待、显示、其他负载和 AP 能量不计入。

**讲解 / 作用：** 这些排除项不是说现实中不存在，而是当前预算只约束指定的增量组成。

<a id="s58"></a>

#### S58

> The budget $\bar E_i$ therefore constrains these specified request components; it does not represent a whole-device electricity or battery-lifetime limit.

**中文意思：** E_i 的预算因此只约束指定请求组件，不表示整机电量或电池寿命上限。

**讲解 / 作用：** 模型内满足预算，不等于真实整机一定满足同样的电池限制。所有保证都必须沿用这个边界。

<a id="s59"></a>

#### S59

> Figure 1 summarizes the execution order and the partition and resource decisions, with $\mathbf{c}^\star$ denoting the partition selected at deployment.

**中文意思：** 系统图概括执行顺序、分区决策和资源决策，c* 表示部署选定分区。

**讲解 / 作用：** 星号在此表示最终选出的解，不自动意味着对所有未来请求或所有可能策略全局最优。

<a id="s60"></a>

#### S60

> FIGURE: System architecture and resource decisions.

**中文意思：** 图注标题：系统架构与资源决策。

**讲解 / 作用：** Partition selection 表示由历史请求和固定预测器选跨请求共用分区；Request control 表示依据当前 P 和预测长度选资源。新版图下半部分的 Adjacent-device transfer 描述任意 1≤i<N 的 i→AP→i+1 传输，而非列出三台不同设备，因此也适用于 N=2。Token feedback 仅在还需要下一次前向时从 N 返回 1。输入 embedding 在设备 1，最终 normalization、head 和 token selection 在设备 N；图示不引入额外计算节点。

<a id="s61"></a>

#### S61

> The deployment partition is fixed across requests.

**中文意思：** 部署分区在各请求间固定。

**讲解 / 作用：** 这是跨请求保持不变，不是只在某一次请求内固定。

<a id="s62"></a>

#### S62

> The controller selects phase-specific GPU frequencies and device transmit powers from arrival-time information; each setting is held constant within its phase.

**中文意思：** 控制器依据到达信息选阶段特定频率和发射功率，并在阶段内保持设置。

**讲解 / 作用：** 再次强调“选择时机”和“执行期间是否变化”是两件事：两组控制都在到达时选好。

<a id="s63"></a>

#### S63

> AP transmit power is fixed.

**中文意思：** AP 发射功率固定。

**讲解 / 作用：** 设备发射功率可变与 AP 功率固定可以同时成立；两跳通信分别使用不同的功率参数。

<a id="section-64"></a>

## IV 分层计算与内存模型

从层放置得到需求量，区分运算、访存和容量。

<a id="s64"></a>

#### S64

> The partition determines which layer and endpoint operators each device executes.

**中文意思：** 分区决定设备负责哪些层和端点算子。

**讲解 / 作用：** 这是从 III 的放置决策进入 IV 的资源需求。端点放置固定，层集合由切点决定。

<a id="s65"></a>

#### S65

> We first specify their computation, memory-access, and storage requirements, then derive a conservative memory requirement for admission.

**中文意思：** 先规定计算、访存和存储需求，再给出准入使用的保守内存需求。

**讲解 / 作用：** 不再把由分项容量合成的需求无条件称为精确峰值。F/D/W/S/V 的含义不变，原内存公式也保留。

<a id="s66"></a>

#### S66

> These quantities enter the latency and energy models in the next section.

**中文意思：** 这些量会进入下一节的时延和能量模型。

**讲解 / 作用：** IV 回答需要执行或存储多少，V 回答在给定设备和资源下需要多久、消耗多少能量。

<a id="section-67"></a>

### IV-A 层级与算子级量

F/D/W/S/V 的职责及组级核算的重要性。

<a id="s67"></a>

#### S67

> For layer $\ell$, let $F_\ell^{\mathrm{pre}}(P)$ denote the number of floating-point operations (FLOP) required to process a prompt of length $P$, and let $D_\ell^{\mathrm{pre}}(P)$ denote its effective memory traffic in bytes.

**中文意思：** 层 ℓ 的 prefill 计算量记为 F_ℓ^pre(P)，单位 FLOP；有效访存量记为 D_ℓ^pre(P)，单位 byte。

**讲解 / 作用：** FLOP 是操作次数，FLOP/s 才是吞吐。F 和 D 是需求量，不包含设备执行速度。

<a id="s68"></a>

#### S68

> For one decode step at context length $q$, the corresponding quantities are $F_\ell^{\mathrm{dec}}(q)$ and $D_\ell^{\mathrm{dec}}(q)$.

**中文意思：** 上下文为 q 的一个 decode 步对应 F_ℓ^dec(q)、D_ℓ^dec(q)。

**讲解 / 作用：** 不是整段响应的 decode 总量；总量还要对 G−1 个不同 q_t 的步骤求和。

<a id="s69"></a>

#### S69

> Memory traffic quantifies data transfers during execution, including repeated accesses and cache reuse under the specified runtime model; it is not the memory capacity occupied by the tensors.

**中文意思：** 访存量描述执行期间的数据传输，包括声明路径中的重复访问和缓存复用，不等于张量占据的容量。

**讲解 / 作用：** 同一份权重存一次，却可能被读很多次；缓存又可能避免部分外层传输，因此只知道权重大小不能确定 D。

<a id="s70"></a>

#### S70

> The transfer boundary used to define this traffic must match that of the bandwidth and per-byte energy coefficients introduced below.

**中文意思：** 访存量的传输边界必须与后面的带宽和每字节能耗系数一致。

**讲解 / 作用：** 例如若 D 数的是某一内存接口的字节，速度和能耗也应对应那个接口，不能混合不同存储层级。

<a id="s71"></a>

#### S71

> Let $W_\ell$ denote the memory required to store layer $\ell$'s weights, and let $S_\ell(q)$ denote the memory required for its inference state at context length $q$.

**中文意思：** W_ℓ 是层权重存储量，S_ℓ(q) 是该层在上下文 q 下的推理状态存储量。

**讲解 / 作用：** 权重由架构和精度决定；状态由类型、上下文和格式决定。二者均是容量，而不是访存流量。

<a id="s72"></a>

#### S72

> The inference state is retained between forward passes and comprises the KV cache for a full-attention layer or the state and convolutional cache for a recurrent layer.

**中文意思：** 状态在前向 pass 之间保留：全注意力层是 KV，循环层是循环状态和卷积缓存。

**讲解 / 作用：** 不能把所有层都套成随 q 线性增长的 KV。目标模型的两类层需要不同核算。

<a id="s73"></a>

#### S73

> Let $V_\ell^s(q)$ denote the size of the intermediate activation transmitted at a partition boundary after layer $\ell$ in phase $s$.

**中文意思：** V_ℓ^s(q) 是阶段 s 在层 ℓ 后切分时需要传输的中间激活字节数。

**讲解 / 作用：** 层是否成为边界由 c 决定，边界载荷大小由 V 给出。后面乘 8 换成 bit。

<a id="s74"></a>

#### S74

> All three quantities are measured in bytes.

**中文意思：** W、S 和 V 三种量都用字节计。

**讲解 / 作用：** 此处 three 指上一组权重、状态、激活，不包含 FLOP。明确单位有助于检查通信中的 8 倍换算。

<a id="s75"></a>

#### S75

> Their values depend on the model architecture, numerical precision, and runtime implementation.

**中文意思：** 这些量随模型架构、数值精度和运行时实现而变。

**讲解 / 作用：** 不能把某模型的层成本或 BF16 大小当成所有模型的常数；本模型需匹配当前目标和路径。

<a id="s76"></a>

#### S76

> The latency and energy models also include the input embedding, final normalization, output projection, and token selection.

**中文意思：** 时延和能量还计入输入嵌入、最终归一化、输出投影和 token 选择。

**讲解 / 作用：** 不仅统计解码层。尤其词表投影可能较大，端点设备的成本不能忽略。

<a id="s77"></a>

#### S77

> Let $\mathcal{O}_i^s(\mathbf{c},q)$ denote the ordered collection of operator groups executed by device $i$ in phase $s$ at length $q$.

**中文意思：** O_i^s(c,q) 是设备 i 在给定分区、阶段、长度下按顺序执行的算子组集合。

**讲解 / 作用：** 它把解码层和端点算子统一起来。ordered 表示执行有序，后续时间按组累加。

<a id="s78"></a>

#### S78

> For operator group $o\in\mathcal{O}_i^s$, let $F_{io}^s(q)$ and $D_{io}^s(q)$ denote its FLOP count and effective memory traffic, and let $t_{io}^s$ and $e_{io}^s$ denote its execution time in seconds and incremental energy consumption in joules.

**中文意思：** 对于组 o，F、D 分别是计算和访存量，t、e 分别是执行秒数和增量焦耳数。

**讲解 / 作用：** 把需求 F、D 与代价 t、e 分开：代价需要进一步结合设备参数及所选频率。

<a id="s79"></a>

#### S79

> For an operator group within decoder layer $\ell$, $r$ indexes the group, and $F_{\ell r}^s(q)$ and $D_{\ell r}^s(q)$ denote its FLOP count and memory traffic.

**中文意思：** 若组位于解码层 ℓ 内，r 是该层的组编号，F_ℓr 和 D_ℓr 表示其需求。

**讲解 / 作用：** o 是统一设备级算子编号，(ℓ,r) 是层内编号。两种写法不是两套重复计算。

<a id="s80"></a>

#### S80

> Operators outside the decoder layers are included as separate entries in the operator specification.

**中文意思：** 解码层之外的算子作为单独条目列入算子说明。

**讲解 / 作用：** 例如 embedding、head 不必强行归到某个解码层，仍可进入统一总和。

<a id="s81"></a>

#### S81

> Operator groups within a layer can have different ratios of computation to memory access.

**中文意思：** 同一层内不同算子组的计算量与访存量之比可能不同。

**讲解 / 作用：** 有的组偏计算密集，有的偏访存密集；一个层的平均比值可能掩盖这些差异。

<a id="s82"></a>

#### S82

> We therefore estimate each sequential group's execution time from its computation and memory-access requirements and then sum the group times.

**中文意思：** 因此先按每个串行算子组的需求估时，再把各组时间相加。

**讲解 / 作用：** 计算 max 的层级必须正确：每组先取瓶颈，再跨组求和。

<a id="s83"></a>

#### S83

> Applying a single maximum to aggregated FLOP counts and memory-traffic quantities would allow different groups' bottlenecks to overlap, contrary to the assumed sequential execution.

**中文意思：** 若把所有组的需求先相加再取一次 max，会让不同组的瓶颈互相重叠，与串行设定不符。

**讲解 / 作用：** 例如两个串行组各需 max(10,1) 和 max(1,10)，正确共 20，而汇总后 max(11,11)=11；数字仅作讲解。

<a id="s84"></a>

#### S84

> The Roofline model provides the compute-bound and memory-bound interpretation [cite: williams2009roofline,nvidia_gpu_performance]; effective throughput, bandwidth, and execution overheads specify the latency model used here.

**中文意思：** Roofline 提供计算受限与访存受限的解释；本文由有效吞吐、带宽和开销确定具体时延。

**讲解 / 作用：** 引用提供建模思想，不代表任何引用已经测量了本虚拟设备。系数仍须明确来源或假设。

<a id="section-85"></a>

### IV-B 架构和运行时相关需求

共同投影、两类层及输入输出端点要匹配实际路径。

<a id="s85"></a>

#### S85

> The operator-level specification must identify tensor dimensions, weight and inference-state sizes, temporary-buffer lifetimes, and boundary activations for the chosen model and runtime revisions.

**中文意思：** 算子说明必须针对固定模型和运行时版本记录维度、权重/状态大小、临时缓冲寿命及边界激活。

**讲解 / 作用：** 这是复现接口要求；must 不是已完成声明。缓冲寿命决定能否复用，直接影响峰值内存。

<a id="s86"></a>

#### S86

> Each quantity requires either a source-backed derivation or an explicit modeling assumption.

**中文意思：** 每项量必须有来源支持的推导，或明确建模假设。

**讲解 / 作用：** 架构可推导量和经验有效量要区分；不能把缺少依据的数写成真实测量。

<a id="s87"></a>

#### S87

> For Qwen3.5-4B, full-attention and recurrent layers require different inference-state and computation models [cite: qwen35_4b_config,qwen35_hf_docs].

**中文意思：** Qwen3.5-4B 的全注意力层和循环层需要不同的计算与状态模型。

**讲解 / 作用：** 当前目标保持 Qwen3.5-4B。不能因为写一个通用 Transformer 公式就把全部层视为全注意力。

<a id="s88"></a>

#### S88

> Appendix A describes this specification in detail.

**中文意思：** 模型与运行时说明的细节在附录中。

**讲解 / 作用：** 正文定义公共接口，附录承担具体张量明细。本讲解只解释该接口，不讲解范围外附录原文。

<a id="s89"></a>

#### S89

> Let $d$ denote the model's hidden dimension and $v$ its vocabulary size.

**中文意思：** d 是隐藏维度，v 是词表大小。

**讲解 / 作用：** 它们是架构给定尺寸，不是设备频率或预测输出长度；后续投影成本用到二者。

<a id="s90"></a>

#### S90

> We distinguish the projection operations shared by the layer types from their attention or recurrent operations and retained inference states.

**中文意思：** 把层类型共有的投影，与各自的注意力/循环操作及保留状态分开核算。

**讲解 / 作用：** 投影公式可共用，不表示完整层计算相同。先讲共有部分，再讲类型专属部分。

<a id="s91"></a>

#### S91

> Consider a linear projection with input dimension $a$ and output dimension $b$.

**中文意思：** 考虑输入维度 a、输出维度 b 的线性投影。

**讲解 / 作用：** 这是为矩阵乘法计数建立小模型；a、b 都是维度数量，没有 Hz 或 byte 单位。

<a id="s92"></a>

#### S92

> Multiplying a $P\times a$ activation matrix by an $a\times b$ weight matrix requires $2Pab$ FLOP under the convention that a multiply-accumulate counts as two operations.

**中文意思：** P×a 的激活乘 a×b 的权重，在乘加算两次操作的约定下需要 2Pab FLOP。

**讲解 / 作用：** 每个 P×b 输出元素累计 a 次乘加，共 Pab 个乘加，再乘 2。FLOP 约定必须与吞吐系数一致。

<a id="s93"></a>

#### S93

> Let $\mathcal{A}_\ell$ denote the set of linear-projection weight matrices in layer $\ell$, and let $A\in\mathcal{A}_\ell$ denote one such matrix.

**中文意思：** A_ℓ 集合包含层 ℓ 的所有线性投影权重矩阵，普通 A 表示其中一块矩阵。

**讲解 / 作用：** 集合与单个矩阵不同。后面遍历集合累加各投影，不能只算 QKV 中某一块。

<a id="s94"></a>

#### S94

> The functions $\operatorname{rows}(A)$ and $\operatorname{cols}(A)$ give its row and column counts.

**中文意思：** rows(A)、cols(A) 分别取矩阵行数和列数。

**讲解 / 作用：** 行列数量的乘积给出矩阵权重元素数，也是每位置投影乘加的主要计数依据。

<a id="s95"></a>

#### S95

> The prefill and one-step decode FLOP counts for these projections, denoted by $F_{\mathrm{proj},\ell}^{\mathrm{pre}}(P)$ and $F_{\mathrm{proj},\ell}^{\mathrm{dec}}$, are

**中文意思：** 所有这些投影的 prefill 与单步 decode 计算量分别记为两个 F_proj，并由下式给出。

**讲解 / 作用：** prefill 有 P 个位置，而 batch=1 的单步 decode 只处理一个新位置，所以 E5 两式相差 P 因子。

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

<a id="s96"></a>

#### S96

> Let $d_{\mathrm{ff}}$ denote the intermediate dimension of a gated feed-forward block.

**中文意思：** d_ff 表示门控前馈块的中间维度。

**讲解 / 作用：** 采用该符号避免与消息编号 m 混淆。它是宽度参数，不是层数或消息长度。

<a id="s97"></a>

#### S97

> Its two $d\times d_{\mathrm{ff}}$ projections and one $d_{\mathrm{ff}}\times d$ projection require $6Pd d_{\mathrm{ff}}$ FLOP in prefill and $6d d_{\mathrm{ff}}$ FLOP per decode step.

**中文意思：** 两个 d×d_ff 和一个 d_ff×d 投影，prefill 共需 6Pdd_ff FLOP，单步 decode 需 6dd_ff FLOP。

**讲解 / 作用：** 三次投影各有 2dd_ff 的每位置成本，所以出现 6；此数不含随后列出的非矩阵算子。

<a id="s98"></a>

#### S98

> Normalization, nonlinearities, elementwise products, and residual operations are recorded separately; any omitted contribution must be identified as a modeling approximation.

**中文意思：** 归一化、非线性、逐元素乘法和残差单列；若省略某项，必须说明它是近似。

**讲解 / 作用：** 不能把主矩阵 FLOP 直接说成全部成本。是否近似属于模型说明，不凭讲解替作者决定省略。

<a id="s99"></a>

#### S99

> For a full-attention layer, let $h_q$ be the number of query heads and $d_h$ the dimension of each head.

**中文意思：** 全注意力层中 h_q 是查询头数，d_h 是每头维度。

**讲解 / 作用：** 这些决定 QKᵀ 和注意力加权 V 的矩阵乘法规模；与 KV 头数 h_kv 不一定相等。

<a id="s100"></a>

#### S100

> The approximate FLOP counts of the two attention matrix products, denoted by $F_{\mathrm{attn}}^{\mathrm{dec}}(q)$ and $F_{\mathrm{attn}}^{\mathrm{pre}}(P)$, are

**中文意思：** 两次注意力矩阵乘法的近似计算量分别记为 decode 和 prefill 的 F_attn，下式给出。

**讲解 / 作用：** 只计这两次主要乘法，不把 softmax 等自动算进去。prefill 的二次长度项与逐步 decode 的 q 项不同。

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

<a id="s101"></a>

#### S101

> The selected count must match the attention kernel used to specify effective throughput.

**中文意思：** 选用的操作计数必须匹配确定有效吞吐时所采用的注意力内核。

**讲解 / 作用：** 若内核跳过上三角，就不能同时使用密集乘法的计数和不相容的吞吐系数。

<a id="s102"></a>

#### S102

> Let $h_{kv}$ denote the number of key/value heads, $b_{kv}$ the number of bytes per KV-state element, and $S_{\mathrm{full}}(q)$ the memory occupied by the principal KV state of one full-attention layer.

**中文意思：** h_kv 是 KV 头数，b_kv 是每状态元素的字节数，S_full(q) 是一层主要 KV 状态占用。

**讲解 / 作用：** 这是容量计数；头数乘头维度、上下文长度和精度，不能使用查询头数代替 KV 头数。

<a id="s103"></a>

#### S103

> Then

**中文意思：** 于是得到下式。

**讲解 / 作用：** 此短语连接前述符号定义与 E7。应与公式一起读，不是独立技术断言。

<a id="e7"></a>

#### E7 · 对应原稿式 9 · 一层 KV 状态容量

$$
S_{\mathrm{full}}(q)=2qh_{kv}d_hb_{kv}
$$

**符号与单位：** h_kv：KV 头数；b_kv：每状态元素 byte；q：上下文长度；结果 byte。

**为什么这样写：** 前面的 2 来自 K、V 两份；每份 q×h_kv×d_h 个元素。这里的 2 不是 FLOP 乘加约定。

**用途 / 条件 / 示例：** 进入内存容量约束，不自动等于每步 D。讲解例：q=10、h_kv=2、d_h=4、b_kv=2，共 320 byte；不代替目标模型实际参数。

<a id="s104"></a>

#### S104

> For a recurrent layer, the non-projection operations and the retained recurrent state and convolutional cache are specified by the selected implementation.

**中文意思：** 循环层的非投影操作、循环状态和卷积缓存由所选实现规定。

**讲解 / 作用：** 循环层不仅有线性投影，还可能有状态更新和卷积；其确切张量不能通过 KV 公式猜测。

<a id="s105"></a>

#### S105

> Their computation, memory traffic, and state-memory requirements enter the same operator-level specification; the full-attention FLOP and KV-state expressions do not apply to them.

**中文意思：** 这些计算、访存和状态量进入同一算子说明，但不套用全注意力 FLOP 与 KV 状态式。

**讲解 / 作用：** 通用的是接口 F、D、S，不是类型专属公式。这里保护混合架构的核算正确性。

<a id="s106"></a>

#### S106

> Appendix A provides the model-specific tensor details.

**中文意思：** 附录给出目标模型专属张量细节。

**讲解 / 作用：** 正文此处明确需要实现信息，不假造新的循环层成本表达式。

<a id="s107"></a>

#### S107

> Endpoint operators are accounted for separately from the decoder layers.

**中文意思：** 端点算子在解码层之外单独核算。

**讲解 / 作用：** 这承接共有投影和类型专属层，最后补齐输入/输出两端，避免漏项。

<a id="s108"></a>

#### S108

> Let $n_{\mathrm{head}}^s$ denote the number of positions projected by the language-model head in phase $s$.

**中文意思：** n_head^s 是阶段 s 在语言模型头中实际进行词表投影的位置数。

**讲解 / 作用：** 重点是实际做了多少位置的矩阵乘法，不是最终保留了多少行输出。

<a id="s109"></a>

#### S109

> The principal matrix-multiplication cost is $2n_{\mathrm{head}}^sdv$ FLOP.

**中文意思：** 输出头主要矩阵乘法成本为 2n_head^s d v FLOP。

**讲解 / 作用：** 每位置从 d 维映射至 v 个词表分数；乘加两次，因此乘 2。

<a id="s110"></a>

#### S110

> Prefill may project the final position or all $P$ positions, depending on the execution path.

**中文意思：** prefill 可能只投影最后一个位置，也可能投影全部 P 个位置，取决于执行路径。

**讲解 / 作用：** 这不是优化器随便选的开关，而是已声明运行时行为。不同路径的 F 必须分别正确计数。

<a id="s111"></a>

#### S111

> Retaining only the final logits row after an all-position projection does not reduce the operations already performed [cite: hf_qwen35_implementation,hf_transformers_generation].

**中文意思：** 全位置投影做完后只保留最后一行 logits，不能减少已经发生的计算。

**讲解 / 作用：** 丢弃结果不等于没做计算。必须区分投影前切片与投影后取最后行。

<a id="s112"></a>

#### S112

> When the embedding and output head share parameters but are stored on different devices, the memory model includes each physical copy.

**中文意思：** 输入嵌入与输出头虽共享参数，但若分存在不同设备，内存模型计入每份物理副本。

**讲解 / 作用：** 模型唯一参数量不等于各设备实际存储之和。跨设备相同数值也可能需要两份存储。

<a id="section-113"></a>

### IV-C 准入内存需求

把权重、状态、同时存在的缓冲和运行时预留一次性核清。

<a id="s113"></a>

#### S113

> Let $U_i(\mathbf{c},s,q)$ denote the peak memory required for simultaneously allocated workspace and temporary buffers on device $i$ in phase $s$ at length $q$.

**中文意思：** U_i(c,s,q) 是设备在指定分区、阶段和长度下同时分配的工作区及临时缓冲峰值。

**讲解 / 作用：** 同时存在才需一起占内存；先后使用并可复用的缓冲不能全部相加。

<a id="s114"></a>

#### S114

> Let $M_{\mathrm{rt},i}$ denote the memory reserved by the inference service for its runtime, and let $W_{\mathrm{extra},i}$ denote the memory for embedding, final normalization, output-head parameters, and any required weight copies outside its assigned decoder layers.

**中文意思：** M_rt,i 是服务运行时预留；W_extra,i 是所分解码层之外的嵌入、末归一化、输出头和必要权重副本。

**讲解 / 作用：** 区分模型端点权重与运行时内存，也不要与 U 的临时缓冲重复核算。

<a id="s115"></a>

#### S115

> These quantities are measured in bytes.

**中文意思：** 这些量都以字节计。

**讲解 / 作用：** 与服务额度 M_bar 使用相同单位，才能直接比较。

<a id="s116"></a>

#### S116

> For an output length $G$, the set of phase-length pairs executed by a request is

**中文意思：** 输出长度为 G 的请求所执行的阶段-长度对组成下式集合。

**讲解 / 作用：** E8 枚举本次会经历的执行形状，为内存容量检查和逐步求和提供索引。

<a id="e8"></a>

#### E8 · 对应原稿式 10 · 请求经历的阶段与形状

$$
\mathcal{Q}(P,G)=\{(\mathrm{pre},P)\}\cup\{(\mathrm{dec},P+t):1\leq t<G\}
$$

**符号与单位：** 每个元素是一对 (阶段,执行长度)。Q 是形状集合，不是计算量或资源集合。

**为什么这样写：** 一次 prefill 加 G−1 个 decode 形状。G=1 时只有第一项。

**用途 / 条件 / 示例：** 内存检查代入 G_cap，实际代价汇总代入真实 G 或预测 G_hat。

<a id="s117"></a>

#### S117

> where the decode set is empty for $G=1$.

**中文意思：** G=1 时 decode 集合为空。

**讲解 / 作用：** 只有 prefill；空求和为零。这是重要边界情形，不能再计一次 decode。

<a id="s118"></a>

#### S118

> To test memory feasibility for all permitted output lengths, we evaluate the peak over $\mathcal{Q}(P,{G_{\mathrm{cap}}})$.

**中文意思：** 为检查所有允许长度的内存可行性，在 Q(P,G_cap) 上取最大容量需求。

**讲解 / 作用：** 检查硬上限覆盖的全部形状，不使用预测长度替代。

<a id="s119"></a>

#### S119

> The resulting conservative memory requirement, denoted by $M_i(\mathbf{c};P,{G_{\mathrm{cap}}})$, is

**中文意思：** 得到的保守内存需求记为 M_i(c;P,G_cap)，如下定义。

**讲解 / 作用：** M_i 是模型准入容量要求，不是实测瞬时峰值。状态所需容量与临时缓冲峰值相加可以保守计费；只有各项峰值同时出现时，才等于实际峰值。

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

**用途 / 条件 / 示例：** 要求 M_i≤M_bar,i。状态容量项必须覆盖该前向执行全过程所需分配，临时缓冲项不能重复包含同一状态。M_bar 已扣非服务占用，但没有重复扣本式 M_rt。此式可能保守地缩小准入空间；只有证明单调后，才能简化形状遍历。

<a id="s120"></a>

#### S120

> The memory constraint is $M_i(\mathbf{c};P,{G_{\mathrm{cap}}})\leq\bar M_i$, where $\bar M_i$ is the service allocation introduced in Section III.

**中文意思：** 内存需求必须不超过 III 定义的服务额度 M_bar,i。

**讲解 / 作用：** 左边是要用多少，右边是允许用多少；可行性判断不能调换角色。

<a id="s121"></a>

#### S121

> The runtime reserve $M_{\mathrm{rt},i}$ is charged once in the requirement on the left-hand side.

**中文意思：** 运行时预留只在左侧需求中计一次。

**讲解 / 作用：** 额度已经排除了非服务占用，但未再次扣掉同一服务预留。

<a id="s122"></a>

#### S122

> The maximum checks every executed phase–length pair, while $U_i$ accounts for simultaneous workspace and temporary-buffer allocations rather than summing reusable buffers across layers.

**中文意思：** 最大值检查每个执行的阶段—长度组合；U_i 按同时分配的工作区和临时缓冲计费，不逐层累加可复用缓冲。

**讲解 / 作用：** 区分两种最大值：外层 max 检查不同形状，U_i 内部的峰值检查同一形状下同时存活的临时内存。状态容量另计，不能据此声称各项峰值必然同时发生。

<a id="s122a"></a>

#### S122a

> The state-memory term must cover the state allocations throughout the corresponding forward pass; adding this capacity requirement to the temporary-buffer peak gives a conservative bound when their peaks do not coincide.

**中文意思：** 状态内存项必须覆盖相应前向执行全过程的状态分配；若它与临时缓冲峰值不同步，将两者相加得到保守上界。

**讲解 / 作用：** 这是内存式保守解释成立的条件，不声称已测到这样的上界。S_ℓ(q) 需包含该形状下状态分配所需容量，U_i 不再重复计同一状态。可能高估需求、缩小准入空间，但不能凭这种保守性保证现实参数误差也被覆盖。

<a id="s123"></a>

#### S123

> Every execution length through the cap is checked unless monotonicity of the memory requirement has been established.

**中文意思：** 除非证明内存需求单调，否则检查到硬上限为止的每个执行长度。

**讲解 / 作用：** 不能仅凭 KV 增长就断言总峰值单调，工作区可能随形状变化。

<a id="section-124"></a>

## V 时延与增量能量模型

把需求转换成秒和焦耳，再汇总请求成本。

<a id="s124"></a>

#### S124

> Using the operator and storage requirements defined above, this section models computation and wireless communication separately and aggregates their costs over the request.

**中文意思：** 本节依据前面的需求，分别建模计算和无线通信，再汇总请求代价。

**讲解 / 作用：** IV 给需求，V 把需求变成秒和焦耳；不是重新定义分区。

<a id="s125"></a>

#### S125

> The resulting latency and per-device incremental energy determine the objective and energy constraints of the optimization problem.

**中文意思：** 得到的时延和各设备增量能量分别用于优化目标及能量约束。

**讲解 / 作用：** 最小化时延，不是最小化能量；能量是必须遵守的上限。

<a id="section-126"></a>

### V-A 计算时延与增量能量

组内 max、组间 sum；四项能量必须互不重复。

<a id="s126"></a>

#### S126

> For operator group $r$ in layer $\ell$ on device $i$, let $\rho_{i\ell r}^s$ denote the effective FLOP count per cycle of the GPU core clock and $\beta_{i\ell r}^s$ the effective memory bandwidth in bytes per second.

**中文意思：** 设备 i、层 ℓ、组 r 的 ρ 是每个 GPU 核心时钟周期的有效 FLOP 数；β 是有效字节每秒内存带宽。

**讲解 / 作用：** ρ 是整个所建模算子组的有效系数，不是某个单独计算核心的吞吐；不能在 ρf 上再额外乘一次核心数量。单位与原式相同。

<a id="s127"></a>

#### S127

> At frequency $f_i^s$, the effective compute throughput is $\rho_{i\ell r}^s f_i^s$ FLOP/s.

**中文意思：** 频率 f 下，有效计算吞吐为 ρf FLOP/s。

**讲解 / 作用：** 每周期操作数乘每秒周期数，单位变为每秒操作数。

<a id="s128"></a>

#### S128

> Both coefficients are positive and refer to the specified operator group and execution shape.

**中文意思：** 两个系数为正，并对应指定组和执行形状。

**讲解 / 作用：** 不能把某一种张量形状的有效系数无说明地套到另一形状。

<a id="s128a"></a>

#### S128a

> Their dependence on the execution shape is suppressed in the notation; for each fixed shape, both are treated as independent of the selected frequency within the declared operating bounds.

**中文意思：** 符号省略了系数对执行形状的依赖；给定形状后，在声明的频率范围内，将两系数视为不随所选频率变化。

**讲解 / 作用：** 这是有效计算模型的固定系数近似，不是真实硬件规律。允许不同 q 的系数不同；对固定 q，ρf 才是线性频率吞吐，D/β 才不随 f 变化。不会把厂家峰值自动当作应用系数。

<a id="s129"></a>

#### S129

> The bandwidth coefficient uses the same memory-transfer boundary as $D_{\ell r}^s$.

**中文意思：** 带宽系数与 D 使用同一传输边界。

**讲解 / 作用：** 这是需求和速度的接口一致性，保证 D/β 有意义。

<a id="s130"></a>

#### S130

> Let $\tau_{i\ell r}^s\geq0$ denote a fixed execution overhead in seconds.

**中文意思：** τ≥0 是该组固定执行开销，单位秒。

**讲解 / 作用：** 固定 launch 等时间不随计算量除以吞吐自动消失。

<a id="s131"></a>

#### S131

> The group's execution time is modeled as

**中文意思：** 该组执行时间用下式建模。

**讲解 / 作用：** E10 是声明的分析近似，不是未经说明的真实硬件计时结果。

<a id="e10"></a>

#### E10 · 对应原稿式 12 · 算子组瓶颈时延

$$
t_{i\ell r}^s=\max\left(\frac{F_{\ell r}^s}{\rho_{i\ell r}^sf_i^s},\frac{D_{\ell r}^s}{\beta_{i\ell r}^s}\right)+\tau_{i\ell r}^s
$$

**符号与单位：** ρf：FLOP/s；β：byte/s；τ：s；F、D 的 q 参数在原文中省略。

**为什么这样写：** 计算秒数 F/(ρf) 与访存秒数 D/β 取较大者，表示组内理想化重叠，再加固定开销。

**用途 / 条件 / 示例：** 跨组再求和。讲解例：两种时间为 3、5 ms，开销 1 ms，组时延为 6 ms，不是 9 ms。改变 f 对访存受限组可能无时延收益。

<a id="s132"></a>

#### S132

> where the length argument $q$ of the FLOP count and memory traffic is omitted for readability.

**中文意思：** 为了简洁，省略 F 和 D 的长度参数 q。

**讲解 / 作用：** 省略记号不等于不依赖长度；读每个 decode 步时应代入 P+t。

<a id="s133"></a>

#### S133

> The maximum models overlap between computation and memory transfers within an operator group, while distinct operator groups execute sequentially.

**中文意思：** max 表示组内计算与访存重叠，而不同组串行。

**讲解 / 作用：** 组内瓶颈取较慢一项；组间则累加，不能跨组抵消瓶颈。

<a id="s134"></a>

#### S134

> It does not introduce overlap between devices or between model execution and wireless communication.

**中文意思：** 这不引入设备间、或模型计算与无线通信之间的重叠。

**讲解 / 作用：** 区分不同层次的 overlap，避免与 III 的串行假设矛盾。

<a id="s135"></a>

#### S135

> Effective coefficients must be specified for the declared execution path using public information or explicit assumptions, rather than equating advertised peak values with application performance.

**中文意思：** 有效系数须匹配声明路径，以公开信息或明确假设规定，而非把广告峰值当应用性能。

**讲解 / 作用：** 这是参数依据要求，不暗示已经实测或完成校准。

<a id="s136"></a>

#### S136

> The incremental energy consumption of the same operator group is

**中文意思：** 同一算子组的增量能量如下。

**讲解 / 作用：** E11 将运算、搬运、残余活跃和启动能量分开。

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

<a id="s137"></a>

#### S137

> where $\kappa_{i\ell r}^s$ is the switching-energy coefficient in $\mathrm{J}/(\mathrm{FLOP}\cdot\mathrm{V}^2)$, $\epsilon_{i\ell r}^s$ is the memory-access energy per byte, $P_{\mathrm{act},i\ell r}^s$ is the residual active power in watts after excluding the switching and memory-access components, and $e_{\mathrm{launch},i\ell r}^s$ is the fixed launch energy in joules.

**中文意思：** κ 是每 FLOP 每电压平方的开关能耗系数；ε 是每字节访存能量；P_act 是排除前两项后的残余活跃功率；e_launch 是固定启动焦耳数。

**讲解 / 作用：** 残余功率不是整机或整个 GPU 总功率，否则再加开关和访存会重复计费。V 在单位中表示伏特。

<a id="s138"></a>

#### S138

> The voltage model is $V_i^s(f)=v_{0,i}^s+v_{1,i}^sf$, with nonnegative intercept $v_{0,i}^s$ and slope $v_{1,i}^s$, measured in volts and volts per hertz.

**中文意思：** 电压用仿射式 V(f)=v_0+v_1f 表示；非负截距单位 V，非负斜率单位 V/Hz。

**讲解 / 作用：** 斜率乘频率后才成为电压。这里的电压 V_i 与边界张量大小 V_ℓ 要按下标和上下文区分。

<a id="s139"></a>

#### S139

> For fixed operation counts, CMOS switching energy depends on the squared voltage [cite: chandrakasan1992lowpower]; the affine voltage model specifies its dependence on frequency.

**中文意思：** 固定操作数量时，CMOS 开关能量与电压平方相关；仿射电压式进一步建立与频率的关系。

**讲解 / 作用：** 不是直接套 CPU 每样本周期公式。频率改变电压，也改变时间。

<a id="s140"></a>

#### S140

> The four terms account for switching, memory access, residual active operation, and launch overhead, respectively.

**中文意思：** 四项依次表示开关、访存、残余活跃和启动开销。

**讲解 / 作用：** 理解每项的物理解释，比记住一长串下标更重要。

<a id="s141"></a>

#### S141

> The memory-access coefficient must use the same traffic definition as $D_{\ell r}^s$, and the four components must be parameterized without overlap.

**中文意思：** 访存系数须匹配 D 的定义，四项参数不能重复覆盖同一能量。

**讲解 / 作用：** “分别相加”成立的前提是核算项互不重叠，而不只是每项单位对。

<a id="s142"></a>

#### S142

> All energy coefficients and additive energy terms are nonnegative.

**中文意思：** 所有能耗系数和附加能量项非负。

**讲解 / 作用：** 这支撑后面的长度上限保证：额外 decode 步不能带来负能量。

<a id="s142a"></a>

#### S142a

> For a fixed operator group and execution shape, the energy coefficients are also treated as frequency independent; frequency dependence enters through the affine voltage model and the execution time.

**中文意思：** 给定算子组和执行形状后，能量系数也按不随频率变化处理；频率影响通过仿射电压模型和执行时间进入。

**讲解 / 作用：** 明确 κ、ε、P_act 和固定启动能量在频率优化中的口径。能量仍随 f 变化，只是变化由原式中电压平方和 t(f) 两条路径表达。这是分析假设，不是已验证的硬件拟合结论。

<a id="s143"></a>

#### S143

> Equations 12 and 13 also apply to operators outside the decoder layers by replacing $(\ell,r)$ with $o$.

**中文意思：** 把层内索引 (ℓ,r) 换为统一算子索引 o，这两式也用于层外算子。

**讲解 / 作用：** 输入嵌入和输出头通过相同代价接口纳入，不另造不一致总和。

<a id="s144"></a>

#### S144

> Each coefficient must have a stated source, derivation, or simulation assumption.

**中文意思：** 每个系数必须说明来源、推导或模拟假设。

**讲解 / 作用：** must 是规范要求，不等于来源表已经全部完成。

<a id="s145"></a>

#### S145

> If a voltage model is fitted, its approximation error must be reported over the specified operating levels; assumed coefficients require explicit uncertainty ranges.

**中文意思：** 若拟合电压模型，应报告工作等级内误差；假设系数应给出明确不确定范围。

**讲解 / 作用：** 条件句不宣称已有拟合结果，本讲解也不替作者虚构误差值。

<a id="s146"></a>

#### S146

> Rated device power alone does not determine operator-level energy coefficients.

**中文意思：** 仅靠设备额定功率无法确定算子级能耗系数。

**讲解 / 作用：** 额定 W 不能唯一反推出每 FLOP 的 κ 和每 byte 的 ε。

<a id="s147"></a>

#### S147

> A non-affine voltage table can be evaluated on the finite resource grid, but the continuous convexity result in Section VII requires the stated affine model.

**中文意思：** 非仿射电压表可用于有限网格评价，但后面的连续凸性结论要求当前仿射模型。

**讲解 / 作用：** 离散枚举能处理表格，不意味着同一个连续证明仍适用。

<a id="s148"></a>

#### S148

> Prior DVFS studies motivate frequency control without providing directly transferable coefficients for different hardware [cite: zhang2023dvfo].

**中文意思：** 已有 DVFS 研究支持频率控制的动机，但不能直接提供可跨硬件搬用的系数。

**讲解 / 作用：** 引用方法思想与转移数值参数是两件事。DVFS 指动态电压与频率调节。

<a id="s149"></a>

#### S149

> Let $E_{\mathrm{ctrl},i}\geq0$ denote a specified per-request control-energy reserve on device $i$ for prediction, optimization, synchronization, and phase transitions.

**中文意思：** E_ctrl,i≥0 是设备 i 为每次请求的预测、优化、同步和阶段切换规定的控制能量预留。

**讲解 / 作用：** 本轮将含糊的“控制能量”明确为保守预留，按控制操作的声明执行位置分配到各设备；不是假定每台设备都运行预测器。此项计入同一增量能量预算。

<a id="s150"></a>

#### S150

> The reserve is assumed to cover these operations uniformly over the permitted prompt domain and legal resource configurations, independently of the predicted and realized output lengths.

**中文意思：** 假定该预留覆盖允许输入域和合法配置中的这些控制操作，并且不依赖预测或实际输出长度。

**讲解 / 作用：** 这是本轮明确加入的统一上界假设，必须以参数来源或明确假设支持，不能当作已完成测量。它使固定 P,c 下的准入集合不因 G_hat 改变，也让不同停止长度共享同一固定控制项。若现实控制消耗超过预留，模型保证就不能直接作为现实保证。

<a id="s151"></a>

#### S151

> Both the executable policy and the continuous reference charge this same reserve; any transition-dependent accounting requires a bound that preserves the stated admission guarantee.

**中文意思：** 可执行策略与连续参考计入同一个预留；若使用依赖切换配置的核算方式，必须有保持既定准入保证的界。

**讲解 / 作用：** 本文主模型统一使用预留，避免有限策略与连续参考采用不同约束口径。配置相关切换能量只有被统一预留覆盖时，才不破坏所述保证；不在这里实施或修改实验核算。

<a id="s152"></a>

#### S152

> A lower-bound comparison using different control-energy accounting requires the feasible-set inclusion condition stated in Section VII.

**中文意思：** 如果比较双方采用不同控制能量核算，连续参考作为下界还需满足解法章节所述可行集合包含条件。

**讲解 / 作用：** 控制开销核算不同，不能仅因变量连续就宣称最优值是下界；必须检查有限合法可行点是否包含在所比较的连续可行集合中。这里只说明适用条件，不展开求解方法。

<a id="section-153"></a>

### V-B 无线时延与增量能量

两跳经 AP、分帧与 ACK、设备收发能量和消息枚举。

<a id="s153"></a>

#### S153

> Let $R_i(p)$ denote the modeled transmission rate, in bits per second, on the link between device $i$ and the AP at radio-frequency output power $p$ watts.

**中文意思：** R_i(p) 是设备 i 与 AP 链路在射频输出功率 p W 下的模型速率，单位 bit/s。

**讲解 / 作用：** p 不是完整设备耗电功率。上行和下行在本文使用对应有效链路函数。

<a id="s154"></a>

#### S154

> Let $B>0$ be the channel bandwidth in hertz, $\xi>0$ a dimensionless effective-rate factor, $\gamma_i>0$ the effective channel gain-to-noise ratio per watt, and $R_{\max}>0$ the rate ceiling in bits per second.

**中文意思：** B 为信道带宽 Hz；ξ 为正的无量纲有效速率因子；γ_i 为每瓦有效增益噪声比；R_max 为速率上限 bit/s。

**讲解 / 作用：** 保留 ξ>0 的原域，改称 effective-rate factor，避免称“效率”却未规定不超过 1 的歧义。没有把 ξ 的范围缩小，也没有改变速率公式或系数值。γp 必须无量纲。

<a id="s155"></a>

#### S155

> The rate model is

**中文意思：** 速率模型如下。

**讲解 / 作用：** E12 同时体现随功率增长和饱和上限。

<a id="e12"></a>

#### E12 · 对应原稿式 14 · 功率到无线速率

$$
R_i(p)=\min\{R_{\max},\xi B\log_2(1+\gamma_i p)\}
$$

**符号与单位：** p：射频 W；γ：W⁻¹；B：Hz；ξ：无量纲；R：bit/s。

**为什么这样写：** γp 是线性信噪比；对数体现边际收益递减；min 加入速率上限。

**用途 / 条件 / 示例：** 给出两跳中的各链路速度。饱和后继续增 p 不加快速率，却仍可能增加功放能量。这是有效速率近似，不是物理验证。

<a id="s156"></a>

#### S156

> which uses the logarithmic signal-to-noise relationship of a wireless link [cite: tse2005wireless].

**中文意思：** 该式采用无线速率与信噪比的对数关系。

**讲解 / 作用：** 是建模依据，不是说家用 Wi-Fi 实测等于 Shannon 容量。

<a id="s157"></a>

#### S157

> The effective-rate factor and rate ceiling specify a link-rate approximation; framing and protocol overheads are accounted for separately below.

**中文意思：** 有效速率因子和速率上限构成链路速率近似；成帧和协议开销在下文另计。

**讲解 / 作用：** ξ 不能无说明地包含随后 H、C、t_0 再次计入的协议开销，否则重复计算。这里仍是链路模型，而不是两跳载荷 goodput。

<a id="s158"></a>

#### S158

> Let $p_{\mathrm{ref}}>0$ denote a reference transmit power and $\mathrm{SNR}_{\mathrm{ref},i}$ the corresponding signal-to-noise ratio in decibels.

**中文意思：** p_ref 是正参考发射功率，SNR_ref,i 是对应 dB 信噪比。

**讲解 / 作用：** dB 是对数单位，不能直接当线性 γp 代入。

<a id="s159"></a>

#### S159

> Then $\gamma_i=10^{\mathrm{SNR}_{\mathrm{ref},i}/10}/p_{\mathrm{ref}}$.

**中文意思：** 因此 γ_i 等于 10 的 SNR_dB/10 次方，再除以参考功率。

**讲解 / 作用：** 先把 dB 转成线性比值，再按功率归一化，得到每瓦系数。

<a id="s160"></a>

#### S160

> The nominal model assumes reciprocal effective client-AP link coefficients, so the fixed-power AP downlink to device $j\in\mathcal{N}$ has rate $R_j(p_{\mathrm{AP}})$.

**中文意思：** 标称模型假设客户端与 AP 的有效链路系数互易，所以到设备 j 的下行速率为 R_j(p_AP)。

**讲解 / 作用：** 互易是声明假设；下行由固定 AP 功率决定，不由发送设备 i 的功率决定。

<a id="s161"></a>

#### S161

> Consider a message from device $i$ to device $j$ with payload size $S$ bits.

**中文意思：** 考虑设备 i 发给 j 的消息，有效载荷 S bit。

**讲解 / 作用：** S 是这条消息的位数，不是层状态字节量 S_ℓ(q)。看下标区分。

<a id="s162"></a>

#### S162

> It traverses two sequential hops, from the source to the AP and from the AP to the destination.

**中文意思：** 消息依次经过源→AP、AP→目的两跳。

**讲解 / 作用：** 必须把两跳时间都加上，而不是只计算客户端上行。

<a id="s163"></a>

#### S163

> Let $L_{\mathrm{pay}}>0$ denote the maximum payload bits per frame, $H\geq0$ the per-frame header and padding bits, and $C(S)\geq0$ the same-direction control bits.

**中文意思：** L_pay 是每帧最大载荷 bit，H 是每帧头部和填充 bit，C(S) 是同方向控制 bit，均按声明条件取值。

**讲解 / 作用：** 分帧头开销乘帧数；C 的具体形式仍需给定，不由这一式自动决定。

<a id="s164"></a>

#### S164

> The number of frames $n(S)$ and the total transmitted data-direction bits $S_{\mathrm{air}}(S)$ are

**中文意思：** 帧数 n(S) 和数据方向总空口位数 S_air(S) 如下。

**讲解 / 作用：** E13 把有效载荷转为实际需发送的位数。

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

<a id="s165"></a>

#### S165

> where $\lceil\cdot\rceil$ denotes rounding upward to an integer.

**中文意思：** 上取整符号表示向上取最近整数。

**讲解 / 作用：** 不足一整帧的最后一部分也需要一帧，不能用小数帧数计头部开销。

<a id="s166"></a>

#### S166

> Reverse-direction acknowledgment (ACK) bits are excluded from $S_{\mathrm{air}}$.

**中文意思：** 反方向 ACK 位不包含在 S_air 中。

**讲解 / 作用：** 并非不计 ACK：其时间进 t_0、能量进固定帧项，避免在两处重复算。

<a id="s167"></a>

#### S167

> With the same aggregate frame format on both hops, the message delay is

**中文意思：** 两跳采用同样汇总帧格式时，消息时延如下。

**讲解 / 作用：** 这是 E14 的适用条件。若两跳帧格式不同，不能不改参数就复用同一 S_air。

<a id="e14"></a>

#### E14 · 对应原稿式 16 · 经 AP 的两跳消息时延

$$
h_{ij}(S,p_i)=\frac{S_{\mathrm{air}}(S)}{R_i(p_i)}+\frac{S_{\mathrm{air}}(S)}{R_j(p_{\mathrm{AP}})}+n(S)t_0
$$

**符号与单位：** 首项源上行，第二项 AP 下行，末项两跳合并每帧协议开销；单位均 s。

**为什么这样写：** 两跳串行，所以相加。设备 i 的可变功率只影响上行；下行由目的 j 的链路及固定 AP 功率决定。

**用途 / 条件 / 示例：** 每条消息进入总时延一次。t_0 已包括声明的反向回复时间，但不再包含这两项数据空口时间。

<a id="s168"></a>

#### S168

> where $h_{ij}$ is measured in seconds and $p_i$ is the source's transmit power for the applicable phase.

**中文意思：** h_ij 单位秒，p_i 是源设备在该阶段的发射功率。

**讲解 / 作用：** 消息方向和阶段决定从 z 中取哪一个 p_i^s。

<a id="s169"></a>

#### S169

> The nonnegative constant $t_0$ is the combined per-frame protocol time across the two hops, including interframe intervals and reverse ACK airtime at fixed reply rates and powers.

**中文意思：** 非负 t_0 是两跳合并的每帧协议时间，包括帧间间隔和固定回复速率/功率下的反向 ACK 时间。

**讲解 / 作用：** 它是每帧开销，不是整条消息总开销，所以乘 n(S)。

<a id="s170"></a>

#### S170

> It excludes the data airtime already represented by the first two terms.

**中文意思：** t_0 不含前两项已经计入的数据传输时间。

**讲解 / 作用：** 否则发送同一数据的时间会重复累加。

<a id="s171"></a>

#### S171

> Hop-specific framing, asymmetric links, or variable reply controls require separate parameters.

**中文意思：** 不同跳分帧、非对称链路或可变回复控制需要单独参数。

**讲解 / 作用：** 当前公式不自动覆盖这些拓展；不要在理解时偷偷引入额外决策。

<a id="s172"></a>

#### S172

> The payload goodput is $S/h_{ij}$, which differs from the link rate because the delay includes both hops and protocol overheads.

**中文意思：** 有效载荷吞吐为 S/h_ij，因包含两跳与开销而不同于链路速率。

**讲解 / 作用：** R 是单链路模型速率；goodput 是最终有效载荷除以完整消息时间。

<a id="s173"></a>

#### S173

> The transmitting and receiving devices consume

**中文意思：** 发送设备和接收设备的能量由下两式给出。

**讲解 / 作用：** E15 的两行针对不同参与设备；AP 能量不在当前预算内。

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

<a id="s174"></a>

#### S174

> respectively, in joules.

**中文意思：** 两式分别以焦耳计。

**讲解 / 作用：** respectively 对应发送与接收的顺序；这是公式后的单位说明片段。

<a id="s175"></a>

#### S175

> Here $0<\eta_i\leq1$ is the source power-amplifier efficiency, $P_{\mathrm{tx,c},i}$ the incremental transmit-circuit power, and $P_{\mathrm{rx},j}$ the incremental receive-circuit power.

**中文意思：** η 是 0 到 1 的功放效率；P_tx,c 是增量发送电路功率；P_rx 是增量接收电路功率。

**讲解 / 作用：** 射频输出 p 需要耗电 p/η，再加电路功率；η 越低，同样 p 的输入耗电越大。

<a id="s176"></a>

#### S176

> The per-frame energies $\chi_{\mathrm{tx},i}$ and $\chi_{\mathrm{rx},j}$ include host and network-interface processing and the participant's fixed ACK-related energy.

**中文意思：** 每帧 χ_tx、χ_rx 包括主机/网卡处理及参与设备固定 ACK 相关能量。

**讲解 / 作用：** 这些项按帧数累加，不按载荷字节数直接累加。

<a id="s177"></a>

#### S177

> The per-message terms $e_{\mathrm{tail},i}$ and $e_{\mathrm{wake},j}$ represent the transmit-tail and receiver-wake energies.

**中文意思：** 每消息的 e_tail、e_wake 表示发送尾态和接收唤醒能量。

**讲解 / 作用：** 是状态相关固定开销，不是数据发送功率乘空口时间的重复项。

<a id="s178"></a>

#### S178

> The incremental radio circuit powers and the per-frame and per-message energy terms are nonnegative.

**中文意思：** 增量无线电路功率、每帧和每消息能量非负。

**讲解 / 作用：** 再次给出能量单调论证的组成条件，不允许人为用负项抵消预算。

<a id="s179"></a>

#### S179

> The model assigns one tail and wake charge to each directed message; it does not infer these charges from a physical radio-state trace.

**中文意思：** 模型为每条有向消息计一次尾态和唤醒，不声称由真实无线状态轨迹推断。

**讲解 / 作用：** 这是会计假设。真实状态可能跨多条消息持续，当前讲解不把该模型写成硬件测量。

<a id="s180"></a>

#### S180

> Reverse ACK energy is included in the fixed frame terms rather than in data-direction amplifier energy.

**中文意思：** 反向 ACK 能量包含于固定帧项，而非数据方向的功放能量。

**讲解 / 作用：** ACK 与主数据方向相反，不能不区分地都乘源设备可变功率。

<a id="s181"></a>

#### S181

> Published Wi-Fi measurements motivate the separate airtime, frame-processing, and state-transition components [cite: garcia2012wifi,xiao2014wifi].

**中文意思：** 已有 Wi-Fi 测量文献支持分开考虑空口、帧处理和状态转换的动机。

**讲解 / 作用：** 文献支持组成结构，不意味着本文设备系数已经由这些文献直接确定。

<a id="s182"></a>

#### S182

> Reducing transmit power can increase airtime and therefore does not necessarily reduce transmit energy.

**中文意思：** 降低发射功率可能延长空口时间，因此并不必然降低发送能量。

**讲解 / 作用：** 修正原英语的方向歧义，没有改变能量式。发送电路功率乘以空口时间；省下的射频功率可能被更长的持续耗能抵消。

<a id="s183"></a>

#### S183

> For the boundary after layer $c_i$, the prefill activation payload is $8V_{c_i}^{\mathrm{pre}}(P)$ bits, and the payload at decode step $t$ is $8V_{c_i}^{\mathrm{dec}}(P+t)$ bits.

**中文意思：** c_i 层后边界的 prefill 载荷为 8V^pre(P) bit，decode 第 t 步为 8V^dec(P+t) bit。

**讲解 / 作用：** V 定义用 byte，通信模型用 bit，因此必须乘 8。

<a id="s184"></a>

#### S184

> A single bfloat16 (BF16) activation of hidden width $d$ occupies $16Pd$ bits in prefill and $16d$ bits in decode.

**中文意思：** 隐藏宽度 d 的单个 BF16 激活，prefill 为 16Pd bit，单步 decode 为 16d bit。

**讲解 / 作用：** 每元素 16 bit；prefill 有 P 个位置，decode 一个新位置。仅适用于所述单张量结构。

<a id="s185"></a>

#### S185

> Additional boundary tensors are included if required by the specified model execution path.

**中文意思：** 若执行路径需要其他边界张量，也必须计入。

**讲解 / 作用：** 不能把 16Pd 或 16d 当成任意运行路径的全部载荷。

<a id="s186"></a>

#### S186

> To enumerate all communication events, represent a directed message by $m=(a_m,b_m,s_m,q_m,S_m)$, where $a_m$ and $b_m$ are its source and destination device indices, $s_m$ its phase, $q_m$ its execution length, and $S_m$ its payload size in bits.

**中文意思：** 有向消息 m 用五元组记录源 a、目的 b、阶段 s、执行长度 q 和载荷 S bit。

**讲解 / 作用：** m 是消息条目，不是 FFN 维度。五项让后续公式能找到消息的方向、控制和大小。

<a id="s187"></a>

#### S187

> The message multiset $\mathcal{M}(P,G)$ retains one entry for each transmitted message; its dependence on $\mathbf{c}$ is suppressed for brevity in the following definition:

**中文意思：** 消息多重集合 M(P,G) 为每次传输保留一个条目；下式为简洁省略它对分区 c 的依赖。

**讲解 / 作用：** M(P,G) 不是与分区无关：边界载荷仍由 c_i 决定。保持原消息集合公式，避免外层换分区时被误读为消息内容固定。多重集合不能去重后少计成本。

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

<a id="s188"></a>

#### S188

> where $S_{\mathrm{tok}}$ is the number of bits used for the token identifier and its control metadata.

**中文意思：** S_tok 是 token 编号及控制元数据的位数。

**讲解 / 作用：** 反馈的是编号等少量信息，不是完整词表 logits 或 KV 状态。

<a id="s189"></a>

#### S189

> The feedback entry indexed by $t$ is the message needed to initiate decode step $t$; its phase label therefore refers to the receiving decode step.

**中文意思：** 第 t 条反馈用于启动第 t 个 decode 步，阶段标签按接收后要执行的 decode 归类。

**讲解 / 作用：** 第一条反馈在 prefill 产生 token 后发生，但本文仍用 decode 功率计费，这是明确的标签约定。

<a id="s190"></a>

#### S190

> For each $m\in\mathcal{M}(P,G)$, define its delay $h_m$ as

**中文意思：** 对多重集合中的每条消息，定义其时延 h_m。

**讲解 / 作用：** E17 把五元组映射到前面通用两跳公式。

<a id="e17"></a>

#### E17 · 对应原稿式 20 · 消息记录调用通用延迟式

$$
h_m(\mathbf{z})=h_{a_mb_m}(S_m,p_{a_m}^{s_m})
$$

**符号与单位：** a_m、b_m 给出方向；S_m 给出载荷；s_m 选择发送者在 z 中对应阶段功率。

**为什么这样写：** 只是把消息五元组逐项送入两跳公式，不增加新通信路径。

**用途 / 条件 / 示例：** 总时延对所有消息 h_m 求和。

<a id="s191"></a>

#### S191

> The transmit and receive message multisets of device $i$ are $\mathcal{M}_i^{\mathrm{tx}}=\{m\in\mathcal{M}:a_m=i\}$ and $\mathcal{M}_i^{\mathrm{rx}}=\{m\in\mathcal{M}:b_m=i\}$.

**中文意思：** 设备 i 的发送集合筛出源为 i 的消息，接收集合筛出目的为 i 的消息。

**讲解 / 作用：** 同一消息会进入源设备发送能量和目的设备接收能量，但端到端时延只计一次。

<a id="s192"></a>

#### S192

> For these messages, $e_{\mathrm{tx},i,m}=e_{\mathrm{tx},i}(S_m,p_i^{s_m})$ and $e_{\mathrm{rx},i,m}=e_{\mathrm{rx},i}(S_m)$ denote the corresponding energies from 17 and 18.

**中文意思：** 按消息载荷和所属阶段功率代入通用收发式，得到设备-消息能量 e_tx,i,m 与 e_rx,i,m。

**讲解 / 作用：** 接收式不含源设备可变功率，因为 AP 下行功率固定；发送式则读取自己的 p。

<a id="s193"></a>

#### S193

> Device $N$ has a decode transmit-power variable for feedback and no prefill transmit-power variable, consistent with the sender sets defined in Section III.

**中文意思：** 末设备有反馈用 decode 发射功率，没有 prefill 发射功率，与 III 发送者集合一致。

**讲解 / 作用：** 检查变量数量与消息事件是否对应，避免无发送变量或漏掉反馈能量。

<a id="section-194"></a>

### V-C 请求总时延和设备能量

时延跨设备求和，能量逐设备约束；端点和控制时间范围要明确。

<a id="s194"></a>

#### S194

> For an executed phase-length pair $(s,q)\in\mathcal{Q}(P,G)$, let $T_i^s(\mathbf{c},f_i^s;q)$ denote device $i$'s computation latency and $E_{\mathrm{comp},i}^s(\mathbf{c},f_i^s;q)$ its incremental computation and memory-access energy.

**中文意思：** 对执行形状 (s,q)，T_i^s 为设备计算时延，E_comp,i^s 为计算和访存的增量能量。

**讲解 / 作用：** comp 不是仅指算术开关项，它汇总该组计算模型中的多项能量；无线另算。

<a id="s195"></a>

#### S195

> Summing over its sequential operator groups gives

**中文意思：** 对该设备串行算子组求和，得到下式。

**讲解 / 作用：** E18 是从组级代价到设备级代价的汇总接口。

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

<a id="s196"></a>

#### S196

> Let $T(\mathbf{c},\mathbf{z};P,G)$ denote the total inference latency of a request.

**中文意思：** T(c,z;P,G) 是请求的总推理时延。

**讲解 / 作用：** 分区 c 和资源 z 都会影响它；P、G 给出要执行多少计算和消息。

<a id="s197"></a>

#### S197

> It comprises one prefill pass, all decode passes, and their communication delays:

**中文意思：** 它包括一次 prefill、所有 decode 及对应通信时延。

**讲解 / 作用：** E19 把三类时间合成总目标，不能漏掉 AP 两跳或反馈。

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

<a id="s198"></a>

#### S198

> where computation and communication times are added because execution is sequential and no cross-device overlap is modeled.

**中文意思：** 由于串行且不考虑跨设备重叠，计算和通信时间直接相加。

**讲解 / 作用：** 若将来改为流水线，这个总和形式不能不加修改地使用。

<a id="s199"></a>

#### S199

> The corresponding incremental request energy on device $i$ is

**中文意思：** 设备 i 对应的请求增量能量如下。

**讲解 / 作用：** E20 是设备本地预算左侧，不是所有设备能量的总和。

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

<a id="s200"></a>

#### S200

> This quantity is evaluated at $G={G_{\mathrm{cap}}}$ for admission and at the realized $G$ for request-level evaluation.

**中文意思：** 准入时以 G_cap 核算，事后请求评价以真实 G 核算。

**讲解 / 作用：** 同一个函数两种用途：安全可行性看上限，实际长度成本看停止时刻。

<a id="s201"></a>

#### S201

> The latency interval begins with prefill on device 1 and ends when the final output token is ready on device $N$.

**中文意思：** 时延从设备 1 开始 prefill，到设备 N 最后输出 token 就绪为止。

**讲解 / 作用：** 这是 T 的精确服务端点，不是从用户按发送到屏幕完整显示的全过程。

<a id="s202"></a>

#### S202

> Delivery to a user-facing client lies outside this interval.

**中文意思：** 向用户客户端交付不在该区间内。

**讲解 / 作用：** 不能把 T 与包含网络回传和显示的用户感知响应时间无条件等同。

<a id="s203"></a>

#### S203

> Prediction and optimization times are reported separately and enter response-time totals only when their execution location and timing are explicitly specified.

**中文意思：** 预测与优化用时单列，只有明确执行位置和时序后才加入响应时间总量。

**讲解 / 作用：** 能量模型含控制项，并不自动意味着 T 已含控制时间；两种会计边界需分别读。

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

<a id="section-205"></a>

## VI 优化问题表述

先准入，再定义主有限策略和辅助连续参考，最后历史评分选分区。

<a id="s205"></a>

#### S205

> The objective is to minimize inference latency under each device's memory and incremental-energy budgets.

**中文意思：** 目标是在每台设备内存及增量能量预算下最小化推理时延。

**讲解 / 作用：** 约束是逐设备预算，不能把一台设备富余能量直接借给另一台；也不是能量-时延加权目标。

<a id="s206"></a>

#### S206

> The deployment decision selects one partition for multiple requests; the request-level decision selects phase-specific frequencies and transmit powers from arrival-time information.

**中文意思：** 部署为多个请求选一个分区，请求级则用到达信息选两阶段频率和发射功率。

**讲解 / 作用：** 分区跨请求保持不变，资源向量依据当前请求的到达信息选择。评价一个分区时，必须考虑该分区对应的资源选择行为，而不能只比较层数；本句定义决策关系，不是在介绍求解算法。

<a id="s207"></a>

#### S207

> We first define cap-based admission, then the finite-grid request-level policy, and finally the deployment objective that evaluates each partition through that policy.

**中文意思：** 依次定义基于上限的准入、有限网格请求策略和经由该策略评价分区的部署目标。

**讲解 / 作用：** 这是 VI 的阅读地图；连续参考是辅助，不是实际主策略。

<a id="s208"></a>

#### S208

> Changing a partition reallocates the FLOP counts, weight storage, and inference-state memory among devices.

**中文意思：** 改变分区会在设备之间重新分配计算量、权重和状态存储。

**讲解 / 作用：** 即使总层数不变，每台设备预算占用也会变，因此好分区不是只看层数均衡。

<a id="s209"></a>

#### S209

> It also changes the energy remaining for communication after computation and control, and may change the activation payload at a boundary.

**中文意思：** 分区还会改变计算和控制之后可供通信使用的剩余能量，并可能改变边界激活载荷。

**讲解 / 作用：** 变化的是预算的使用分配，不是给定预算 E_bar 本身；若所有边界宽度相同，仍可能通过计算能量改变可选发射功率。

<a id="s210"></a>

#### S210

> Even if all boundary activations have the same width, computation and transmission share each device's request-level energy budget, and prefill and decode share that same budget.

**中文意思：** 即使各边界激活同宽，计算与发送、prefill 与 decode 仍共用设备的请求级预算。

**讲解 / 作用：** 因此通信载荷相同不意味着分区与资源无关；共享能量约束就是耦合渠道。

<a id="s211"></a>

#### S211

> The resource vector selected by 25 therefore depends on the partition.

**中文意思：** 该策略选择的资源向量因此以分区为条件。

**讲解 / 作用：** 这是依赖关系，不是说任意微小切点变化都一定让最优资源数值改变。

<a id="s212"></a>

#### S212

> A deployment partition must be evaluated through the causal policy it induces.

**中文意思：** 部署分区应通过其诱导的因果在线策略来评价。

**讲解 / 作用：** 不能用事后已知真实 G 的理想配置来给在线分区打分。

<a id="s213"></a>

#### S213

> This dependence is compatible with the fixed-partition device-wise decomposition established in Section VII.

**中文意思：** 这种依赖与后文固定分区下按设备分解并不矛盾。

**讲解 / 作用：** 外层分区与内层策略耦合，不等于固定分区后所有设备的资源变量还必须互相耦合。

<a id="section-214"></a>

### VI-A 请求准入与可行性

合法等级不等于预算可行；可行集合不能依赖预测长度。

<a id="s214"></a>

#### S214

> Let $P_{\min}$ and $P_{\max}$ be integers with $1\leq P_{\min}\leq P_{\max}$ denoting the minimum and maximum permitted prompt lengths, and let $\mathcal{P}=[P_{\min},P_{\max}]\cap\mathbb{Z}$ be the admissible prompt-length set, where $\mathbb{Z}$ denotes the integers.

**中文意思：** P_min 和 P_max 是满足 1≤P_min≤P_max 的整数输入长度界；花体 P 是该区间内的整数集合。

**讲解 / 作用：** 补出计数域和界的顺序，不填实际长度数值。输入域合法是准入必要条件，不代表能源或内存可行。

<a id="s214a"></a>

#### S214a

> The prompt range is chosen so that every pair in $\mathcal{Q}(P,{G_{\mathrm{cap}}})$ is supported by the specified model and runtime for all $P\in\mathcal{P}$.

**中文意思：** 选择输入范围时，要保证每个允许 P 对应的 Q(P,G_cap) 中所有阶段—长度组合均被指定模型和运行时支持。

**讲解 / 作用：** 最晚的前向长度是 P+G_cap−1；最后输出 token 不再被前向消费。若存在最大支持长度 q_max，应满足 P_max+G_cap−1≤q_max；这里只解释条件，不新增一个未经确认的 q_max 数值，也不假定内存足够就代表模型支持。

<a id="s215"></a>

#### S215

> Let $\mathcal{Z}_{\mathrm{legal}}$ denote the finite set of valid frequency and transmit-power vectors for the specified devices.

**中文意思：** Z_legal 是各设备允许的有限频率/功率配置向量集合。

**讲解 / 作用：** legal 表示等级合法，不表示一定满足请求能量或内存预算。

<a id="s216"></a>

#### S216

> Resource levels are identified as supported hardware values or simulation assumptions.

**中文意思：** 资源等级须区分硬件支持值和模拟假设。

**讲解 / 作用：** 再次明确配置来源，不把假设等级说成已经能在实物上执行。

<a id="s216a"></a>

#### S216a

> The legal operating levels are specified independently for each device, without cross-device restrictions on their selection.

**中文意思：** 每台设备的合法工作等级独立规定，不对不同设备的等级选择施加跨设备限制。

**讲解 / 作用：** 这是明确的模型设定，使合法向量由各设备合法配置组合得到。设备内部的两阶段预算仍耦合；AP 功率固定、串行通信也保持不变。并非声称所有现实硬件或协议天然满足这种独立性。

<a id="s217"></a>

#### S217

> For partition $\mathbf{c}$ and prompt length $P$, the feasible resource set is

**中文意思：** 给定分区 c 与输入长度 P，可行资源集合如下。

**讲解 / 作用：** E21 在合法等级中再筛选满足设备预算的点。

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

<a id="s218"></a>

#### S218

> With both constraints evaluated at the enforced output cap and the control-energy reserve independent of the prediction, the feasible set depends on $P$ and $\mathbf{c}$, but not on the output-length prediction.

**中文意思：** 两约束在强制生成上限检查，且控制预留不依赖预测，因此可行集合依赖 P 和 c，而不依赖预测输出长度。

**讲解 / 作用：** 把原来省略的控制能量条件写出来。G_hat 改变可行点的目标排名，不放宽准入预算；这个结论仅适用于本文规定的固定预留口径。

<a id="s219"></a>

#### S219

> A request is admitted if and only if $P\in\mathcal{P}$ and $\mathcal{Z}(\mathbf{c},P)\neq\varnothing$.

**中文意思：** 当且仅当 P 在允许范围内且可行资源集合非空时准入。

**讲解 / 作用：** if and only if 是充要条件；至少存在一个合法可行配置才可开始。

<a id="s220"></a>

#### S220

> Otherwise, it is rejected before model execution and the failed feasibility test is recorded.

**中文意思：** 否则执行前拒绝，并记录可行性检查失败。

**讲解 / 作用：** 拒绝不等于软件求解失败；后者可能只是没找到或来不及找到配置。

<a id="s221"></a>

#### S221

> The runtime enforces max_new_tokens$={G_{\mathrm{cap}}}$; any continuation requires a separate admission decision.

**中文意思：** 运行时强制 max_new_tokens=G_cap；继续生成需另一次准入。

**讲解 / 作用：** 否则超出上限后，前面的能量和内存保证不再覆盖延长部分。

<a id="s222"></a>

#### S222

> The prompt domain and generation cap specify the permitted workload, while admission additionally requires a feasible resource vector.

**中文意思：** 输入域和生成上限定义服务允许负载，准入还需可行资源。

**讲解 / 作用：** 请求形式合法不代表设备一定承受得住。

<a id="s223"></a>

#### S223

> Memory feasibility uses the complete set of execution lengths defined in 10.

**中文意思：** 内存检查使用前面定义的完整执行长度集合。

**讲解 / 作用：** 不能只查最后 decode 长度而漏掉可能更大的 prefill 工作区。

<a id="section-224"></a>

### VI-B 请求资源分配

预测影响目标，硬上限保护模型预算；理解命题前提及连续参考地位。

<a id="s224"></a>

#### S224

> For an admitted request and a fixed partition, the resource objective evaluates latency at the predicted output length $\widehat{G}$, while the constraints evaluate energy and memory at ${G_{\mathrm{cap}}}$.

**中文意思：** 固定分区的已准入请求，以预测长度计算目标时延，以硬上限计算能量和内存约束。

**讲解 / 作用：** 这是模型最重要的信息分工。它优化的是预测时延代理，不保证事后实际长度下最优。

<a id="s225"></a>

#### S225

> The executable policy, denoted by $\mathcal{A}$, selects a valid frequency and transmit-power vector from the finite feasible set:

**中文意思：** 可执行策略 A 从有限可行集合中选择合法频率和功率向量。

**讲解 / 作用：** E22 的 argmin 返回配置，不是返回最小的时延数值。

<a id="e22"></a>

#### E22 · 对应原稿式 25 · 主要有限网格策略

$$
\mathcal{A}(\mathbf{c},P,\widehat{G})\in\mathrm{argmin}_{\mathbf{z}\in\mathcal{Z}(\mathbf{c},P)}T(\mathbf{c},\mathbf{z};P,\widehat{G})
$$

**符号与单位：** argmin 返回使目标最小的配置集合；A 按正文破平局规则选其中一个；min 则只返回最小值。

**为什么这样写：** 约束已藏在 Z 中，所以这并不是无约束问题。预测进入目标，硬上限进入 Z。

**用途 / 条件 / 示例：** 外层对每个 c、请求 r 调用同一个 A；不把真实 G_r 交给它。并列时先最低上限总能量，再字典序。

<a id="s226"></a>

#### S226

> If the feasible set is empty, the policy returns a rejection; computational failures and timeouts are recorded separately.

**中文意思：** 可行集为空返回拒绝；计算失败与超时另记。

**讲解 / 作用：** 数学不可行和求解器没完成不能混为一类。

<a id="s227"></a>

#### S227

> Among objective minimizers, it selects the one with the lowest total energy evaluated at the cap, followed by the lexicographically smallest resource vector.

**中文意思：** 时延最优点并列时，先选上限下总能量最低者，再选字典序最小向量。

**讲解 / 作用：** 这是确定性破平局规则，能量不是主要目标；字典序是按固定变量顺序逐个比较。

<a id="s228"></a>

#### S228

> Decode variables remain in the cap constraints and tie rule even when $\widehat{G}=1$.

**中文意思：** 即使预测只生成一个 token，decode 变量仍参与上限约束及破平局。

**讲解 / 作用：** 预测可能低估，所以不能删除实际可能使用的 decode 资源和预算要求。

<a id="s229"></a>

#### S229

> Section VII develops the solution method.

**中文意思：** 解法在后面的章节展开。

**讲解 / 作用：** 这里只定义策略要返回什么，不讲解范围外的算法细节。

<a id="s230"></a>

#### S230

> For a fixed partition and realized request, output-length prediction can affect modeled inference latency only through changes in the selected resources.

**中文意思：** 对固定分区和真实请求，长度预测只能通过改变所选资源来影响模型推理时延。

**讲解 / 作用：** 这是必要路径，不是收益保证。资源变化也可能得到同样时延甚至更差的真实时延；这里讨论 T，不包括另计的预测或优化时间。

<a id="s231"></a>

#### S231

> If the feasible set is unchanged and varying $\widehat{G}$ only rescales the entire resource-dependent objective by a positive factor and adds a resource-independent term, the set of minimizers is unchanged.

**中文意思：** 若可行集合不变，预测变化只让整个资源相关目标乘正系数，并加资源无关项，则最小化解集合不变。

**讲解 / 作用：** 强调“整个目标”，而非只缩放其中一个资源相关项。a(G_hat)Φ(z)+b(G_hat) 且 a>0 时排序不变；若 prefill 和 decode 各有资源相关项，而只改变其中一项权重，这个结论不能直接使用。

<a id="s232"></a>

#### S232

> Shared energy budgets across phases and context-dependent computation can make the selected vector depend on $\widehat{G}$, but the presence of a predictor alone does not imply a latency benefit.

**中文意思：** 跨阶段共享预算和上下文相关计算可能使资源依赖预测，但有预测器本身不保证时延收益。

**讲解 / 作用：** “可能”不是实证结论；收益取决于配置如何改变和真实长度下的成本。

<a id="s233"></a>

#### S233

> Section VIII specifies comparisons that evaluate this decision dependence.

**中文意思：** 后面的评价章节安排比较来检验这种决策依赖。

**讲解 / 作用：** 这是跨节指引，不是已有结果。本讲解不展开或调整实验内容。

<a id="s234"></a>

#### S234

> Proposition 1 (energy feasibility under the generation cap): Suppose that every additional decode operation and message has nonnegative modeled energy, and that the energy of an executed operation does not depend on the eventual stopping point.

**中文意思：** 命题 1 假设新增 decode 操作和消息能量非负，且已执行操作的成本不依赖最终停止位置。

**讲解 / 作用：** 需两条条件：新增项不负；相同前缀按相同成本核算，不能因较早停止而重定义先前成本。

<a id="s235"></a>

#### S235

> For fixed $(\mathbf{c},\mathbf{z},P)$, every device $i\in\mathcal{N}$, and every $1\leq G\leq{G_{\mathrm{cap}}}$,

**中文意思：** 固定 c、z、P 时，对每台参与设备 i 以及所有 1≤G≤G_cap，满足下式。

**讲解 / 作用：** 补全逐设备量词，不改变不等式。控制预留在不同停止长度下相同；额外 decode 和消息项非负，才得到逐设备单调关系。

<a id="e23"></a>

#### E23 · 对应原稿式 26 · 上限下能量覆盖较早停止

$$
E_i^{\mathrm{acct}}(\mathbf{c},\mathbf{z};P,G)\leq E_i^{\mathrm{acct}}(\mathbf{c},\mathbf{z};P,G_{\mathrm{cap}})
$$

**符号与单位：** 固定 c、z、P，且 1≤G≤G_cap。相同前缀成本一致，新增步骤和消息非负。

**为什么这样写：** 长到上限的请求包含短请求所有前缀，再加非负能量，所以不会更小。无需假设每步成本不变，也不比较不同资源向量。

**用途 / 条件 / 示例：** 上限能量通过则允许范围内任何停止长度也通过。内存另由全形状最大值覆盖。保证只针对声明核算模型，并非整机电池保证。

<a id="s236"></a>

#### S236

> Proof: The cap-length request contains the same prefill operation and the same decode and communication operations through output $G$, plus the nonnegative increments for decode steps $G,\ldots,{G_{\mathrm{cap}}}-1$.

**中文意思：** 证明：上限请求包含到第 G 个输出为止的相同前缀，并多出编号 G 至 G_cap−1 的非负步骤增量。

**讲解 / 作用：** 输出 G 对应 G−1 个 decode；下一新增 decode 的编号就是 G，索引没有差一。

<a id="s237"></a>

#### S237

> Summing these additional increments establishes the inequality.

**中文意思：** 把这些额外非负项相加即得到不等式。

**讲解 / 作用：** 这是前缀包含的直接证明，不要求每步能量相同。

<a id="s238"></a>

#### S238

> Together with the conservative memory test over $\mathcal{Q}(P,{G_{\mathrm{cap}}})$, Proposition 1 ensures that an admitted configuration satisfies the modeled budgets for every permitted stopping length, regardless of prediction error.

**中文意思：** 结合覆盖所有执行形状的保守内存检查，命题 1 保证准入配置在所有允许停止长度下满足模型预算，与预测误差无关。

**讲解 / 作用：** 把 peak-memory 改为 conservative memory，与 IV-C 的口径一致。保证依赖于状态容量和临时缓冲界、非负能量项以及固定控制预留，不是现实测量或模型失配下的无条件保证。

<a id="s239"></a>

#### S239

> The guarantee applies to the incremental-energy components and fixed accounting boundary specified in Section III.

**中文意思：** 保证适用于 III 指定的增量能量组件与固定核算边界。

**讲解 / 作用：** 不将理论模型保证扩大到真实整机、电池寿命或未建模行为。

<a id="s240"></a>

#### S240

> For complementary continuous analysis, the same latency objective and cap-based constraints can be considered with controls varying continuously within their operating bounds.

**中文意思：** 作为辅助连续分析，可让控制在上下界内连续变化，仍使用同样目标与上限约束。

**讲解 / 作用：** 真实有限等级和连续区间不同；连续参考不是直接可部署配置。

<a id="s241"></a>

#### S241

> When this reference is feasible, let $\mathcal{A}_{\mathrm{cont}}(\mathbf{c},P,\widehat{G})$ denote a resource vector solving

**中文意思：** 连续参考可行时，以 A_cont 表示下式的资源解。

**讲解 / 作用：** E24 显式列出时延目标、能量/内存约束及控制区间。

<a id="e24"></a>

#### E24 · 对应原稿式 27a–27e · 辅助连续参考

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

<a id="s242"></a>

#### S242

> The frequency and power bounds are those defined in Section III.

**中文意思：** 频率和功率界沿用 III 的定义。

**讲解 / 作用：** 不是为连续参考另造更宽的硬件范围。

<a id="s243"></a>

#### S243

> This reference treats the controls as continuous within those bounds; the deployment formulation below uses the finite-grid policy $\mathcal{A}$, not $\mathcal{A}_{\mathrm{cont}}$.

**中文意思：** 连续参考允许区间中任意值；下面部署问题使用离散 A，而不是 A_cont。

**讲解 / 作用：** 外层分区必须按主策略评分，不能拿连续理想资源代替。

<a id="s244"></a>

#### S244

> Its continuous properties are analyzed separately from executable control in Section VII.

**中文意思：** 连续性质在解法章节与可执行控制分开分析。

**讲解 / 作用：** 本范围只定义参考问题，不借讲解扩展后文证明。

<a id="section-245"></a>

### VI-C 部署分区优化

先因果选资源、再用历史真实长度评分；最优性范围是指定策略的校准目标。

<a id="s245"></a>

#### S245

> Let $K\geq1$ denote the number of historical calibration requests, and let $\mathcal{D}_{\mathrm{cal}}=\{1,\ldots,K\}$ be their index set.

**中文意思：** K≥1 为历史校准请求数，D_cal={1,…,K} 为其编号集合。

**讲解 / 作用：** K 是数量，D_cal 是索引。均值分母不能为零；这里 r 将表示请求编号。

<a id="s246"></a>

#### S246

> For request $r\in\mathcal{D}_{\mathrm{cal}}$, let $P_r\in\mathcal{P}$, $\widehat{G}_r$, and $G_r$ denote its prompt length, prediction from the fixed predictor, and realized output length, respectively.

**中文意思：** 校准请求 r 的 P_r、G_hat,r、G_r 分别为输入长度、固定预测器预测和真实输出长度。

**讲解 / 作用：** 三者不可混用。校准历史可以事后知道 G_r，但内层仍只看前两者。

<a id="s247"></a>

#### S247

> For each candidate partition that admits every calibration request, let $\mathbf{z}_r(\mathbf{c})$ be the resource vector selected by the same causal policy:

**中文意思：** 对能准入全部校准请求的候选分区，以 z_r(c) 表示同一个因果策略选定的资源。

**讲解 / 作用：** 先筛出有定义的可行候选，再调用策略；不对拒绝请求凭空指定时延。

<a id="e25"></a>

#### E25 · 对应原稿式 28 · 历史请求的因果资源选择

$$
\mathbf{z}_r(\mathbf{c})=\mathcal{A}(\mathbf{c},P_r,\widehat{G}_r)
$$

**符号与单位：** r 为校准请求编号；z_r(c) 是该分区下该请求的资源；预测器固定。

**为什么这样写：** 不同分区会诱导不同资源，所以资源要写成 c 的函数；选择不读取 G_r。

**用途 / 条件 / 示例：** 这是评分前的步骤。必须先选 z_r，再在 E26 使用真实长度。

<a id="s248"></a>

#### S248

> The calibration objective $J_{\mathrm{cal}}(\mathbf{c})$ is the mean inference latency obtained with these selected resources at the historical realized output lengths:

**中文意思：** J_cal(c) 是采用这些选定资源、按历史真实输出长度评价得到的平均推理时延。

**讲解 / 作用：** 明确被平均的是请求时延，而不是资源向量或输出长度；每个 G_r 只进入评分，不进入该请求的资源选择。

<a id="e26"></a>

#### E26 · 对应原稿式 29 · 历史真实长度下评分

$$
J_{\mathrm{cal}}(\mathbf{c})=\frac{1}{K}\sum_{r\in\mathcal{D}_{\mathrm{cal}}}T(\mathbf{c},\mathbf{z}_r(\mathbf{c});P_r,G_r)
$$

**符号与单位：** K 为正历史请求数；D_cal 为索引集合；J 的单位 s；G_r 是事后真实长度。

**为什么这样写：** 平均的是已经因果选定资源在真实历史长度下的时延，不是内层预测目标的平均，也不是 oracle 资源的平均。

**用途 / 条件 / 示例：** 部署比较候选分区。讲解例：两个请求在其选定配置下为 2、4 秒，评分为 3 秒；不是论文结果。

<a id="s249"></a>

#### S249

> The overall deployment problem is

**中文意思：** 总体部署问题如下。

**讲解 / 作用：** E27 在满足分区与全部校准请求可行性条件的候选中最小化评分。

<a id="e27"></a>

#### E27 · 对应原稿式 30a–30c · 总体部署优化问题

$$
\min_{\mathbf{c}}\ J_{\mathrm{cal}}(\mathbf{c})
$$

$$
0=c_0<c_1<\cdots<c_N=L,\quad c_i\in\mathbb{Z}
$$

$$
\mathcal{Z}(\mathbf{c},P_r)\ne\varnothing,\quad\forall r\in\mathcal{D}_{\mathrm{cal}}
$$

**符号与单位：** 只优化整数内部切点；J 内部包含指定 A 的资源选择。每个历史请求都须至少有一个可行配置。

**为什么这样写：** 外层依次遵守层结构和同负载可行性，再按真实长度评分。不同请求可选不同 z，不要求同一个资源向量覆盖全部历史。

**用途 / 条件 / 示例：** 所得 c* 固定用于未来请求。最优范围是该候选空间、该校准目标和指定策略，不是所有可能在线策略或所有未来分布。

<a id="s250"></a>

#### S250

> A solution is denoted by $\mathbf{c}^\star$ and is held fixed for subsequent requests.

**中文意思：** 得到的分区解记为 c*，后续请求保持使用它。

**讲解 / 作用：** 请求级资源仍变化；星号不表示对所有未来流量必然最优。

<a id="s251"></a>

#### S251

> The first constraint assigns consecutive nonempty layer blocks in the specified device order.

**中文意思：** 第一条约束按照固定设备顺序分配连续非空层块。

**讲解 / 作用：** 它是可部署分区结构，不包含设备挑选或重排序。

<a id="s252"></a>

#### S252

> The second requires every calibration request to have at least one valid resource vector satisfying the cap-based memory and energy constraints.

**中文意思：** 第二条要求每个校准请求至少存在一组满足上限内存和能量预算的合法资源。

**讲解 / 作用：** 不同请求可以用不同 z；不要求一个资源向量覆盖整个校准集。

<a id="s253"></a>

#### S253

> Thus, candidate partitions are scored on the same calibration workload, and the objective is defined only for feasible candidates.

**中文意思：** 因此候选都在同一校准负载上评分，目标仅对可行候选定义。

**讲解 / 作用：** 避免只服务容易请求的分区获得较小均值；也避免对不存在的策略输出计算 T。

<a id="s254"></a>

#### S254

> Equal-score partitions are ordered lexicographically by their boundary vectors.

**中文意思：** 评分相同的分区按边界向量字典序排序。

**讲解 / 作用：** 先比第一个切点，再比后续切点，保证确定性选择。

<a id="s255"></a>

#### S255

> If no candidate is feasible, the deployment problem is infeasible for the specified workload and parameters.

**中文意思：** 如果无候选可行，该负载与参数下的部署问题不可行。

**讲解 / 作用：** 不能把不可行包装成算法失败或偷偷删请求使问题变得可行。

<a id="s256"></a>

#### S256

> The historical length $G_r$ is used only to score the vector already selected from $(P_r,\widehat{G}_r)$.

**中文意思：** 历史真实长度只用于给已按 P_r、预测长度选好的配置打分。

**讲解 / 作用：** 重复强调信息边界，因为这里最容易把离线已知信息泄漏给在线策略。

<a id="s257"></a>

#### S257

> Allowing the inner optimizer to observe $G_r$ would define a different, oracle-based deployment objective.

**中文意思：** 若允许内层看到真实 G_r，就会形成另一种预知真实长度的 oracle 部署目标。

**讲解 / 作用：** oracle 是不可在线获得的参考信息，不能给这种问题的最优结果冠以当前因果策略保证。

<a id="s258"></a>

#### S258

> The stated formulation selects a partition for the specified causal policy rather than jointly optimizing over all possible policies.

**中文意思：** 当前公式为指定因果策略选择分区，不是在全部可能策略空间中联合寻优。

**讲解 / 作用：** “联合”指分区通过资源策略评价、计算与无线共用预算，不意味着证明所有可设计策略中最优。

<a id="s259"></a>

#### S259

> Calibration feasibility does not guarantee feasibility for every future prompt; each new request still undergoes the admission test in 24.

**中文意思：** 校准可行不保证所有未来输入可行，新请求仍须逐次准入检查。

**讲解 / 作用：** 历史优化目标与未来服务保证不同：固定的是分区，不是自动准入所有未来请求。

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

本讲解忠实说明上述线上版本的定义与假设，不把模型接口要求写成已经完成的测量或验证。公式卡中的换行、临时省略参数和英文标签为教学排版转换，均在卡片中注明；没有修改 Overleaf 论文。若线上稿后续改变，原稿公式编号可能变化，可用 S/E 编号及小节标题继续定位。

方法说明：采用 latex-paper-en 的原意与事实保护原则、math-reasoning 的符号/单位/边界检查，以及 PDF 技能的生成和渲染核对流程。本材料不引入新的文献结论、实验结果、模型替换或实验协议。
