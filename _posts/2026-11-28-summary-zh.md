---
layout: default
title: "Horizon Summary: 2026-11-28 (ZH)"
date: 2026-11-28
lang: zh
---

> 从 30 条内容中筛选出 9 条重要资讯。

---

**科技新闻**
1. [Google Research 提出 DeepCrossAttention 残差连接，宣称最高 3 倍加速](#item-tech-news-1) ⭐️ 7.0/10
2. [热门购物网站出现滥用 WebRTC 的盗刷脚本](#item-tech-news-2) ⭐️ 7.0/10
3. [Convex AI 编码 skill 被指未告知上传应用创意](#item-tech-news-3) ⭐️ 7.0/10
4. [计算机验证的证明也可能为假：检查器健全性争议](#item-tech-news-4) ⭐️ 7.0/10
5. [SemiAnalysis 微基准：Trainium3 每美元推理性能仅次于 Vera Rubin](#item-tech-news-5) ⭐️ 7.0/10
6. [OpenSec 称 Linux nfsd 存在 9.8 分预认证漏洞](#item-tech-news-6) ⭐️ 7.0/10
7. [《我的世界》基岩版资源包漏洞于 26.65 修复](#item-tech-news-7) ⭐️ 7.0/10

**财经新闻**
1. [国常会部署完善资本市场稳市机制](#item-finance-news-1) ⭐️ 7.0/10
2. [央行公布大额存单新规 个人起购门槛降至 10 万元](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Google Research 提出 DeepCrossAttention 残差连接，宣称最高 3 倍加速](https://research.google/blog/supercharging-transformer-residual-connections/) ⭐️ 7.0/10

Google Research 在一篇研究博客中介绍了 DeepCrossAttention，这是一种面向 Transformer 残差连接的架构改动，宣称能在模型质量相当的情况下带来最高 3 倍的速度提升。该结果目前仅来自研究博客的公告，尚无独立复现或第三方测量，因此 3 倍加速应视为研究团队的声明，而不是已经验证的性能结论。

hackernews · ComputedCamp995 · 11月27日 23:06 · [社区讨论](https://news.ycombinator.com/item?id=50672565)

**「背景」** 传统 Transformer 的残差连接会把各层输出直接累加到同一条表示流中，深层网络中较早层的信息可能因此被稀释。Google Research 提出的 DeepCrossAttention 改用可学习权重和跨层交叉注意力来动态组合先前各层的输出，并称仅增加极少量参数。

**「社区讨论」** 评论区中，pollorollo 批评结果展示不应使用折线图，因为各方法之间不存在时间或连续关系，应改用柱状图；yieldcrv 则追问该方法能否与 MTP、Dflash 等已有优化叠加，把吞吐提升到 30 倍 tokens/秒。这些是评论者的质疑和提问，并不构成对 3 倍加速声明的独立验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://research.google/blog/supercharging-transformer-residual-connections/">Supercharging transformer residual connections - Google Research</a></li>
<li><a href="https://arxiv.org/abs/2502.06785">[2502.06785] DeepCrossAttention: Supercharging Transformer ...</a></li>

</ul>
</details>

**标签**: `#transformers`, `#model efficiency`, `#Google Research`, `#deep learning architecture`, `#residual connections`

---

<a id="item-tech-news-2"></a>
### [热门购物网站出现滥用 WebRTC 的盗刷脚本](https://www.infohawk.com/news/2026-11-27-black-friday-webrtc-skimmer) ⭐️ 7.0/10

一篇提交至 Hacker News 的报道称，热门购物网站中发现滥用 WebRTC 的信用卡盗刷脚本；现有材料只有标题和评论，没有文章正文，因此受影响站点、脚本数量和发现时间均不明确。评论者认为，问题不在 WebRTC 本身，而在于电商页面嵌入的第三方脚本难以被持续监控，攻击者只是借 WebRTC 规避检测，同样手法也可用普通 HTTP 请求实现。有评论者称，攻击者只针对移动设备是为了降低被发现概率，但这一说法未获现有材料独立验证。

hackernews · scanr · 11月27日 15:40 · [社区讨论](https://news.ycombinator.com/item?id=50668145)

**「背景」** 评论所讨论的信用卡盗刷脚本，是指在电商结账页面植入恶意 JavaScript、窃取支付信息的攻击；评论者强调，真正的入口通常是网站嵌入的第三方脚本，而不是 WebRTC 本身。WebRTC 是浏览器内置的实时通信接口，可用于建立网络连接；按评论者的说法，它只是较少被用于监测恶意行为的通道，类似手法也可用普通 HTTP 请求实现。

**「影响」** 对电商运营者而言，只要页面继续嵌入可执行任意 JavaScript 的第三方脚本，风险就不限于支付表单本身；按评论者的说法，封禁 WebRTC 并不能消除同类盗刷，关键仍是控制第三方代码的加载与执行。

**「社区讨论」** 讨论集中在责任归属：有评论者认为这证明拦截广告和第三方脚本合理，也有人强调 WebRTC 只是较少被监控的通道，根因是站点允许第三方代码在浏览器中执行。另有评论提出浏览器应只渲染数据、广告脚本应被沙箱化，但这些属于观点，现有材料未显示已有对应实现。

**标签**: `#web security`, `#credit card skimming`, `#WebRTC`, `#third-party scripts`, `#e-commerce`

---

<a id="item-tech-news-3"></a>
### [Convex AI 编码 skill 被指未告知上传应用创意](https://github.com/convex/convex-backend-skill/issues/64) ⭐️ 7.0/10

一份针对 Convex 的 GitHub issue 指控其 AI 编码 skill 在未明确告知的情况下，把用户的应用创意上传到远程服务器，涉及使用该工具构建应用的开发者。Convex CEO Jamie 在讨论中回应称，该插件中的提示上传用于支撑 Convex 的“quickstart”功能，并提到公司近期关闭了端到端 vibe-coding 产品 Convex Chef。现有信息主要是这项指控和厂商解释，尚无独立验证，也未说明上传数据的范围、保留时间或是否可关闭。

hackernews · MickyTheMouse · 11月27日 18:02 · [社区讨论](https://news.ycombinator.com/item?id=50669765)

**「背景」** Convex 是托管式后端平台，开发者把数据和代码存放在其服务器上，并通过它的 AI 网关构建应用或为应用内功能提供模型能力；此次争议中的上传行为，发生在其提供给 AI 编码工具调用的 skill（插件）里。据该公司 CEO 在讨论串中说明，Convex 近期关停了端到端的“vibe-coding”产品 Convex Chef，而这个插件中的 prompt 上传正是为“quickstart”功能服务，他称该功能是 Chef 的延续。

**「影响」** 使用该 skill 的开发者需要把“提示是否离开本地”纳入审查：CEO 的回应确认插件存在提示上传并用于 quickstart，但可见说明没有交代数据保留、访问权限或关闭方式。涉及保密产品创意的团队在厂商补齐这些信息前，可能需要避免把未公开方案交给该流程处理。

**「社区讨论」** 在 CEO 解释提示上传用于 quickstart 后，有评论者认为长期方向是自托管开源权重模型，也有人强调信任是这类工具的核心问题；另有评论指出，相比模型主动发起恶意工具调用，提示注入更常见。这些均为评论者观点，未附独立证据。

**标签**: `#AI coding tools`, `#privacy`, `#data exfiltration`, `#developer trust`, `#prompt security`

---

<a id="item-tech-news-4"></a>
### [计算机验证的证明也可能为假：检查器健全性争议](https://cr.yp.to/proofs/falseccp.html) ⭐️ 7.0/10

cr.yp.to 上的一篇技术文章讨论“经计算机检查的证明”仍可能因证明检查器的健全性（soundness）缺陷而为假，重点不是数学证明本身，而是验证工具是否可信。Hacker News 讨论中提到的具体防线包括：Lean 社区已知并持续处理健全性 bug；Metamath 的 set.mm 和 iset.mm 要求证明通过 5 个独立开发、分别用 5 种语言实现的验证器。评论者强调，单个检查器被攻破不等于能骗过数学界，还需同时绕过其他检查器并通过非形式化审阅。

hackernews · \_tk\_ · 11月27日 15:26 · [社区讨论](https://news.ycombinator.com/item?id=50667989)

**「背景：可靠性缺陷与检查器清单」** 所谓“可靠性缺陷”（soundness bug），是指证明检查器错误地接受了本应拒绝的证明步骤，从而可能让假命题通过机器检验；DJB 的页面正是收集此类已被报告、部分已被演示可利用的案例。该页面覆盖 HOL Light、Mizar、Metamath、Isabelle、Lean、HOL98/HOL4 与 Coq/Rocq 七套系统，他在发布帖中称共链接了 199 条可靠性缺陷报告。

**「影响」** 对依赖 Lean、Metamath 等证明助手的人而言，实际保障来自独立验证器与人工审阅的组合，而不是某一个检查器的“通过”结果；只运行单一检查器会把健全性 bug 直接变成错误证明被接纳的风险。

**「社区讨论」** 评论区的分歧在于风险有多大：twotwotwo 和 dwheeler 认为多重独立验证器大幅降低了假证明被接受的概率，gr\_norm 则称相关健全性 bug 少到几乎能塞进一条推文，对绝大多数软件已经足够。andai 补充了另一类问题：自动代理可能证明的是自己对需求的错误理解，而不是用户真正想要的性质。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://cr.yp.to/proofs/falseccp.html">False computer-checked proofs (djb) - cr.yp.to</a></li>
<li><a href="https://x.com/hashbreaker/status/2120889008389837049">Daniel J. Bernstein on X: &quot;Posted new page &quot;False computer ...</a></li>
<li><a href="https://news.lavx.hu/article/d-j-bernstein-catalogs-soundness-bugs-in-seven-proof-checkers">D. J. Bernstein catalogs soundness bugs in seven proof ...</a></li>

</ul>
</details>

**标签**: `#formal verification`, `#proof assistants`, `#soundness bugs`, `#Lean`, `#Metamath`

---

<a id="item-tech-news-5"></a>
### [SemiAnalysis 微基准：Trainium3 每美元推理性能仅次于 Vera Rubin](https://newsletter.semianalysis.com/p/trainium3-inferencex) ⭐️ 7.0/10

SemiAnalysis 发布了对 AWS Trainium3 的推理与微架构深度分析，并称 Trainium3 与 TPU 已上线其 InferenceX 基准平台，与 TPUv7、Nvidia Rubin NVL72、OpenAI Jalapeño、AMD 等加速器同列对比。在 AgentX 端到端智能体推理测试（回放真实编码智能体会话到 Trainium3 服务器）中，Trainium3 搭配 PDS 与 vLLM 的每美元吞吐（perf/$ TCO）在整个 TCO–p90 交互性曲线上优于除 Vera Rubin 之外的所有加速器；文章还称其在生成 token 的 TCO 上与 Nvidia GB300「互有胜负甚至领先」。微架构上，Trainium 以 tile 为第一类原语、从零为 ML 负载设计，其 Descriptor Generation Engine（DGE，对应 Nvidia TMA 与 AMD MI455X TDM）在微基准中可于较小消息尺寸下达到峰值 HBM 带宽利用率，而文章称这在 Nvidia GPU 上无法实现。需要说明的是，这些数字出自 SemiAnalysis 自有的 UBenchX/InferenceX 测试方法，AWS Annapurna Labs 团队参与了架构讲解与实验验证，且公开摘录在结论段处被截断。

rss · Semianalysis · 11月27日 15:54

**「背景」** 要理解这篇分析，需要先知道两条不同的架构路线：Nvidia 的数据中心 GPU 源自图形渲染架构，2017 年以来逐代加装 AI 专用单元——Volta 的 Tensor Core、Hopper 的 TMA、Blackwell 的 Tensor Memory；AWS Trainium 则从一开始就按机器学习负载设计，把 tile 作为一等原语。SemiAnalysis 此次正是围绕这一差异，用微基准测试比较 Trainium3 的推理表现。

**「对推理硬件选型的影响」** 对正在评估推理硬件的团队而言，SemiAnalysis 的 AgentX 回放测试称，Trainium3 UltraServer 在某一测试点上每美元估算基础设施成本生成的 token 数达到 Nvidia GB300 NVL72 的 2.28 倍；在整条 TCO 对 p90 交互性曲线上，Trainium3 PDS + vLLM 除 Vera Rubin 外优于其他所有加速器。该结果来自 SemiAnalysis 的 UBenchX/AgentX 基准而非独立生产测量，企业仍应结合自身模型、延迟目标和软件适配成本做选型验证，不宜把这一比值直接视为生产环境承诺。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://cryptobriefing.com/trainium3-nvidia-gb300-inference-benchmark/">Trainium3 competes with Nvidia GB300 in inference performance ...</a></li>
<li><a href="https://thedefiant.io/frontier/ai/amazon-s-trainium3-shows-cost-edge-in-ai-benchmark">Amazon’s Trainium3 Shows Cost Edge in AI Benchmark</a></li>

</ul>
</details>

**标签**: `#Trainium3`, `#AWS`, `#AI hardware`, `#inference`, `#microarchitecture`

---

<a id="item-tech-news-6"></a>
### [OpenSec 称 Linux nfsd 存在 9.8 分预认证漏洞](https://opensec.in/blog/nfs2root-cve-2026-99362) ⭐️ 7.0/10

据 Telegram 频道转述 OpenSec 博客，Linux 内核 NFS 服务器组件 nfsd 存在被命名为 CVE-2026-99362 的预认证堆溢出漏洞，CVSS 评分为 9.8；攻击者无需登录，仅通过发往 tcp/2049 的连接即可越界写入内核堆并获取 root，启用 NFSv4.1 或 4.2 的文件服务器、NAS 和集群存储节点受影响，该来源称漏洞自 2014 年的 Linux 3.16 起存在。修复版本列为 6.12.117、6.18.61、7.3.2 和 7.4-rc1，需升级内核并重启；无法立即升级者可限制 tcp/2049 访问。CVE 据称于 2026 年 11 月 20 日公开。上述 CVE 编号、版本和影响范围来自单一转述来源，尚未获得独立核实。

telegram · zaihuapd · 11月27日 12:57

**「背景」** nfsd 是 Linux 内核内的 NFS 服务端实现，默认监听 tcp/2049；NFSv4.1 与 4.2 是常见的默认协议版本，所以只要该端口对外可达，内核在完成任何身份验证之前就必须先解析客户端请求，这正是无需凭据即可触发堆溢出的入口。BleepingComputer 等报道称该缺陷在代码中已存在约 12 年，与来源所称自 2014 年 Linux 3.16 起存在相符。

**「受影响资产需升级内核或限制 2049 端口」** 运行 NFSv4.1 或 4.2 且对不可信网络开放 tcp/2049 的文件服务器、NAS 和集群存储节点应优先处置：按披露升级到 6.12.117、6.18.61、7.3.2 或 7.4-rc1 并重启；无法立即升级时，应在上游防火墙限制 tcp/2049 访问，以阻断未认证攻击路径。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://opensec.in/blog/nfs2root-cve-2026-99362">NFS2ROOT ( CVE - 2026 - 99362 ): pre-auth root in Linux nfsd | OpenSec</a></li>
<li><a href="https://www.bleepingcomputer.com/news/security/new-nfs2root-linux-flaw-can-let-attackers-gain-root-privileges/">New NFS2ROOT Linux flaw can let attackers gain root privileges</a></li>
<li><a href="https://opensec.in/blog/nfs2root-cve-2026-99362">NFS2ROOT ( CVE - 2026 - 99362 ): pre-auth root in Linux nfsd | OpenSec</a></li>
<li><a href="https://www.getpagespeed.com/server-setup/security/nfs2root-cve-2026-99362-centos-7">NFS2ROOT ( CVE - 2026 - 99362 ) on CentOS 7: Fixed Kernel</a></li>

</ul>
</details>

**标签**: `#Linux kernel`, `#security vulnerability`, `#NFS`, `#remote exploitation`, `#patching`

---

<a id="item-tech-news-7"></a>
### [《我的世界》基岩版资源包漏洞于 26.65 修复](https://www.zaikei.co.jp/article/20261119/878386.html) ⭐️ 7.0/10

《我的世界》基岩版被报告存在资源包漏洞：带有 content.zipe 文件的资源包可改动游戏界面框架 Ore UI 的文件并运行隐藏脚本。附加组件开发者 8Crafter 于 11 月 15 日在 Reddit 公开该问题，称已确认影响 26.52 至 26.63 版本，更早版本也可能受影响，覆盖 PC、手机和主机，Java 版不受影响。加入服务器或 Realm 且开启资源包自动下载时，玩家可能无需手动安装就收到问题文件；所列利用方式包括删除全部存档、获取玩家 IP，以及在 Windows 特定条件下无提示打开任意 URI、启动资源包内的批处理文件下载恶意软件。Mojang 已在 26.65 版修复，AxmBro 发布的 Windows 只读检测工具可查找 content.zipe，但不能判定资源包是否恶意；所给汇总未附官方公告或 CVE 级技术细节。

telegram · zaihuapd · 11月27日 18:04

**「背景」** 《我的世界》基岩版的资源包可用于替换材质和界面；当玩家加入服务器或 Realm 并开启自动下载时，资源包会不经手动安装直接应用到客户端。此次问题中，资源包携带的 content.zipe 能修改 Ore UI 的界面文件并执行隐藏脚本，因此自动下载成为攻击入口。

**「影响与处置」** 仍在使用 26.52 至 26.63 的玩家应升级至 26.65；若不能立即升级，加入服务器或 Realm 时关闭资源包自动下载，可降低无需手动确认就接收问题资源包的风险。

**标签**: `#Minecraft Bedrock`, `#security vulnerability`, `#resource packs`, `#game security`, `#auto-download`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [国常会部署完善资本市场稳市机制](https://www.tmtpost.com/nictation/8220182.html) ⭐️ 7.0/10

11 月 27 日，国务院常务会议由总理李强主持，部署持续完善资本市场稳市机制，要求加力发挥“国家队”稳市作用、进一步优化中央汇金公司的类“平准基金”功能，并完善保险、企业年金、社保基金等中长期资金入市支持引导政策。会议未公布具体规模、工具安排或时间表。

telegram · zaihuapd · 11月27日 05:35

**「背景」** 国务院常务会议是国务院部署重要政策工作的会议机制；“国家队”在此指以中央汇金公司为代表的国有稳市资金，而“平准基金”通常指通过逆向买卖平抑市场波动、提供流动性支持的资金安排。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cls.cn/detail/2546318">cls.cn/detail/2546318</a></li>
<li><a href="https://finance.eastmoney.com/a/202611273941564045.html">finance.eastmoney.com/a/202611273941564045.html</a></li>

</ul>
</details>

**标签**: `#中国资本市场`, `#国常会`, `#中央汇金`, `#平准基金`, `#中长期资金`

---

<a id="item-finance-news-2"></a>
### [央行公布大额存单新规 个人起购门槛降至 10 万元](https://www.news.cn/fortune/20261127/70789d77822242cc82216f51a416f872/c.html) ⭐️ 7.0/10

中国人民银行公布大额存单管理办法，将个人和机构认购起点分别降至 10 万元和 500 万元，并同步发布要求金融机构自主定价的存贷款利率管理规定，均于 2027 年 3 月 21 日施行。

telegram · zaihuapd · 11月27日 11:36

**标签**: `#中国央行`, `#大额存单`, `#存款利率`, `#金融监管`, `#个人理财`

---