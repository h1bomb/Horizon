---
layout: default
title: "Horizon Summary: 2026-11-05 (ZH)"
date: 2026-11-05
lang: zh
---

> 从 46 条内容中筛选出 11 条重要资讯。

---

**科技新闻**
1. [Go 公布新 JSON API：encoding/json/v2 设计](#item-tech-news-1) ⭐️ 8.0/10
2. [OpenAI 称自动流水线发现 948 个 Linux 提权漏洞](#item-tech-news-2) ⭐️ 8.0/10
3. [腾讯发布开放权重模型 Hy4，开源科研模型并适配三大游戏引擎](#item-tech-news-3) ⭐️ 8.0/10
4. [Anthropic 开源 FlashProve：用加密证明核验 LLM 推理](#item-tech-news-4) ⭐️ 8.0/10
5. [月之暗面开源 Kimi K3.1 Pro 权重并开放 API](#item-tech-news-5) ⭐️ 8.0/10
6. [GLM-5.3-Flash 在 Trainium2 上的 NKI 巨型内核](#item-tech-news-6) ⭐️ 8.0/10
7. [IEEE Spectrum：AI 漏洞挖掘正迫使偿还四十年技术债](#item-tech-news-7) ⭐️ 7.0/10
8. [实测 Huginn 循环 Transformer：权重共享未必减少 HBM 读取](#item-tech-news-8) ⭐️ 7.0/10
9. [华为据报要求客户自购升腾 960DT 的 HBM](#item-tech-news-9) ⭐️ 7.0/10
10. [苹果将在 27.3 系统检查 iCloud 公共链接内容](#item-tech-news-10) ⭐️ 7.0/10

**财经新闻**
1. [甲骨文据报取消与腾讯约 70 亿美元 AI 芯片租赁协议](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Go 公布新 JSON API：encoding/json/v2 设计](https://go.dev/blog/jsonv2) ⭐️ 8.0/10

Go 官方博客宣布了一项新的 JSON API，核心是 \`encoding/json/v2\` 的设计，面向所有依赖 Go 标准库处理 JSON 的开发者。现有条目未提供完整接口清单或可用时间，具体兼容性仍需查阅官方文档。社区讨论主要集中在迁移成本、\`MarshalIndent\` 等常用接口的取舍，以及 \`jsontext\` 包在解析性能和错误信息上的表现。

hackernews · olexsmir · 11月4日 17:52 · [社区讨论](https://news.ycombinator.com/item?id=50369106)

**「背景」** Go 标准库此前由 encoding/json 承担 JSON 编解码，开发者已广泛依赖其字段标签、接口和错误处理方式。此次公告提出 encoding/json/v2，意味着标准库的 JSON API 进入重新设计阶段，后续迁移与兼容性讨论都围绕新旧接口的差异展开。

**「影响」** 对已大量使用 \`encoding/json\` 的 Go 项目，若采用新 API，需要重点检查缩进输出等常用写法；社区反馈称 \`MarshalIndent\` 未被保留，等价实现更复杂，升级前应预留改写和测试成本。

**「社区讨论」** 有开发者认可 \`encoding/json/v2\` 的方向，但抱怨去掉 \`MarshalIndent\` 后生成可读 JSON 的等价代码复杂、迁移不便；另一位开发者报告在公司用 \`jsontext\` 为苛刻客户端做解析，能按错误类型给出具体信息且性能很好。上述均为个人使用体验，不能据此推断整个社区已形成共识。

**标签**: `#Go`, `#JSON`, `#API design`, `#standard library`, `#software engineering`

---

<a id="item-tech-news-2"></a>
### [OpenAI 称自动流水线发现 948 个 Linux 提权漏洞](https://openai.com/index/a-thousand-fewer-paths-to-root/) ⭐️ 8.0/10

OpenAI 在一篇文章中称，其自主漏洞研究流水线在 2026 年 10 月的一次 Linux 内核扫描中复现了 1,724 个漏洞，并生成 948 个可让本地低权限用户获得 root 权限的可用提权利用程序，另有 291 个信息泄露 PoC。OpenAI 称总 API 成本为 1,213,430 美元，平均每个成功 LPE 利用程序为 1,279 美元；这些数字属于厂商自述，尚未经过独立验证。帖子还称至少发现 10 种经第三方专家确认为新颖的 Linux 利用技术，包括新的缓存喷洒持久化对象、page grooming、纯数据提权和任意类型混淆。

hackernews · dangelosaurus · 11月4日 23:33 · [社区讨论](https://news.ycombinator.com/item?id=50372929)

**「背景」** 本地提权（LPE）指攻击者已经能在目标机器上以低权限运行代码后，再利用内核或系统服务缺陷取得 root 权限；在 Linux 中，用户态与内核共享同一套权限边界，因此内核漏洞往往直接决定普通账户能否变成管理员。OpenAI 将此次结果描述为由自主漏洞研究流水线完成发现和验证，而非人工逐项审计的产物，这让 948 个 LPE 的数量更适合放在自动化漏洞研究的背景下理解。

**「实际影响」** 如果这些利用程序确如 OpenAI 所述可用，拥有本地低权限账户的攻击者获取 root 的门槛将降低；对多用户主机和服务器运营者而言，本地账户隔离、最小权限和内核补丁节奏会成为更紧迫的控制项。但这些结果仍属厂商自述，独立复现情况和上游修复状态尚不清楚。

**「社区讨论」** 在 Hacker News 讨论中，有评论者追问内核为何会有上千条提权路径，质疑其复杂度或安全模型是否本身就有问题；也有人表示 Linux 本地提权并不意外，但 948 个仍令人震惊。OpenAI 团队成员在评论中确认这是其团队的工作，并表示愿意回答提问。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/a-thousand-fewer-paths-to-root/">A thousand fewer paths to root | OpenAI</a></li>

</ul>
</details>

**标签**: `#linux-kernel`, `#privilege-escalation`, `#vulnerability-research`, `#ai-security`, `#open-source-security`

---

<a id="item-tech-news-3"></a>
### [腾讯发布开放权重模型 Hy4，开源科研模型并适配三大游戏引擎](https://hy.tencent.ai/research/hy4) ⭐️ 8.0/10

腾讯发布开放权重基础模型 Hy4，并同时开源两个科学领域基础模型：用于单细胞表征的 HyCell 和用于物理场建模的 HyPDE，二者由 Hy4 与 Hyra 2.0 共同开发。Hy4 针对游戏开发做了专门适配，覆盖 Unreal Engine、Unity 和 Godot，并扩展到多人游戏开发；其训练数据与评测由腾讯互动娱乐事业群（IEG）的专业开发者参与构建。腾讯在发布材料中承认，Hy4 虽是当前较强的开放权重模型之一，但在研究级数学、长周期编程、模型自我改进和高级视觉问答等内部基准上，与顶级闭源模型仍有明显差距，并表示将继续扩大预训练与后训练规模。

hackernews · Philpax · 11月4日 14:11 · [社区讨论](https://news.ycombinator.com/item?id=50365780)

**「背景」** Hy4 是腾讯 Hy 模型家族的新一代成员。据 Interesting Engineering 报道，这一代首次为该系列加入视觉理解能力。

**「对开发者的影响」** 对游戏开发者而言，最直接的可用性在于 Hy4 已针对 Unreal Engine、Unity 和 Godot 做适配，并扩展到多人游戏开发，团队可据此评估它在功能实现、玩法逻辑和资源管线中的使用；不过有社区测试者报告，它在数据分析任务上处于成本与精度的前沿，但耗时明显偏长，延迟敏感场景需先做基准测试。

**「社区讨论」** 有评论者称赞腾讯开源 HyCell 与 HyPDE 这类面向科研的基础模型，认为这与部分美国公司限制研究用途的做法形成对比；也有人认可官方坦承与顶级闭源模型的差距。simonw 认为游戏开发这一侧重值得关注；chriddyp 则称在 Plotly 的数据分析基准中，Hy4 落在 GPT-6.1 Sol 与 GPT-6.1 Terra 之间的成本与准确率前沿上，但工作非常细致也因此速度很慢。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://interestingengineering.com/ai-robotics/tencent-hy4-open-source-model">China&#x27;s Tencent Hy 4 challenges world&#x27;s top models with 7.2% error rate</a></li>

</ul>
</details>

**标签**: `#open-weight models`, `#foundation models`, `#AI research`, `#game development`, `#open source`

---

<a id="item-tech-news-4"></a>
### [Anthropic 开源 FlashProve：用加密证明核验 LLM 推理](https://www.anthropic.com/research/provable-inference) ⭐️ 8.0/10

Anthropic 发布并开源了 FlashProve 的技术规范与代码，该系统用加密证明验证某段输出确实由指定模型及其权重生成。模型提供方需为发布的模型公开指纹，供后续比对输出；指纹不会披露权重，验证也可在本地设备上完成，因此可用于识别模型被替换，或核实第三方关于模型执行任务的说法。Anthropic 表示研究仍在进行，目前没有部署计划。

hackernews · ltononro · 11月4日 17:17 · [社区讨论](https://news.ycombinator.com/item?id=50368626)

**「背景」** 可验证推理要解决的是“输出是否确由某组权重算出”这一信任问题：提供方先公开不泄露权重的模型指纹，再为每次请求生成证明，客户端可在本地校验。此前已有研究尝试让私有且可验证的大语言模型推理变得实用，例如 2026 年 9 月的 Maverick 论文就指出，既有方案往往带来显著的服务器开销或额外信任假设；Anthropic 的 FlashProve 也属于这一方向。

**「实际影响」** 对使用闭源模型的用户和企业来说，这套机制提供了一条不依赖厂商自述的核验路径：拿到指纹后，就能在本地判断返回结果是否来自所称的模型。但它要求提供方先公开指纹并配合生成证明，因此在 Anthropic 明确部署之前，还无法用于实际的服务核验。

**「社区讨论」** 评论者 neuwirth 称 FlashProve 建立在其担任 MARS 研究员期间完成的工作 VerInf 之上，却几乎没有署名；nemo1618 则指出，对开源权重模型而言，直接重新计算推理即可完成验证，速度更快、成本更低，而且不需要零知识证明。vessenes 认为这是对既有 zk 结果的显著改进，但闭源模型的推理证明要困难得多，用四家独立推理服务商对同一非批处理提示做概率性交叉验证，成本远低于他所说的 90–100 倍计算开销；gopalv 引用论文数据称，承诺约 6.5 MB、覆盖约 1600 万次请求，单次证明校验在 24 线程上需 17 秒。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://eprint.iacr.org/2026/1955">Maverick: Private and Verifiable LLM Inference Made Practical ...</a></li>

</ul>
</details>

**标签**: `#provable inference`, `#LLM verification`, `#cryptography`, `#zero-knowledge proofs`, `#AI trust and safety`

---

<a id="item-tech-news-5"></a>
### [月之暗面开源 Kimi K3.1 Pro 权重并开放 API](https://huggingface.co/moonshotai/Kimi-K3.1-Pro) ⭐️ 8.0/10

月之暗面在 Hugging Face 发布 Kimi K3.1 Pro 的开放权重，称其为原生多模态智能体模型，总参数 2.8T、激活 104B、上下文约 100 万 token，是 K3.1 系列首个模型；权重以 MXFP4 量化形式提供。官方同步在 platform.kimi.ai 开放 API，模型名为 kimi-k3.1-pro，兼容 OpenAI 与 Anthropic 接口。上述参数与能力来自发布方说明，帖子本身没有给出可核验的基准测试结果。

hackernews · abrarthought · 11月4日 15:30 · [社区讨论](https://news.ycombinator.com/item?id=50366999)

**「前代背景」** 月之暗面此前发布的 Kimi K3 同样是 2.8T 参数、约 100 万 token 上下文的原生多模态智能体模型，其权重以开放形式提供。据分析报道，该次发布推送到 Hugging Face 的权重文件达 1.56 TB，这一体量也把托管与推理成本问题直接摆到了台面上。本次 K3.1 Pro 属于 K3.1 系列的首个模型，来源称其总参数仍为 2.8T，激活参数 104B。

**「影响」** 对想自建部署的团队，评论者估计需要约 8 张 B300 的节点，这一门槛尚未由官方确认；对应用开发者，官方 API 兼容 OpenAI 与 Anthropic 接口，可减少现有调用代码的改动。

**「社区讨论」** 评论对基准可信度分歧明显：有人称 K3.1 在 Hy4 的内部基准上不如 Opus5.5、疑似“benchmaxxed”，也有测试者称实际测试未观察到这一点，认为它是略低于前沿但适合多数场景的强开源模型。另有评论称 OpenRouter 等第三方已托管该模型，Together 在同价下吞吐似乎约为官方端点两倍，Modal 再翻倍。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/moonshotai/Kimi-K3">moonshotai/ Kimi -K3 · Hugging Face</a></li>
<li><a href="https://researchaudio.io/p/the-largest-open-model-ever-runs-on-3-7-percent-of-itself">The largest open model ever runs on 3.7 percent of itself</a></li>

</ul>
</details>

**标签**: `#open-weight models`, `#LLM release`, `#Moonshot AI`, `#model benchmarks`, `#LLM inference`

---

<a id="item-tech-news-6"></a>
### [GLM-5.3-Flash 在 Trainium2 上的 NKI 巨型内核](https://www.reddit.com/r/MachineLearning/comments/1xo0yuq/p_nki_layer_megakernels_for_glm53flash_on_aws/) ⭐️ 8.0/10

RunAnywhere 开源了一套面向 AWS Trainium2 的推理引擎，可在单台 trn2.48xlarge 上服务 320B MoE、1M token 上下文的 GLM-5.3-Flash，并把每个层的一半计算改写为单个 NKI 巨型内核（稀疏注意力层则整层一个）。作者称，同一布局下 batch 8 解码步从 10 月 17 日构建的 32.2 ms 降至 11 月 1 日构建的 24.2 ms；融合稀疏注意力层省 3.2 ms，KDA 与 MoE 内核合计再省 3.2 ms，而 24.2 ms 中仍有 6.1 ms 内存下限、10.0 ms 超出下限的引擎忙碌和 2.8 ms 暴露的集合通信。在作者自跑的 SemiAnalysis AgentX 上，单机最高 28.9 个 agent 请求/分钟，16 个 agent 时中位解码 35.9 tokens/s；但作者明确说没有 AWS 原生基线、没有 GPU 同轨迹对比，也未做任务级评测。精度方面，稀疏注意力 prefill 的一处近似影响 1.2% 的选择，相对精确重跑使下一 token 对数概率平均偏移 0.012–0.021 nats，并在 448 个位置中的 3 个改变了最高概率 token。

reddit · r/MachineLearning · /u/WildCard727 · 11月4日 21:47

**「背景」** GLM-5.3-Flash 是 Z.ai 发布的开放权重模型：320B 总参数、每 token 激活 18B 的 MoE，上下文长度 1,048,576 token，并把 KDA 线性注意力与稀疏注意力混合在同一模型里（工具结果 2-2、2-3）。正因每层分属 KDA、稀疏注意力或 MoE 三类结构，这个 Trainium2 引擎才按层类型分别编写 NKI 内核。作者同时指出 Neuron 侧没有可直接对照的现成基线：最新 vLLM Neuron 插件不注册 GLM 模型，NxD Inference 已进入维护模式。

**「影响」** 对在 Trainium2 上部署 GLM 的团队，现实约束是缺少可直接对照的原生路径：最新 vLLM Neuron 插件不注册 GLM 模型，NxD Inference 处于维护模式；采用这类自建内核栈前，需要自行补做任务级评测并验证那处稀疏注意力近似。代码和 docs/RESULTS.md 的重跑命令已公开，但上述性能数字均为作者自测，尚无独立复现或 GPU 对照。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.marktechpost.com/2026/08/26/z-ai-releases-glm-5-3-flash-a-320b-a18b-natively-multimodal-moe-with-a-1m-token-context/">Z.ai Releases GLM-5.3-Flash: A 320B-A18B Natively Multimodal ...</a></li>
<li><a href="https://local-ai-zone.github.io/blog/glm-5-3-flash-deep-dive.html">GLM-5.3-Flash: 320B MoE Beats GLM-5.2, Formerly Ox Alpha</a></li>

</ul>
</details>

**标签**: `#AWS Trainium`, `#LLM inference`, `#kernel optimization`, `#Mixture-of-Experts`, `#open source`

---

<a id="item-tech-news-7"></a>
### [IEEE Spectrum：AI 漏洞挖掘正迫使偿还四十年技术债](https://spectrum.ieee.org/ai-in-cybersecurity-php2shell-vulnerability) ⭐️ 7.0/10

IEEE Spectrum 的一篇分析文章提出，AI 辅助的漏洞发现正在把过去四十年累积的软件技术债集中暴露出来，并迫使维护者着手修复，而不是继续长期搁置。文章的核心论点是：这类工具让原本依赖人工审计、难以覆盖的旧代码缺陷被批量找出，修复工作因而从可选变为必须。需要注意的是，这是一篇观点与分析文章，并未给出可独立验证的测量数据或具体版本信息，其“被迫偿还”的判断仍属作者论证而非已证实的结果。

hackernews · pseudolus · 11月4日 11:52 · [社区讨论](https://news.ycombinator.com/item?id=50364336)

**「背景：PHP2Shell 与“40 年技术债”」** IEEE Spectrum 于 2026 年 11 月 2 日发表的这篇文章，以“PHP2Shell 漏洞”为引子，称其展示了遗留系统如何演变为危险负担（tool-1-1、tool-1-3）。标题中的“40 年技术债”指几十年前写就、至今仍运行在生产环境中的老代码栈，其安全缺陷长期缺乏系统性审计。文章的论证前提是：AI 辅助的漏洞发现与代码审计使大规模排查这类老代码成为可能，从而把这些积压的旧账集中翻了出来。

**「对运维与开发团队的实际影响」** 具体的后果已经出现在 PHP2Shell 这类案例上：前沿模型在 PHP 运行时中发现的两个未授权远程代码执行漏洞（CVE-2026-109618、CVE-2026-109619，CVSS v4.0 评分 9.2）躲过了长达十年的手工审计，而 Cloud Security Alliance 的研究指出这类 AI 发现的漏洞其利用窗口已压缩到披露之前。这意味着运行受影响 PHP 版本的组织不能再把披露日当作安全缓冲期，而应将 AI 上报的严重漏洞默认按“披露时已被利用”处理，事先备好紧急补丁与回滚流程；CSA 为此建议为这类漏洞设立 72 小时快速通道。

**「社区讨论」** 在 Hacker News 的讨论中，swatcoder 质疑“偿还技术债”这一说法，认为不少缺陷需要重构而非逐个打补丁，因此更可能变成长期、与功能无关的修补 treadmill；xbmcuser 则认为开源软件长期依赖“总会有人审计”的假设，AI 审计让这一承诺更接近现实。以上均为评论者的个人判断，而非已证实的结论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://spectrum.ieee.org/ai-in-cybersecurity-php2shell-vulnerability">PHP2Shell Is a Wakeup Call for AI in Cybersecurity - IEEE ...</a></li>
<li><a href="https://hn.today/s/ai-is-forcing-us-to-pay-off-40-years-of-technical-debt">AI is forcing us to pay off 40 years of technical debt - hn.today</a></li>
<li><a href="https://labs.cloudsecurityalliance.org/research/csa-research-note-php2shell-pre-disclosure-exploitation-2026/">PHP2Shell: Exploitation Before Disclosure for an AI-Found Flaw</a></li>
<li><a href="https://tech.yahoo.com/cybersecurity/articles/ai-assisted-research-uncovers-critical-012743884.html">AI-Assisted Research Uncovers Critical PHP2Shell RCE ...</a></li>
<li><a href="https://alphasignal.ai/news/openai-s-php2shell-exposes-70-of-websites-to-remote-code-attacks">OpenAI&#x27;s PHP2Shell Exposes 70% of Websites to Remote Code ...</a></li>

</ul>
</details>

**标签**: `#AI security`, `#vulnerability discovery`, `#technical debt`, `#open source security`, `#cybersecurity`

---

<a id="item-tech-news-8"></a>
### [实测 Huginn 循环 Transformer：权重共享未必减少 HBM 读取](https://www.reddit.com/r/MachineLearning/comments/1xnskvt/do_looped_transformers_save_hbm_traffic_profiling/) ⭐️ 7.0/10

一位作者在 Reddit 技术帖中公布了对 Huginn 式循环 Transformer 的 B200 性能剖析：在由 8 个矩阵乘法组成的链中，单个共享的 72 MiB 权重比 8 份相同副本快 24%，且几乎不从 HBM 读取数据；当权重增至 288 MiB、超出 L2 缓存后，这一差距消失。作者还用随机权重的教学版 Huginn Core 测得，8 次迭代的耗时和 HBM 读取量都约为 1 次迭代的 8 倍。结论是权重共享本身节省存储，但除非权重能留在缓存中，否则并不能阻止 GPU 在每次迭代时重新从 HBM 读取权重。上述为作者基于 Nsight Compute 数据的单方测量，完整模型结果来自教学实现。

reddit · r/MachineLearning · /u/2dayyy6 · 11月4日 16:26

**「背景：循环 Transformer 与权重驻留」** 循环 Transformer（也称 recurrent-depth 或递归 Transformer）把同一个 Transformer 块反复施加多次，并在各次迭代间共享同一套权重，从而显著减少需要存储的参数数量。问题在于，共享权重只减少显存占用，并不自动减少 HBM 读取：每次迭代是否要重新从 HBM 取权重，取决于这套权重能否在两次迭代之间留在片上缓存（如 L2）中。

**「对循环权重优化的实际影响」** 对做循环（looped）权重优化的开发者来说，这意味着参数共享只能降低存储占用，不能直接当作带宽优化：在 Huginn Core 教学实现（随机权重）中，8 次迭代的耗时与 HBM 读取量都约为 1 次的 8 倍，说明每次迭代仍会重新从 HBM 读取共享权重。若要真正省下这部分流量，需要让循环权重常驻片上，例如作者提出但尚未验证的 persistent kernel 或按缓存容量分块；否则应按迭代次数线性预估显存带宽与延迟成本。同时该收益依赖模型规模：72 MiB 共享权重链条比 8 份副本快 24%，但权重增至 288 MiB、超出 L2 后差异消失。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://tosea.ai/blog/looped-transformer-recurrent-depth-astra-guide">What Is a Looped Transformer ? Complete Guide to Recurrent Depth...</a></li>

</ul>
</details>

**标签**: `#looped transformers`, `#HBM bandwidth`, `#GPU profiling`, `#weight reuse`, `#Nsight Compute`

---

<a id="item-tech-news-9"></a>
### [华为据报要求客户自购升腾 960DT 的 HBM](https://thenextweb.com/news/huawei-hbm-smuggling-samsung-sk-hynix-ascend-960dt) ⭐️ 7.0/10

据 The Information 报道，华为已告知部分客户，下一代旗舰 AI 芯片升腾 960DT 将主要使用三星和 SK 海力士的 HBM，并要求客户自行解决内存来源，原因是中国厂商 HBM 产能不足。报道还称，这些 HBM 被焊在性能较弱的处理器上，按处理器编码报关运至香港，再由人携带入境并加热拆下；一名深圳芯片经纪人称，单颗 HBM3E 价格已从一年前数百美元涨到约 4000 美元。上述走私细节与价格均来自该报道的转述，尚未获得独立证实。

telegram · zaihuapd · 11月4日 14:52

**「背景：升腾 950DT 已因 HBM 短缺涨价」** TrendForce 的报道称，HBM 短缺已推高华为芯片价格：华为近期将当前最强 AI 芯片升腾 950DT 的建议价上调至超过 25 万元人民币（约 3.7 万美元）。这为理解华为要求 960DT 客户自行解决 HBM 来源提供了直接背景。

**「影响」** 对计划采用升腾 960DT 的中国客户而言，内存不再随华为芯片一并解决，而需自行建立三星/SK 海力士 HBM 的采购渠道，并承担报道所述的价格与跨境合规风险。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.trendforce.com/news/2026/11/03/news-china-reportedly-obtains-smuggled-hbm-via-server-packages-huawei-960dt-faces-domestic-hbm-shortage/">[News] China Reportedly Obtains Smuggled HBM via Server Packages...</a></li>

</ul>
</details>

**标签**: `#Huawei`, `#Ascend 960DT`, `#HBM`, `#AI chips`, `#supply chain`

---

<a id="item-tech-news-10"></a>
### [苹果将在 27.3 系统检查 iCloud 公共链接内容](https://9to5mac.com/2026/11/04/with-ios-27-3-apple-will-start-checking-icloud-public-links-for-harmful-content/) ⭐️ 7.0/10

苹果表示，从 iOS、iPadOS、macOS 和 visionOS 27.3 起，通过“任何拥有链接的人”方式分享的 iCloud 内容将接受有害内容检查；仅分享给指定人员的内容不在所述范围内。若内容被判定有害，苹果保留移动、拒绝、修改或删除内容的权利，并可能限制或停用上传者的账户，必要时移交执法部门。上述措施属于苹果公布的计划，源内容未说明具体执行细节。

telegram · zaihuapd · 11月5日 02:11

**「背景」** iCloud 的“任何拥有链接的人”分享模式，原本是让持有 URL 的人直接访问文件，而不必由分享者逐一指定收件人；仅与指定人员分享的内容则不在这一公开链接范围内。苹果随首个 iOS 27.3 测试版发布支持文档说明，从 iOS、iPadOS、macOS 和 visionOS 27.3 起，这类公开链接内容将对苹果可见，以接受有害内容检查。

**「影响」** 使用公共链接分享 iCloud 内容的用户需要预期内容可能被平台审查、删除，账户也可能受限；若希望分享不进入该检查范围，应改用仅限指定人员的分享方式，因为源内容称该方式不在所述范围内。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://support.apple.com/en-us/149168">Learn more about sharing content that can be accessed by ...</a></li>

</ul>
</details>

**标签**: `#Apple`, `#iCloud`, `#content moderation`, `#privacy`, `#platform policy`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [甲骨文据报取消与腾讯约 70 亿美元 AI 芯片租赁协议](https://www.tradingview.com/news/seekingalpha:e51e68f4d094b:0-oracle-cancels-7b-ai-chip-lease-with-tencent-amid-us-concerns-ft/) ⭐️ 7.0/10

据 TradingView/Seeking Alpha 援引《金融时报》报道，甲骨文取消了与腾讯价值约 70 亿美元的 AI 芯片租赁协议；此前美国官员曾向甲骨文表达对该交易的担忧。该协议原计划为期五年，让腾讯租用约 10 万枚先进 AI 芯片。

telegram · zaihuapd · 11月4日 11:01

**「背景」** 此前，腾讯今年签署了这份五年期租赁协议，计划通过甲骨文在东南亚的数据中心获得约 10 万枚先进 AI 芯片；这些芯片无法直接在中国获取。

**「影响」** 若取消属实，腾讯通过甲骨文在东南亚的数据中心获取先进 AI 芯片的五年计划将受阻，甲骨文相关租赁业务也将失去这笔收入。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://xenospectrum.com/en/tencent-oracle-ai-chip-lease-prepayments/">Tencent Reportedly Leases About 100,000 AI Chips From Oracle in...</a></li>

</ul>
</details>

**标签**: `#US-China tech policy`, `#AI chips`, `#Oracle`, `#Tencent`, `#data centers`

---