---
layout: default
title: "Horizon Summary: 2026-11-21 (ZH)"
date: 2026-11-21
lang: zh
---

> 从 39 条内容中筛选出 15 条重要资讯。

---

**科技新闻**
1. [Inkling 2 Mini 开放权重循环 Transformer 模型发布](#item-tech-news-1) ⭐️ 8.0/10
2. [Ravi Vakil 公布 Masullo 的广义黎曼猜想证明草案](#item-tech-news-2) ⭐️ 8.0/10
3. [CVE-2026-99312：KVM 漏洞致虚拟机可读 AMD 宿主内存](#item-tech-news-3) ⭐️ 8.0/10
4. [台积电据报暂停对中国企业 16nm 及以下订单](#item-tech-news-4) ⭐️ 8.0/10
5. [Alpöge 声称用 Claude 证明广义黎曼猜想](#item-tech-news-5) ⭐️ 7.0/10
6. [陶哲轩博客：无外力纳维-斯托克斯奇点与广义黎曼猜想](#item-tech-news-6) ⭐️ 7.0/10
7. [语言模型改写自身权重：论文与争议](#item-tech-news-7) ⭐️ 7.0/10
8. [Scott Aaronson 博客讨论“随机鹦鹉”与黎曼猜想](#item-tech-news-8) ⭐️ 7.0/10
9. [Signal 发文讨论限制移动端 AI 代理抓取数据](#item-tech-news-9) ⭐️ 7.0/10
10. [美国收紧芯片出口，印度 Yotta 拟增 10 万 GPU](#item-tech-news-10) ⭐️ 7.0/10
11. [OpenAI 后台模式支持 8 小时长任务，Token 费率最高降 40%](#item-tech-news-11) ⭐️ 7.0/10

**科技博客**
1. [为什么缓存 LLM 输出收效甚微](#item-tech-blog-1) ⭐️ 6.0/10

**财经新闻**
1. [美国企业由回购转向净发股，牛市面临新增供给](#item-finance-news-1) ⭐️ 8.0/10
2. [沃什回避利率指引，美联储官员公开表态增多并现加息分歧](#item-finance-news-2) ⭐️ 7.0/10
3. [北京拟明确租房正常损耗不得扣减押金](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Inkling 2 Mini 开放权重循环 Transformer 模型发布](https://thinkingmachines.ai/news/inkling-2-mini/) ⭐️ 8.0/10

Inkling 2 Mini 以开放权重的小型模型形式发布，采用循环 Transformer 架构，面向本地部署场景。社区用户自测称，在 Ryzen 395 上通过 llama.cpp Vulkan 解码约 27 tokens/s，在 32GB M1 Pro 上以 q4 xl 运行约 10 tokens/s；这些数字并非官方基准。有评论称其编码表现接近 Qwen3.8-27B，但该对比在现有材料中未获独立验证；本地用户还需处理多个 llama.cpp 未合并 PR，并应用一个据称约 30% 提速的小补丁。

hackernews · jasondavies · 11月20日 20:12 · [社区讨论](https://news.ycombinator.com/item?id=50581260)

**「背景」** Inkling 2 Mini 所说的“循环 Transformer”，指模型对每个 token 把中间若干层重复运行三次——这样增加的是单 token 的计算量而非参数量，官方称这能让模型用更少的 token 完成推理密集型任务（如 agentic 编码）。这延续了 Thinking Machines 的 Inkling 2 系列：同系列的 Inkling 2 Small 于 11 月 5 日发布，那一代在攻防与两用 agentic 网络安全基准上较 Inkling Small 有明显提升，但仍落后于开放权重前沿。

**「本地部署影响」** 对本地部署者而言，模型能否顺畅使用取决于 llama.cpp 的补丁状态：有用户报告在 Ryzen 395 搭配 Vulkan 时解码速度约为 27 tokens/s，但需要先合入尚未合并的 PR（32694、32657、32429、32704），再额外应用一个小补丁才能获得约 30% 的提速；在 M1 Pro 与 32GB 内存上，q4 量化版本约为 10 tokens/s。实际部署前应预留打补丁和调参成本，并且这些数字来自用户自测，并非官方基准。

**「社区讨论」** 有评论者认为，循环架构加上开放权重可能促使更多开放模型跟进，也有人把这类效率优化归因于资源约束，并有人提出安全与可解释性方面的疑问。实际体验方面，有用户报告快速编码测试表现不错，但基准能否在真实场景成立仍待验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://thinkingmachines.ai/news/inkling-2-mini/">Introducing Inkling 2 Mini - Thinking Machines Lab</a></li>
<li><a href="https://thinkingmachines.ai/news/inkling-2-small/">Introducing Inkling 2 Small - Thinking Machines Lab</a></li>

</ul>
</details>

**标签**: `#open-weight models`, `#looped transformers`, `#local LLM inference`, `#llama.cpp`, `#model release`

---

<a id="item-tech-news-2"></a>
### [Ravi Vakil 公布 Masullo 的广义黎曼猜想证明草案](https://simonwillison.net/2026/Nov/20/ravi-vakil/) ⭐️ 8.0/10

Ravi Vakil 在博客发布“紧急公告”，称 Alessandro Masullo 已有一份广义黎曼猜想的证明草案；Brian Conrad 已仔细审阅数月并给出大量反馈，这些反馈正在被纳入草案，目前“看起来不错”。Vakil 特别说明这项工作完全由人类完成，没有使用 AI。原计划是邀请 Masullo 到斯坦福一年打磨写作、并在征询足够多人意见后再公布，但 Vakil 表示现在最好先公开当前草案。该证明尚未经过正式验证，仍属未经验证的声明。

rss · Simon Willison · 11月20日 19:21

**「背景」** 广义黎曼猜想是黎曼猜想的推广，属于数论中长期未解的核心问题。此次草案并非正式发表：据外部报道，这份约 940 页的证明耗时约 12 年，且已在 Brian Conrad 手中审阅数月；Vakil 原本希望先邀请 Masullo 到斯坦福打磨一年、再经足够多人审阅后宣布。

**「核验优先」** 对研究 L 函数的数论学家而言，最直接的后果是这份草稿在反馈纳入和专家核验完成前不应被当作已确立结果使用；Vakil 说原计划是先打磨一年再宣布，现在只是提前公开当前稿。若证明最终成立，一个具体推论是这类 L 函数不存在 1/2 与 1 之间的 Siegel 零点，但该推论仍取决于审阅结果。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://xenospectrum.com/en/masullo-riemann-proof-draft-release/">Draft Proof of the Generalized Riemann Hypothesis, 12 Years ...</a></li>
<li><a href="https://en.wikipedia.org/wiki/Generalized_Riemann_hypothesis">Generalized Riemann hypothesis - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Riemann_hypothesis">Riemann hypothesis - Wikipedia</a></li>

</ul>
</details>

**标签**: `#mathematics`, `#Generalized Riemann Hypothesis`, `#proof verification`, `#research announcement`

---

<a id="item-tech-news-3"></a>
### [CVE-2026-99312：KVM 漏洞致虚拟机可读 AMD 宿主内存](https://thehackernews.com/2026/11/new-linux-kvm-flaw-cve-2026-99312-lets.html) ⭐️ 8.0/10

Linux 内核 KVM 被披露编号为 CVE-2026-99312 的漏洞，仅影响启用了嵌套虚拟化的 AMD 主机。研究人员在 DigitalOcean 环境中从虚拟机内部读取到约 127 GB 宿主内存，说明该缺陷可造成跨虚拟机的宿主机数据泄露。上游修复已于 11 月 18 日随稳定内核 7.3.5 等版本发布，但 Debian、Ubuntu 等发行版的内核尚未包含该修复。在补丁到位前，受影响环境可关闭嵌套虚拟化作为临时缓解措施。

telegram · zaihuapd · 11月20日 14:23

**「背景」** KVM 是 Linux 内核内置的虚拟化层；嵌套虚拟化允许一台虚拟机内部再运行自己的虚拟机管理程序，因此该场景下的隔离边界更复杂。Terra Security 的分析指出，CVE-2026-99312 是早先一次安全修复引入的陈旧指针缺陷，已在内核中潜伏近四年（tool-2-3）；DigitalOcean 同样将其描述为 KVM 中的 stale pointer（tool-2-2）。

**「影响与处置」** 运行 AMD 主机且开启嵌套虚拟化的运维方需要检查内核是否已升至包含修复的 7.3.5 或更高版本；使用 Debian、Ubuntu 等尚未跟进发行版内核的用户在当前仍处于暴露状态，若无法立即升级，应关闭嵌套虚拟化以缩小攻击面。该漏洞的实际风险集中在多租户或允许租户自行创建嵌套虚拟机的环境，因为这些场景下 guest 可触达宿主内存。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.digitalocean.com/blog/cve-2026-99312-kvm-patch">Virtualization , Responsible Disclosure, and CVE - 2026 - 99312</a></li>
<li><a href="https://www.terra.security/blog/kvm-guest-to-host-escape">KVM Guest-to-Host Escape | Terra Security Research</a></li>

</ul>
</details>

**标签**: `#KVM`, `#Linux内核`, `#CVE-2026-99312`, `#AMD`, `#虚拟化安全`

---

<a id="item-tech-news-4"></a>
### [台积电据报暂停对中国企业 16nm 及以下订单](https://appleinsider.com/articles/26/11/20/apple-supplier-tsmc-cuts-off-china-chip-orders-amid-tighter-export-controls) ⭐️ 8.0/10

有消息称，台积电已通知客户暂停接收中国企业 16 纳米及以下制程的芯片订单。按收紧后的美国半导体出口新规，除非事先取得美国出口许可或豁免，否则台积电不得供货；此前台积电可自行评估客户设计是否符合豁免条件，现在须由客户提前申请。美国获批名单中有苹果、AMD 和英伟达，尚没有中国公司，台积电表示将遵守新规。

telegram · zaihuapd · 11月21日 02:01

**「背景」** 此次暂停的直接制度背景是合规判断环节前移：过去台积电可自行评估客户设计是否满足豁免条件，新规下则须由客户事先申请美国出口许可或豁免。TrendForce 11 月 20 日报道，台积电与三星均据报在新规下暂停对部分中国客户出货，影响范围可能从 AI 处理器扩大到消费电子，16nm 订单亦受影响。

**「影响」** 对依赖台积电先进制程的中国芯片设计公司而言，短期可行路径是申请美国许可或豁免，或退回 28 纳米、40 纳米等旧制程；源报道同时称，这将使其无法使用 AI 数据中心所需的高带宽内存。由于获批名单尚无中国公司，这一限制并非自动豁免。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.trendforce.com/news/2026/11/20/news-tsmc-samsung-reportedly-pause-china-consumer-chip-shipments-under-new-u-s-rules-16nm-orders-affected/">[News] TSMC , Samsung Reportedly Pause China Consumer Chip...</a></li>

</ul>
</details>

**标签**: `#semiconductors`, `#TSMC`, `#export controls`, `#AI hardware`, `#China tech`

---

<a id="item-tech-news-5"></a>
### [Alpöge 声称用 Claude 证明广义黎曼猜想](https://alpo.ge/remark.pdf) ⭐️ 7.0/10

Anthropic 的数学家 Levent Alpöge 于 11 月 20 日声称，他借助 Claude 证明了黎曼猜想，并称相关证明确认了更广泛的广义黎曼猜想；证明以 Lean 编码发布在个人站点，文稿据称超过 25 万页。Hacker News 评论者称该 Lean 归档约 1.3GB、约 1500 万行，并链接了一份据称完全由人类完成的证明。上述内容目前只是作者与社区的说法，尚未经过独立验证或同行评议，应视为待核实的数学声明。

hackernews · iamronaldo · 11月20日 14:16 · [社区讨论](https://news.ycombinator.com/item?id=50574968)

**「背景」** 黎曼猜想由黎曼于 1859 年提出，讨论素数在数轴上的分布规律；广义黎曼猜想则是该猜想的推广形式。Lean 是可用于机器检查数学证明的证明助手，Alpöge 的声明附有 PDF 说明和 Lean 代码，但目前仍是发布在个人网站上的未验证主张，而非已通过同行评审或独立确认的结果。

**「验证前的影响」** 若该证明通过独立验证，数论中依赖广义黎曼猜想的结论——例如算术级数中的素数分布——将不再以该猜想为前提。但当前它仍是发布在个人 PDF 上的未验证声明，且相关 Lean 形式化约 1.3 GB、约 1500 万行，研究者在独立复核完成前不应把它当作既定结果使用。

**「社区讨论」** 评论者一方面核对了 Lean 归档的体量（约 1.3GB、1500 万行），并指出另有一份据称完全由人类完成的证明；另一方面有人引用陶哲轩此前对 AI 攻关黎曼猜想的怀疑，也有评论称多路形式验证已足以消除疑问。这些都属于社区意见，不能替代独立验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.unite.ai/levent-alpoges-unverified-riemann-claim-puts-claudes-lean-code-in-focus/">Levent Alpöge’s Unverified Riemann Claim Puts Claude’s Lean ...</a></li>
<li><a href="https://explainx.ai/blog/levent-alpoge-anthropic-riemann-hypothesis-claude-lean-proof-claimed-vs-verified-2026">Riemann Hypothesis Proof Claim: Claimed vs Verified ...</a></li>
<li><a href="https://en.wikipedia.org/wiki/Generalized_Riemann_hypothesis">Generalized Riemann hypothesis - Wikipedia</a></li>
<li><a href="https://www.scientificamerican.com/article/what-the-riemann-hypothesis-proof-really-means-about-ai-and-the-future/">What the Riemann hypothesis proof really... | Scientific American</a></li>

</ul>
</details>

**标签**: `#Riemann Hypothesis`, `#formal verification`, `#Lean`, `#mathematics`, `#AI theorem proving`

---

<a id="item-tech-news-6"></a>
### [陶哲轩博客：无外力纳维-斯托克斯奇点与广义黎曼猜想](https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/) ⭐️ 7.0/10

陶哲轩（Terry Tao）于 2026 年 11 月 20 日在其个人博客发表文章，标题将无外力欧拉方程奇点、无外力纳维-斯托克斯方程奇点与广义黎曼猜想并列讨论。该条目未随附原文正文，因此文章给出的具体命题、证明路径与成立条件无法在此核实，读者需以博客原文为准。Hacker News 上的讨论则明显偏向形式化验证工具与 AI 对数学研究方式的影响，而非结果本身的数学细节。

hackernews · archon1410 · 11月20日 17:21 · [社区讨论](https://news.ycombinator.com/item?id=50578358)

**「背景」** 三维不可压缩纳维–斯托克斯方程解的存在性与光滑性，是克雷数学研究所悬赏 100 万美元的千禧年难题之一，其核心问题是：从光滑初值出发的流体演化能否在有限时间内形成奇点。陶哲轩这篇博客讨论的是无外力情形下的欧拉与纳维–斯托克斯奇点问题，并将其与广义黎曼猜想联系起来；所给材料显示这是博客层面的论述，并未提供经同行评议确认的完整结果。

**「社区讨论」** 有评论者引用 Lean 相关的 Zulip 讨论，称两个相互独立的内核都接受了该结果，因此内核被利用出 bug 的可能性较低——这一说法来自社区，未经独立验证。另有评论者（如 sega\_sai、actusual）表达了职业上的不安，认为 AI 在数学等以“纸笔”推演为主的领域进展迅速，令科研人员的空间变得不确定；也有人追问，这类工作能否创造出新的抽象与概念，而不只是运用既有的 Langlands 纲领等框架。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_existence_and_smoothness">Navier – Stokes existence and smoothness - Wikipedia</a></li>
<li><a href="https://www.youtube.com/watch?v=9gcTWy2pNFU">$1 million dollar unsolved math problem: Navier – Stokes singularity ...</a></li>

</ul>
</details>

**标签**: `#mathematics`, `#Navier-Stokes`, `#Generalized Riemann Hypothesis`, `#formal verification`, `#theorem proving`

---

<a id="item-tech-news-7"></a>
### [语言模型改写自身权重：论文与争议](https://arxiv.org/abs/2611.21885) ⭐️ 7.0/10

一篇 arXiv 预印本《Language Models Can Rewrite Their Own Weights》声称，语言模型能依靠自身推理直接改写权重，在不使用梯度、不进行训练的情况下变好：它在练习题上测试每次编辑、只保留有效修改，并在连续八个会话中保持准确率上升。对关注自修改模型、权重编辑和 AI 安全的研究者而言，这提供了新的讨论对象；但在现有材料中，这仍是论文自身的说法，未见独立复现。Hacker News 评论者则指出，演示出的改进可能只是缩短推理链以避免 token 上限，并质疑这与既有工作的差异。

hackernews · lwhsiao · 11月20日 16:29 · [社区讨论](https://news.ycombinator.com/item?id=50577265)

**「背景」** 大语言模型通常在训练完成后就被冻结，要让它变强，往往需要再做一次训练，或者依赖提示、外部框架和推理时的额外计算，而这些手段在任务结束后并不会留在模型里。该论文（arXiv 2611.21885）把“自我重写”作为第三条路径提出：模型用自己的推理直接修改自身权重，并声称整个过程不依赖梯度、不需要训练。理解“训练后冻结、改进只能靠外部手段”这一前提，才能看清这一说法为何被当作不同的机制来讨论。

**「对开发者的实际含义」** 对照这项演示的开发者应注意，评论者 aesthesia 指出，模型自发做出的唯一有效改动是缩短推理链以避开 token 上限，而不是普遍意义上的能力提升；同一评论者还称，此前的 weight-space programming 实验也只在模型存在这类明显缺陷时才看到改进。因此，目前可支持的用途仅限于在固定 token 预算下让模型自我压缩推理过程；若要把它接入训练或部署流水线，需要先在没有此类明显缺陷的基线上复现出同等收益。

**「社区讨论」** Hacker News 讨论的焦点是新颖性与风险：有评论者认为论文展示的自我改进只是缩短推理链以避开 token 上限，并与近期“权重空间编程”的结果相似；也有人把“无梯度”的表述类比为训练，并担忧自主模型可识别和压制与安全对齐相关的激活。上述均为评论者观点，不是已确认的结论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2611.21885">[2611.21885] Language Models Can Rewrite Their Own Weights</a></li>
<li><a href="https://arxiv.org/pdf/2611.21885v2">Language Models Can Rewrite Their Own Weights - arXiv.org</a></li>

</ul>
</details>

**标签**: `#self-modifying models`, `#weight editing`, `#LLM research`, `#AI safety`, `#arXiv preprint`

---

<a id="item-tech-news-8"></a>
### [Scott Aaronson 博客讨论“随机鹦鹉”与黎曼猜想](https://scottaaronson.blog/?p=10344) ⭐️ 7.0/10

Scott Aaronson 的博客文章以“随机鹦鹉”和黎曼猜想为引子，审视关于这类 AI 系统产出数学突破的声称，并在 Hacker News 上引发讨论。文章把焦点放在机器推理与人类理解上：当模型给出看似完整的数学论述时，读者应如何判断它是否构成可验证的证明。目前提供的材料没有给出具体证明、论文或独立验证细节，因此不能据此认定黎曼猜想已被证明。

hackernews · stratos123 · 11月20日 20:03 · [社区讨论](https://news.ycombinator.com/item?id=50581084)

**「背景」** 黎曼猜想由黎曼在 1859 年提出，断言 ζ 函数的所有非平凡零点实部均为 1/2，是克雷数学研究所的千禧年大奖难题之一。Scott Aaronson 的这篇博文标题以“随机鹦鹉”指代相关 AI 系统，并称其“显然证明了”该猜想；理解这一说法时，关键在于数学证明要求可复核的推导过程，而不只是给出一个结论。

**「影响」** 对使用大语言模型辅助数学或形式化证明的开发者而言，实际影响是验证环节不能省略：模型生成的推导必须经过独立检查或形式化工具验证，不能仅凭叙述连贯就当作证明。

**「社区讨论」** 评论区较有实质内容的讨论集中在“解释”上：janalsncm 认为 Stockfish 的评估看似解释，实质仍是大量计算叠加在 NNUE 评估器上的聚合，无法回答人们想要的“为什么”；jstummbillig 则担心人类在科学与工程上会越来越难以理解，并质疑人类能否接受这种角色。elorant 还反问，如果数学家拥有近乎无限的算力，会有多少人取得类似突破。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://scottaaronson.blog/?p=10344">Shtetl-Optimized » Blog Archive » The stochastic parrots have...</a></li>
<li><a href="https://www.claymath.org/millennium/riemann-hypothesis/">Riemann Hypothesis - Clay Mathematics Institute</a></li>

</ul>
</details>

**标签**: `#AI mathematics`, `#LLM reasoning`, `#AI epistemology`, `#mathematical proof`, `#Hacker News discussion`

---

<a id="item-tech-news-9"></a>
### [Signal 发文讨论限制移动端 AI 代理抓取数据](https://signal.org/blog/protecting-your-privacy/) ⭐️ 7.0/10

Signal 在博客文章中讨论针对 AI 代理与移动操作系统平台数据抓取的隐私防护，涉及跨应用数据泄漏和截屏保护等场景。现有材料没有显示这是一项已交付的功能或具体版本更新，因此目前更像是 Signal 对平台访问边界与透明度的防护主张，而非可验证的已上线能力。

hackernews · dotcoma · 11月20日 09:42 · [社区讨论](https://news.ycombinator.com/item?id=50572348)

**「背景」** Signal 一直以隐私保护为核心使命，并在此前通过截图拦截来应对 Windows Recall 这类会持续记录屏幕内容的功能。此次 Signal 在博客中表示，将限制移动操作系统内置的 AI 代理获取和存储 Signal 数据；相关报道指出，其做法是在 iOS 27 和 Android 上阻止应用内截图，从而避免 Siri、Gemini 等助手读取屏幕内容。

**「影响」** Signal 在 iOS 27 上阻止应用内截图，并在 Android 上拦截 AI 助手发起的屏幕数据抓取，从而切断这些系统上的 AI 代理读取 Signal 聊天内容的通道；代价是用户无法再直接在 Signal 内截图分享或留存对话。

**「社区讨论」** 评论者总体支持限制 AI 代理访问，但在实现路径上有分歧：有人认为仅靠应用层阻止截屏无法长期奏效，应让用户重新掌控操作系统并考虑 GrapheneOS 等替代方案；也有人要求 Signal 公开其取证调查结果，供其他开发者复用。另有用户报告称，Signal 在 VPN 场景下因验证码和反垃圾机制而难以添加联系人，且 Windows 端无法截屏，认为隐私保护不应牺牲基本可用性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://signal.org/blog/protecting-your-privacy/">Signal &gt;&gt; Blog &gt;&gt; Signal is Serious About Protecting Your Privacy</a></li>
<li><a href="https://www.theverge.com/ai-artificial-intelligence/1038390/signal-blocking-ai-agent-screenshots-mobile-app">Signal is blocking Gemini and Siri AI from reading your... | The Verge</a></li>
<li><a href="https://www.securityweek.com/signal-adds-screenshot-blocker-to-thwart-windows-recall/">Signal Adds Screenshot - Blocker to Thwart ‘Windows... - SecurityWeek</a></li>
<li><a href="https://www.theverge.com/ai-artificial-intelligence/1038390/signal-blocking-ai-agent-screenshots-mobile-app">Signal is blocking Gemini and Siri AI from reading your... | The Verge</a></li>
<li><a href="https://signal.org/blog/protecting-your-privacy/">Signal &gt;&gt; Blog &gt;&gt; Signal is Serious About Protecting Your Privacy</a></li>

</ul>
</details>

**标签**: `#privacy`, `#AI agents`, `#mobile security`, `#Signal`, `#platform policy`

---

<a id="item-tech-news-10"></a>
### [美国收紧芯片出口，印度 Yotta 拟增 10 万 GPU](https://www.bloomberg.com/news/articles/2026-11-20/nvidia-scandal-fallout-india-ai-yotta-ambani-adani-am-intelligence-e2e-networks) ⭐️ 7.0/10

据彭博社报道，美国收紧对马来西亚、泰国和新加坡的先进芯片出口，印度 AI 业界认为这为承接外溢的算力需求提供了机会。Yotta 表示，未来一年将新增约 10 万块 GPU，相当于把印度现有算力提高约 10%。印度目前有 153 个数据中心，数量居全球第 14；信实承诺投入至多 1100 亿美元、阿达尼承诺投入 1000 亿美元建设 AI 基础设施。报道同时指出，印度长期受算力基础设施短缺和资本受限拖累。

telegram · zaihuapd · 11月20日 07:31

**「背景」** 这轮扩张建立在今年早些时候宣布的一批大型项目之上：据《经济时报》和《福布斯》报道，信实工业承诺七年内投入至多 1100 亿美元，阿达尼集团计划到 2035 年投入 1000 亿美元建设 AI 数据中心。Yotta 的 GPU 采购计划因此是在印度已有大规模数据中心投资、但本地算力基数仍小的背景下提出的。

**「影响」** 对在印度布局算力的企业而言，短期可观察到的增量主要是 Yotta 宣称的约 10 万块 GPU，这只相当于印度现有算力的约 10%；信实和阿达尼的 1100 亿美元与 1000 亿美元属于投资承诺，不能当作已经上线的数据中心容量。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://economictimes.indiatimes.com/tech/artificial-intelligence/reliance-puts-110-billion-on-table-joins-adani-tata-in-big-ticket-ai-buildout/articleshow/128589413.cms">Reliance puts $110 billion on table, joins Adani &amp; Tata in ...</a></li>
<li><a href="https://www.forbes.com/sites/yessarrosendar/2026/09/30/the-billionaires-backing-indias-massive-ai-infrastructure-buildout/">The Billionaires Backing India’s Massive AI Infrastructure ...</a></li>

</ul>
</details>

**标签**: `#AI infrastructure`, `#chip export controls`, `#India AI`, `#GPU capacity`, `#data centers`

---

<a id="item-tech-news-11"></a>
### [OpenAI 后台模式支持 8 小时长任务，Token 费率最高降 40%](https://developers.openai.com/api/docs/guides/background) ⭐️ 7.0/10

据该 Telegram 消息，OpenAI 为 API 长耗时请求新增后台模式：开发者设置 background: true，并通过 background\_options.completion\_window 选择 2 小时或 8 小时完成时限；不设置则采用默认的 soonest，且没有折扣。选择 2h 或 8h 时，Token 费率分别比标准价低 30% 和 40%，目前该折扣在 GPT-6.2 Astra、GPT-6.2 Sol、GPT-6.1 Terra 和 GPT-6 Luna 上公测。后台模式还会临时存储响应数据，即使 store 设为 false 或启用零数据保留也不例外。

telegram · zaihuapd · 11月20日 11:15

**「背景」** OpenAI API 此前已为可等待的工作负载提供 Batch API 和 Flex processing 等低于标准价的处理方式。此次后台模式的差别在于把异步执行放到单个请求上，开发者设置 background: true 后可轮询响应对象获取状态，而不是仅面向批量作业。

**「影响」** 对需要运行长任务的开发者，这提供了用更长完成时限换取 30% 至 40% Token 折扣的选项；但处理敏感数据的团队需先确认临时存储是否满足合规要求，因为该模式在 store=false 或零数据保留下仍会保留响应数据。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://developers.openai.com/api/docs/guides/background">Background mode | OpenAI API</a></li>
<li><a href="https://developers.openai.com/api/docs/guides/cost-optimization">Cost optimization | OpenAI API</a></li>

</ul>
</details>

**标签**: `#OpenAI API`, `#background processing`, `#async inference`, `#API pricing`, `#data retention`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [为什么缓存 LLM 输出收效甚微](https://seangoedecke.com/why-output-caching-doesnt-work/) ⭐️ 6.0/10

rss · Sean Goedecke · 11月21日 00:00

**「背景」** LLM 推理成本优化通常依赖输入缓存，避免每轮重算对话历史，但作者认为把同样思路用于输出缓存并不能带来多少节省。

**「方案」** 输出缓存看似有吸引力：编码 agent 常复述代码，调研 agent 会引用证据文档，而输出 token 又比输入 token 贵得多；作者设想的办法是让模型只输出“文件:行号”或历史片段引用，再由代理执行框架（harness）展开。但他指出，这只优化用户可见的重复，模型内部推理未必需要复述；据其自身 agent 历史估计，可见输出仅约 6%，推理 token 占 50%、工具调用占 44%。按 Amdahl 定律（局部优化受占比上限约束），即使乐观地省掉可见输出的三分之二，也只减少约 4% 的总输出 token。真正要降成本，应压缩占 94% 的不可见输出，这更依赖模型智能与 harness 效率；更贵的模型可能单 token 贵 5 倍，却因少用 6 倍 token 而总成本更低。作者也承认 6% 只是个人样本，关于前沿模型思维链不重复的判断带有推测性，并提到推测解码可能已利用重复模式获得速度收益，但这不等于降低 token 成本。

**「启示」** 作者的核心论点是，输出缓存受限于可见输出这块很小的比例，难以成为 LLM 成本优化的主线；更大的杠杆在于提升模型和 harness 的 token 效率，让推理与工具调用本身更精简。

**标签**: `#LLM inference costs`, `#output token caching`, `#agent workflows`, `#Amdahl&\#x27;s law`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美国企业由回购转向净发股，牛市面临新增供给](https://www.cnbc.com/2026/11/20/equity-issuance-bull-market-problem.html) ⭐️ 8.0/10

据 Acadian Asset Management 的分析，美国公司已从 2024 年的净回购转为净发行股票，截至上周晚些时候，净股票发行规模相当于美国股市总市值的 3.1%，为持续四年的牛市增加供给。

rss · CNBC Finance · 11月20日 14:15

**「背景」** 过去几年，美国公司一直是股票的净回购方：回购减少了市场上可交易的股份数量，在资金追逐更少股票的情况下帮助推高股价，同时也压低了计算每股收益时的分母（即总股本）。Acadian 的分析认为这一趋势已经逆转，公司在 2026 年转为净发行股票；Baker 与 Wurgler 的研究则发现，当企业相对于债务更多地发行股票时，随后的股市回报往往偏低。

**「影响」** 这可能成为股市估值的逆风：新股供给增加会削弱回购通过减少流通股对股价和每股收益的支撑，投资者需要吸收包括 Anthropic 规模 810 亿美元 IPO 在内的新增发行。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.econstor.eu/bitstream/10419/230674/1/1748697749.pdf">Market sentiment, financial fragility, and economic activity: The role of...</a></li>
<li><a href="https://www.semanticscholar.org/paper/The-Equity-Share-in-New-Issues-and-Aggregate-Stock-Baker-Wurgler/14be014490dc773638650618a432fbc7d50a13c5">[PDF] The Equity Share in New Issues and Aggregate Stock Returns</a></li>

</ul>
</details>

**标签**: `#equity issuance`, `#buybacks`, `#IPO market`, `#AI infrastructure`, `#market liquidity`

---

<a id="item-finance-news-2"></a>
### [沃什回避利率指引，美联储官员公开表态增多并现加息分歧](https://www.cnbc.com/2026/11/20/warsh-fed-forward-guidance-rate-hikes.html) ⭐️ 7.0/10

CNBC 报道，美联储主席凯文·沃什上任六个月来刻意不提供利率前瞻指引，其他官员则公开表态增多，并在是否及多快加息上出现分歧。据 CME Group 的 FedWatch，交易员认为 12 月至少加息 25 个基点的概率为 100%，美国银行分析则称过去两周官员发言量为 2025 年初以来同期最多。

rss · CNBC Finance · 11月20日 21:10

**「背景」** 制定利率的联邦公开市场委员会（FOMC）有 19 名参与者，主席通常通过表态让市场判断主张加息者还是主张观望者占上风；沃什认为前瞻指引会提前束缚决策，美国银行称这一缺位可能促使两派官员更频繁、更强硬地发声。

**标签**: `#Federal Reserve`, `#interest rates`, `#monetary policy`, `#FOMC`, `#forward guidance`

---

<a id="item-finance-news-3"></a>
### [北京拟明确租房正常损耗不得扣减押金](https://mp.weixin.qq.com/s/PmGxh5knIyxiBRhpRoJnoQ) ⭐️ 7.0/10

北京市住建委与市场监管局起草的《北京市住房租赁合同（示范文本）（修订征求意见稿）》自 11 月 20 日起公开征求意见，拟明确承租人正常使用造成的房屋正常损耗不承担赔偿责任，出租人不得以此为由扣减押金；征求意见稿还要求从事转租经营的租赁企业将租金和押金付至监管账户，并新增保密和个人信息保护条款。

telegram · zaihuapd · 11月20日 13:46

**「背景」** 此次修订的是北京市住房租赁合同的示范文本，由北京市住建委与市场监管局起草，自 11 月 20 日起公开征求意见；示范文本为租赁双方提供合同模板，征求意见稿正是在这一模板中拟新增“正常损耗不得扣减押金”的条款。

**「影响」** 若草案最终实施，北京租客在退租时可依据合同文本对抗“正常磨损”扣款，而从事转租的租赁企业须将租金和押金放入监管账户，资金使用受到托管约束。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://house.cnr.cn/rdtj/20250710/t20250710_527254499.shtml">北 京 加强个人“二 房 东” 监 管 促进 住 房 租 赁 市场健康发展_央广网</a></li>

</ul>
</details>

**标签**: `#housing rental regulation`, `#tenant rights`, `#deposit protection`, `#Beijing policy`, `#rental market`

---