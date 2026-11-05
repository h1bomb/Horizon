---
layout: default
title: "Horizon Summary: 2026-11-05 (EN)"
date: 2026-11-05
lang: en
---

> From 46 items, 11 important content pieces were selected

---

**Technology News**
1. [Go announces encoding/json/v2, a new standard-library JSON API](#item-tech-news-1) ⭐️ 8.0/10
2. [OpenAI says pipeline found 948 Linux root exploits in one scan](#item-tech-news-2) ⭐️ 8.0/10
3. [Tencent Hy4 Open-Weight Model Adds HyCell, HyPDE, and Game Engine Support](#item-tech-news-3) ⭐️ 8.0/10
4. [Anthropic publishes FlashProve specification and code for provable LLM inference](#item-tech-news-4) ⭐️ 8.0/10
5. [Moonshot AI publishes Kimi K3.1 Pro open weights](#item-tech-news-5) ⭐️ 8.0/10
6. [NKI megakernels cut GLM-5.3-Flash decode on Trainium2 to 24.2 ms](#item-tech-news-6) ⭐️ 8.0/10
7. [IEEE Spectrum argues AI vulnerability discovery forces technical debt repayment](#item-tech-news-7) ⭐️ 7.0/10
8. [Huginn looped-transformer profiling on B200 finds weight sharing alone does not cut HBM reads](#item-tech-news-8) ⭐️ 7.0/10
9. [Huawei reportedly asks Ascend 960DT buyers to source Samsung, SK Hynix HBM](#item-tech-news-9) ⭐️ 7.0/10
10. [Apple to screen iCloud public links for harmful content in iOS 27.3](#item-tech-news-10) ⭐️ 7.0/10

**Financial News**
1. [Oracle Reportedly Cancels $7 Billion Tencent AI Chip Lease](#item-finance-news-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Go announces encoding/json/v2, a new standard-library JSON API](https://go.dev/blog/jsonv2) ⭐️ 8.0/10

Go has announced a new JSON API centered on encoding/json/v2, a redesign of how the standard library handles JSON, according to the Go blog. The naming casts it as a successor to the existing encoding/json package rather than a separate third-party library. The announcement as supplied does not detail release timing, specific version numbers, or backward-compatibility guarantees, so those remain unconfirmed.

hackernews · olexsmir · Nov 4, 17:52 · [Discussion](https://news.ycombinator.com/item?id=50369106)

**「Background」** Go’s \`encoding/json\` package is the long-standing standard-library API for marshaling and unmarshaling JSON, and it is the interface many Go programs use for that work. The newly announced \`encoding/json/v2\` is a redesign of that API rather than a separate data format, so the practical context is how existing \`encoding/json\` code and idioms map onto the new packages and options.

**「Impact」** For teams already using encoding/json, moving to v2 is not a drop-in swap: code that relies on convenience helpers such as MarshalIndent has to be rewritten, which adds migration work for existing services that emit human-readable JSON.

**「Community discussion」** Commenter CamouflagedKiwi said they generally like encoding/json/v2 but wished MarshalIndent had been kept, arguing the equivalent v2 code is complicated and non-obvious for both migration and quick readable output. Another commenter, txomon, reported using the lower-level jsontext package at their company for clients requiring specific parse errors, praising its speed while noting it offers no introspection.

**Tags**: `#Go`, `#JSON`, `#API design`, `#standard library`, `#software engineering`

---

<a id="item-tech-news-2"></a>
### [OpenAI says pipeline found 948 Linux root exploits in one scan](https://openai.com/index/a-thousand-fewer-paths-to-root/) ⭐️ 8.0/10

OpenAI says its autonomous vulnerability-research pipeline dynamically reproduced 1,724 Linux kernel vulnerabilities in a single October 2026 scan and generated 948 working local privilege-escalation \(LPE\) exploits that let an unprivileged local user obtain root, plus 291 information-leak proof-of-concepts. The company put total API cost at $1,213,430, or about $1,279 per successful LPE exploit, and cites roughly $359 as the lower marginal development cost; it also says at least 10 exploitation techniques were confirmed novel by third-party experts, including new cache-spraying objects, page grooming, data-only arbitrary-write escalation, and arbitrary type confusion. These figures are OpenAI&\#x27;s own account, and the post does not say how many of the flaws were previously known, already patched, or reported upstream.

hackernews · dangelosaurus · Nov 4, 23:33 · [Discussion](https://news.ycombinator.com/item?id=50372929)

**「Why local privilege escalation matters」** Local privilege escalation \(LPE\) is a post-compromise step: the attacker needs a way to run code as an unprivileged local user, but a working exploit then crosses the kernel&\#x27;s user/root boundary. Linux kernel LPE research is difficult because a defect must still be reachable, reliably triggerable, and convertible into a privilege change across many drivers, filesystems, and networking subsystems.

**「Why it matters」** Because the exploits need only local access, the reported volume weakens the practice of treating an unprivileged shell as a containment boundary: operators should assume local compromise can become root until the affected kernel paths are identified and fixed. The cost figures also shift exploit economics, since OpenAI&\#x27;s stated $359–$1,279 per working exploit is far below the $20,000–$70,000 per-exploit bounty range it cites for Pwn2Own and TyphoonPWN.

**「Discussion」** Commenters focused on why a general-purpose kernel contains so many escalation paths, with Plasmoid asking whether Linux is simply too complex to reason about or whether the flaw lies in the security model or language implementation, and nas saying local escalation was long assumed possible but 948 cases is &quot;kind of shocking.&quot; rmbryan asked what mitigating factors keep that level of vulnerability from being an existential threat, while OpenAI&\#x27;s dangelosaurus identified the work as his team&\#x27;s and invited questions.

**Tags**: `#linux-kernel`, `#privilege-escalation`, `#vulnerability-research`, `#ai-security`, `#open-source-security`

---

<a id="item-tech-news-3"></a>
### [Tencent Hy4 Open-Weight Model Adds HyCell, HyPDE, and Game Engine Support](https://hy.tencent.ai/research/hy4) ⭐️ 8.0/10

Tencent has released Hy4, an open-weight foundation model, with open-sourced HyCell and HyPDE models for single-cell representation and physical-field modeling. For game development, Tencent says it worked with its Interactive Entertainment Group to curate training data and evaluations covering feature implementation, gameplay logic, state tracking, and asset pipelines, and adapted Hy4 for Unreal Engine, Unity, and Godot plus multiplayer development. The release acknowledges a gap between Hy4 and top proprietary models on internal benchmarks for research-level mathematics, long-horizon coding, model self-improvement, and advanced visual question answering, and says it will continue scaling pre-training and post-training.

hackernews · Philpax · Nov 4, 14:11 · [Discussion](https://news.ycombinator.com/item?id=50365780)

**「Background」** Hy4 is the latest entry in Tencent&\#x27;s Hy model family and, according to Interesting Engineering, the first in that family to add visual understanding. Tencent said it planned to publish the model weights and system cards in the days after launch, along with safety work focused on cybersecurity and biological safety.

**「Impact」** Developers building games in Unreal Engine, Unity, or Godot gain an open-weight model that Tencent says was adapted for feature implementation, gameplay logic, state tracking, and asset pipelines. Teams considering it for latency-sensitive workflows should first check the reported trade-off: commenter chriddyp found it accurate but &quot;verrrry slow&quot; in a data-analytics benchmark, spending a long time on each question.

**「Community Discussion」** Commenters highlighted the open-sourcing of HyCell and HyPDE as a notable contrast with more restrictive releases, while simonw singled out the game-development focus and engine adaptations. chriddyp reported that in Plotly&\#x27;s data-analytics benchmark Hy4 landed between GPT-6.1 Sol and GPT-6.1 Terra on cost/accuracy, describing it as very thorough but very slow.

<details><summary>References</summary>
<ul>
<li><a href="https://www.tencent.com/tencent-launches-hy4-joining-the-ranks-of-the-worlds-leading-open-source-ai-models/">Tencent Launches Hy 4 , Joining the Ranks of the... - Tencent</a></li>
<li><a href="https://interestingengineering.com/ai-robotics/tencent-hy4-open-source-model">China&#x27;s Tencent Hy 4 challenges world&#x27;s top models with 7.2% error rate</a></li>

</ul>
</details>

**Tags**: `#open-weight models`, `#foundation models`, `#AI research`, `#game development`, `#open source`

---

<a id="item-tech-news-4"></a>
### [Anthropic publishes FlashProve specification and code for provable LLM inference](https://www.anthropic.com/research/provable-inference) ⭐️ 8.0/10

Anthropic has published a technical specification and code for FlashProve, a cryptographic system intended to prove that a given LLM output was produced by a specified model and set of weights. The approach calls for providers to publish a model fingerprint that can be matched against outputs without disclosing the weights, and Anthropic says verification can run locally. The company describes the research as ongoing and says it has no deployment plan; the stated goals include detecting model substitution and checking third-party claims about which model performed a task.

hackernews · ltononro · Nov 4, 17:17 · [Discussion](https://news.ycombinator.com/item?id=50368626)

**「Background」** Provable-inference schemes aim to let a verifier confirm that a claimed model produced a given output without revealing its weights, a problem that is especially hard for closed models. A September 2026 paper proposed Maverick, a protocol for private and verifiable LLM inference built around delegated matrix-vector multiplication, while noting that existing approaches often imposed substantial server overhead or additional trust assumptions.

**「Impact」** For closed-model providers, the scheme would require committing to and publishing fingerprints, and commenters summarizing the design say a roughly 6.5 MB commitment covers about 16 million requests, with clients downloading that commitment plus one proof per request. Proof checking was reported at 17 seconds on 24 threads and 21 seconds on a single thread, making per-request verification impractical for routine low-latency use and more suitable for spot audits or high-assurance checks.

**「Community Discussion」** Commenters debated both credit and practicality: one said the work builds on their earlier VerInf project with little attribution, while others argued that open-weight models can be verified simply by re-running deterministic inference and that closed-model proofs are harder and cost roughly 90–100× more compute. Another commenter noted that such proofs could catch providers silently routing requests to a different model.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/html/2609.10264v1">Maverick: Private and Verifiable LLM Inference Made Practical ...</a></li>
<li><a href="https://eprint.iacr.org/2026/1955">Maverick: Private and Verifiable LLM Inference Made Practical ...</a></li>

</ul>
</details>

**Tags**: `#provable inference`, `#LLM verification`, `#cryptography`, `#zero-knowledge proofs`, `#AI trust and safety`

---

<a id="item-tech-news-5"></a>
### [Moonshot AI publishes Kimi K3.1 Pro open weights](https://huggingface.co/moonshotai/Kimi-K3.1-Pro) ⭐️ 8.0/10

Moonshot AI has published open weights for Kimi K3.1 Pro on Hugging Face, the first model in its K3.1 series. The model is natively multimodal and agent-oriented, with 2.8 trillion total parameters, 104 billion active parameters, and roughly 1 million tokens of context; the weights are released in MXFP4 quantization. Moonshot also offers an API through platform.kimi.ai under the kimi-k3.1-pro identifier, compatible with OpenAI and Anthropic interfaces. The supplied material does not include verified benchmark results.

hackernews · abrarthought · Nov 4, 15:30 · [Discussion](https://news.ycombinator.com/item?id=50366999)

**「Predecessor: Kimi K3」** Moonshot AI&\#x27;s previous flagship, Kimi K3, was itself an open-weight, natively multimodal agentic model at 2.8 trillion parameters with a 1-million-token context window, and its release put roughly 1.56 TB of weights on Hugging Face. K3.1 Pro is described as the first model in the successor K3.1 series and keeps that same 2.8T total / 104B active parameter scale, now shipped in MXFP4 quantized form.

**「Impact」** Full local deployment is likely to require multi-GPU infrastructure: one commenter estimated an 8x B300 node, so most developers will probably use the API or third-party inference rather than run the 2.8T-parameter model themselves. The weights are quantized to MXFP4, but the 2.8T total parameter count still implies substantial memory and serving capacity.

**「Community discussion」** Commenters clashed over benchmark legitimacy, with some calling K3.1 Pro “benchmaxxed” relative to DeepSeek V4.1-Flash and Hy4, while commenter dmckinno said their testing did not show that and described it as a strong open model slightly behind the frontier. Commenter minimaxir reported that third-party providers including OpenRouter, Together, and Modal were hosting the model, with Together apparently offering double the throughput of Moonshot’s endpoint at the same price and Modal double that.

<details><summary>References</summary>
<ul>
<li><a href="https://huggingface.co/moonshotai/Kimi-K3">moonshotai/ Kimi -K3 · Hugging Face</a></li>
<li><a href="https://researchaudio.io/p/the-largest-open-model-ever-runs-on-3-7-percent-of-itself">The largest open model ever runs on 3.7 percent of itself</a></li>

</ul>
</details>

**Tags**: `#open-weight models`, `#LLM release`, `#Moonshot AI`, `#model benchmarks`, `#LLM inference`

---

<a id="item-tech-news-6"></a>
### [NKI megakernels cut GLM-5.3-Flash decode on Trainium2 to 24.2 ms](https://www.reddit.com/r/MachineLearning/comments/1xo0yuq/p_nki_layer_megakernels_for_glm53flash_on_aws/) ⭐️ 8.0/10

RunAnywhere open-sourced an AWS Trainium2 inference engine for GLM-5.3-Flash, a 320B Mixture-of-Experts model with a 1M-token context, that serves the model on one trn2.48xlarge and rewrites each layer half as a single NKI kernel, or each whole layer for sparse-attention layers. On the same layout, a batch-8 decode step fell from 32.2 ms in the 17 October build to 24.2 ms on 1 November; the author attributes the gap to long chains of small vector-engine instructions at about 153 ns fixed cost each, HBM writes at every kernel boundary, and 125 cross-chip collectives per step. The remaining 24.2 ms includes a 6.1 ms memory floor, 10.0 ms of engines busy beyond it, 4.6 ms of waits inside kernels, and 2.8 ms of exposed collectives. An approximation remains in sparse-attention prefill on 1.2% of selections, shifting next-token log-probabilities by 0.012 to 0.021 nats on average and changing the top token at 3 of 448 positions; no task-level evaluation has been run on this build.

reddit · r/MachineLearning · /u/WildCard727 · Nov 4, 21:47

**「Context: the model and the missing stock path」** GLM-5.3-Flash, released by Z.ai in August 2026 under an MIT license, is a 320B-total, 18B-active mixture-of-experts model with a 1,048,576-token context window that combines KDA linear attention with sparse attention. That hybrid architecture is what this engine targets: the author notes the latest vLLM Neuron plugin registers no GLM model and NxD Inference is in maintenance mode, so there was no stock AWS stack to benchmark the custom kernels against.

**「Impact」** Developers adopting the engine should validate kernels on actual Trainium2 hardware rather than relying on NKI&\#x27;s simulator alone: the author reports that three kernels passed simulation but returned wrong answers on the device, involving PSUM accumulation groups, unfenced in-kernel collectives, and cross-program shared-HBM reads. The reported AgentX result of up to 28.9 agent requests per minute and 35.9 tokens/s median decode at 16 agents is self-run, one hour per point, and has no GPU comparison, so teams must benchmark their own workload before treating it as a cross-platform performance claim.

<details><summary>References</summary>
<ul>
<li><a href="https://www.marktechpost.com/2026/08/26/z-ai-releases-glm-5-3-flash-a-320b-a18b-natively-multimodal-moe-with-a-1m-token-context/">Z.ai Releases GLM-5.3-Flash: A 320B-A18B Natively Multimodal ...</a></li>
<li><a href="https://local-ai-zone.github.io/blog/glm-5-3-flash-deep-dive.html">GLM-5.3-Flash: 320B MoE Beats GLM-5.2, Formerly Ox Alpha</a></li>

</ul>
</details>

**Tags**: `#AWS Trainium`, `#LLM inference`, `#kernel optimization`, `#Mixture-of-Experts`, `#open source`

---

<a id="item-tech-news-7"></a>
### [IEEE Spectrum argues AI vulnerability discovery forces technical debt repayment](https://spectrum.ieee.org/ai-in-cybersecurity-php2shell-vulnerability) ⭐️ 7.0/10

An IEEE Spectrum article argues that AI-assisted vulnerability discovery is exposing decades of accumulated technical debt in software and forcing organizations to remediate it. The piece is an argument about software maintenance and security practice, not the announcement of a specific tool, version, or independently measured result, and the supplied material provides no remediation figures. It is aimed at software engineers and security teams facing a larger volume of vulnerability fixes.

hackernews · pseudolus · Nov 4, 11:52 · [Discussion](https://news.ycombinator.com/item?id=50364336)

**「Background」** The IEEE Spectrum article, published 2 November 2026, is an analysis built around the PHP2Shell vulnerability \(tool-1-1\). PHP2Shell serves as its example of legacy systems becoming dangerous liabilities \(tool-1-3\). That example underpins the piece&\#x27;s argument that AI-assisted vulnerability discovery is exposing decades of accumulated security debt \(tool-1-3\).

**「Patch without a disclosure window」** For teams running affected PHP versions, the practical consequence is that patching can no longer assume a gap between disclosure and exploitation: the PHP2Shell flaws were rated CVSS 9.2 and reportedly exploited before disclosure. Operators should inventory PHP deployments and apply fixes immediately rather than waiting for a coordinated disclosure window.

**「Community discussion」** Commenters debated whether AI-driven fixes amount to paying down debt or create a compulsory treadmill of feature-neutral repair work; swatcoder argued many issues require restructuring rather than narrow patches, while xbmcuser said AI auditing could finally make open-source code review a reality. Others welcomed incidental discovery of state-held zero-days but treated the short-term patch burden as a tradeoff for more robust software.

<details><summary>References</summary>
<ul>
<li><a href="https://spectrum.ieee.org/ai-in-cybersecurity-php2shell-vulnerability">PHP2Shell Is a Wakeup Call for AI in Cybersecurity - IEEE ...</a></li>
<li><a href="https://hn.today/s/ai-is-forcing-us-to-pay-off-40-years-of-technical-debt">AI is forcing us to pay off 40 years of technical debt - hn.today</a></li>
<li><a href="https://labs.cloudsecurityalliance.org/research/csa-research-note-php2shell-pre-disclosure-exploitation-2026/">PHP2Shell: Exploitation Before Disclosure for an AI-Found Flaw</a></li>
<li><a href="https://tech.yahoo.com/cybersecurity/articles/ai-assisted-research-uncovers-critical-012743884.html">AI-Assisted Research Uncovers Critical PHP2Shell RCE ...</a></li>
<li><a href="https://alphasignal.ai/news/openai-s-php2shell-exposes-70-of-websites-to-remote-code-attacks">OpenAI&#x27;s PHP2Shell Exposes 70% of Websites to Remote Code ...</a></li>

</ul>
</details>

**Tags**: `#AI security`, `#vulnerability discovery`, `#technical debt`, `#open source security`, `#cybersecurity`

---

<a id="item-tech-news-8"></a>
### [Huginn looped-transformer profiling on B200 finds weight sharing alone does not cut HBM reads](https://www.reddit.com/r/MachineLearning/comments/1xnskvt/do_looped_transformers_save_hbm_traffic_profiling/) ⭐️ 7.0/10

A technical post profiling Huginn-style looped transformers on a B200 reports that sharing one set of recurrent weights saves storage but, by itself, does not prevent the GPU from rereading those weights from HBM at every iteration. In a synthetic chain of eight matmuls, one shared 72 MiB weight ran 24% faster than eight identical copies and read almost nothing from HBM; at 288 MiB, which exceeds L2, the advantage disappeared. In the full Huginn Core teaching implementation with random weights, eight iterations took roughly eight times as long and read about eight times as much HBM data as one. The author links the code and raw Nsight Compute data and asks whether persistent kernels could keep recurrent weights on chip across iterations.

reddit · r/MachineLearning · /u/2dayyy6 · Nov 4, 16:26

**「Background」** Looped, or recurrent-depth, transformers apply one shared transformer block repeatedly rather than stacking distinct layers, so the same parameters are reused at every iteration. Whether that reuse also reduces memory traffic depends on the GPU cache hierarchy, since weights that do not stay resident in L2 must be fetched from HBM again on each pass.

**「What this means for looped-model builders」** For teams building looped or weight-tied models, the profile implies storage savings and bandwidth savings must be engineered separately: a shared 72 MiB weight chain avoided HBM reads and ran 24% faster, but at 288 MiB — far beyond the B200&\#x27;s L2 cache, which spec sheets list at roughly 50 MB — the advantage vanished and the full eight-iteration Huginn Core still read about eight times as much data as a single pass. The practical step is to profile reuse with Nsight Compute and either size recurrent weight blocks to stay cache-resident or test the persistent-kernel approach the author raises, rather than assuming tied weights automatically cut HBM traffic.

<details><summary>References</summary>
<ul>
<li><a href="https://tosea.ai/blog/looped-transformer-recurrent-depth-astra-guide">What Is a Looped Transformer ? Complete Guide to Recurrent Depth...</a></li>
<li><a href="https://cputronic.com/gpu/nvidia-b200-sxm-192-gb">NVIDIA B200 SXM 192 GB: Detailed Specifications and Benchmark ...</a></li>
<li><a href="https://hmc-tech.com/gpus/nvidia-b200">NVIDIA B200 Full Specs - HMC</a></li>

</ul>
</details>

**Tags**: `#looped transformers`, `#HBM bandwidth`, `#GPU profiling`, `#weight reuse`, `#Nsight Compute`

---

<a id="item-tech-news-9"></a>
### [Huawei reportedly asks Ascend 960DT buyers to source Samsung, SK Hynix HBM](https://thenextweb.com/news/huawei-hbm-smuggling-samsung-sk-hynix-ascend-960dt) ⭐️ 7.0/10

The Information reported that Huawei has told some customers its next-generation flagship AI chip, Ascend 960DT, will rely mainly on Samsung and SK Hynix HBM and that those customers must source the memory themselves because Chinese HBM capacity is insufficient. The report also describes HBM being shipped into mainland China soldered to low-performance processors and declared under processor codes via Hong Kong, then removed; a Shenzhen chip broker cited by the report said a single HBM3E unit now costs about $4,000, up from a few hundred dollars a year earlier. These details are secondhand, and the smuggling and pricing claims were not independently verified in the supplied material.

telegram · zaihuapd · Nov 4, 14:52

**「Background」** HBM is the high-bandwidth memory that AI accelerators rely on, and China’s domestic suppliers have not produced enough to meet Huawei’s needs. The shortage was already affecting Huawei’s current top AI chip: TrendForce, citing The Information, reported that Huawei had raised the suggested price of the Ascend 950DT to more than RMB 250,000 \(about US$37,000\), with HBM shortages pushing chip prices higher.

**「Impact」** For Ascend 960DT buyers, the reported arrangement shifts HBM procurement and cost onto them rather than Huawei, with the cited $4,000-per-HBM3E price indicating a steep burden compared with a year earlier.

<details><summary>References</summary>
<ul>
<li><a href="https://www.trendforce.com/news/2026/11/03/news-china-reportedly-obtains-smuggled-hbm-via-server-packages-huawei-960dt-faces-domestic-hbm-shortage/">[News] China Reportedly Obtains Smuggled HBM via Server Packages...</a></li>

</ul>
</details>

**Tags**: `#Huawei`, `#Ascend 960DT`, `#HBM`, `#AI chips`, `#supply chain`

---

<a id="item-tech-news-10"></a>
### [Apple to screen iCloud public links for harmful content in iOS 27.3](https://9to5mac.com/2026/11/04/with-ios-27-3-apple-will-start-checking-icloud-public-links-for-harmful-content/) ⭐️ 7.0/10

Apple says it will begin checking iCloud content shared through “anyone with the link” links for harmful material starting with iOS, iPadOS, macOS, and visionOS 27.3. Content shared only with specified people is not covered, according to the report. If content is judged harmful, Apple reserves the right to move, refuse, modify, or delete it, and may restrict or disable accounts that upload harmful material and refer cases to law enforcement when necessary.

telegram · zaihuapd · Nov 5, 02:11

**「Context: link sharing policy」** iCloud&\#x27;s &quot;Anyone with the Link&quot; option makes an item accessible to anyone holding its URL, and Apple&\#x27;s new support document states that from version 27.3 of iOS, iPadOS, macOS and visionOS, content shared that way &quot;is made accessible to Apple to check for harmful content.&quot; The policy arrives alongside the first iOS 27.3 beta, which 9to5Mac reports also adds Siri AI improvements and new Safari features.

<details><summary>References</summary>
<ul>
<li><a href="https://9to5mac.com/2026/11/04/with-ios-27-3-apple-will-start-checking-icloud-public-links-for-harmful-content/">With iOS 27.3, Apple will start checking iCloud public links ...</a></li>
<li><a href="https://www.macrumors.com/2026/11/04/ios-27-3-icloud-link-check/">Apple Will Check Public iCloud Links for Harmful Content ...</a></li>
<li><a href="https://support.apple.com/en-us/149168">Learn more about sharing content that can be accessed by ...</a></li>

</ul>
</details>

**Tags**: `#Apple`, `#iCloud`, `#content moderation`, `#privacy`, `#platform policy`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Oracle Reportedly Cancels $7 Billion Tencent AI Chip Lease](https://www.tradingview.com/news/seekingalpha:e51e68f4d094b:0-oracle-cancels-7b-ai-chip-lease-with-tencent-amid-us-concerns-ft/) ⭐️ 7.0/10

Oracle reportedly canceled a five-year AI chip lease with Tencent worth about $7 billion after US officials raised concerns about the deal, according to a Financial Times report cited by Seeking Alpha. The arrangement would have given Tencent access to roughly 100,000 advanced AI chips through Oracle data centers in Southeast Asia.

telegram · zaihuapd · Nov 4, 11:01

**「Background」** Tencent signed the five-year lease this year for about 100,000 advanced chips hosted in Oracle’s Southeast Asian data centers, a way to use chips that could not be deployed in China.

<details><summary>References</summary>
<ul>
<li><a href="https://xenospectrum.com/en/tencent-oracle-ai-chip-lease-prepayments/">Tencent Reportedly Leases About 100,000 AI Chips From Oracle in...</a></li>

</ul>
</details>

**Tags**: `#US-China tech policy`, `#AI chips`, `#Oracle`, `#Tencent`, `#data centers`

---