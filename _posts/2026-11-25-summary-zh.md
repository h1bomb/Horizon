---
layout: default
title: "Horizon Summary: 2026-11-25 (ZH)"
date: 2026-11-25
lang: zh
---

> 从 27 条内容中筛选出 8 条重要资讯。

---

**科技新闻**
1. [Broadcom 修复 vCenter 9.8 分鉴权绕过漏洞](#item-tech-news-1) ⭐️ 8.0/10
2. [未验证预印本宣称矩阵乘法指数为 9/4](#item-tech-news-2) ⭐️ 7.0/10
3. [Ternary Bonsai 2.5 27B：三元量化模型主打本地 128k 上下文](#item-tech-news-3) ⭐️ 7.0/10
4. [OpenAI 称 GPT-6 能设计蛋白质，关键序列步骤仍靠专用模型](#item-tech-news-4) ⭐️ 7.0/10
5. [Check Point 管理服务器遭入侵，V8 随机数状态被重建](#item-tech-news-5) ⭐️ 7.0/10
6. [Simon Willison 回顾 LLM 一年内的三个能力拐点](#item-tech-news-6) ⭐️ 7.0/10
7. [GPT-6.2 Astra 22 分钟破解 1808 年耶鲁素描本作者之谜](#item-tech-news-7) ⭐️ 7.0/10

**财经新闻**
1. [美联储威廉姆斯：通胀回到 2%仍需进一步行动](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Broadcom 修复 vCenter 9.8 分鉴权绕过漏洞](https://thehackernews.com/2026/11/vmware-vcenter-hit-by-another-critical.html) ⭐️ 8.0/10

Broadcom 为 VMware 产品线发布补丁，修复 23 个漏洞，其中 vCenter 目录服务（vmdir）的鉴权绕过漏洞 CVE-2026-123903 被评为 9.8 分。该漏洞允许任何能访问 vCenter 的攻击者绕过认证直接进入系统；据报道，它在披露前几天已被作为零日漏洞利用。补丁已发布，但现有摘要未说明具体受影响版本范围或其他利用前提。

telegram · zaihuapd · 11月24日 14:50

**「背景」** vCenter 是 VMware 虚拟化环境的管理中枢，vmdir 则是其目录服务，负责身份与目录相关功能。鉴权绕过意味着攻击者无需有效凭据即可访问受保护接口，因此这类漏洞通常被列为最高风险等级。

**「暴露面与修复优先级」** 由于利用该漏洞无需任何凭据，只要 vCenter 管理接口可达就可能被绕过认证，因此暴露在互联网或共享管理网段的实例应优先处置。Broadcom 在 VMSA-2026-0011 中列出了受影响分支与修复版本，同批还包含两个同为 9.8 分的 ESX 代码执行漏洞，运维方需按公告核对自身版本并升级，仅靠网络隔离不足以作为长期缓解措施。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://brandefense.io/knowledge-hub/vulnerabilities/cve-2026-123903/">CVE-2026-123903: vCenter Auth Bypass, Fix Status</a></li>
<li><a href="https://www.rescana.com/post/vmware-vcenter-cve-2026-123903-auth-bypass-and-esx-code-execution-patch-now">VMware vCenter Auth Bypass CVE-2026-123903 and ESX Code ...</a></li>
<li><a href="https://securityaffairs.com/203931/security/vmware-patches-critical-vcenter-authentication-bypass-and-esx-flaws.html">VMware patches critical vCenter authentication bypass and ESX ...</a></li>

</ul>
</details>

**标签**: `#security`, `#VMware`, `#vCenter`, `#vulnerabilities`, `#zero-day`

---

<a id="item-tech-news-2"></a>
### [未验证预印本宣称矩阵乘法指数为 9/4](https://github.com/openai/math/blob/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/paper.pdf) ⭐️ 7.0/10

一份托管在 OpenAI 的 GitHub 仓库的预印本《The matrix multiplication exponent is nine fourths》声称矩阵乘法的指数为 9/4，即 Θ\(n^2.25\)。该预印本尚未经过同行评审，当前可见信息也不足以独立复核其证明，因此应视为未经证实的声明。相关评论称论文给出的是覆盖任意域的精确指数，并否定“指数等于 2”的猜想；若成立，这将确定矩阵乘法的渐近复杂度，而不只是给出一个上界。

hackernews · E-Reverance · 11月25日 01:19 · [社区讨论](https://news.ycombinator.com/item?id=50637220)

**「背景」** 矩阵乘法指数 ω 定义为：对任意 ε&gt;0，两个 n×n 矩阵可在 O\(n^\{τ+ε\}\) 次算术运算内相乘的指数 τ 的下确界（MathWorld）。据 Office Chai 报道，七周前 OpenAI 曾称其内部模型找到了显著更快的理论矩阵乘法方法；本次挂出的 preprint 则声称证明精确指数为 9/4（即 2.25），也就是说无法再做得更好。

**「影响」** 对复杂度理论研究者，最直接的后果是这篇预印本会成为需要复核的下界证明：在独立验证前，不应把 ω=2.25 当作既定事实写入依赖快速矩阵乘法的算法分析或教学材料。对一般开发者，目前没有可据以修改实现的算法细节，因此现有矩阵乘法库和实际性能没有明确的改变依据。

**「社区讨论」** 评论中最实质的技术分歧是结论表述：orlp 指出标题写成 O\(n^2.25\) 不正确，因为该上界早已知道，结果应是 Θ\(n^2.25\)；brandonb 进一步称论文证明的是 Ω\(n^2.25\) 下界，而 2.25 的上界此前已知。另有评论称这组工作来自未发布模型且未公开配方，并对 OpenAI 连续产出开放问题结果的动机提出猜测。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://mathworld.wolfram.com/MatrixMultiplicationExponent.html">Matrix Multiplication Exponent -- from Wolfram MathWorld</a></li>
<li><a href="https://officechai.com/ai/openai-says-it-has-pinned-down-the-exact-speed-limit-for-matrix-multiplication-9-4/">OpenAI Says It Has Pinned Down The Exact Speed Limit For ...</a></li>

</ul>
</details>

**标签**: `#complexity-theory`, `#matrix-multiplication`, `#ai-for-math`, `#openai`, `#research-preprint`

---

<a id="item-tech-news-3"></a>
### [Ternary Bonsai 2.5 27B：三元量化模型主打本地 128k 上下文](https://prismml.com/news/bonsai-2-5-27b) ⭐️ 7.0/10

Ternary Bonsai 2.5 27B 是一款新发布的三元量化 27B 模型，面向本地推理；HN 评论中的 Q2 GGUF 版本在 Mac Mini M5 Pro（24GB 内存）上报告约 22–25 tokens/s，并可轻松容纳 128k 上下文。当前材料缺少官方技术细节和基准结果，评论中“在 SWE-bench Verified 上相当于 Opus 4.6”的说法被该评论者本人标为不确定。对本地部署者来说，关键看点是长上下文与生成速度能否支撑 agentic coding，但实际能力仍需与同尺寸量化模型做独立对比。

hackernews · b0m · 11月24日 20:08 · [社区讨论](https://news.ycombinator.com/item?id=50633922)

**「背景」** 三元量化把模型权重压缩到 -1、0、1 三档取值，从而把 27B 规模的模型塞进很小的体积：据 PrismML 的发布说明，Bonsai 2.5 27B 维持了约 5.9 GB 的占用，并在此基础上强化了 agentic coding、多轮工具调用与多步任务执行能力。该模型以 GGUF 格式在 Hugging Face 上发布（含 Q2\_0 量化版本），可通过命令行工具或 vLLM 在本地部署运行，这也是社区能用消费级 Mac 直接测速的前提。

**「影响」** 对 24GB 内存级别的本地部署者，这一版本把 128k 上下文和约 22–25 tokens/s 的组合放进可运行范围，但评论者尚未完成 agentic 任务验证；在采用前应先用自有任务对比同尺寸 Q2 模型，并核实内存余量。

**「社区讨论」** 评论区的核心分歧在于基准可信度：一位评论者猜测 SWE-bench 表现可能来自“benchmaxxing”、基准漂移或小模型约六个月的追赶，另一位则要求与同等大小的流行 Q1/Q2 量化模型（例如评论提到的 Qwen3.8）直接对比。也有用户用自己的长任务测试报告，Bonsai 2.5 与上一版同样通过 5/8 项，但步数少 17%、耗时少 29%，不过这不是标准化评测。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://prismml.com/news/bonsai-2-5-27b">PrismML — Introducing Ternary Bonsai 2 . 5 27 B : Powering Agentic...</a></li>
<li><a href="https://huggingface.co/prism-ml/Ternary-Bonsai-2.5-27B-GGUF">prism - ml / Ternary - Bonsai - 2 . 5 - 27 B -GGUF · Hugging Face</a></li>

</ul>
</details>

**标签**: `#ternary quantization`, `#local LLMs`, `#model release`, `#GGUF`, `#agentic coding`

---

<a id="item-tech-news-4"></a>
### [OpenAI 称 GPT-6 能设计蛋白质，关键序列步骤仍靠专用模型](https://openai.com/index/gpt-6-models-demonstrate-intrinsic-protein-design-capabilities/) ⭐️ 7.0/10

OpenAI 发表文章称，GPT-6 系列（评论引述为 GPT-6.2）可完成蛋白质设计任务：给它五个靶蛋白的三维结构和指定结合位点，它能自行编写代码生成 minibinder 的三维设计，且这一步未调用专门的蛋白质 AI 模型。但要把这些设计变成可在实验室测试的蛋白质，仍需专用模型 SolubleMPNN 给出氨基酸序列，并用其他蛋白质模型筛选可能按设计折叠、在目标位点结合的候选。按评论引述的材料，这支持的是模型能编写设计代码并串联流程，而非无需专用工具即可端到端设计蛋白质。

hackernews · acossta · 11月24日 21:02 · [社区讨论](https://news.ycombinator.com/item?id=50634658)

**「背景」** 蛋白质设计通常要同时解决两个问题：提出目标三维结构，并给出能折叠成该结构的氨基酸序列。传统流程会把结构生成、序列设计（例如使用 SolubleMPNN）以及折叠与结合筛选分交给不同的专用模型，因此“模型能否内生完成设计”取决于它是否仍需这些专用工具来完成关键子任务。

**「影响」** 对蛋白质设计团队和开发者而言，实际工作流仍是混合式的：大语言模型可承担把任务拆解并生成结构设计代码的“胶水层”，但序列生成和候选筛选要依赖 SolubleMPNN 等专用模型；团队需要保留这些工具并验证计算设计，不能把模型输出直接当作可实验的蛋白质。

**「社区讨论」** 评论区对“内在”能力提出质疑：fabian2k 认为序列才是蛋白质的关键，因而追问 GPT-6.2 究竟设计出了什么；plaidfuji 认为把它描述为“超越专用模型”为时过早，更准确的角色是连接各专用工具的胶水层，尽管它有时能在子任务上胜过专用模型。joe-esquibel 还指出，展示的证据偏重计算探索、实验室对照较少。

**标签**: `#AI for biology`, `#protein design`, `#GPT-6`, `#OpenAI`, `#specialized models`

---

<a id="item-tech-news-5"></a>
### [Check Point 管理服务器遭入侵，V8 随机数状态被重建](https://www.greynoise.io/blog/check-point-security-management-servers-intrusion-campaign) ⭐️ 7.0/10

GreyNoise 报告了一起针对 Check Point 安全管理服务器的活跃入侵活动。攻击者向 HFS 的 loginSrp1 登录端点连续发起 POST 请求，收集由 JavaScript Math.random\(\) 生成并写入签名会话 cookie 的 sid，再据此重建 Node.js V8 PRNG 的内部状态，从而恢复 HFS 会话 cookie 的签名密钥并伪造管理员会话。目前公开讨论中，攻击者如何获得初始访问权限仍不清楚；有评论者推测与 CVE-2026-16232 以及相关服务器暴露在互联网上有关，但这只是提问和推测。

hackernews · louiereederson · 11月24日 16:32 · [社区讨论](https://news.ycombinator.com/item?id=50630594)

**「漏洞与随机数背景」** 此前 Check Point 已确认身份验证绕过漏洞 CVE-2026-16232 遭到利用：远程攻击要求管理服务器 IP 可从互联网访问，且未限制 Trusted Clients，受影响客户数量被描述为“非常少”。评论者因此推测它可能是本次入侵活动的初始入口，但现有材料尚未完整说明初始访问是如何获得的。另一个关键前提是 JavaScript 的 Math.random\(\) 并非密码学安全随机源；连续观测由其生成的 sid 会话值，可能让攻击者推断 V8 PRNG 的内部状态，进而为恢复会话 Cookie 签名密钥创造条件。

**「实际影响」** 对运行 Check Point 安全管理服务器的组织而言，直接影响是管理员认证可能被完全绕过：攻击者从连续登录返回的会话 Cookie 中恢复签名密钥后，可伪造管理员会话，无需猜口令或钓鱼即可取得管理权限，因此仅靠强密码不足以防护。应优先限制管理界面在公网暴露、让现有会话全部失效并轮换 Cookie 签名密钥，同时核查是否已修补评论中怀疑的初始入侵向量 CVE-2026-16232。

**「社区讨论」** 评论者 omh 指出初始访问方式仍不明确：多家 Check Point 客户同时受影响，可能暗示 CVE-2026-16232 是入口，但这也意味着相关安全管理服务器可能暴露在互联网上；这仍是待证实的疑问。另有评论者认为根本问题在于 Math.random\(\)，主张让随机数生成器默认具备安全性，而不是要求大量应用各自正确使用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://support.checkpoint.com/results/sk/sk185169">sk185169 - CVE-2026-16232 - Authentication bypass with ...</a></li>
<li><a href="https://nvd.nist.gov/vuln/detail/cve-2026-16232">NVD-CVE-2026-16232</a></li>
<li><a href="https://dev.to/kozhevniko/rejetto-hfs-signs-its-admin-session-cookie-with-mathrandom-1lgj">Rejetto HFS signs its admin session cookie with Math.random()</a></li>

</ul>
</details>

**标签**: `#security`, `#vulnerability-research`, `#Node.js`, `#PRNG`, `#exploitation`

---

<a id="item-tech-news-6"></a>
### [Simon Willison 回顾 LLM 一年内的三个能力拐点](https://simonwillison.net/2026/Nov/24/llm-inflection-points/) ⭐️ 7.0/10

Simon Willison 在其 AI Engineer Code Summit 主题演讲的延伸文章中提出，过去十二个月 LLM 与编程代理的能力出现了三个拐点。第一个是 2025 年 11 月的 Claude Opus 4.5（以及同期的 GPT-5.1 系列），他认为这让 Claude Code 和 Codex 从需要频繁纠正变为大多数日常编程任务可直接给出正确结果；第二个是 2026 年 6–7 月的 Claude Fable 5，他把“给定目标和工具后能主动设法解决问题”的模型称为“Fable 级”，并将 Opus 5.5、GPT-6 Astra、Gemini 4 Neon 也归入此类；第三个是 2026 年 9–10 月，以 Opus 5.5 等模型在 Blender/Three.js 3D 建模和游戏玩法调优上的表现作为标志。文章明确是作者基于个人使用经验的回顾性判断，而非新的基准测试或厂商发布，且源文本在讨论 Fable 5.2 是否构成第四个拐点处被截断。

rss · Simon Willison · 11月24日 23:02

**「背景」** 这篇回顾发表于 2026 年 11 月 24 日，正好是 Claude Opus 4.5 发布一周年。更早的背景是，Claude Code 于 2025 年 2 月 24 日随 Claude 3.7 Sonnet 推出，到 Opus 4.5 面世时已存在约九个月；作者据此比较该工具在模型升级前后的可用性变化。

**「影响」** 对日常写代码的开发者而言，直接的后果是评估编码代理的标准从「能否完成任务」转为「默认输出是否需要频繁纠正」：Willison 称 Opus 4.5 是他第一个默认结果基本正确的模型，这让他把 Claude Code 从偶尔试用变成日常主力工具，而外部汇总给出的 SWE-bench Verified 80.9% 也印证了这一代模型在真实软件工程任务上的定位。他提出的「Fable 类」判据——只要能定义目标并提供工具，模型就能靠蛮力解决问题——意味着团队在模型选型或采购时会把这类能力当作新的最低预期，而不是加分项。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.digitalapplied.com/blog/claude-opus-4-5-complete-guide-agents-coding">Claude Opus 4.5 Complete Guide: Agents &amp; Coding</a></li>

</ul>
</details>

**标签**: `#LLM`, `#coding agents`, `#AI engineering`, `#software development`, `#Anthropic Claude`

---

<a id="item-tech-news-7"></a>
### [GPT-6.2 Astra 22 分钟破解 1808 年耶鲁素描本作者之谜](https://simonwillison.net/2026/Nov/24/astra-historical-mystery/) ⭐️ 7.0/10

历史学者 Mark Humphries 报告称，在极少提示下，GPT-6.2 Astra 自主识别出耶鲁大学 Beinecke 图书馆藏匿名 1808 年素描本的作者，全程仅用 22 分钟，且只依赖公开的一手与二手资料。该模型找到一份论文档案中鲜为人知的日记记载：在素描本提到的某个日期前五天，vicomte de Chabot 曾造访附近河流，据此推断 Chabot 的旅行日记（需向克利夫兰州立大学订购）可验证该假设，结果果然得到证实。Humphries 还指出，这份日记本身即为对加拿大史与毛皮贸易史有重要意义的新史料。需注意，这是单一案例的学者叙述，未提供方法细节，也无独立验证。

rss · Simon Willison · 11月24日 16:53

**「背景」** 耶鲁大学贝内克图书馆收藏的这本 1808 年速写本没有署名，且已有数字化副本可供查阅，这是此次档案识别任务的起点。报道以 Deep Blue 和数学领域的经验作类比，讨论自主研究系统可能给历史学带来的信心冲击；但现有材料只有历史学者的转述，未披露完整提示词、检索路径或独立复核结果。

**「对研究实践的影响」** 对历史学家和档案工作者而言，这一案例显示代理式检索可能把“发现线索—提出假设—定位未数字化文献”的周期压缩到分钟级，但关键证据仍需人工订购、查阅与核对。Humphries 预计，明年春夏会出现一场关于如何回应这类代理系统的信心危机，不过他认为史学受到的冲击会小于数学，因为史学研究并不追求单一普适真理。

**标签**: `#AI agents`, `#LLM applications`, `#autonomous research`, `#digital humanities`, `#historical research`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美联储威廉姆斯：通胀回到 2%仍需进一步行动](https://www.cnbc.com/2026/11/23/john-williams-fed-inflation-rate-hikes.html) ⭐️ 7.0/10

纽约联储主席威廉姆斯表示，美联储仍需采取进一步行动，才能让通胀持续回到 2%目标，并暗示加息等收紧措施可能随时间推进；市场完全预期 12 月 8-9 日会议将把 3.75%-4%的利率目标区间上调 25 个基点。

rss · CNBC Finance · 11月24日 13:33

**「背景」** 联邦公开市场委员会（FOMC）负责制定利率，下一次会议在 12 月 8-9 日；当前通胀仍远高于 2%目标，而威廉姆斯称其看法与先前表态一致，并未明确预告 12 月决定。

**标签**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#inflation`, `#FOMC`

---