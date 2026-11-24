---
layout: default
title: "Horizon Summary: 2026-11-24 (EN)"
date: 2026-11-24
lang: en
---

> From 38 items, 13 important content pieces were selected

---

**Technology News**
1. [Ladybird releases first alpha builds for macOS and Linux](#item-tech-news-1) ⭐️ 8.0/10
2. [Zhipu&\#x27;s GLM-5.4 debuts looped transformer architecture for coding](#item-tech-news-2) ⭐️ 8.0/10
3. [Codex2api suspected supply-chain backdoor in versions 3.1.10–3.1.12](#item-tech-news-3) ⭐️ 8.0/10
4. [Nvidia Board Reinstates Jensen Huang as CEO After U.S. Input](#item-tech-news-4) ⭐️ 7.0/10
5. [NariQ releases 3-bit Qwen3.8-27B GGUF claiming near-BF16 quality](#item-tech-news-5) ⭐️ 7.0/10
6. [AI-assisted Lean Riemann Hypothesis proof alleged vacuous](#item-tech-news-6) ⭐️ 7.0/10
7. [Singapore PM says no chip-control evasion route amid Megaspeed probe](#item-tech-news-7) ⭐️ 7.0/10
8. [Anthropic says internal Claude model found VP≠VNP, publishes Lean 4 proof](#item-tech-news-8) ⭐️ 7.0/10

**Technology Blog**
1. [vLLM Day-0 Support for ERNIE 5.5 Flash via a Plugin](#item-tech-blog-1) ⭐️ 7.0/10

**Financial News**
1. [Fed&\#x27;s Williams Says More Work Needed on Inflation](#item-finance-news-1) ⭐️ 8.0/10
2. [AI selloff casts shadow over DeepSeek and Moonshot listing plans](#item-finance-news-2) ⭐️ 8.0/10
3. [Shanghai Metro to Adjust Fares for First Time in 21 Years](#item-finance-news-3) ⭐️ 7.0/10
4. [Report: SpaceX Rents AI Computing Power to Anthropic and Google](#item-finance-news-4) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Ladybird releases first alpha builds for macOS and Linux](https://ladybird.org/posts/alpha/) ⭐️ 8.0/10

Ladybird has released its first alpha, providing installable macOS and Linux builds of its from-scratch browser engine instead of requiring users to compile it. The project implements most core browser components itself, including HTML parsing, CSS, layout, JavaScript and WebAssembly, while relying on external HarfBuzz, Skia, ffmpeg and SQLite. It runs tabs in separate processes and handled most sites in a reviewer&\#x27;s tests, including ffmpeg-in-WebAssembly and Pyodide, but Datasette Lite failed because Service Worker support is incomplete. The alpha announcement warns that some websites will not work and that the browser will sometimes crash.

hackernews · janvdberg · Nov 23, 16:13 · [Discussion](https://news.ycombinator.com/item?id=50614249)

**「Background」** Ladybird descends from SerenityOS and still incorporates code from that predecessor project alongside external libraries such as HarfBuzz, Skia, ffmpeg, and SQLite; the rest of the browser engine is its own implementation. The alpha follows an October 2026 development push that added a new JavaScript JIT, moved style and layout onto their own thread, and replaced the Cranelift-based WebAssembly engine with new code, while web-platform-tests passes rose by 75,650.

**「Impact」** Developers can now test Ladybird without building it, but service-worker-dependent applications remain a concrete compatibility gap—Datasette Lite fails on a missing navigator.serviceWorker.startMessages implementation—so the alpha should not be treated as a complete compatibility target.

**「Community discussion」** Commenters reported that many sites rendered correctly, though one noted slightly jerky scrolling; another said NoVNC felt snappier than in Firefox and planned to try Ladybird seriously. Others argued the project needs a stronger fingerprinting defense and asked what security precautions alpha users should take.

**Tags**: `#Ladybird`, `#browser engine`, `#open source`, `#alpha release`, `#web compatibility`

---

<a id="item-tech-news-2"></a>
### [Zhipu&\#x27;s GLM-5.4 debuts looped transformer architecture for coding](https://z.ai/blog/glm-5.4) ⭐️ 8.0/10

Z.ai released GLM-5.4, its first model built on a looped transformer architecture, in which a group of weight-shared layers runs for multiple iterations to deepen the network without increasing parameter count. The coding-focused model is not available as open weights and cannot currently be reached through Z.ai&\#x27;s regular API or OpenRouter; access requires the Coding Plan subscription, whose API key works with the same OpenAI-compatible Responses API at https://api.z.ai/api/v1. Simon Willison tested it through that route and found its &quot;pelican riding a bicycle&quot; outputs similar in quality to GLM-5.3, while the architecture description remains a vendor claim without independent benchmark results in the source.

hackernews · foohis · Nov 23, 10:06 · [Discussion](https://news.ycombinator.com/item?id=50609685)

**「Context: looped layers and the GLM line」** A loop transformer reuses one set of weight-shared layers for several iterations per forward pass, buying extra depth without adding parameters; Thinking Machines Lab described the same approach for its Inkling 2 Mini model on November 20, days before Z.ai&\#x27;s release. GLM-5.4 also continues a fast cadence of Z.ai releases — the source compares its output against GLM-5.1, 5.2 and 5.3, noting that 5.3 and 5.4 produce stylistically similar results while 5.1 and 5.2 were visibly distinct.

**「Access and cost constraints for developers」** Developers who want to try GLM-5.4 cannot reach it through Z.ai&\#x27;s regular Model API or OpenRouter; the only reported route is a Coding Plan subscription, whose API key still works against the same OpenAI-compatible endpoint at https://api.z.ai/api/v1. Early testers report runs that spend 30 to 60+ minutes reasoning and consume subscription quota quickly, and Z.ai&\#x27;s documentation says the standard Model API will be opened only after a security assessment is completed.

**「Community discussion」** Commenters praised Zhipu for publishing architectural detail that Western labs keep private, with one calling looped transformers an obvious direction despite unresolved problems. A competing experience held that Chinese models&\#x27; long &quot;marathon thinking&quot; sessions make even conceptually simple tasks slow because they second-guess themselves, which the commenter speculated helps benchmark scores; another commenter framed looping as a response to inference&\#x27;s memory-bandwidth bottleneck.

<details><summary>References</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=0dOluS-T4yc">GLM - 5 . 4 is here! looped transformer ?! no benchmarks ?!</a></li>
<li><a href="https://docs.z.ai/guides/llm/glm-5.4">GLM - 5 . 4 - Overview - Z.AI DEVELOPER DOCUMENT</a></li>

</ul>
</details>

**Tags**: `#LLMs`, `#loop transformers`, `#GLM-5.4`, `#coding models`, `#model architecture`

---

<a id="item-tech-news-3"></a>
### [Codex2api suspected supply-chain backdoor in versions 3.1.10–3.1.12](https://github.com/WormW/codex2api-incident-2026-11) ⭐️ 8.0/10

According to a circulating incident report, Codex2api&\#x27;s author account was compromised and an attacker bypassed the main branch by pushing tags, causing releases to be built with a backdoor. Version 3.1.11 removed authentication, creating an unauthenticated remote command execution path, while a workflow exfiltrated 16 GitHub Actions secrets and affected at least 21 repositories under the same account. Users who installed or updated to versions 3.1.10–3.1.12 are advised to stop using them immediately, roll back to 3.1.9, and rotate the GitHub token, SSH keys, database credentials, DeepSeek keys, and all other related secrets.

telegram · zaihuapd · Nov 23, 11:21

**「CI pipelines as an attack surface」** GitHub release builds typically run inside Actions workflows that hold repository secrets such as tokens, SSH keys, and API credentials, so a pushed tag can ship code that never went through review on the main branch. Researchers documented this pattern in the &quot;wfx&quot; campaign, where hijacked GitHub accounts injected workflow code that harvested reachable credentials, then reverted the malicious commit and deleted the run and its logs \(tool-2-1, tool-2-3\). The Codex2api report follows the same shape — tag-based publishing plus a workflow exfiltrating 16 Actions secrets — although the supplied source does not establish a link to that specific campaign.

**「Required remediation」** Users who installed or updated Codex2api 3.1.10–3.1.12 should stop it, roll back to 3.1.9, and rotate GitHub tokens, SSH keys, database credentials, and DeepSeek API keys; the report says v3.1.11 removed authentication, exposing deployments to unauthenticated remote command execution.

<details><summary>References</summary>
<ul>
<li><a href="https://www.ox.security/blog/thousands-of-github-accounts-hijacked-with-wfx-loot-ci-secret-stealing-malware-via-github-actions-npm/">Thousands Of GitHub Accounts Hijacked With wfx-loot CI Secret ...</a></li>
<li><a href="https://labs.cloudsecurityalliance.org/research/csa-research-note-wfx-github-ci-secret-stealer-20261112-csa/">The wfx Campaign: Hijacked GitHub Accounts Harvest CI Secrets</a></li>

</ul>
</details>

**Tags**: `#supply-chain security`, `#GitHub Actions`, `#security incident`, `#secrets exfiltration`, `#remote code execution`

---

<a id="item-tech-news-4"></a>
### [Nvidia Board Reinstates Jensen Huang as CEO After U.S. Input](https://www.cnbc.com/2026/11/23/nvidia-jensen-huang-ceo.html) ⭐️ 7.0/10

Nvidia&\#x27;s board reinstated Jensen Huang as president, CEO, and board director, according to the Nvidia newsroom announcement linked in a Hacker News post. The board statement, quoted in the discussion, says it received input from senior levels of the U.S. government and is confident that Huang&\#x27;s reinstatement poses no national security risk. The post also links to a CNBC report but supplies no article text, so the circumstances of Huang&\#x27;s earlier departure and the government&\#x27;s role remain unverified in the supplied material.

hackernews · jaz · Nov 23, 14:00 · [Discussion](https://news.ycombinator.com/item?id=50611576)

**「Earlier context」** Nvidia’s board had rejected an offer from Huang to return just days before the Nov. 23, 2026 reinstatement, according to CNBC, making the announcement a rapid reversal rather than a routine succession decision. Nvidia’s own release confirms the Nov. 23 board action but, in the supplied excerpt, gives no account of the events that led to Huang’s departure.

**「Community Discussion」** Commenters seized on the board&\#x27;s disclosure that it received input from &quot;senior levels of the United States government,&quot; with one calling it the most operative part of the statement. Others debated whether the rapid reversal reflected political pressure or an absence of evidence of wrongdoing, and one argued the episode shows a firm&\#x27;s nominal governance structure may not be its real one.

<details><summary>References</summary>
<ul>
<li>NVIDIA Board Reinstates Jensen Huang as President, CEO and ...</li>
<li>Nvidia board reinstates Jensen Huang as CEO just days after rejecting his ...</li>

</ul>
</details>

**Tags**: `#Nvidia`, `#tech industry`, `#corporate governance`, `#US politics`, `#semiconductors`

---

<a id="item-tech-news-5"></a>
### [NariQ releases 3-bit Qwen3.8-27B GGUF claiming near-BF16 quality](https://huggingface.co/nari-labs/Qwen3.8-27B-NariQ-GGUF) ⭐️ 7.0/10

NariQ has released 3-bit-or-lower GGUF quantizations of Qwen3.8-27B for local inference, including a 10 GB file it says retains near-BF16 quality across agentic, math, multilingual, and image-understanding tasks; running them currently requires NariQ&\#x27;s llama.cpp fork. In NariQ&\#x27;s self-reported benchmarks, the 3-bit and 2.5-bit versions are roughly at BF16 parity on several tests—Terminal-Bench 2.1 scores 63.8 and 60.2 versus 62.6 for BF16, and AIME 25+26 scores 98.3 and 96.5 versus 97.7—while the 2-bit version drops to 52.4 and 86.0. NariQ reports decode speed comparable to other quants on an RTX PRO 6000.

hackernews · toebee · Nov 23, 13:42 · [Discussion](https://news.ycombinator.com/item?id=50611402)

**「Background」** GGUF is the model file format used by llama.cpp for local inference, and quantization lowers weight precision so a large model can fit into much less memory. Lower-bit quantizations normally degrade reasoning, math, multilingual, and agentic performance, so they are evaluated against BF16. NariQ&\#x27;s files currently require the project&\#x27;s own llama.cpp fork.

**「Compatibility caveat」** The quantized files cannot be loaded by upstream llama.cpp as-is; the authors state that running them currently requires their own nari-llama.cpp fork, and Metal users on Apple silicon must build that fork from source. One commenter reports about 3.8 tok/s decode on an 18 GB M3 Pro with the 3.0-bit file \(4.9 tok/s at 2.0-bit\), far below the CUDA figures the release reports, so Mac users should test speed on their own hardware before adopting these weights.

**「Community discussion」** Commenters praised the use of multiple held-out long-horizon tasks but remained skeptical of benchmark validity: one said high-compute quantization tends to over-optimize benchmark-like data, and another argued the plots suggest most gains come from harness differences rather than the model. A Mac user reported roughly 3.8 tok/s on an M3 Pro \(18 GB\) with the 3.0-bpw file and 4.9 tok/s with 2.0-bpw, far slower than CUDA.

**Tags**: `#quantization`, `#local LLM inference`, `#GGUF`, `#model compression`, `#benchmark evaluation`

---

<a id="item-tech-news-6"></a>
### [AI-assisted Lean Riemann Hypothesis proof alleged vacuous](https://x.com/i/web/status/2124987173439209561) ⭐️ 7.0/10

A social-media report alleges that a claimed AI-assisted Lean formalization of the Riemann Hypothesis and a generalized version was vacuous: key definitions were written as tautologies and geometric conditions were effectively empty. The report says Alpöge and Claude released only 17 million lines of Lean across 175,000 files, with no human-readable proof, and that Lean and Mathlib community members said the next day they had &quot;sufficient confidence&quot; the code proved the proposition. It further says Alpöge later conceded that &quot;250,000 pages is a joke&quot; and that the code was &quot;full of garbage but compiles,&quot; calling the criticism entirely reasonable. These claims are unverified and no technical artifacts were supplied, so the status of any proof remains unresolved.

telegram · zaihuapd · Nov 24, 01:29

**「Background」** Alpöge announced on 20 November 2026 that he and Anthropic&\#x27;s Claude had produced a Lean proof of the Riemann Hypothesis and the Generalized Riemann Hypothesis for Dirichlet L-functions. Contemporaneous coverage described 17 million lines of Lean assembled in about six weeks and said dozens of people had compiled and checked it; the later dispute turned on whether the formal definitions encoded the intended theorem rather than a vacuous stand-in.

**「Impact」** For researchers assessing AI-generated formal proofs, the case shows that a successful Lean build is not sufficient evidence: reviewers need to inspect the theorem statement, definitions, and axioms for vacuity before treating a formalization as a proof of the intended claim.

<details><summary>References</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=-Tzliv3mzds">AI Helped Prove the Riemann Hypothesis . Nobody Can... - YouTube</a></li>
<li><a href="https://math.uwaterloo.ca/~mrubinst/alpoge_claude_grh/">Alpöge / Claude proof of the Generalized Riemann Hypothesis</a></li>

</ul>
</details>

**Tags**: `#AI proof`, `#Lean`, `#formal verification`, `#Riemann Hypothesis`, `#AI research controversy`

---

<a id="item-tech-news-7"></a>
### [Singapore PM says no chip-control evasion route amid Megaspeed probe](https://www.bloomberg.com/news/articles/2026-11-24/singapore-won-t-be-conduit-to-skirt-us-chip-curbs-wong-says) ⭐️ 7.0/10

Singapore Prime Minister Lawrence Wong said Singapore will not be used as a conduit for companies to evade U.S. chip export controls, as authorities investigate Megaspeed&\#x27;s purchases of Nvidia chips. The statement followed the U.S. Commerce Department&\#x27;s addition of Megaspeed and six other Southeast Asian companies to a trade blacklist; the Federal Register cited a “significant risk” that they would divert advanced computing products to unauthorized users and said the designations include related entities in Malaysia and Thailand. Reuters reported that Alibaba&\#x27;s Singapore subsidiary Apex Enterprise Solutions was also listed, and Alibaba said it had never transferred controlled advanced computing chips.

telegram · zaihuapd · Nov 24, 05:03

**「Background」** US export controls restrict transfers of advanced computing products, including Nvidia chips, to unauthorized users. The Commerce Department&\#x27;s trade blacklist is an enforcement mechanism aimed at firms assessed as posing a diversion risk.

**「Impact」** AI-hardware buyers and logistics providers routing Nvidia products through Singapore or the named Southeast Asian entities face a clearer compliance risk: Singapore&\#x27;s government says it will not serve as a bypass route, and U.S. authorities have flagged the listed firms over possible diversion to unauthorized users.

**Tags**: `#chip export controls`, `#AI hardware`, `#Singapore`, `#Nvidia`, `#trade policy`

---

<a id="item-tech-news-8"></a>
### [Anthropic says internal Claude model found VP≠VNP, publishes Lean 4 proof](https://github.com/anthropics/formal-math/blob/main/vp-vnp/README.md) ⭐️ 7.0/10

Anthropic published a paper titled &quot;VP ≠ VNP over every field&quot; together with a Lean 4 formalization on November 24; the repository states the result was discovered by an internal research Claude model and that both the paper and code were written by AI. The paper claims a superpolynomial arithmetic-circuit lower bound for the Hamiltonian cycle polynomial, from which it derives that VP is a proper subclass of VNP — a result that, if correct, would resolve Valiant&\#x27;s 1979 algebraic complexity conjecture, though it addresses arithmetic circuits only and says nothing about P versus NP. The proof passed an audit against three standard axioms and an independent check by the nanoda kernel, with no \`sorry\` outside reserved files. No human mathematician has yet read it through, Lean cannot confirm that the formal statement matches the claimed theorem, and Appendix Q lists discrepancies; independent review is pending.

telegram · zaihuapd · Nov 24, 06:02

**「Background」** VP and VNP are Valiant&\#x27;s arithmetic-circuit complexity classes: arithmetic circuits use addition, subtraction, and multiplication gates over a field, and Valiant&\#x27;s hypothesis states that VNP is not contained in VP. The claimed lower bound concerns the Hamiltonian-cycle polynomial, a VNP-family polynomial, and would establish that VP is a proper subclass of VNP; the source stresses that this does not settle P versus NP.

**「Verification limits」** Because Lean checks the proof against the encoded statement but does not establish that the statement matches the claimed VP≠VNP theorem, researchers should treat the result as pending human review of Appendix Q’s noted discrepancies before citing it as a resolved conjecture.

<details><summary>References</summary>
<ul>
<li>[PDF] INTERPOLATION IN VALIANT&#x27;S THEORY</li>
<li>[PDF] On the Structure of Valiant&#x27;s Complexity Classes - CiteSeerX</li>
<li>Lies, Damned Lies and Proofs: Formal Methods Are Not Slopless</li>

</ul>
</details>

**Tags**: `#complexity theory`, `#Lean 4`, `#formal verification`, `#AI for mathematics`, `#Anthropic`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [vLLM Day-0 Support for ERNIE 5.5 Flash via a Plugin](https://vllm.ai/blog/2026-11-24-ernie-5-5-flash-preview) ⭐️ 7.0/10

rss · vLLM Blog · Nov 24, 00:00

**「Background」** Baidu&\#x27;s ERNIE team and the vLLM team shipped day-0 support for ERNIE 5.5 Flash Preview, a sparse MoE with 280B total and 14B active parameters, a 1M-token context, and a design explicitly optimized for inference cost. That goal produced unfamiliar attention and MoE structures — low-rank VHA cross-head post-mixing, Multi-Router Latent MoE, a MultiMax output head — that are expensive when implemented op by op, with many intermediate tensors paying for memory traffic and kernel launches.

**「Solution」** The teams wrote a dedicated fused kernel for each structure and folded everything precomputable into the weights at load time: the VHA mixing parameters collapse into a single matrix with the downstream FP8 quantization done in registers, the router weights are concatenated so one GEMM yields all logits, MultiMax becomes a single-pass piecewise transform that is bitwise identical to the term-by-term version, and the gate projection shares one GEMM with query up-projection. The authors report per-kernel gains of 1.55×–6.53×, and note these are team-reported figures without described hardware or baselines. The bundled FlashIndexer adds a lightweight head router that picks a few sparse indexer heads per token from its hidden state alone, so routing cost does not grow with context; it needs a roughly 1B-token fine-tune in which the frozen full indexer acts as teacher, and yields a 40% \(1.4×\) indexing speedup at 1M context. Quantization is MXFP4 routed experts \(W4A8, quantized-aware training matched to inference numerics\), FP8 elsewhere, FP8 KV cache, plus a 3-layer DSpark draft model with mean acceptance above 4.0. Delivery uses a standalone plugin loaded through vllm.general\_plugins, registering architectures as module paths so other models pay no import cost and hooks fire only for ERNIE; the tradeoff is that plugin fixes ship on the model&\#x27;s schedule rather than vLLM&\#x27;s.

**「Takeaway」** The authors argue that a new model can reach a stock vLLM release on day zero without a fork, by pairing load-time weight folding and fused kernels with a plugin that keeps model-specific code and hooks out of vLLM core — provided the model team owns that plugin&\#x27;s release cadence.

**Tags**: `#vLLM`, `#MoE inference`, `#kernel fusion`, `#speculative decoding`, `#quantization`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Fed&\#x27;s Williams Says More Work Needed on Inflation](https://www.cnbc.com/2026/11/23/john-williams-fed-inflation-rate-hikes.html) ⭐️ 8.0/10

New York Fed President John Williams said Monday that the Federal Reserve still has “work to do” to bring inflation back to 2% and that further rate increases may come “over time,” ahead of a Dec. 8-9 meeting where markets fully price a quarter-point rise from the current 3.75%-4% target range.

rss · CNBC Finance · Nov 23, 21:02

**「Background」** The comments come as inflation remains above the Fed’s 2% goal even with continued economic growth, and as officials differ over how quickly to raise rates; Williams has favored a measured approach.

**Tags**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#inflation`, `#John Williams`

---

<a id="item-finance-news-2"></a>
### [AI selloff casts shadow over DeepSeek and Moonshot listing plans](https://www.bloomberg.com/news/articles/2026-11-23/china-s-next-ai-deals-clouded-by-selloff-after-anthropic-ipo) ⭐️ 8.0/10

A global AI stock selloff that followed Anthropic&\#x27;s record $119.5 billion IPO is clouding planned or considered share sales by Chinese AI developers DeepSeek, Moonshot and StepFun, Bloomberg reported. Chinese tech stocks have lost a combined $1.7 trillion in market value since late June, while Zhipu has fallen more than 85% from its June peak and MiniMax dropped below its issue price this month, according to the report.

telegram · zaihuapd · Nov 23, 09:31

**「Background」** The report traces the chill to Anthropic’s record IPO, which it says triggered a global AI-stock selloff; Chinese tech stocks have shed $1.7 trillion in market value since late June. DeepSeek, Moonshot AI and StepFun are among Anthropic’s direct competitors weighing or preparing share sales, and Bloomberg says the weaker AI trade adds complexity even though their plans do not depend entirely on Anthropic’s shares.

**「Who is affected」** Investors who bought recent Chinese AI listings are already underwater — MiniMax fell below its issue price this month and Zhipu is down more than 85% from its June peak — a backdrop that weighs on demand for the next wave of AI share sales from DeepSeek, Moonshot and StepFun.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-23/china-s-next-ai-deals-clouded-by-selloff-after-anthropic-ipo">China’s Next AI Deals Clouded by Selloff After Anthropic IPO</a></li>
<li><a href="https://www.theedgesingapore.com/news/tech/chinas-next-ai-deals-clouded-selloff-after-anthropic-ipo">China’s next AI deals clouded by selloff after Anthropic IPO</a></li>

</ul>
</details>

**Tags**: `#AI selloff`, `#China tech stocks`, `#AI IPOs`, `#Anthropic IPO`, `#market volatility`

---

<a id="item-finance-news-3"></a>
### [Shanghai Metro to Adjust Fares for First Time in 21 Years](https://weibo.com/1699432410/5368461393397183) ⭐️ 7.0/10

Shanghai&\#x27;s rail transit system will adjust fares for the first time in 21 years, setting a 3-yuan base fare for journeys of 0–4 km, with the new fares taking effect on Dec. 1. Passengers using the same payment channel will receive a 10% discount after spending 90 yuan in a month.

telegram · zaihuapd · Nov 23, 10:45

**「Background」** Shanghai’s metro fare had gone 21 years without adjustment, and local reports in September 2026 said the city was set to change its fare mechanism for the first time in that period.

**「Impact」** Shanghai commuters will pay on average about 1 yuan more per trip under the plan, with the new count tickets and 10% monthly discount intended to reduce the effect on frequent riders.

<details><summary>References</summary>
<ul>
<li><a href="https://news.qq.com/rain/a/20260908A05NH700">news.qq.com/rain/a/20260908A05NH700</a></li>
<li><a href="https://news.qq.com/rain/a/20260819A0ARAE00">时隔21...</a></li>

</ul>
</details>

**Tags**: `#上海地铁`, `#公共交通票价`, `#票价调整`, `#通勤成本`, `#优惠政策`

---

<a id="item-finance-news-4"></a>
### [Report: SpaceX Rents AI Computing Power to Anthropic and Google](https://www.nytimes.com/2026/11/23/business/elon-musk-ai-anthropic-google.html) ⭐️ 7.0/10

The New York Times reported on Nov. 23 that SpaceX has since May been renting large-scale computing power from its data centers to Anthropic, Google and others for billions of dollars a month, citing three unnamed sources; Musk reportedly told employees SpaceX lags in AI and that selling compute is more profitable than using it internally.

telegram · zaihuapd · Nov 24, 02:06

**「Background」** SpaceX operates data centers with GPUs that can either support its own AI work or be leased to outside AI developers, and the report says Musk concluded that renting the capacity was more profitable than using it internally.

**「Impact」** Anthropic and Google gain dedicated GPU capacity — Anthropic roughly 325,000 Nvidia chips for $1.25 billion a month — while SpaceX turns its data centers into recurring revenue ahead of a planned IPO.

<details><summary>References</summary>
<ul>
<li><a href="https://www.nytimes.com/2026/11/23/business/elon-musk-ai-anthropic-google.html">Elon Musk Faces an A.I. Dilemma at SpaceX - The New York Times</a></li>
<li><a href="https://fortune.com/2026/07/19/spacex-ai-compute-renting-business-google-anthropic-pentagon-deals-revenue-valuation-elon-musk-colossus-data-centers/">SpaceX is quietly building an AI compute business that may ...</a></li>
<li><a href="https://www.cnbc.com/2026/06/05/google-to-pay-spacex-920-million-a-month-for-xai-compute-capacity.html">Google to pay SpaceX $920 million a month for compute ...</a></li>

</ul>
</details>

**Tags**: `#SpaceX`, `#AI compute`, `#data centers`, `#Anthropic`, `#Google`

---