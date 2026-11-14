---
layout: default
title: "Horizon Summary: 2026-11-14 (EN)"
date: 2026-11-14
lang: en
---

> From 41 items, 8 important content pieces were selected

---

**Technology News**
1. [TorchTitan trains 1T-parameter MoE at 1,300 tokens/s per GPU on 384 GH200s](#item-tech-news-1) ⭐️ 8.0/10
2. [FAA orders nationwide ground stop of departing flights](#item-tech-news-2) ⭐️ 7.0/10
3. [Python early contributor Tim Peters dies at 74](#item-tech-news-3) ⭐️ 7.0/10
4. [Microsoft Outlook, Teams global outage exceeds 12 hours](#item-tech-news-4) ⭐️ 7.0/10
5. [DeepSeek opens app-level API with tool orchestration and multimodal endpoints](#item-tech-news-5) ⭐️ 7.0/10
6. [OpenAI launches ChatGPT Wallet for US agent payments](#item-tech-news-6) ⭐️ 7.0/10

**Financial News**
1. [Cantor Fitzgerald&\#x27;s Nvidia stake cut draws scrutiny amid Lutnick spy-case questions](#item-finance-news-1) ⭐️ 8.0/10
2. [Chicago Fed&\#x27;s Goolsbee Says Fed Has &\#x27;Work to Do&\#x27; on Inflation](#item-finance-news-2) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [TorchTitan trains 1T-parameter MoE at 1,300 tokens/s per GPU on 384 GH200s](https://www.reddit.com/r/MachineLearning/comments/1xvce5h/scaling_to_1t_moe_on_torchtitan_p/) ⭐️ 8.0/10

A practitioner report from a team working with TorchTitan and PyTorch maintainers describes training a roughly 1-trillion-parameter mixture-of-experts model at about 1,300 tokens/s per GPU on 384 GH200 GPUs, a 14x improvement over its starting point. The setup uses 384-way FSDP plus 4-way expert parallelism kept inside each node and deliberately skips pipeline parallelism to avoid long steps. Reported gains come from full activation checkpointing, offloading checkpoint activations to Grace, the Muon optimizer, FlexShard expert sharding, running Newton-Schulz on GPU, attention-cost load balancing, bf16 expert-gradient all-to-all with local fp32 accumulation, FP8 expert all-gathers, and fixing stream-pool allocator fragmentation. The post is practitioner documentation rather than an independently verified benchmark, and some techniques, such as group-limited routing, which added 7% throughput but may affect training, remain under evaluation.

reddit · r/MachineLearning · /u/f14-bertolotti · Nov 13, 16:28

**「Context: TorchTitan and MoE sharding」** TorchTitan is the PyTorch project’s large-model training stack, and mixture-of-experts \(MoE\) models route each token to a subset of expert subnetworks rather than activating every parameter. The reported run used the GH200 GPUs inside the JUPITER supercomputer and combined fully sharded data parallelism \(FSDP\) with expert parallelism \(EP\), splitting weights and experts across ranks while token all-to-all traffic moves between them.

**「Impact」** For distributed-training teams, the report suggests that on GH200 clusters with slower InfiniBand, keeping expert parallelism node-local and replacing fp32 gradient reduce-scatter with bf16 all-to-all plus local fp32 summation can preserve precision while halving bytes on the wire. It also documents an allocator pitfall in which per-stream pools strand memory and produce misleading OOM retries; reproducing the work would require TorchTitan&\#x27;s FlexShard and FSDP2&\#x27;s private unshard\_async\_op flag, which the report says is becoming a public API.

**Tags**: `#mixture-of-experts`, `#TorchTitan`, `#distributed training`, `#GH200`, `#FSDP`

---

<a id="item-tech-news-2"></a>
### [FAA orders nationwide ground stop of departing flights](https://www.nbcnews.com/news/us-news/faa-orders-nationwide-ground-stop-departing-flights-reasons-safety-rcna609247) ⭐️ 7.0/10

The FAA issued a nationwide ground stop on Nov. 13, 2026, halting departing flights, according to the FAA advisory and NYT live-coverage links that constitute the item. The supplied source gives no official cause, scope, or duration; cause details appear only in reader comments citing outside reporting.

hackernews · zulln · Nov 13, 21:05 · [Discussion](https://news.ycombinator.com/item?id=50489641)

**「Background」** Three days before the ground stop, on November 10, 2026, the FAA expanded its AI-assisted air traffic management system, SMART \(Strategic Management of Airspace, Routes and Trajectories\), to the airspace of all 22 centers nationwide following a Washington, D.C. test. The proximity drew scrutiny after the November 13 outage, but the FAA has denied that SMART caused the ground stop, and aviation experts cited in contemporaneous reporting likewise considered it an unlikely factor.

**「Impact」** The ground stop disrupted more than 11,000 U.S. flights before it was lifted after about four hours, leaving airlines and travelers to absorb cascading delays and cancellations even after departures resumed. Operators should expect residual schedule recovery rather than an immediate return to normal service.

**「Community discussion」** Commenters citing a WSJ report said the outage appeared to affect an L3Harris Technologies telecommunications network that carries radio frequencies controllers use to communicate with pilots, and one commenter speculated it followed the FAA&\#x27;s Nov. 10 announcement that it would extend its SMART AI tool to all 22 air route traffic control centers—an asserted link, not a confirmed cause. Others noted how little official information was available; one commenter said NYT later reported the stop had been lifted, while another quoted DHS Secretary Mullin warning the outage would likely be extended.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/2026_FAA_communication_outage">2026 FAA communication outage - Wikipedia</a></li>
<li><a href="https://explainx.ai/blog/faa-smart-ai-nationwide-rollout-november-2026-ground-stop">FAA SMART AI Nationwide: $875M Tool, Ground Stop Denial ...</a></li>
<li><a href="https://airguide.info/faa-smart-ai-system-faces-questions-after-nationwide-ground-stop/">FAA SMART AI System Faces Questions After Nationwide Ground Stop</a></li>
<li><a href="https://www.cnbc.com/2026/11/13/faa-ground-stop.html">FAA lifts ground stop after four hours, but flight ... - CNBC</a></li>
<li><a href="https://www.theguardian.com/world/2026/nov/13/faa-nationwide-ground-stop-flights">Nationwide FAA ground stop: nearly 11,000 flights delayed or ...</a></li>

</ul>
</details>

**Tags**: `#FAA`, `#air traffic control`, `#critical infrastructure`, `#network outage`, `#AI deployment`

---

<a id="item-tech-news-3"></a>
### [Python early contributor Tim Peters dies at 74](https://x.com/Itsfoss/status/2120957452937998716) ⭐️ 7.0/10

Guido van Rossum announced that Tim Peters, an early Python contributor, has died at 74. Peters wrote Timsort, the sorting algorithm that carries his name, and PEP 20, &quot;The Zen of Python,&quot; and he served on the Python Software Foundation board for 13 years. The source describes him as Python&\#x27;s second real user; no cause of death was given.

telegram · zaihuapd · Nov 13, 09:55

**「Background」** PEP 20, known as &quot;The Zen of Python,&quot; is a Python Enhancement Proposal consisting of short aphorisms about the language&\#x27;s design philosophy. Timsort is the sorting algorithm Peters authored and after which it is named.

**Tags**: `#Python`, `#open source`, `#community`, `#Tim Peters`, `#Timsort`

---

<a id="item-tech-news-4"></a>
### [Microsoft Outlook, Teams global outage exceeds 12 hours](https://www.reuters.com/technology/microsoft-365-outlook-down-thousands-us-users-downdetector-shows-2026-11-12/) ⭐️ 7.0/10

Microsoft Outlook, Teams, and Copilot remained disrupted on November 13 for more than 12 hours, affecting enterprises and government agencies worldwide. Microsoft attributed the outage to a server issue, said it found no evidence of malicious activity, and reported expanding remediation with signs of stabilization. Australia, Japan, and U.S. government agencies were affected, Euronext email was disrupted, and a Taiwanese financial institution switched to fax for transaction confirmations; the report says this is Microsoft 365&\#x27;s second outage this year.

telegram · zaihuapd · Nov 13, 12:21

**「Background」** Outlook, Teams and Copilot are all delivered as Microsoft 365 cloud services, and the item reports that a server problem affected all three at the same time. The item also notes that this was the second Microsoft 365 outage this year, without detailing the earlier incident.

**「Operational impact」** Organizations that rely on Outlook and Teams for time-sensitive work had to fall back to manual channels: a Taiwan financial institution used fax to confirm trades, and Euronext&\#x27;s email was disrupted. That makes tested out-of-band communication and manual approval paths a practical continuity requirement during Microsoft 365 incidents.

**Tags**: `#microsoft-365`, `#cloud-outage`, `#service-reliability`, `#enterprise-software`, `#incident-response`

---

<a id="item-tech-news-5"></a>
### [DeepSeek opens app-level API with tool orchestration and multimodal endpoints](https://mp.weixin.qq.com/s/78KBHc4-4N5b2vfL9SkutQ) ⭐️ 7.0/10

DeepSeek announced an expansion of its API that exposes app-level conversational capabilities: developers enable the corresponding parameters in the existing API to get deep-thinking search, file input, link reading and voice, with tool invocation and context assembly handled server-side. The company said the V4.1-Flash model is supported across three interfaces, and that Search, Fetch, OCR, ASR and TTS can also be called individually. It also open-sourced a frontend chat demo \(deepseek-ai/chat-demo, with a hosted instance at deepseek-ai.github.io/chat-demo\) that can import existing conversation history, so developers can run a DeepSeek web-style client locally against the API. The post did not disclose pricing, rate limits, regional availability, or independent performance results.

telegram · zaihuapd · Nov 13, 14:27

**「Background」** DeepSeek&\#x27;s API documentation shows developers using an API key with OpenAI-format request scripts to call its models. This update adds server-side tool orchestration to existing API calls, while Search, Fetch, OCR, ASR, and TTS are also exposed as standalone APIs for custom workflows.

**「Impact for developers」** The practical change is granularity: one API surface now offers an orchestrated chat endpoint that runs tool calls server-side plus standalone Search, Fetch, OCR, ASR and TTS endpoints, so an application needing only one capability, such as OCR for document parsing, can skip the full agent loop, while chat clients can offload tool sequencing to DeepSeek. Teams planning adoption should verify pricing, rate limits and which parameters V4.1-Flash actually supports, since the announcement provided none of these details.

<details><summary>References</summary>
<ul>
<li><a href="https://api-docs.deepseek.com/">Your First API Call | DeepSeek API Docs</a></li>
<li><a href="https://extrapolator.ai/2026/11/13/deepseek-flash-api-adds-web-search-file-parsing-and-ocr-tools/">DeepSeek Flash API adds web search, file parsing, and OCR ...</a></li>

</ul>
</details>

**Tags**: `#DeepSeek`, `#API`, `#AI agents`, `#multimodal`, `#open source`

---

<a id="item-tech-news-6"></a>
### [OpenAI launches ChatGPT Wallet for US agent payments](https://openai.com/index/introducing-chatgpt-wallet/) ⭐️ 7.0/10

OpenAI announced ChatGPT Wallet, a payment wallet that lets AI agents make purchases without receiving the user&\#x27;s real card number, in partnership with American Express, Mastercard, and Visa. OpenAI says it is available starting today in the US through dots to ChatGPT Pro subscribers aged 18 and older who use a US-issued card. For each purchase, the user reviews the item and amount and confirms with Face ID or a fingerprint, while the card network issues a payment token that substitutes for the real card number. The announcement presents these capabilities as launching, but the item comes from a Telegram aggregator and provides no independent verification or details on availability outside the US.

telegram · zaihuapd · Nov 13, 15:43

**「Context」** ChatGPT Wallet builds on two existing pieces: OpenAI&\#x27;s &quot;dots&quot; agents, which act on a user&\#x27;s behalf, and card-network tokenization, in which the network issues a substitute payment token so the underlying card number is not exposed. The feature lets those agents complete purchases using users&\#x27; existing payment cards.

**「Effect on eligible users」** For eligible US ChatGPT Pro subscribers, agent-initiated purchases cannot complete silently: each transaction requires the user to review the item and amount and confirm with Face ID or a fingerprint. The payment network issues a token in place of the real card number, so the agent does not receive the underlying card credential.

<details><summary>References</summary>
<ul>
<li><a href="https://tech.yahoo.com/ai/chatgpt/articles/openai-introduces-chatgpt-wallet-visa-162102250.html">OpenAI Introduces ChatGPT Wallet With Visa, Mastercard, Amex ...</a></li>

</ul>
</details>

**Tags**: `#OpenAI`, `#AI agents`, `#digital payments`, `#tokenization`, `#product launch`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Cantor Fitzgerald&\#x27;s Nvidia stake cut draws scrutiny amid Lutnick spy-case questions](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 8.0/10

Cantor Fitzgerald reported a nearly 50% decline in the number of Nvidia shares it held between September 2025 and March 2026 — from 3.5 million shares worth $652 million to 1.78 million worth $310 million, per CNBC&\#x27;s analysis of securities filings — as the firm, formerly run by Commerce Secretary Howard Lutnick and now led by his sons, faces questions over Lutnick&\#x27;s handling of suspected Nvidia chip smuggling to China. Cantor said its Nvidia positions were &quot;immaterial&quot; and tied to client swap transactions, and CNBC reported there is no evidence the holdings changes were linked to intelligence warnings or that Lutnick shared nonpublic information.

rss · CNBC Finance · Nov 13, 23:42

**「Background」** The scrutiny follows Nvidia CEO Jensen Huang&\#x27;s resignation on Thursday, after Axios reported that Commerce Secretary Howard Lutnick had received a classified intelligence warning about Huang&\#x27;s ties to a suspected Chinese spy and resisted a crackdown on Megaspeed, a Singapore-based company suspected of funneling Nvidia AI chips to China.

**「Who is affected」** The decision sits with Commerce: companies placed on its Entity List cannot receive advanced U.S. technology without a special export license that is almost never granted, so if Megaspeed were added, the Singapore-based firm&\#x27;s access to Nvidia&\#x27;s advanced AI chips would be cut off.

<details><summary>References</summary>
<ul>
<li><a href="https://www.nytimes.com/interactive/2026/11/13/technology/nvidia-jensen-huang.html">The Fall of Jensen Huang : How the Nvidia Scandal Unfolded</a></li>
<li><a href="https://www.theguardian.com/technology/2026/nov/12/jensen-huang-affair-timeline">A timeline of the affair scandal that sank Nvidia ’s Jensen Huang</a></li>
<li><a href="https://www.nytimes.com/2026/11/12/us/politics/lutnick-nvidia-commerce-china-chips.html">Howard Lutnick Took Softer Line on Nvidia as Calls for Tougher...</a></li>
<li><a href="https://www.thestreet.com/technology/scott-bessent-and-lutnick-clash-over-nvidia-chips-and-china">Scott Bessent and Lutnick clash over Nvidia chips and... - TheStreet</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#U.S. export controls`, `#Howard Lutnick`, `#Cantor Fitzgerald`, `#corporate governance`

---

<a id="item-finance-news-2"></a>
### [Chicago Fed&\#x27;s Goolsbee Says Fed Has &\#x27;Work to Do&\#x27; on Inflation](https://www.cnbc.com/2026/11/13/chicago-feds-goolsbee-says-central-bank-has-definitely-got-work-to-do-on-inflation.html) ⭐️ 8.0/10

Chicago Fed President Austan Goolsbee said the Federal Reserve &quot;has definitely got work to do&quot; to restore credibility on inflation, after the producer price index rose 6.5% over the year to October, its highest annual gain since November 2022. Markets were fully pricing a quarter-point rate increase at the Fed&\#x27;s Dec. 8-9 meeting, according to CME Group&\#x27;s FedWatch.

rss · CNBC Finance · Nov 13, 14:22

**「Background」** The Fed aims for 2% annual inflation over the longer run, measured by the PCE price index, and its benchmark federal funds target range was 3.75%–4.00% after a September 2026 increase.

**「Impact」** If the Fed raises its benchmark rate in December as markets expect, households with variable-rate debt and businesses seeking new loans would face higher borrowing costs.

<details><summary>References</summary>
<ul>
<li><a href="https://www.federalreserve.gov/economy-at-a-glance-inflation-pce.htm">The Fed - Inflation (PCE) - Federal Reserve Board</a></li>
<li><a href="https://wealthvieu.com/banking/interest-rates/federal-funds-rate/">Current Federal Funds Rate 2026 — Fed Rate History, FOMC ...</a></li>

</ul>
</details>

**Tags**: `#Federal Reserve`, `#inflation`, `#monetary policy`, `#PPI`, `#interest rates`

---