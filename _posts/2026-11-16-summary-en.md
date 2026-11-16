---
layout: default
title: "Horizon Summary: 2026-11-16 (EN)"
date: 2026-11-16
lang: en
---

> From 36 items, 9 important content pieces were selected

---

**Technology News**
1. [Meta FAIR/NYU: 200+ MLLMs show encoder pretraining optional, vision-only parameters required](#item-tech-news-1) ⭐️ 8.0/10
2. [Meituan open-sources LongCat-2.5, a 1.6T-parameter agent model trained on Huawei Ascend](#item-tech-news-2) ⭐️ 8.0/10
3. [Protomaps makes self-hosted map tiles cheap and easy, blog argues](#item-tech-news-3) ⭐️ 7.0/10
4. [Positional embeddings explainer prompts group-theory framing on Hacker News](#item-tech-news-4) ⭐️ 7.0/10
5. [Tool claims 5x faster pageable cudaMemcpy on NVIDIA B300](#item-tech-news-5) ⭐️ 7.0/10
6. [Huawei Cloud launches openPangu-2.1-Pro on MaaS with token pricing](#item-tech-news-6) ⭐️ 7.0/10

**Financial News**
1. [China Says US, Chinese and Russian Leaders to Hold First Trilateral Meeting at APEC](#item-finance-news-1) ⭐️ 8.0/10
2. [Lutnick Faces Questions Over Cantor Fitzgerald&\#x27;s Nvidia Holdings](#item-finance-news-2) ⭐️ 7.0/10
3. [U.S. judge denies Micron, Samsung and SK Hynix bid to dismiss DRAM price-fixing lawsuit](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Meta FAIR/NYU: 200+ MLLMs show encoder pretraining optional, vision-only parameters required](https://www.reddit.com/r/MachineLearning/comments/1xx1k2o/meta_fair_nyu_unbundling_multimodal_vision/) ⭐️ 8.0/10

An author-posted preprint from Meta FAIR and NYU reports that training 200+ multimodal LLMs from scratch on identical data shows separate vision-encoder pretraining is optional, vision-only parameters are not, and placement of the encoder before the LLM is optional. Encoder pretraining was counted against the same lifetime compute budget; main comparisons used Qwen3-1.7B and 4B backbones with 0.4B parameters of vision capacity, plus a scaling ladder from 0.6B to 6.4B, evaluated on 16 Cambrian VQA benchmarks at 448 px and 12 language benchmarks. Pretrained encoders built with contrastive, self-supervised, and two captioning objectives at best tied a from-scratch encoder at matched compute, and pretraining MetaCLIP 6.5x longer raised ImageNet linear-probe accuracy from 80.4% to 84.4% without improving VQA; encoder-free models trailed at every size and needed about 3x the compute to catch up. The authors&\#x27; &quot;in-fusion&quot; variant adds zero-initialized vision-only attention projections and FFNs to the LLM&\#x27;s first eight layers, matching an encoder from 1.7B to 6.4B with about 13% lower time to first token \(45.0 vs 44.4 VQA at 1.7B\), though these remain preprint claims that have not been peer-reviewed.

reddit · r/MachineLearning · /u/trungh98 · Nov 15, 17:38

**「Background」** Most multimodal LLMs pair a language model with a vision encoder that is pretrained separately, then feed visual tokens into the LLM before or within its layers. Published systems also differ in training data and compute, so comparing them directly cannot isolate whether encoder pretraining, vision-only parameters, or encoder placement drives VQA performance.

**「What changes for multimodal architects」** For teams choosing a vision stack, the study&\#x27;s breakdown implies the encoder itself can be dropped or folded into the LLM&\#x27;s early layers without a VQA penalty at 1.7B–6.4B scale, and the in-fusion variant reported about 13% lower time to first token — so long as vision-only parameters are kept, since removing them cost roughly 3x compute to recover. That distinction matters against shipping encoder-free designs like Gemma 4 12B, which projects raw image patches and audio directly into the LLM embedding space through lightweight linear layers; the findings are from a preprint covering backbones up to 6.4B and have not been shown to hold at larger scales.

<details><summary>References</summary>
<ul>
<li><a href="https://huggingface.co/google/gemma-4-12B">google/ gemma - 4 - 12 B · Hugging Face</a></li>
<li><a href="https://developers.googleblog.com/gemma-4-12b-the-developer-guide/">Gemma 4 12 B : The Developer Guide - Google Developers Blog</a></li>

</ul>
</details>

**Tags**: `#multimodal learning`, `#vision encoders`, `#MLLM training`, `#model architecture`, `#research preprint`

---

<a id="item-tech-news-2"></a>
### [Meituan open-sources LongCat-2.5, a 1.6T-parameter agent model trained on Huawei Ascend](https://the-decoder.com/meituan-releases-a-1-6-trillion-parameter-agent-model-that-never-touched-an-nvidia-gpu/) ⭐️ 8.0/10

Meituan&\#x27;s LongCat team published the weights for LongCat-2.5 about a week after unveiling the model, releasing them under the MIT license, which permits commercial use. The mixture-of-experts model totals roughly 1.6 trillion parameters with about 48 billion active per token, and accepts text, image, and video input; it is positioned for agents that carry out long, multi-step tasks, especially coding. Meituan says training used only Chinese silicon — Huawei Ascend accelerator cards — with no Nvidia GPUs, and reports a Terminal Bench v2.1 score of 88.4, just below the 89.1 it attributes to Claude Opus 5. The account comes from a Telegram aggregator citing The Decoder, and the training-hardware and benchmark claims have not been independently verified.

telegram · zaihuapd · Nov 15, 11:08

**「Background」** LongCat-2.5 is the successor to LongCat-2.0, which Meituan&\#x27;s LongCat team released on June 30 with the same 1.6-trillion-parameter scale, a one-million-token context window, and an MIT license, describing it as trained and served end-to-end on roughly 50,000 domestic Chinese chips, including Huawei Ascend via its HCCL library, with no Nvidia hardware in the stack. Within hours of that release, Huawei Ascend, MetaX, and Muxi had announced inference compatibility with the weights.

**「What it means for adopters」** Because the MIT license allows commercial use, teams can download and self-host the weights rather than going through an API, but a 1.6T-parameter model implies substantial serving infrastructure even with only ~48B parameters active per token. Organizations evaluating it as an Nvidia-independent stack should treat the Ascend-only training claim and the Terminal Bench v2.1 result as vendor statements until third-party reproductions appear.

<details><summary>References</summary>
<ul>
<li><a href="https://temperaturezero.com/2026/07/05/meituan-trained-frontier-model-without-nvidia/">Meituan Trained a Frontier Model Without Nvidia – TemperatureZero</a></li>
<li><a href="https://aicodingweekly.datadriftpress.com/p/61-longcat-edges-out-gpt-5-5">#61 - LongCat edges out GPT-5.5 | AI Coding Weekly</a></li>
<li><a href="https://www.ainchina.com/blog/meituan-longcat-2-trillion-domestic-chips-china-ai-independence-2026/">How Meituan Built a Trillion - Parameter AI Model on 50,000 Domestic...</a></li>

</ul>
</details>

**Tags**: `#open-source AI`, `#large language models`, `#Huawei Ascend`, `#AI agents`, `#model benchmarks`

---

<a id="item-tech-news-3"></a>
### [Protomaps makes self-hosted map tiles cheap and easy, blog argues](https://bruceroettgers.eu/blog/protomaps/) ⭐️ 7.0/10

A blog post argues that self-hosting map tiles with Protomaps has become cheap and easy enough for cost-conscious software projects. It is an explanatory write-up rather than a product release, and the supplied material contains no version, price, or benchmark figures.

hackernews · bcye · Nov 15, 19:26 · [Discussion](https://news.ycombinator.com/item?id=50509837)

**「What Protomaps provides」** Protomaps is an open-source map of the world packaged as a single static file that can be deployed on cloud storage rather than requiring a dedicated tile server. Clients can load map tiles directly from object storage such as Supabase Storage, which is the model behind the cheap self-hosting described in the post.

**「Impact」** Developers who need control over map access can keep PMTiles in object storage such as Cloudflare R2 and serve tiles themselves; one commenter reports doing this for privacy and access control while reducing load on public infrastructure.

**「Community discussion」** Commenters mostly shared alternatives and constraints rather than disputing the premise. OpenFreeMap was cited as a free public option, and one developer warned that high-resolution satellite imagery grows too large and expensive at higher zoom levels, forcing them to stop at z17; another said Protomaps made a live-rendered walking game affordable where Mapbox or Google Maps would not have been.

<details><summary>References</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=l7QBpiLRwJc">Self - host Maps with Protomaps and Supabase Storage - YouTube</a></li>
<li><a href="https://supabase.com/blog/self-host-maps-storage-protomaps.md">supabase.com/blog/ self - host - maps -storage- protomaps .md</a></li>
<li><a href="https://protomaps.com/">Protomaps - The open source map in a file</a></li>

</ul>
</details>

**Tags**: `#protomaps`, `#map-tiles`, `#self-hosting`, `#open-source`, `#pmtiles`

---

<a id="item-tech-news-4"></a>
### [Positional embeddings explainer prompts group-theory framing on Hacker News](https://magazine.sebastianraschka.com/p/understanding-positional-embeddings) ⭐️ 7.0/10

A technical explainer titled &quot;Understanding Positional Embeddings in Modern LLMs&quot; describes how positional embeddings are implemented in current transformer-based language models. It is an educational deep-dive rather than a report of a new method, result, or release, and the supplied material contains only a summary with no article text, so its specific architectural claims and examples could not be checked. In the accompanying Hacker News thread, commenter programjames argued that implementation coverage alone is insufficient, framing positional embeddings as group representations and describing rotary positional embeddings as representations of the translation group, which the commenter notes is abelian in ℝⁿ.

hackernews · vismit2000 · Nov 15, 12:14 · [Discussion](https://news.ycombinator.com/item?id=50506376)

**「Background」** Transformer attention has no built-in notion of token order, so positional embeddings provide the ordering signal the model otherwise lacks. Rotary positional embeddings \(RoPE\), introduced by Su et al., encode position by rotating query and key vectors in a complex vector space; the article’s implementation walkthrough builds on that mechanism.

**「Community discussion」** The substantive contribution came from commenter programjames, who contended that the article explains only how positional embeddings are implemented and that a real understanding requires group theory: in this framing, positional embeddings are group representations, and rotary embeddings correspond to representations of the abelian translation group ℝⁿ, a route the commenter presents as a way to derive and parameterize learnable embeddings. This is one commenter&\#x27;s theoretical position, not a claim established by the article itself.

<details><summary>References</summary>
<ul>
<li><a href="https://micrologics.org/blog/beyond-standard-attention-demystifying-gqa-and-rope-in-modern-llm-architectures">Beyond Standard Attention: Demystifying GQA and RoPE in Modern ...</a></li>

</ul>
</details>

**Tags**: `#positional embeddings`, `#LLMs`, `#transformer architectures`, `#deep learning theory`

---

<a id="item-tech-news-5"></a>
### [Tool claims 5x faster pageable cudaMemcpy on NVIDIA B300](https://www.reddit.com/r/MachineLearning/comments/1xx2n25/making_cudamemcpy_5x_faster_on_a_b300_p/) ⭐️ 7.0/10

A Reddit author \(/u/makneeee\) released an open-source tuner, cudamemcpy-tuner, that claims to speed up pageable cudaMemcpy transfers on an NVIDIA B300. In the posted benchmark, copying a 1 GB uint8 tensor from CPU to GPU ran at 10.2 GB/s unmodified and 51.5 GB/s after wrapping the same script with \`cmt tune -- python bench.py\`. The claim covers only pageable CPU-to-GPU copies on a single GPU model, comes from the author&\#x27;s own unrun-by-others measurement, and the terse post defers technical detail to a linked blog and the GitHub repository; no independent verification is provided.

reddit · r/MachineLearning · /u/makneeee · Nov 15, 18:20

**「Why pageable copies are slow」** CUDA distinguishes pageable host memory, such as ordinary malloc allocations, from page-locked \(pinned\) memory. Because the GPU cannot directly access pageable memory, the driver first stages the data in an internal pinned buffer before transferring it, adding an extra copy; pinned allocations such as cudaMallocHost allow direct transfer and typically reach higher host-to-device bandwidth.

**「Scope of the gain」** The speedup applies to pageable host-to-device copies taken through the default path, such as \`x.to\(&quot;cuda&quot;\)\` on a non-pinned tensor, so pipelines that already stage data through pinned memory and asynchronous copies have less to gain. Even at the reported 51.5 GB/s, the transfer remains far below the B300&\#x27;s 8 TB/s of HBM3e memory bandwidth, so the tuner narrows a host-side bottleneck rather than removing it. Because the roughly 5x figure comes from a single benchmark on a single GPU model, users should re-run the author&\#x27;s \`cmt tune -- python bench.py\` harness on their own hardware before depending on it.

<details><summary>References</summary>
<ul>
<li><a href="https://developer.nvidia.com/blog/how-optimize-data-transfers-cuda-cc/">How to Optimize Data Transfers in CUDA C/C++ | NVIDIA ...</a></li>
<li><a href="https://cuda.live/tutorials/memory-model">CUDA Memory: Global, Shared, Constant &amp; Pinned Memory</a></li>
<li><a href="https://inferencex.semianalysis.com/chips/b300">NVIDIA B300 Specs: ~$2.26/hr, 268 GB HBM3e | InferenceX</a></li>

</ul>
</details>

**Tags**: `#cuda`, `#gpu-memory-transfer`, `#performance-optimization`, `#ml-systems`, `#open-source-tools`

---

<a id="item-tech-news-6"></a>
### [Huawei Cloud launches openPangu-2.1-Pro on MaaS with token pricing](https://mp.weixin.qq.com/s/8JfFmscBTDl_mPQMycD8Nw) ⭐️ 7.0/10

On November 15, Huawei Cloud added openPangu-2.1-Pro, which it describes as an open-source Pangu model, to its MaaS platform for agent development, AI coding, and inference optimization. Huawei says the model was tuned on more than 100,000 specialized examples for Skills triggering and tool calls, and is adapted to HarmonyOS ArkTS development and Ascend operator generation. It is integrated with AgentArts, CodeArts, and OfficeAce. MaaS inference is priced at RMB 0.8 per million input tokens, RMB 3.2 per million output tokens, and RMB 0.016 per million cached input tokens; the announcement did not give model size, benchmark results, or license terms.

telegram · zaihuapd · Nov 15, 16:03

**「Background」** Huawei Cloud had announced on November 1 that its MaaS platform would stop selling openPangu-2.0-Flash and openPangu-2.0-Pro on November 6, 2026, while saying that new openPangu versions were planned. The 2.1-Pro model had already appeared in Huawei&\#x27;s Xiaoyi Work assistant before this MaaS listing.

**「Impact」** Developers using Huawei Cloud MaaS can call the model at the listed per-token rates, and teams building on HarmonyOS/ArkTS or Ascend gain the most direct fit through the CodeArts, AgentArts, and OfficeAce integrations. Because the announcement does not specify parameter count, license, or weight availability, organizations should confirm self-hosting and redistribution terms before planning production use.

<details><summary>References</summary>
<ul>
<li><a href="https://www.ithome.com/1/022/974.htm">消息称 华 为 云 MaaS 平台 11 月 15 日更新上线 openPangu - 2 . 1 - Pro ...</a></li>
<li><a href="https://www.163.com/dy/article/LAUGH8N10511B8LM.html">华 为 小艺Work率先上线 openPangu - 2 . 1 - Pro 模 型 ，主打“鸿蒙任务增强”</a></li>

</ul>
</details>

**Tags**: `#Huawei Cloud`, `#Pangu`, `#open-source LLM`, `#AI agents`, `#AI coding`

---

## Financial News

<a id="item-finance-news-1"></a>
### [China Says US, Chinese and Russian Leaders to Hold First Trilateral Meeting at APEC](https://apnews.com/article/trump-xi-putin-summit-china-5fe92253ef38100bae913834a9b74d72) ⭐️ 8.0/10

China’s Foreign Ministry said the US, Chinese and Russian leaders plan to meet on November 19 on the sidelines of the APEC summit in Shenzhen, in what media described as their first dedicated trilateral meeting. The meeting is not part of APEC’s official agenda, and no agenda or expected outcomes were announced.

telegram · zaihuapd · Nov 16, 01:38

**「Background」** China is hosting APEC&\#x27;s 2026 leaders&\#x27; meeting in Shenzhen on November 18–19, the third time it has hosted the forum after 2001 and 2014, and the trilateral is a side event outside the official agenda. Kremlin spokesman Dmitry Peskov said on November 14 that the three governments had agreed to the November 19 meeting.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/APEC_China_2026">APEC China 2026 - Wikipedia</a></li>
<li><a href="https://www.riotimesonline.com/apec-shenzhen-2026/">APEC 2026 in Shenzhen : Dates , Agenda and What to Watch</a></li>
<li><a href="https://sputnikglobe.com/20261114/putin-xi-trump-to-hold-trilateral-meeting-in-chinas-shenzhen-on-november-19---peskov-1125073196.html">Putin, Xi, Trump to Hold Trilateral Meeting in China &#x27;s Shenzhen on...</a></li>

</ul>
</details>

**Tags**: `#geopolitics`, `#US-China-Russia`, `#APEC`, `#diplomacy`, `#market risk`

---

<a id="item-finance-news-2"></a>
### [Lutnick Faces Questions Over Cantor Fitzgerald&\#x27;s Nvidia Holdings](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 7.0/10

Cantor Fitzgerald, formerly run by Commerce Secretary Howard Lutnick and now led by his sons, reported a 49% drop in its Nvidia share count between September 2025 and March 2026, from 3.5 million shares worth $652 million to 1.78 million worth $310 million, according to CNBC&\#x27;s review of securities filings; the scrutiny follows Axios reporting that Lutnick resisted a crackdown on alleged Nvidia chip smuggling to China.

rss · CNBC Finance · Nov 15, 19:58

**「Background」** Howard Lutnick has served as U.S. commerce secretary since 2025 and previously ran Cantor Fitzgerald, the Wall Street firm now led by his sons; Commerce oversees U.S. AI-chip export controls. Megaspeed, a Singapore-based company, is suspected by U.S. officials of diverting Nvidia’s advanced chips to China in violation of those controls, and Lutnick is set to testify before the Senate about Commerce’s handling of the matter.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cbsnews.com/news/howard-lutnick-scott-bessent-nvidia-megaspeed-testimony/">Lutnick agrees to testify as Bessent blames him for not banning Nvidia ...</a></li>
<li><a href="https://nypost.com/2026/11/13/business/howard-lutnick-to-testify-before-senate-on-nvidia-megaspeed-fiasco/">Howard Lutnick to testify before Senate on Nvidia , Megaspeed fiasco</a></li>
<li><a href="https://en.wikipedia.org/wiki/Howard_Lutnick">Howard Lutnick - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#US-China tech`, `#export controls`, `#ethics/conflicts`, `#semiconductor policy`

---

<a id="item-finance-news-3"></a>
### [U.S. judge denies Micron, Samsung and SK Hynix bid to dismiss DRAM price-fixing lawsuit](https://www.tomshardware.com/tech-industry/big-tech/judge-denies-motion-to-dismiss-dram-price-fixing-lawsuit-against-micron-samsung-and-sk-hynix-says-chipmakers-acted-like-hawks-flying-in-formation-finds-evidence-of-dram-collusion-plausible-after-500-percent-price-surge) ⭐️ 7.0/10

U.S. Judge Noël Wise rejected motions by Micron, Samsung and SK Hynix to dismiss a DRAM price-fixing class action \(group lawsuit\), allowing the case to proceed. The plaintiffs allege the three chipmakers coordinated to limit DRAM supply and that prices rose by as much as 500%; the ruling does not establish liability.

telegram · zaihuapd · Nov 15, 16:39

**「Background」** The case is a proposed class action by 17 individuals and small businesses that bought DRAM—memory chips used in computers and other devices—through intermediaries rather than directly from Samsung, SK Hynix and Micron; they allege the three suppliers coordinated to restrict conventional DRAM supply.

<details><summary>References</summary>
<ul>
<li><a href="https://litnews.ai/articles/garciaguirre-samsung-sk-hynix-micron-dram-conspiracy-suit-survives-dismissal">Judge Refuses to Dismiss DRAM Supply Conspiracy Suit Against...</a></li>

</ul>
</details>

**Tags**: `#DRAM`, `#antitrust litigation`, `#semiconductor industry`, `#price-fixing`, `#Micron/Samsung/SK Hynix`

---