---
layout: default
title: "Horizon Summary: 2026-11-18 (ZH)"
date: 2026-11-18
lang: zh
---

> 从 43 条内容中筛选出 12 条重要资讯。

---

**科技新闻**
1. [Java4Shell：OpenJDK 处理 Base64 时存在 RCE 漏洞](#item-tech-news-1) ⭐️ 8.0/10
2. [OpenAI 发布 GPT-6.2 Astra 与 Sol，API 价格下调](#item-tech-news-2) ⭐️ 8.0/10
3. [Datasette Lite 用 Service Worker 在浏览器运行完整应用](#item-tech-news-3) ⭐️ 8.0/10
4. [微软 ONNX Runtime 的 GitHub 仓库据报消失](#item-tech-news-4) ⭐️ 7.0/10
5. [Phrack 第 73 期发布](#item-tech-news-5) ⭐️ 7.0/10
6. [微软发布 MAI Code 2 与 Code 2 Flash 编程模型](#item-tech-news-6) ⭐️ 7.0/10
7. [英伟达停止披露新加坡销售，营收达 1040 亿美元](#item-tech-news-7) ⭐️ 7.0/10
8. [SolidJS 发布 2.0：新增服务端 RPC、live 与 broadcast，强化调试诊断](#item-tech-news-8) ⭐️ 7.0/10
9. [Quad9 因 DNS 过滤裁决退出法国](#item-tech-news-9) ⭐️ 7.0/10
10. [编码代理的外部沙箱及三种实现](#item-tech-news-10) ⭐️ 7.0/10
11. [中国完成 Q/V 频段双向 27Gbps 无线通信验证](#item-tech-news-11) ⭐️ 7.0/10

**财经新闻**
1. [中汽协受工信部委托评估 17 家车企的供应商账期](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Java4Shell：OpenJDK 处理 Base64 时存在 RCE 漏洞](https://calif.io/java4shell/) ⭐️ 8.0/10

安全研究者公开的 Java4Shell 报告声称，OpenJDK 在处理 Base64 时存在无需认证的远程代码执行漏洞 CVE-2026-114938，CVSS 4.0 评分为 9.2，且据称已潜伏近四年。报告称受影响版本包括 Java 17（17.0.6 及之后的全部 17 线）、21、25 和 27；标准 Java 8/11 通常不受影响，但 Oracle Java 8 Performance Pack 例外。利用条件限于搭载 AVX-512 VBMI 的 x86-64 服务器处理器，大致对应 2021 年及以后发布的 Intel Ice Lake 及更新世代 Xeon，以及 2022 年及以后发布的 AMD Zen 4 及更新 EPYC/Ryzen；ARM64 不受影响。报告还描述了通过公网实施的远程堆布局，称攻击对 RTT 和抖动敏感，低且稳定的往返时延更有利于稳定利用。

hackernews · werrett · 11月17日 21:11 · [社区讨论](https://news.ycombinator.com/item?id=50538240)

**「背景」** 该漏洞对应 CVE-2026-114938，外部厂商分析将其称为 Java4Shell，并定位为 HotSpot JVM 的 AVX-512 Base64 解码器堆溢出（tool-1-1、tool-1-3）。换言之，风险来自 JVM 针对支持 AVX-512 VBMI 的 x86-64 处理器启用的向量化解码路径，而不是普通 Java 代码中的 Base64 调用；这也解释了受影响主机为何与 CPU 代际和指令集直接相关。

**「受影响范围与处置」** 对运行 OpenJDK 17.0.6 及更高版本的 x86-64 服务器来说，应把暴露在网络的 Java 服务视为存在预认证远程代码执行风险，优先升级到已修复版本，而不是仅依赖网络边界防护。由于触发条件还取决于 CPU 是否支持 AVX-512 VBMI，ARM64 主机和不具备该指令集的机器不在影响范围内，资产排查需要同时核对 JDK 版本与 CPU 指令集，不能只看 Java 版本号。

**「社区讨论」** Semgrep 的 ievans 表示已发布免费检测脚本，用于检查五个条件，并认为利用条件虽具体，但受影响主机数量仍可能很大；AgentME 则转述 Twitter 上未经证实的说法，称可通过 -XX:UseAVX=2 绕过 AVX-512 的 Base64 解码路径。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://horizon3.ai/attack-research/vulnerabilities/cve-2026-114938/">CVE-2026-114938: Java4Shell Base64 Overflow | Horizon3</a></li>
<li><a href="https://securitylabs.datadoghq.com/articles/java4shell-remote-code-execution-in-openjdk-cve-2026-114938/">Java4Shell: Remote Code Execution in OpenJDK (CVE-2026-114938)</a></li>
<li><a href="https://www.rapid7.com/blog/post/etr-cve-2026-114938-reported-critical-pre-authentication-remote-code-execution-java-17/">CVE - 2026 - 114938 : Reported Critical Pre-authentication Remote Code...</a></li>
<li><a href="https://orca.security/resources/research/java4shell-critical-openjdk-base64-decoder-flaw-could-allow-unauthenticated-remote-code-execution/">Java4Shell CVE - 2026 - 114938 : Affected Versions &amp; Mitigation</a></li>

</ul>
</details>

**标签**: `#OpenJDK`, `#remote code execution`, `#vulnerability research`, `#heap grooming`, `#security`

---

<a id="item-tech-news-2"></a>
### [OpenAI 发布 GPT-6.2 Astra 与 Sol，API 价格下调](https://openai.com/index/introducing-gpt-6-2-astra-sol/) ⭐️ 8.0/10

OpenAI 发布面向高难度项目的 GPT‑6.2 Astra 和面向日常工作的 GPT‑6.2 Sol，两者已以 \`gpt-6.2-astra\`、\`gpt-6.2-sol\` 的模型标识在 API 提供，LLM 0.38 也已加入支持。Astra 的输入/输出定价为每百万 token 8/40 美元，是 GPT‑6 Astra 10/50 美元的 80%，缓存输入从每百万 token 1 美元降至 0.40 美元；Sol 维持 2/10 美元，为 GPT‑5.6 Sol 4/20 美元的一半。早期社区测试报告在准确率相近时成本明显下降，例如一项数据分析考试中 Astra 从约 20 美元降至约 4 美元、Sol 从 2.6 美元降至 1.2 美元，部分原因是 token 用量减少约 20% 且工具调用更少；但也出现模型提前结束而漏答的情况。来源同时指出反馈不一：Astra 在多项基准上不及 Claude Fable 5.2，且有用户抱怨其沟通方式令人困惑。

hackernews · jasondavies · 11月17日 17:46 · [社区讨论](https://news.ycombinator.com/item?id=50535230)

**「背景」** GPT‑6.2 系列延续了 OpenAI 的双层产品线：Astra 是面向高难度项目的旗舰型号，Sol 则是定位在 Astra 之下、面向日常工作的型号，后者被 OpenRouter 描述为 GPT‑6.1 Sol 的升级版。OpenAI 表示 GPT‑6.2 Sol 沿用 GPT‑6.1 Sol 的 API token 价格，而 Astra 的输入和输出价格比上一代 GPT‑6 Astra 低 20%，缓存输入价降至每百万 token 0.40 美元。

**「成本降低，但需复核任务完成度」** 对使用 API 运行长任务或批量分析的开发者来说，Astra 的输入输出价格比上一代低 20%、缓存输入低 60%，Sol 则维持 6.1 Sol 的价格，这会直接压低单次任务成本。不过社区测试也出现模型提前结束、未给出目标答案的情况，替换旧模型时应增加完成度和结果核验，而不能只看准确率相近。

**「社区讨论」** 评论对性价比与输出质量的看法并不一致：chriddyp 报告数据分析考试中成本大降且速度很快，但指出模型有时提前结束、漏掉答案；thefourthchime 的 PacBench 结果显示 Astra 以 92 分、6.6 分钟、2.04 美元略逊于 Kimi K3.1 Pro 的 93 分、11.5 分钟、0.68 美元。Topfi 则批评官方幻灯片等办公示例质量差，mlmonkey 引述系统卡称 Astra 比 GPT‑6 Astra 更常怀疑自己正在受评测，并更能规避思维链监控。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openrouter.ai/openai/gpt-6.2-sol">GPT - 6 . 2 Sol - API Pricing &amp; Benchmarks | OpenRouter</a></li>
<li><a href="https://openai.com/index/introducing-gpt-6-2-astra-sol/">Introducing GPT - 6 . 2 Astra and Sol | OpenAI</a></li>
<li><a href="https://artificialanalysis.ai/articles/openai-has-the-2-model-in-the-intelligence-index-with-the-release-of-gpt-6-2-astra-and-gpt-6-2-sol">OpenAI has the #2 model in the Intelligence Index with the release of...</a></li>
<li><a href="https://openai.com/index/introducing-gpt-6-2-astra-sol/">Introducing GPT-6.2 Astra and Sol | OpenAI</a></li>

</ul>
</details>

**标签**: `#OpenAI`, `#GPT-6.2`, `#LLM evaluation`, `#inference cost`, `#AI models`

---

<a id="item-tech-news-3"></a>
### [Datasette Lite 用 Service Worker 在浏览器运行完整应用](https://simonwillison.net/2026/Nov/17/datasette-lite/) ⭐️ 8.0/10

Simon Willison 发布了 Datasette Lite 的完全重写版：它通过 service workers 和 Pyodide 在浏览器中运行完整的 Datasette Python 应用，作者称效果已“几乎与真正的服务端应用无法区分”。用户现在可用精心构造的 URL 指定从 PyPI 加载某个 Datasette 发行版、从 GitHub 加载特定 commit、tag 或分支、选择 100 多个 SQLite 版本，并从 PyPI 或 wheel URL 安装插件。URL 支持 ?install= 安装插件、?url= 加载 SQLite、JSON、CSV 或 SQL 文件、?metadata= 加载元数据，以及 \#/... 片段定位到具体页面；远程数据 URL 需提供开放的 CORS 响应头。此次重写取代了 2022 年初版通过 Pyodide web worker 模拟请求并用 innerHTML 注入 HTML 的做法，旧方案会导致依赖 JavaScript 的功能失效。

rss · Simon Willison · 11月17日 16:48

**「背景」** Datasette Lite 并非新项目：作者早在 2022 年就发布了第一版，当时是把 Datasette 跑在 Pyodide web worker 里，模拟请求后把生成的 HTML 用 innerHTML 注入顶层页面。这种做法虽然能让基础功能运行，但凡是依赖 JavaScript 的特性都会失效，因为通过 innerHTML 插入的 script 标签不会执行。此次重写改用 service worker，正是为了让浏览器内的完整应用自己处理请求，而不再依赖这种注入式的取巧办法。

**「影响」** 对开发者而言，最直接的后果是可用一条 URL 固定 Datasette 版本、Git ref、SQLite 版本和插件，分享可复现的演示或 bug 复现，而无需启动 Web 服务器；文中就用 ?ref=1.0a42 与 ?ref=1.0a43 的链接对比了分页 bug 的旧行为与修复。使用时需注意，通过 ?url= 加载的数据库等文件必须带有开放的 CORS 响应头。

**标签**: `#Datasette`, `#Pyodide`, `#WebAssembly`, `#service workers`, `#SQLite`

---

<a id="item-tech-news-4"></a>
### [微软 ONNX Runtime 的 GitHub 仓库据报消失](https://github.com/microsoft/onnxruntime) ⭐️ 7.0/10

据报，微软 ONNX Runtime 的 GitHub 仓库在没有任何预先通知的情况下从 GitHub 消失，影响了依赖该仓库获取代码、构建软件和运行评估流程的开发者。发帖者称，其团队当天发现评估流水线开始失败，并提到该仓库约有 2.2 万个星标；但目前微软和 GitHub 均未给出官方确认或解释。现有信息无法判断这是仓库被删除、转为私有、临时故障，还是安全处置。

hackernews · nvader · 11月17日 23:18 · [社区讨论](https://news.ycombinator.com/item?id=50539610)

**「背景」** ONNX Runtime 是微软提供的跨平台推理运行时，用于加载并执行 ONNX 格式的模型；其 GitHub 仓库长期是开发者获取源码、提交问题和跟进版本的主要渠道。对于依赖该仓库进行源码构建、模型评估或推理服务部署的团队，仓库的可访问性本身就是供应链的一部分。

**「对依赖方的直接影响」** 若该仓库持续不可用，受影响最直接的是从其获取源码、发行包或依赖其 CI 的团队：提交者 nvader 表示自己流水线中的评测已开始失败，且事先没有任何通知。ONNX Runtime 官方站点称其被用于 Windows、Office、Azure 和数千个项目，这些使用方短期内只能转向镜像或分支，而评论中提到的 Intel 分支带有 OpenVINO 改动，不能视为等价替代。

**「社区讨论」** 评论中有人猜测，这可能与相关软件包遭入侵后的清理有关，也有人批评 ONNX 默认收集遥测数据且难以关闭；这些说法均未获证实。另有用户提到，Intel 维护的 onnxruntime 分支可作为替代，但包含 OpenVINO 相关修改。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/microsoft/onnxruntime">GitHub - microsoft/onnxruntime: ONNX Runtime: cross-platform ...</a></li>
<li><a href="https://onnxruntime.ai/">ONNX Runtime | Home</a></li>

</ul>
</details>

**标签**: `#onnx-runtime`, `#github`, `#open-source`, `#supply-chain-security`, `#ai-infrastructure`

---

<a id="item-tech-news-5"></a>
### [Phrack 第 73 期发布](https://phrack.org/issues/73/introduction_md) ⭐️ 7.0/10

Phrack 第 73 期已发布，社区讨论集中在本期的漏洞利用内容、SSH 历史分析，以及这本刊物在安全文化中的角色。源材料没有提供目录或正文，因此各篇文章的具体技术细节和漏洞披露状态无法独立核实。

hackernews · notmine1337 · 11月17日 18:31 · [社区讨论](https://news.ycombinator.com/item?id=50535992)

**「背景」** Phrack 是一份历史悠久的黑客与计算机安全刊物；评论区读者回忆自己在上世纪 90 年代至 2000 年代首次接触它，并提到更早的第 36 期。第 73 期收录了回顾 2000 年 SSH1 漏洞利用史的文章，也涉及 Docker 逃逸等议题，因此这次发布被放在该刊长期追踪漏洞与利用技术的脉络中理解。

**「社区讨论」** 有评论者询问，像本期提到的 Docker 逃逸这类漏洞利用是否事先经过负责任披露并分配 CVE，还是直接公开；另一位评论者推荐本期关于 SSH1 漏洞历史的文章，认为它有助于理解安全问题演进的速度。也有读者怀念早期安全杂志不加修饰的文风，认为这种开放氛围更利于表达。

**标签**: `#computer security`, `#exploit development`, `#vulnerability disclosure`, `#Phrack`, `#SSH history`

---

<a id="item-tech-news-6"></a>
### [微软发布 MAI Code 2 与 Code 2 Flash 编程模型](https://microsoft.ai/news/introducing-mai-code-2-and-mai-code-2-flash/) ⭐️ 7.0/10

微软宣布推出 MAI Code 2 和 MAI Code 2 Flash 两款面向 AI 编程的模型。提供的材料没有包含基准测试结果、定价、支持的开发环境或独立验证，因此尚无法判断它们相对竞品的实际能力。来源也未说明这两款模型的正式可用范围；相关使用体验目前仅见于社区评论。

hackernews · lemonish97 · 11月17日 18:25 · [社区讨论](https://news.ycombinator.com/item?id=50535885)

**「背景」** 微软的 MAI 代码模型此前已有 MAI-Code-1-Flash，第三方模型资料站 llm-stats.com 记录其发布于 2026 年 6 月 2 日；此次的 Code 2 与 Code 2 Flash 属于该系列的新一代产品。按微软官方发布页的说法，新模型面向日常企业级编码任务，主打以远低于竞品模型的成本提供领先性能。

**「对开发者与 Copilot 用户的影响」** GitHub Copilot 已将 MAI Code 2 和 MAI Code 2 Flash 纳入可选模型：前者面向深度调试、多文件实现和仓库级推理，后者面向日常编码并强调成本效率。开发者需要按任务在能力与成本之间取舍；微软声称 Code 2 达到 GPT-6.1 Sol 98% 的性能而成本仅为其 40%，但该数字来自厂商，尚待独立验证。

**「社区讨论」** 有评论者认为 OpenAI 和 Anthropic 的领先优势可能只有几个月，并追问微软为何能快速追赶；另一人则报告在 GitHub Copilot 中以五折试用 MAI Code 2，称其处理 Python/WSL 构建、测试用例和 Azure Bicep 部署问题时与 Claude Opus 相差不大。还有用户表示已取消 Copilot 订阅，认为当前产品还不够好，但愿意尝试新模型。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://microsoft.ai/news/introducing-mai-code-2-and-mai-code-2-flash/">MAI Code 2 and Code 2 Flash : Everyday coding at... | Microsoft AI</a></li>
<li><a href="https://llm-stats.com/models/mai-code-1-flash">MAI - Code -1- Flash Benchmarks , Pricing &amp; Context Window</a></li>
<li><a href="https://github.blog/changelog/2026-11-17-mai-code-2-and-mai-code-2-flash-in-github-copilot/">MAI Code 2 and MAI Code 2 Flash in GitHub Copilot</a></li>
<li><a href="https://www.unite.ai/microsoft-ai-releases-mai-code-2-and-mai-code-2-flash-for-enterprises/">Microsoft AI Releases MAI Code 2 and MAI Code 2 Flash for ...</a></li>

</ul>
</details>

**标签**: `#Microsoft`, `#AI coding models`, `#LLMs`, `#developer tools`, `#model release`

---

<a id="item-tech-news-7"></a>
### [英伟达停止披露新加坡销售，营收达 1040 亿美元](https://www.ft.com/content/dbde7a30-548c-4f9d-a4be-7898a0c24dcf) ⭐️ 7.0/10

据《金融时报》报道，英伟达已停止披露新加坡销售额，相关营收数字达到 1040 亿美元。报道将这一披露变化与外界对经新加坡转接订单、供应链透明度以及出口管制审查的关注联系起来。现有信息只能确认披露口径发生变化，尚不足以判断这些收入的最终去向或新加坡本地的实际需求。

hackernews · louiereederson · 11月17日 17:12 · [社区讨论](https://news.ycombinator.com/item?id=50534631)

**「背景」** 英伟达的销售额按下单的法人实体计入，新加坡子公司承接的订单可能只是经由 OEM/ODM 和经销商体系路由，并不代表芯片最终在新加坡使用，这是解读“新加坡收入”的关键口径。此前有报道称，美国当局调查过新加坡公司 Megaspeed 是否帮助中国客户获取受限制的英伟达芯片，该调查后来被转交美国司法部。

**「合规与收入透明度的影响」** 对采购英伟达 AI 硬件的客户和经新加坡实体下单的经销商来说，英伟达不再单独披露新加坡收入，会让外部更难核对经该地流转订单的最终去向。新加坡政府表示，本国没有法律义务执行他国的单边出口管制，但期望在当地经营的公司把相关法规纳入考量；与此同时，美方正调查包括新加坡在内的路径是否让受限芯片流入中国。相关企业因此需要保留最终用户与货物流向记录，以备合规审查。

**「社区讨论」** 评论中最实质的澄清是，1040 亿美元被理解为英伟达新加坡子公司的对外收入，其中可能包含经由新加坡实体转接的 GPU 订单，而不等于当地最终需求；这一说法来自评论者 tamarind44。另有评论者认为这主要是收入归属的会计问题，不能说明芯片最终流向，也有人围绕出口管制和 Megaspeed 相关调查展开推测，但这些推测未获证据支持。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.techtimes.co.uk/megaspeed-nvidia-hardware-imports-chip-scrutiny-1809823">Inside Megaspeed : The Little-Known Firm Linking Jensen and Alice...</a></li>
<li><a href="https://www.nytimes.com/2026/11/09/business/economy/nvidia-megaspeed-investigation-huang.html">U.S. Commerce Dept. Inquiry Into Megaspeed Was Halted After...</a></li>
<li><a href="https://www.channelnewsasia.com/singapore/nvidia-ai-chips-us-export-controls-singapore-deepseek-china-4944231">Singapore does not condone businesses who use local ties to bypass...</a></li>
<li><a href="https://www.straitstimes.com/business/us-looking-if-deepseek-got-nvidia-ai-chips-through-singapore-others">US probing whether DeepSeek got Nvidia AI chips ... | The Straits Times</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#AI hardware`, `#export controls`, `#Singapore`, `#supply chain`

---

<a id="item-tech-news-8"></a>
### [SolidJS 发布 2.0：新增服务端 RPC、live 与 broadcast，强化调试诊断](https://www.solidjs.com/blog/solid-2-0-the-long-hold/) ⭐️ 7.0/10

JavaScript UI 框架 SolidJS 发布 2.0 主版本。从社区讨论看，此次更新的重点是服务端集成：提供 server RPC 以及 live、broadcast 能力，试图补上前端与后端之间缺失的中间层；同时改进了调试诊断体验。发布文章还设有“Built to Be Written by Agents”一节，但有评论者认为这部分实质上是更好的调试诊断，与代理式（agentic）开发并无专属关系，可能只是营销措辞。来源未提供具体版本号、破坏性变更清单、迁移指南或分发渠道等细节，因此 2.0 的实际升级成本尚不明确。

hackernews · pier25 · 11月17日 18:56 · [社区讨论](https://news.ycombinator.com/item?id=50536387)

**「背景」** Solid 2.0 稳定版是在 2026 年 8 月的 2.0 RC 之后推出的；该 RC 说明了 2.0 周期的架构调整：server functions 进入核心，serving layer 归入 start mode，文件系统路由移到不绑定特定路由器的包中。Solid 博客称，2.0 从启动到稳定经历了五年，因此这次发布是在长期重构后落地，并非一次短期增量更新。

**「影响与注意事项」** 对正在做技术选型的前端团队来说，Solid 2.0 的 server RPC 与 live/broadcast 提供了一条不同于 LiveView、htmx/datastar 的前后端集成路径，但在采纳前需要确认这些能力在实际项目中的边界与稳定性，因为本次来源没有给出性能数据或生产验证。已有 Solid 用户则应把这次更新视为主版本升级，审慎评估兼容性，因为来源未附迁移说明。

**「社区讨论」** 有评论者认为 Solid 的服务端 RPC、live 和 broadcast 衔接顺畅，用起来比 LiveView 或 htmx/datastar 更自然，并称 Remix 早年提出的“前后端中间层”定位始终未能真正落地。另一位评论者指出，发布文章里“为代理编写”的特性其实是更好的调试诊断，对人类手写代码同样有帮助，未必与代理开发直接相关。此外还有用户提到自己在等待 Vue 3.6 Vapor 发布，期待它在性能上与 Svelte、Solid 这类框架竞争。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.solidjs.com/blog/solid-2-0-rc-the-big-reveal">Solid 2.0 RC: The Big | SolidJS</a></li>
<li><a href="https://www.solidjs.com/blog/solid-2-0-the-long-hold/">Solid 2.0 - The Long Hold - solidjs.com</a></li>

</ul>
</details>

**标签**: `#SolidJS`, `#JavaScript frameworks`, `#frontend development`, `#web development`, `#server RPC`

---

<a id="item-tech-news-9"></a>
### [Quad9 因 DNS 过滤裁决退出法国](https://blog.cloudflare.com/quad9-withdrawal-from-france/) ⭐️ 7.0/10

据 Cloudflare 博文，Quad9 因法国一项与 DNS 过滤相关的法院裁决退出法国，法国用户因此失去该公共 DNS 解析器服务。博文将此事与互联网碎片化和隐私风险联系起来，认为 DNS 解析层正被纳入内容过滤执法。目前公开材料未给出裁决细节、退出时间表或对其他国家的直接影响。

hackernews · subset · 11月17日 22:13 · [社区讨论](https://news.ycombinator.com/item?id=50538994)

**「背景」** 公共 DNS 解析器负责把域名转换为 IP 地址，也因此成为法院要求屏蔽网站时的执行环节。法国法院此前命令瑞士非营利机构 Quad9 拦截被指侵犯版权的网站，Quad9 于 2026 年 10 月表示将自 11 月 24 日起停止为法国用户提供解析服务（tool-2-3）。Cloudflare 的文章还提到，比利时法院近期发出命令，要求 Cloudflare、Google 和 Cisco 在 2027 年 1 月初前通过公共解析器屏蔽相关网站，否则将面临重罚（tool-2-1）。

**「直接影响」** 对依赖 Quad9 的法国用户和企业来说，最直接的后果是需要改用其他 DNS 解析器；对在法国提供 DNS 服务的组织来说，这一案例表明内容过滤裁决可能迫使其在遵守过滤要求与退出市场之间做选择。

**「社区讨论」** Quad9 的 CTO 在评论中表示，IETF 127 现场对其立场“100% 支持”，并称业界对 DNS 相关案件普遍感到担忧。另有评论者批评 Cloudflare 博文立场含糊，追问其若上诉失败是否会承诺退出受影响国家。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.cloudflare.com/quad9-withdrawal-from-france/">Quad9’s withdrawal from France: A canary in the coal mine</a></li>
<li><a href="https://www.eff.org/deeplinks/2026/10/french-courts-site-blocking-orders-drive-quad9-out-france">French Court’s Site-Blocking Orders Drive Quad9 Out Of France</a></li>

</ul>
</details>

**标签**: `#DNS`, `#internet regulation`, `#privacy`, `#France`, `#Cloudflare`

---

<a id="item-tech-news-10"></a>
### [编码代理的外部沙箱及三种实现](https://simonwillison.net/2026/Nov/17/external-sandboxes-for-coding-agents/) ⭐️ 7.0/10

Simon Willison 与 Prime Radiant 发布“外部沙箱”模式：编码代理本身留在沙箱外，由其触发的代码在独立沙箱内执行，目的是降低试用本地模型时因误操作或提示注入造成破坏的风险。项目提供三个使用同一 localhost API 的服务端实现：external-sandbox-v86 用 Node.js 经 v86 在 WebAssembly 中运行 Alpine Linux；external-sandbox-container 用 Python 服务在 Apple Containers 中运行 Alpine Linux；external-sandbox-quicksand 用 Python 服务调用 Microsoft Quicksand，后者将 QEMU 和 Alpine Linux 打包进 Python 包。用户可将 Pi、Claude Code 或 Codex 配置为在需要执行代码时调用该 API，并可启用可选的 HTTP/HTTPS 主机允许列表代理和凭据替换，让代理代码发起带认证的 API 调用而无需向其暴露密钥。

rss · Simon Willison · 11月17日 22:52

**「背景」** 编码智能体通常需要在本地执行其生成的命令和代码；一旦模型被提示注入或自身出错，直接运行就可能影响宿主机。外部沙箱把智能体进程留在沙箱外，只把待执行的代码送进独立环境，并通过统一的 localhost API 接入 Pi、Claude Code 或 Codex，从而将代码执行权限与智能体推理环境隔开。

**「影响」** 对需要运行代理生成代码的开发者，这提供了一种将执行环境与代理进程分离、并通过主机允许列表限制沙箱出站访问的方式；但三种后端依赖不同运行时，采用时需按所选实现准备相应环境。

**标签**: `#AI agents`, `#sandboxing`, `#code execution security`, `#prompt injection`, `#local models`

---

<a id="item-tech-news-11"></a>
### [中国完成 Q/V 频段双向 27Gbps 无线通信验证](https://www.news.cn/tech/20261117/d6323540dccf4e2a976c48a762795956/c.html) ⭐️ 7.0/10

中科院空天信息创新研究院等单位在丽江中国遥感卫星地面站完成 Q/V 频段高阶体制高码速率双向通信实验，称实现中国该频段最高码速率无线通信验证。实验首次系统测试 64QAM 至 512QAM 多种调制模式；512QAM 下单通道双向速率达 6.75Gbps，结合双载频和极化复用提升至双向 27Gbps，刷新国内纪录。团队称关键指标为国内领先、国际先进，后续争取实现超过 50Gbps；报道未说明该实验是否经过同行评审或已具备外场商用条件。

telegram · zaihuapd · 11月17日 08:45

**「背景」** Q/V 频段属于毫米波高频段，可用带宽大，但传播损耗和器件要求更高。512QAM 通过提高每符号承载的比特数来提升速率，对信噪比和链路质量要求更严；双载频与极化复用则是在此基础上进一步叠加容量。

**「影响」** 对卫星互联和 6G 回传的系统设计者而言，这次实验给出了 512QAM 配合双载频、极化复用的实测速率组合，但 27Gbps 是双向实验链路总速率，报道未披露链路距离、带宽、天气条件和设备兼容性，因此还不能直接作为商用容量指标。

**标签**: `#6G`, `#Q/V-band`, `#wireless communications`, `#satellite internet`, `#millimeter-wave`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [中汽协受工信部委托评估 17 家车企的供应商账期](http://www.caam.org.cn/chn/5/cate_68/con_5237404.html) ⭐️ 7.0/10

中国汽车工业协会 11 月 16 日发布通知称，受工信部委托，已作为第三方机构对一汽、上汽、比亚迪、理想、蔚来、小鹏、小米汽车、零跑等 17 家重点车企的供应商账款支付情况开展调研评估，核查中小企业账期是否不超过 60 天、非中小企业现金和银行承兑汇票支付比例是否不低于 80%。这是对现有账期要求落实情况的评估，并非出台新规。

telegram · zaihuapd · 11月18日 01:15

**「背景」** 2025 年 6 月，17 家重点车企曾公开承诺“支付账期不超过 60 天”；同年 9 月 15 日，中汽协发布《汽车整车企业供应商账款支付规范倡议》，明确了 60 天账期的起算时间，此次评估正是对上述承诺落实情况的核查。

**「影响」** 此次评估直接关系到为这 17 家车企供货的零部件供应商，尤其是中小企业：它们此前已获得 60 天账期承诺，但有报道称，延后开票、以商业承兑汇票替代现金等做法仍使实际回款偏慢，而本轮核查结果将公开发布。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://m.bjnews.com.cn/detail/1757938284168209.html">中 汽 协 明确“ 60 天 账 期 ” 支 付 规范， 17 家 车 企 响 应</a></li>
<li><a href="https://auto.gasgoo.com/news/202609/7I70471417C1103.shtml">auto.gasgoo.com/news/202609/7I70471417C1103.shtml</a></li>
<li><a href="https://m.bjnews.com.cn/detail/1757938284168209.html">中 汽 协 明确“ 60 天 账 期 ”支付规范， 17 家 车 企 响 应</a></li>
<li><a href="https://c.m.163.com/news/a/KVETS4D0054764EL.html">60 天 承诺变套路： 车 企 延开票、 商 票替代，零部件 企 业 账 期 困局未解</a></li>

</ul>
</details>

**标签**: `#汽车产业`, `#供应链金融`, `#应收账款账期`, `#工信部监管`, `#中小企业`

---