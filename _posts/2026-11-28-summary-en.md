---
layout: default
title: "Horizon Summary: 2026-11-28 (EN)"
date: 2026-11-28
lang: en
---

> From 30 items, 9 important content pieces were selected

---

**Technology News**
1. [Google Research&\#x27;s DeepCrossAttention claims up to 3x transformer speedup](#item-tech-news-1) ⭐️ 7.0/10
2. [WebRTC-based card skimming scripts reported on shopping sites](#item-tech-news-2) ⭐️ 7.0/10
3. [Convex AI coding skill accused of uploading app ideas without disclosure](#item-tech-news-3) ⭐️ 7.0/10
4. [Essay examines false computer-checked proofs and checker soundness](#item-tech-news-4) ⭐️ 7.0/10
5. [SemiAnalysis details Trainium3 microarchitecture and inference cost results](#item-tech-news-5) ⭐️ 7.0/10
6. [OpenSec discloses CVE-2026-99362, a 9.8 pre-auth root flaw in Linux nfsd](#item-tech-news-6) ⭐️ 7.0/10
7. [Minecraft Bedrock resource-pack flaw affected 26.52–26.63, fixed in 26.65](#item-tech-news-7) ⭐️ 7.0/10

**Financial News**
1. [China&\#x27;s State Council Executive Meeting Calls for Stronger Market-Stabilization Role by &\#x27;National Team&\#x27;](#item-finance-news-1) ⭐️ 7.0/10
2. [央行公布大额存单新规 个人起购门槛降至 10 万元](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Google Research&\#x27;s DeepCrossAttention claims up to 3x transformer speedup](https://research.google/blog/supercharging-transformer-residual-connections/) ⭐️ 7.0/10

Google Research has described DeepCrossAttention, a transformer residual-connection technique that it says can deliver model quality comparable to standard approaches while running up to 3x faster. The claim comes from a research blog post, not independent benchmarks or a shipped product; the available summary does not specify the baseline, workload, or whether the speedup applies to training or inference.

hackernews · ComputedCamp995 · Nov 27, 23:06 · [Discussion](https://news.ycombinator.com/item?id=50672565)

**「Background」** Transformer residual connections add each sublayer&\#x27;s output to a running representation, a simple path that can let information from earlier layers become diluted as networks get deeper. Google Research&\#x27;s DeepCrossAttention instead uses learnable weights and depth-wise cross-attention to combine outputs from previous layers. An arXiv paper posted in February 2025 reported that DCA improved perplexity for a given training time and matched model quality up to 3x faster while adding a negligible number of parameters.

**「Impact」** Teams evaluating transformer efficiency should treat the 3x figure as an &quot;up to&quot; research claim and benchmark DeepCrossAttention against their own workloads and baselines before planning adoption, especially since no independent validation is available.

**「Community discussion」** Commenters largely did not assess the technique itself: one criticized the blog&\#x27;s line graphs as inappropriate for categorical method comparisons, and another asked whether the speedup could compound with MTP and DFlash decoding.

<details><summary>References</summary>
<ul>
<li><a href="https://research.google/blog/supercharging-transformer-residual-connections/">Supercharging transformer residual connections - Google Research</a></li>
<li><a href="https://arxiv.org/abs/2502.06785">[2502.06785] DeepCrossAttention: Supercharging Transformer ...</a></li>

</ul>
</details>

**Tags**: `#transformers`, `#model efficiency`, `#Google Research`, `#deep learning architecture`, `#residual connections`

---

<a id="item-tech-news-2"></a>
### [WebRTC-based card skimming scripts reported on shopping sites](https://www.infohawk.com/news/2026-11-27-black-friday-webrtc-skimmer) ⭐️ 7.0/10

A report published by Infohawk on November 27, 2026 states that credit-card skimming scripts abusing WebRTC were found on popular shopping sites, timing the finding to the Black Friday shopping period. No article body was supplied, so specifics such as the affected merchants, the script names, or the number of compromised sites remain unconfirmed. In the accompanying Hacker News discussion, commenters push back on framing the problem as a WebRTC flaw, arguing the protocol is simply monitored less often for malicious behavior and that the same approach could work over ordinary HTTP requests.

hackernews · scanr · Nov 27, 15:40 · [Discussion](https://news.ycombinator.com/item?id=50668145)

**「What the WebRTC skimmer relies on」** Skimming scripts are injected code that quietly copies payment details from checkout pages, and the recurring vector is not the retailer&\#x27;s own code but the third-party scripts a site embeds. WebRTC — the browser API normally used for video calls and peer-to-peer data transfer — matters here only as a channel: commenters in the discussion argue the technique has little to do with WebRTC&\#x27;s technical capabilities and works because such traffic is monitored less often than ordinary HTTP requests, adding that the same approach could be taken with simple HTTP requests. The item supplies only a headline and reader discussion, with no article body or independent confirmation of which sites were affected or how large the campaign was.

**「Impact」** The discussion points to third-party script embeds, rather than WebRTC itself, as the exposure that merchants would need to address; as one commenter put it, &quot;If you&\#x27;re embedding third party scripts on your site you&\#x27;re always vulnerable.&quot; Blocking or restricting WebRTC alone would therefore not remove the skimming path described in the report.

**「Community discussion」** Commenters focused on the underlying vector: afavour argued the technique &quot;isn&\#x27;t really anything to do with the technical capabilities of WebRTC,&quot; only that it is less frequently monitored, while jszymborski cited the report as justification for ad blocking. Others questioned why ad providers and browsers do not sandbox third-party JavaScript at all, a proposal raised without evidence that it would fully prevent skimming.

**Tags**: `#web security`, `#credit card skimming`, `#WebRTC`, `#third-party scripts`, `#e-commerce`

---

<a id="item-tech-news-3"></a>
### [Convex AI coding skill accused of uploading app ideas without disclosure](https://github.com/convex/convex-backend-skill/issues/64) ⭐️ 7.0/10

A GitHub issue on the convex-backend-skill repository \(issue \#64\) alleges that a Convex AI coding skill sends the user&\#x27;s app idea to a remote server without clearly telling them. Convex CEO Jamie responded in the thread, saying the prompt upload in the plugin powers Convex&\#x27;s &quot;quickstart&quot; feature, which he described as the spiritual successor to Convex Chef, an end-to-end vibe-coding product the company recently shut down; he also noted that Convex as a platform stores customers&\#x27; data and code and runs an AI gateway. The thread as supplied does not show whether the skill&\#x27;s documentation or disclosure was changed, and no further product detail on what exactly is transmitted was provided.

hackernews · MickyTheMouse · Nov 27, 18:02 · [Discussion](https://news.ycombinator.com/item?id=50669765)

**「Background」** The dispute follows Convex&\#x27;s recent shutdown of Convex Chef, an end-to-end AI &quot;vibe-coding&quot; product. In the thread, Convex CEO Jamie said the prompt upload in the plugin powers Convex&\#x27;s &quot;quickstart&quot; feature, which he described as Chef&\#x27;s spiritual successor.

**「What to check」** Developers using the Convex skill should review what the tool sends before running it on confidential product plans, since the vendor has confirmed a prompt upload exists rather than denying it. Teams with data-handling requirements may need to treat app descriptions entered into such skills as data leaving their environment until the disclosure is clarified.

**「From the comments」** One commenter argued that self-hosted open-weight models are the right long-term approach, framing the incident as a reason not to depend on remote services. Another noted that prompt injection is far more common than models making malicious tool calls on their own, while explicitly not claiming malice in this case.

**Tags**: `#AI coding tools`, `#privacy`, `#data exfiltration`, `#developer trust`, `#prompt security`

---

<a id="item-tech-news-4"></a>
### [Essay examines false computer-checked proofs and checker soundness](https://cr.yp.to/proofs/falseccp.html) ⭐️ 7.0/10

A newly published essay hosted at cr.yp.to examines how computer-checked proofs can be false when the proof checker itself has a soundness bug, a concern for formal-methods users working with systems such as Lean and Metamath. It is a technical critique rather than a report of a new compromise, and the supplied material does not identify a specific theorem or deployment that was fooled. The practical question raised is whether acceptance by one checker is enough evidence, given that independent verification and review can catch different failures.

hackernews · \_tk\_ · Nov 27, 15:26 · [Discussion](https://news.ycombinator.com/item?id=50667989)

**「Background」** Proof checkers are supposed to reject any derivation that does not establish a true statement; a soundness bug is a flaw that lets one accept a false result. Daniel J. Bernstein&\#x27;s page links to 199 reports of such bugs across seven proof-checking systems: HOL Light, Mizar, Metamath, Isabelle, Lean, HOL98/HOL4, and Coq/Rocq.

**「Impact」** For developers relying on proof assistants, the concrete takeaway is that a single checker&\#x27;s acceptance should be treated as one layer of assurance, not proof that the intended claim is true; the discussion points to independent verifiers and review of the formal statement as checks against checker soundness bugs and specification errors.

**「Community Discussion」** Commenters argued that the risk is overstated for systems that require multiple independent verifiers—one described Metamath&\#x27;s main databases as requiring five verifiers in five programming languages—while another noted that soundness bugs have been rare and would still need to be exploited to hide a further flaw. A separate commenter raised a different failure mode: an agent can formally verify an implementation against its own incorrect understanding of the requirement.

<details><summary>References</summary>
<ul>
<li><a href="https://cr.yp.to/proofs/falseccp.html">False computer-checked proofs (djb) - cr.yp.to</a></li>
<li><a href="https://x.com/hashbreaker/status/2120889008389837049">Daniel J. Bernstein on X: &quot;Posted new page &quot;False computer ...</a></li>
<li><a href="https://news.lavx.hu/article/d-j-bernstein-catalogs-soundness-bugs-in-seven-proof-checkers">D. J. Bernstein catalogs soundness bugs in seven proof ...</a></li>

</ul>
</details>

**Tags**: `#formal verification`, `#proof assistants`, `#soundness bugs`, `#Lean`, `#Metamath`

---

<a id="item-tech-news-5"></a>
### [SemiAnalysis details Trainium3 microarchitecture and inference cost results](https://newsletter.semianalysis.com/p/trainium3-inferencex) ⭐️ 7.0/10

SemiAnalysis published a Trainium3 deep dive arguing that AWS&\#x27;s ML-first design—where tiles are a first-class primitive rather than an addition to a GPU thread model—now has sufficiently mature software to compete on inference. Its UBenchX microbenchmarks report that Trainium&\#x27;s Descriptor Generation Engines allow peak HBM bandwidth utilization at small message sizes, which the authors say is not possible on Nvidia GPUs, and cover cycle-level SRAM, rack-scale, and attention latency. On InferenceX, the firm reports that Trainium3 PDS with vLLM delivers better performance per TCO than every accelerator except Nvidia Vera Rubin across the TCO-versus-p90-interactivity frontier, while Trainium3 and TPUs trade blows with or beat GB300 on token-generation TCO; the supplied excerpt gives no absolute benchmark figures.

rss · Semianalysis · Nov 27, 15:54

**「Background」** Nvidia&\#x27;s datacenter GPUs evolved from graphics hardware, with Volta adding Tensor Cores, Hopper adding TMA, and Blackwell adding Tensor Memory while graphics-only units were removed. Trainium is AWS&\#x27;s ML-first alternative, built around tiles as a first-class primitive; the source says that approach previously made software a major challenge, and SemiAnalysis&\#x27;s InferenceX/AgentX benchmarks now test it on throughput-latency tradeoffs and TCO using replayed coding-agent sessions.

**「What the cost edge means for inference teams」** Teams weighing Trainium3 for production inference have a concrete cost case to evaluate, but one that comes with a porting condition: the up-to-2.28x tokens-per-dollar advantage over Nvidia&\#x27;s GB300 NVL72 that SemiAnalysis reported came from results Amazon itself submitted to the InferenceX/AgentX benchmark, so it is a vendor-supplied figure rather than an independent measurement. The practical work is therefore in the software stack — moving a serving path off CUDA onto AWS&\#x27;s Neuron toolchain and re-validating KV-cache behavior and tail latency — since the headline per-token saving only materializes if the migrated workload holds its throughput and p95 targets in production.

<details><summary>References</summary>
<ul>
<li><a href="https://cryptobriefing.com/trainium3-nvidia-gb300-inference-benchmark/">Trainium3 competes with Nvidia GB300 in inference performance ...</a></li>
<li><a href="https://blog.eveestatistic.com/blog/trainium3-inference-cost-benchmark">Trainium3 Inference Cost Benchmark: Neuron vs NVIDIA</a></li>
<li><a href="https://thedefiant.io/frontier/ai/amazon-s-trainium3-shows-cost-edge-in-ai-benchmark">Amazon’s Trainium3 Shows Cost Edge in AI Benchmark</a></li>

</ul>
</details>

**Tags**: `#Trainium3`, `#AWS`, `#AI hardware`, `#inference`, `#microarchitecture`

---

<a id="item-tech-news-6"></a>
### [OpenSec discloses CVE-2026-99362, a 9.8 pre-auth root flaw in Linux nfsd](https://opensec.in/blog/nfs2root-cve-2026-99362) ⭐️ 7.0/10

OpenSec has disclosed CVE-2026-99362, a CVSS 9.8 pre-authentication heap overflow in the Linux kernel NFS server, nfsd. According to the alert, an unauthenticated attacker can trigger an out-of-bounds kernel heap write with a single connection to tcp/2049 and obtain a root shell; hosts running NFSv4.1 or NFSv4.2 are affected, including file servers, NAS devices and cluster storage nodes, with the flaw present since Linux 3.16 in 2014. Fixes are listed in Linux 6.12.117, 6.18.61, 7.3.2 and 7.4-rc1 and require a kernel upgrade and reboot; systems that cannot be upgraded immediately can restrict access to tcp/2049 at the firewall. The CVE was made public on November 20, 2026, but the item relays a single OpenSec blog post and does not provide root-cause or exploit details, so the version and impact claims could not be independently verified from the supplied material.

telegram · zaihuapd · Nov 27, 12:57

**「Background」** nfsd is the NFS server built into the Linux kernel; any host exporting NFSv4.1 or 4.2, the default, accepts connections on tcp/2049. The bug is a heap overflow reachable before any login, and the source says it has existed since Linux 3.16 in 2014, with BleepingComputer similarly describing it as a 12-year-old flaw.

**「What affected operators need to do」** Administrators of hosts serving NFSv4.1 or 4.2 should upgrade to a fixed kernel and reboot, because the patch does not take effect until the system restarts. If upgrading immediately is not possible, restricting access to tcp/2049 is the listed workaround, though it can also block legitimate NFS clients.

<details><summary>References</summary>
<ul>
<li><a href="https://opensec.in/blog/nfs2root-cve-2026-99362">NFS2ROOT ( CVE - 2026 - 99362 ): pre-auth root in Linux nfsd | OpenSec</a></li>
<li><a href="https://www.getpagespeed.com/server-setup/security/nfs2root-cve-2026-99362-centos-7">NFS2ROOT ( CVE - 2026 - 99362 ) on CentOS 7: Fixed Kernel</a></li>
<li><a href="https://www.bleepingcomputer.com/news/security/new-nfs2root-linux-flaw-can-let-attackers-gain-root-privileges/">New NFS2ROOT Linux flaw can let attackers gain root privileges</a></li>
<li><a href="https://opensec.in/blog/nfs2root-cve-2026-99362">NFS2ROOT ( CVE - 2026 - 99362 ): pre-auth root in Linux nfsd | OpenSec</a></li>
<li><a href="https://www.getpagespeed.com/server-setup/security/nfs2root-cve-2026-99362-centos-7">NFS2ROOT ( CVE - 2026 - 99362 ) on CentOS 7: Fixed Kernel</a></li>

</ul>
</details>

**Tags**: `#Linux kernel`, `#security vulnerability`, `#NFS`, `#remote exploitation`, `#patching`

---

<a id="item-tech-news-7"></a>
### [Minecraft Bedrock resource-pack flaw affected 26.52–26.63, fixed in 26.65](https://www.zaikei.co.jp/article/20261119/878386.html) ⭐️ 7.0/10

A publicly reported vulnerability in Minecraft Bedrock allowed resource packs carrying a content.zipe file to alter Ore UI files and run hidden scripts when auto-download was enabled on servers or Realms. Developer 8Crafter said in a November 15 Reddit disclosure that it affected versions 26.52 through 26.63, possibly earlier releases, across PC, mobile and console; Java Edition was unaffected. Mojang fixed the issue in version 26.65, and AxmBro released a Windows read-only detection tool that can find content.zipe but cannot determine whether a resource pack is malicious.

telegram · zaihuapd · Nov 27, 18:04

**「Background」** Minecraft Bedrock can automatically download server- or Realm-designated resource packs when a player joins, so the pack&\#x27;s files are applied without a separate manual install. The reported flaw abused that path: a pack containing a content.zipe file could alter files in the game&\#x27;s Ore UI interface framework and run hidden scripts.

**「Impact」** Players running versions 26.52–26.63 should update to 26.65 before joining servers or Realms with resource-pack auto-download enabled. The reported exploits included deleting all saves and obtaining player IP addresses; on Windows, under specific conditions, a pack could open arbitrary URIs without prompting and launch batch files that download malware.

**Tags**: `#Minecraft Bedrock`, `#security vulnerability`, `#resource packs`, `#game security`, `#auto-download`

---

## Financial News

<a id="item-finance-news-1"></a>
### [China&\#x27;s State Council Executive Meeting Calls for Stronger Market-Stabilization Role by &\#x27;National Team&\#x27;](https://www.tmtpost.com/nictation/8220182.html) ⭐️ 7.0/10

At a State Council executive meeting on November 27 chaired by Premier Li Qiang, China&\#x27;s government called for greater use of the &quot;national team&quot; to stabilize the stock market and for optimizing Central Huijin&\#x27;s quasi-&quot;stabilization fund&quot; function, while guiding insurance, enterprise annuity, and social security funds into the market. The meeting also urged listed companies to increase dividends and buybacks and called for stronger full-chain market supervision, but the report gave no specific funding size, tool arrangements, or timetable.

telegram · zaihuapd · Nov 27, 05:35

**「Background」** “National team” is market shorthand for state-backed buyers that step in during downturns, while a “stabilization fund” is a pool meant to absorb selling pressure and support prices. The readout casts Central Huijin, a state-owned financial holding company, as the main vehicle for this quasi-stabilization role, without giving a fund size or operating details.

**「Impact」** If carried out, the plan would enlarge Central Huijin&\#x27;s role as a buyer of broad-based exchange-traded funds — the company has said it will increase ETF purchases — so the most directly affected would be ETF holders and the large listed companies those funds track, while insurers, corporate annuity plans and the social security fund would be encouraged to put more of their money into stocks.

<details><summary>References</summary>
<ul>
<li><a href="https://finance.eastmoney.com/a/202611273941564045.html">finance.eastmoney.com/a/202611273941564045.html</a></li>
<li><a href="https://pro.huxiu.com/article/4781521.html">起底救 市 旗手 中 央 汇 金 - 妙投</a></li>
<li><a href="https://www.21jingji.com/article/20260306/herald/aeea35480d200f8630b204ef92189c17.html">潘功胜：支 持 中 央 汇 金 公司发挥类 平 准 基 金 作用 - 21经济网</a></li>

</ul>
</details>

**Tags**: `#中国资本市场`, `#国常会`, `#中央汇金`, `#平准基金`, `#中长期资金`

---

<a id="item-finance-news-2"></a>
### [央行公布大额存单新规 个人起购门槛降至 10 万元](https://www.news.cn/fortune/20261127/70789d77822242cc82216f51a416f872/c.html) ⭐️ 7.0/10

中国人民银行公布大额存单管理办法，将个人和机构认购起点分别降至10万元和500万元，并同步发布要求金融机构自主定价的存贷款利率管理规定，均于2027年3月21日施行。

telegram · zaihuapd · Nov 27, 11:36

**Tags**: `#中国央行`, `#大额存单`, `#存款利率`, `#金融监管`, `#个人理财`

---