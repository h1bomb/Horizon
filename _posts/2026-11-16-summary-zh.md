---
layout: default
title: "Horizon Summary: 2026-11-16 (ZH)"
date: 2026-11-16
lang: zh
---

> 从 36 条内容中筛选出 9 条重要资讯。

---

**科技新闻**
1. [Meta FAIR 与 NYU：视觉编码器预训练可选、专属参数必需](#item-tech-news-1) ⭐️ 8.0/10
2. [美团开源 LongCat-2.5：1.6 万亿参数，称全程用升腾训练](#item-tech-news-2) ⭐️ 8.0/10
3. [Protomaps：自托管地图瓦片变得便宜又简单](#item-tech-news-3) ⭐️ 7.0/10
4. [现代 LLM 位置嵌入：实现解释与群表示视角](#item-tech-news-4) ⭐️ 7.0/10
5. [开源工具称将 B300 上页式 cudaMemcpy 提速约 5 倍](#item-tech-news-5) ⭐️ 7.0/10
6. [华为云 MaaS 上线 openPangu-2.1-Pro](#item-tech-news-6) ⭐️ 7.0/10

**财经新闻**
1. [中美俄领导人计划在深圳 APEC 场边举行三方会晤](#item-finance-news-1) ⭐️ 8.0/10
2. [卢特尼克因英伟达关系受审视，Cantor 申报持股降约 49%](#item-finance-news-2) ⭐️ 7.0/10
3. [美法官驳回美光、三星、SK 海力士 DRAM 价格操纵案撤诉动议](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Meta FAIR 与 NYU：视觉编码器预训练可选、专属参数必需](https://www.reddit.com/r/MachineLearning/comments/1xx1k2o/meta_fair_nyu_unbundling_multimodal_vision/) ⭐️ 8.0/10

Meta FAIR 与 NYU 的一篇预印本报告称，他们从零训练了 200 多个多模态大模型，在相同数据和包含编码器预训练的总算力预算下，分别检验视觉编码器的三项常见绑定选择。结果显示，单独预训练视觉编码器在匹配算力下至多与随 LLM 从零训练的编码器打平，并未带来 VQA 增益；但仅视觉 token 使用的专属参数不可少，无编码器模型在 0.6B 到 6.4B 各规模均落后，约需 3 倍算力才能追上。编码器放在 LLM 之前同样非必需：把零初始化的视觉专属权重注入 LLM 前 8 层（“in-fusion”）在 1.7B 到 6.4B 与编码器方案相当，并报告首 token 时间低约 13%。主要对比基于 Qwen3-1.7B/4B 骨干和 0.4B 视觉容量，评测覆盖 Cambrian 的 16 个 448px VQA 基准及 12 个语言基准；作者在帖子中披露了身份，结论仍属未经同行评审的预印本。

reddit · r/MachineLearning · /u/trungh98 · 11月15日 17:38

**「背景」** 多模态大模型通常把视觉编码器作为独立预训练组件接在 LLM 之前，并且该编码器的参数只用于处理视觉 token；这实际上把三项选择捆绑在一起：是否单独预训练、是否保留视觉专用参数、是否把编码器放在 LLM 前面。由于已发布模型所用的数据与算力不同，很难直接比较它们来判断这三项中哪一项才是必要的。

**「对多模态架构设计的影响」** 对正在设计多模态模型的开发者来说，这项预印本给出的可操作结论是：即便像 Gemma 4 12B 那样取消独立视觉编码器（据 Google 文档，该模型将原始图像块经轻量线性层直接投影进 LLM 嵌入空间），仍应为视觉 token 保留专属参数；作者报告，缺少这类参数的编码器免费模型在 0.6B 至 6.4B 各规模上均落后，需约 3 倍算力才能追平，而在 LLM 前 8 层加入零初始化视觉专用分支的方案与独立编码器表现相当，且首 token 时间约低 13%。这些数字来自单一预印本、尚未经同行评审，采用前应视为待独立验证的架构建议。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/google/gemma-4-12B">google/ gemma - 4 - 12 B · Hugging Face</a></li>
<li><a href="https://developers.googleblog.com/gemma-4-12b-the-developer-guide/">Gemma 4 12 B : The Developer Guide - Google Developers Blog</a></li>

</ul>
</details>

**标签**: `#multimodal learning`, `#vision encoders`, `#MLLM training`, `#model architecture`, `#research preprint`

---

<a id="item-tech-news-2"></a>
### [美团开源 LongCat-2.5：1.6 万亿参数，称全程用升腾训练](https://the-decoder.com/meituan-releases-a-1-6-trillion-parameter-agent-model-that-never-touched-an-nvidia-gpu/) ⭐️ 8.0/10

美团 LongCat 团队在模型正式发布一周后公布了 LongCat-2.5 的权重；该模型总参数约 1.6 万亿，采用 MIT 许可证，允许商用。它面向能够自主完成冗长、多步骤任务（尤其是编程任务）的智能体，每个 token 激活约 480 亿参数，并支持文本、图像和视频输入。团队称其训练全程使用华为升腾加速卡、未使用英伟达 GPU，在 Terminal Bench v2.1 上得分 88.4，略低于 Claude Opus 5 的 89.1；这些硬件与跑分声明尚待独立验证。

telegram · zaihuapd · 11月15日 11:08

**「背景」** 据 TemperatureZero 报道，美团 LongCat 团队于 6 月 30 日开源了 LongCat-2.0：该模型拥有 1.6 万亿参数，并称在 5 万颗国产芯片上端到端训练，且未使用英伟达 GPU。该版本以 MIT 许可证发布，因此 LongCat-2.5 是在同一参数级别和同一开放许可下的一次版本更新，并非首次转向国产算力。

**「影响」** 对希望商用或修改权重的智能体开发团队而言，MIT 许可证降低了法律门槛，但 1.6 万亿总参数仍意味着高昂的推理部署成本。官方给出的 Terminal Bench 得分只比 Claude Opus 5 低 0.7 分，并不保证在自有编程任务上同样接近，团队在上线前仍需用自身任务集复测。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://temperaturezero.com/2026/07/05/meituan-trained-frontier-model-without-nvidia/">Meituan Trained a Frontier Model Without Nvidia – TemperatureZero</a></li>
<li><a href="https://www.ainchina.com/blog/meituan-longcat-2-trillion-domestic-chips-china-ai-independence-2026/">How Meituan Built a Trillion - Parameter AI Model on 50,000 Domestic...</a></li>

</ul>
</details>

**标签**: `#open-source AI`, `#large language models`, `#Huawei Ascend`, `#AI agents`, `#model benchmarks`

---

<a id="item-tech-news-3"></a>
### [Protomaps：自托管地图瓦片变得便宜又简单](https://bruceroettgers.eu/blog/protomaps/) ⭐️ 7.0/10

一篇博文结合实践说明，用 Protomaps 自托管地图瓦片如今成本低、上手也容易；文章讲的是自建瓦片服务的做法与开销，并未涉及新版本或新功能发布。讨论主要围绕 PMTiles 格式配合对象存储（如 Cloudflare R2）的组合展开：评论者表示可以把瓦片放在自己的存储上对外提供，从而自己掌握地图基础设施。需要区分的是，这些均为博客作者与评论者的实践描述，没有第三方基准或厂商数据佐证“便宜”的具体幅度。

hackernews · bcye · 11月15日 19:26 · [社区讨论](https://news.ycombinator.com/item?id=50509837)

**「背景」** Protomaps 是一个开源世界地图项目，可把地图数据打包成单个静态文件放在云存储上，客户端直接读取瓦片，因此无需自建瓦片服务器。Supabase 的示例也采用这种做法，将 Protomaps 瓦片直接从 Supabase Storage 提供给 MapLibre 地图。

**「影响」** 对有地图需求的小团队和独立开发者来说，最直接的后果是不必再绑定 Mapbox 或 Google Maps 的按量计费与 API key 体系：一位评论者称，正因为 Protomaps，他才觉得这个维基百科步行游戏在副业预算内可行。但这个方案有容量上限：另一位评论者为提供离线访问而自建北美卫星影像拼接图时，受存储预估限制只能停到 z17，并称高分辨率全球覆盖可能达到数百 TB 量级，已超出“放对象存储加个 worker”的范围。

**「社区讨论」** 评论者 boramalper 推荐了同类项目 OpenFreeMap，其公共实例声称不限地图浏览量与请求数、无需注册和 API key，靠捐赠覆盖运行成本；neomantra 则介绍了用 Cloudflare R2 承载 PMTiles 的做法，动机是隐私与访问控制，并提到自己的工具目前对大瓦片（&gt;128M）和部分栅格格式的支持仍有问题。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://supabase.com/blog/self-host-maps-storage-protomaps.md">supabase.com/blog/ self - host - maps -storage- protomaps .md</a></li>
<li><a href="https://protomaps.com/">Protomaps - The open source map in a file</a></li>

</ul>
</details>

**标签**: `#protomaps`, `#map-tiles`, `#self-hosting`, `#open-source`, `#pmtiles`

---

<a id="item-tech-news-4"></a>
### [现代 LLM 位置嵌入：实现解释与群表示视角](https://magazine.sebastianraschka.com/p/understanding-positional-embeddings) ⭐️ 7.0/10

Sebastian Raschka 的文章讨论现代大语言模型中位置嵌入的实现方式，面向希望理解具体机制的开发者。文章在 Hacker News 的讨论进一步延伸到群论解释。

hackernews · vismit2000 · 11月15日 12:14 · [社区讨论](https://news.ycombinator.com/item?id=50506376)

**「背景」** 位置编码用于让 Transformer 在并行处理 token 时仍能获得顺序信息。Rotary Position Embeddings（RoPE）由 Su 等人提出，它通过对 Query 和 Key 向量施加旋转来编码相对位置；这篇解释文章从不同位置编码方法讲到 RoPE 的工作方式，并讨论了近期开源 LLM 的选择。

**「社区讨论」** 评论者 programjames 主张，要真正理解位置嵌入，就必须理解其理论：位置嵌入是群表示，这也是找到它们并对其参数化、使其可微且可学习的方式。他以旋转位置嵌入为例，称其是平移群的表示，并指出 n 维平移群 ℝⁿ 是阿贝尔群；这些是评论者的观点，不是文章结论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://magazine.sebastianraschka.com/p/understanding-positional-embeddings">Understanding Positional Embeddings in Modern LLMs</a></li>
<li><a href="https://micrologics.org/blog/beyond-standard-attention-demystifying-gqa-and-rope-in-modern-llm-architectures">Beyond Standard Attention: Demystifying GQA and RoPE in Modern ...</a></li>

</ul>
</details>

**标签**: `#positional embeddings`, `#LLMs`, `#transformer architectures`, `#deep learning theory`

---

<a id="item-tech-news-5"></a>
### [开源工具称将 B300 上页式 cudaMemcpy 提速约 5 倍](https://www.reddit.com/r/MachineLearning/comments/1xx2n25/making_cudamemcpy_5x_faster_on_a_b300_p/) ⭐️ 7.0/10

一位开发者在 Reddit 发布开源工具 cudamemcpy-tuner，声称在 NVIDIA B300 上把页式（pageable）cudaMemcpy 的 CPU→GPU 传输速度从约 10.2 GB/s 提升到 51.5 GB/s，约 5 倍。作者给出的示例用 1 GB uint8 张量、连续 5 次复制并同步计时，并链接了博客与 GitHub 代码。该结果目前是作者自测，尚未独立验证，且仅覆盖单一 GPU 型号和页式传输场景。

reddit · r/MachineLearning · /u/makneeee · 11月15日 18:20

**「背景：可分页内存与页锁定内存」** 在 CUDA 中，用普通 malloc 分配的主机内存属于 pageable（可分页）内存，驱动需要先把它复制到内部的 pinned（页锁定）缓冲区，再传输给 GPU，因此实际上发生了两次拷贝；而用 cudaMallocHost 分配的 pinned 内存可被 GPU 直接读取，通常能获得更高的主机—设备带宽。这也解释了为何“加速 pageable cudaMemcpy”本质上是在优化或绕开这条中转路径。

**「适用条件与验证建议」** 对长期用 pageable 主机内存做 CPU→GPU 拷贝的数据管线来说，按作者给出的数字，1 GB 张量单次传输大致从约 98 ms 降到约 19 ms；但这是作者自建基准、只在 B300 的 pageable 路径上测得的结果，而且实际使用时需要用 \`cmt tune --\` 包裹原命令重新运行，所以团队在改用之前，应先在自己的 GPU 型号和张量形状上复测，并确认它同 pinned memory/异步拷贝路径相比是否还有收益。即便按 51.5 GB/s 计算，这个速度也远低于 B300 约 8 TB/s 的 HBM 带宽，可见优化的是主机到设备的搬运环节，而不是显存内部带宽。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://developer.nvidia.com/blog/how-optimize-data-transfers-cuda-cc/">How to Optimize Data Transfers in CUDA C/C++ | NVIDIA ...</a></li>
<li><a href="https://cuda.live/tutorials/memory-model">CUDA Memory: Global, Shared, Constant &amp; Pinned Memory</a></li>
<li><a href="https://inferencex.semianalysis.com/chips/b300">NVIDIA B300 Specs: ~$2.26/hr, 268 GB HBM3e | InferenceX</a></li>

</ul>
</details>

**标签**: `#cuda`, `#gpu-memory-transfer`, `#performance-optimization`, `#ml-systems`, `#open-source-tools`

---

<a id="item-tech-news-6"></a>
### [华为云 MaaS 上线 openPangu-2.1-Pro](https://mp.weixin.qq.com/s/8JfFmscBTDl_mPQMycD8Nw) ⭐️ 7.0/10

11 月 15 日，华为云 MaaS 模型即服务平台上线 openPangu-2.1-Pro，称该模型围绕 Agent 开发、AI 编码和推理优化升级能力。公告称其基于 10 万余条专项数据优化 Skills 触发与工具调用，并适配鸿蒙 ArkTS 开发、升腾算子生成，接入智果 AgentArts、码道 CodeArts、果办 OfficeAce 等产品。推理定价为输入 0.8 元/百万 tokens、输出 3.2 元/百万 tokens，缓存命中输入 0.016 元/百万 tokens。公告未披露模型规模、基准测试结果和开源许可证，也尚无独立评测。

telegram · zaihuapd · 11月15日 16:03

**「前代版本背景」** 据 IT 之家报道，华为云 11 月 1 日发布公告称，MaaS 模型即服务平台于 2026 年 11 月 6 日停止销售 openPangu-2.0-Flash 和 openPangu-2.0-Pro 两款模型服务，相关服务并于 11 月 30 日 00:00 终止，同时华为官方表示 openPangu 系列新版本已在规划中。已开源的 openPangu-2.0-Flash 是基于升腾 NPU 训练的大规模混合专家（MoE）语言模型，参数规模约 92B、每 token 激活参数约 6B，支持 512k 上下文长度。

**「影响」** 对鸿蒙和升腾相关开发者而言，该模型可直接通过华为云 MaaS 调用并按 token 计费；但在生产采用前，仍需自行验证其 Skills 触发、工具调用及 ArkTS/升腾算子生成效果，因为公告未提供基准测试结果或许可证信息。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.ithome.com/1/022/974.htm">消息称 华 为 云 MaaS 平台 11 月 15 日更新上线 openPangu - 2 . 1 - Pro ...</a></li>
<li><a href="https://www.163.com/dy/article/LAUGH8N10511B8LM.html">华 为 小艺Work率先上线 openPangu - 2 . 1 - Pro 模 型 ，主打“鸿蒙任务增强”</a></li>
<li><a href="https://huggingface.co/lovedheart/openPangu-2.0-Flash-FP8">lovedheart/ openPangu - 2 .0-Flash-FP8 · Hugging Face</a></li>

</ul>
</details>

**标签**: `#Huawei Cloud`, `#Pangu`, `#open-source LLM`, `#AI agents`, `#AI coding`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [中美俄领导人计划在深圳 APEC 场边举行三方会晤](https://apnews.com/article/trump-xi-putin-summit-china-5fe92253ef38100bae913834a9b74d72) ⭐️ 8.0/10

中国外交部发言人宣布，中美俄三国领导人计划于 11 月 19 日在深圳 APEC 峰会期间举行场边三方会晤，会晤不属于 APEC 正式议程；媒体称这将是三国领导人首次专门举行三方会晤。

telegram · zaihuapd · 11月16日 01:38

**「背景」** 这是中国第三次主办 APEC 领导人会议，前两次分别在 2001 年和 2014 年；本届峰会于 11 月 18 日至 19 日在深圳举行，三方会晤安排在峰会正式议程之外的场边进行。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/APEC_China_2026">APEC China 2026 - Wikipedia</a></li>
<li><a href="https://www.riotimesonline.com/apec-shenzhen-2026/">APEC 2026 in Shenzhen : Dates , Agenda and What to Watch</a></li>

</ul>
</details>

**标签**: `#geopolitics`, `#US-China-Russia`, `#APEC`, `#diplomacy`, `#market risk`

---

<a id="item-finance-news-2"></a>
### [卢特尼克因英伟达关系受审视，Cantor 申报持股降约 49%](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 7.0/10

美国商务部长霍华德·卢特尼克因与英伟达的关系受到审视：其子领导的 Cantor Fitzgerald 申报持有的英伟达股票数量在 2025 年 9 月至 2026 年 3 月间下降 49%。据 Axios 11 月 11 日报道，卢特尼克多次抵制白宫和情报官员要求打击新加坡 Megaspeed 的努力，该公司涉嫌将英伟达先进 AI 芯片转运至中国；报道未证明 Cantor 的持股变化与这些警告有关。

rss · CNBC Finance · 11月15日 19:58

**「背景」** 美国商务部负责出口管制，其实体清单用于限制受制裁企业；新加坡的 Megaspeed 被怀疑将英伟达先进芯片转运至中国、绕过美国出口禁令，而 Lutnick 已同意就商务部处理此案的方式赴参议院作证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cbsnews.com/news/howard-lutnick-scott-bessent-nvidia-megaspeed-testimony/">Lutnick agrees to testify as Bessent blames him for not banning Nvidia ...</a></li>
<li><a href="https://nypost.com/2026/11/13/business/howard-lutnick-to-testify-before-senate-on-nvidia-megaspeed-fiasco/">Howard Lutnick to testify before Senate on Nvidia , Megaspeed fiasco</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#US-China tech`, `#export controls`, `#ethics/conflicts`, `#semiconductor policy`

---

<a id="item-finance-news-3"></a>
### [美法官驳回美光、三星、SK 海力士 DRAM 价格操纵案撤诉动议](https://www.tomshardware.com/tech-industry/big-tech/judge-denies-motion-to-dismiss-dram-price-fixing-lawsuit-against-micron-samsung-and-sk-hynix-says-chipmakers-acted-like-hawks-flying-in-formation-finds-evidence-of-dram-collusion-plausible-after-500-percent-price-surge) ⭐️ 7.0/10

美国法官 Noël Wise 驳回美光、三星和 SK 海力士要求撤销 DRAM 价格操纵集体诉讼的动议，认为原告提出的新证据使三家厂商在一年内四次同步限制供应、价格至多上涨 500% 的指控具备合理性；上述价格涨幅仍属指控，责任尚未认定。

telegram · zaihuapd · 11月15日 16:39

**「背景」** DRAM 是手机、电脑和服务器普遍使用的内存芯片；这起案件是代表间接购买者的集体诉讼，原告指控三家公司限制 DRAM 供应、推高价格。法官驳回“撤诉动议”，只意味着诉讼可以继续审理，并不等于认定三家厂商存在操纵行为；此前这几家公司也曾面对类似的价格操纵指控。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://litnews.ai/articles/garciaguirre-samsung-sk-hynix-micron-dram-conspiracy-suit-survives-dismissal">Judge Refuses to Dismiss DRAM Supply Conspiracy Suit Against...</a></li>
<li><a href="https://allthings.how/samsung-sk-hynix-and-micron-face-dram-price-fixing-class-action-in-california/">Samsung , SK Hynix , and Micron Face DRAM Price - Fixing Class ...</a></li>

</ul>
</details>

**标签**: `#DRAM`, `#antitrust litigation`, `#semiconductor industry`, `#price-fixing`, `#Micron/Samsung/SK Hynix`

---