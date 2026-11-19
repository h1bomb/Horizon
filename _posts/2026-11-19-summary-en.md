---
layout: default
title: "Horizon Summary: 2026-11-19 (EN)"
date: 2026-11-19
lang: en
---

> From 43 items, 14 important content pieces were selected

---

**Technology News**
1. [Google Releases Gemini 4 Neon for Coding and Research](#item-tech-news-1) ⭐️ 8.0/10
2. [Wiz reports unauthenticated RCE in Nginx HTTP/2](#item-tech-news-2) ⭐️ 8.0/10
3. [Xint discloses NGINX2Root chain from nginx to host root](#item-tech-news-3) ⭐️ 8.0/10
4. [Microsoft announces seven AI models at Ignite 2026](#item-tech-news-4) ⭐️ 7.0/10
5. [Show HN: Voyager 1 tour goes down to individual memory chips](#item-tech-news-5) ⭐️ 7.0/10
6. [Quad9&\#x27;s France exit and the argument against DNS piracy blocking](#item-tech-news-6) ⭐️ 7.0/10
7. [Google DeepMind says Genie 4 is available to eligible AI Ultra subscribers](#item-tech-news-7) ⭐️ 7.0/10
8. [Tencent says WeChat Xiaowei reaches 30M daily users in expanded test](#item-tech-news-8) ⭐️ 7.0/10
9. [US Weighs Public Disclosure of Chinese AI Use by Firms](#item-tech-news-9) ⭐️ 7.0/10

**Financial News**
1. [Fed minutes show officials expect more rate hikes, flag AI inflation risk](#item-finance-news-1) ⭐️ 8.0/10
2. [Fed Governor Waller says a half-point rate hike may be needed in December](#item-finance-news-2) ⭐️ 8.0/10
3. [Trump, Xi and Putin to gather at APEC summit in Shenzhen as trade truce talks resume](#item-finance-news-3) ⭐️ 7.0/10
4. [腾讯三季度资本开支升至814亿元，自由现金流为负691亿元](#item-finance-news-4) ⭐️ 7.0/10
5. [中国与韩国宣布自贸协定服务与投资后续谈判实质性结束](#item-finance-news-5) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Google Releases Gemini 4 Neon for Coding and Research](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/) ⭐️ 8.0/10

Google released Gemini 4 Neon, a model aimed at fast end-to-end work in complex software engineering, knowledge work and research workflows, available to developers, enterprises and Google AI Pro/Ultra subscribers. It is priced at $3 per million input tokens \($0.15 cached\) and $15 per million output tokens, with a 1 million-token context window. Google says Neon ranks first on Artificial Analysis&\#x27;s coding agent index at 58.6, third on its intelligence index at the xhigh setting with 61, scores 65.2% on Terminal-Bench 4.1, and lowers per-task cost by 32% versus Carbon at the default high setting.

hackernews · yigitdemirag · Nov 18, 21:34 · [Discussion](https://news.ycombinator.com/item?id=50552424)

**「Predecessor context」** Gemini 4 Neon is not a new base model: Google DeepMind&\#x27;s model card says it was adapted from Gemini 4 Carbon, the predecessor that Google positioned as its flagship. Coverage of the launch compares Neon directly with Carbon, including Google&\#x27;s claim that Neon is three times faster, making Carbon the baseline for assessing the new variant&\#x27;s speed and benchmark positioning.

**「Impact」** Developers and enterprises evaluating Neon should budget around output volume rather than input volume: at $15 per million output tokens versus $3 per million input, generation-heavy agent runs will dominate cost, while cached input at $0.15 rewards repeated long-context workflows.

**「Community Discussion」** Commenters criticized Google&\#x27;s growing set of model names as difficult to map to use cases. One argued Neon is positioned as more intelligent overall than Carbon while Carbon remains the “long-horizon” model with stronger results on research-scale evals, and another reported Neon serving at 127 tokens per second on OpenRouter versus Carbon&\#x27;s 46 and questioned the gap.

<details><summary>References</summary>
<ul>
<li><a href="https://artificialanalysis.ai/models/gemini-4-neon">Gemini 4 Neon Models - Intelligence, Performance &amp; Price Comparison</a></li>
<li><a href="https://www.neowin.net/news/google-launches-gemini-4-neon-claims-its-three-times-faster-than-carbon/">Google launches Gemini 4 Neon , claims it&#x27;s three times... - Neowin</a></li>
<li><a href="https://deepmind.google/models/model-cards/gemini-4-neon/">Gemini 4 Neon - Model Card — Google DeepMind</a></li>

</ul>
</details>

**Tags**: `#Gemini 4`, `#LLM releases`, `#Google AI`, `#model benchmarking`, `#AI industry`

---

<a id="item-tech-news-2"></a>
### [Wiz reports unauthenticated RCE in Nginx HTTP/2](https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities) ⭐️ 8.0/10

Wiz has published a report on unauthenticated remote code execution vulnerabilities in Nginx&\#x27;s HTTP/2 handling, linking to CVE-2026-123633 and CVE-2026-123007. The supplied material does not specify affected Nginx versions, the precise exploit conditions, or whether either flaw has been exploited in the wild. It is a vulnerability write-up rather than an Nginx advisory with fixed releases or a remediation timeline.

hackernews · speedping · Nov 18, 15:19 · [Discussion](https://news.ycombinator.com/item?id=50547374)

**「Background」** HTTP/2 replaces HTTP/1.1&\#x27;s free-form text parsing with a binary framing and stream-multiplexing layer, which gives servers a much larger and more intricate parsing surface to defend. In Nginx, HTTP/2 is opt-in: it must be explicitly enabled on a TLS \`listen\` directive, so only deployments that turned it on carry the affected code path at all.

**「Impact」** Operators running Nginx with HTTP/2 enabled face a potential unauthenticated RCE path, while those who have left HTTP/2 off are not exposed through it; commenters described disabling HTTP/2 as a simple workaround. The supplied material does not identify patched releases, so version-specific remediation cannot be confirmed from it.

**「Community discussion」** Commenters disagreed on severity: one noted that HTTP/2 is not enabled by default and cited roughly 12% server adoption, while another argued exploitation requires about 128 Gb of HTTP/2 traffic and specific CPU instructions and called it a non-issue. A separate commenter criticized the disclosure process, saying the fix landed in the open-source repository a week before publication without a public advisory.

**Tags**: `#nginx`, `#http2`, `#remote code execution`, `#security vulnerability`, `#CVE`

---

<a id="item-tech-news-3"></a>
### [Xint discloses NGINX2Root chain from nginx to host root](https://nginx2root.com/) ⭐️ 8.0/10

Xint has publicly disclosed NGINX2Root, a claimed chain of five nginx vulnerabilities plus a Linux kernel flaw that takes an nginx visitor to host root. The main flaw, CVE-2026-123007, is described as an unauthenticated HTTP/2 flow-control memory-corruption bug that allows command execution in an nginx worker. The disclosure says nginx 1.30.7 and 1.31.9 fixed 10 CVEs on Nov 18, that Rapid7 has released a PoC, and that no in-the-wild exploitation is known; operators who cannot upgrade should disable external HTTP/2. Because the item is a terse Telegram post rather than a primary advisory, the CVE identifier and fix details are not independently confirmed.

telegram · zaihuapd · Nov 18, 16:21

**「Decade-old HTTP/2 defect」** The lead flaw, CVE-2026-123007, is an HTTP/2 integer underflow that has existed in nginx&\#x27;s open-source code since version 1.9.5, released on September 22, 2015, according to The Hacker News. Exploitation requires HTTP/2 to be enabled on the target server, a condition the Wiz analysis also emphasizes for the related nginx vulnerabilities.

**「Impact」** For operators running nginx at the edge, the immediate concern is that unauthenticated HTTP/2 traffic can reach the worker-level memory-corruption flaw, with the disclosed chain claiming escalation to host root; the stated mitigation is to upgrade or disable external HTTP/2.

<details><summary>References</summary>
<ul>
<li><a href="https://thehackernews.com/2026/11/10-year-old-nginx-http2-flaw-lets.html">10-Year-Old NGINX HTTP / 2 Flaw Lets Unauthenticated Attackers...</a></li>
<li><a href="https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities">Unauthenticated Remote Code Execution in NGINX ... | Wiz Blog</a></li>

</ul>
</details>

**Tags**: `#nginx`, `#vulnerability disclosure`, `#remote code execution`, `#HTTP/2`, `#patching`

---

<a id="item-tech-news-4"></a>
### [Microsoft announces seven AI models at Ignite 2026](https://microsoft.ai/news/microsoft-ignite-2026/) ⭐️ 7.0/10

Microsoft announced seven new AI models at its Ignite 2026 event, positioning them around scalable price-performance. The supplied announcement text does not include model names beyond MAI Code 2 being discussed by commenters, nor does it provide pricing, release dates, or availability details, so the concrete capabilities remain unverified.

hackernews · gmays · Nov 18, 16:08 · [Discussion](https://news.ycombinator.com/item?id=50548021)

**「Background」** Microsoft&\#x27;s Ignite conference is a venue for major product and developer announcements, and the new lineup sits under the company&\#x27;s MAI brand. That brand already appears in third-party API marketplaces, where OpenRouter lists an MAI-Image-2.7 model with per-use pricing, and Microsoft is backing the price-performance pitch with a benchmark claim: MAI Cyber 2 Flash matches GPT-6 Astra&\#x27;s quality at less than 2% of the cost per task on CyberGymE 2, a vendor comparison rather than an independent result.

**「Cost-driven model choice」** Developers picking a coding model now have a substantially cheaper option to evaluate: Microsoft claims MAI Code 2 reaches 98% of GPT-6.1 Sol&\#x27;s performance at 40% of the cost and 96% of Claude Opus 5.5&\#x27;s at 5% of the cost, with the model also being rolled into Copilot. Those figures are Microsoft&\#x27;s own benchmark claims rather than independent measurements, so teams should test them against their own workloads before switching, and should confirm per-token pricing rather than assume the advertised ratios translate directly into total spend.

**「Community discussion」** One commenter, johnshahbazian, said they had been testing MAI Code 2 and found it &quot;quite good&quot; for their usual work, adding that they would not argue much with claims it is on par with Opus or Sol. Another commenter, ahmedfromtunis, argued that Microsoft should release some models as open source or open weight if it hopes to secure market share, warning otherwise it would be &quot;Windows Phone OS all over again.&quot;

<details><summary>References</summary>
<ul>
<li><a href="https://microsoft.ai/news/microsoft-ignite-2026/">Seven new world class models at scalable... | Microsoft AI</a></li>
<li><a href="https://ignite.microsoft.com/">Your home for Microsoft Ignite</a></li>
<li><a href="https://openrouter.ai/microsoft/mai-image-2.7">MAI -Image- 2 . 7 - Image Generation API Pricing | OpenRouter</a></li>
<li><a href="https://felloai.com/mai-code-2/">MAI Code 2: Price, Benchmarks and Copilot Plans - felloai.com</a></li>
<li><a href="https://explainx.ai/blog/microsoft-ignite-mai-code-2-seven-models-november-2026">Microsoft Ignite 2026: MAI Code 2, Cyber 2 Flash, and Six ...</a></li>

</ul>
</details>

**Tags**: `#Microsoft`, `#AI models`, `#MAI Code 2`, `#LLM pricing`, `#model competition`

---

<a id="item-tech-news-5"></a>
### [Show HN: Voyager 1 tour goes down to individual memory chips](https://rshekhar.com/voyager/) ⭐️ 7.0/10

Raj Shekhar posted an interactive Voyager 1 breakdown that lets visitors inspect the spacecraft&\#x27;s systems at component level, including its nuclear battery&\#x27;s 24 plutonium spheres and the data computer&\#x27;s individual memory chips. The site also shows where both Voyagers are now, which Earth dish is listening live, how the Golden Record&\#x27;s cover explains playback, and includes a four-minute film. Shekhar presented it as Voyager 1 reached one light-day from Earth today.

hackernews · raj-shekhar · Nov 18, 16:18 · [Discussion](https://news.ycombinator.com/item?id=50548161)

**「What a light-day means」** Voyager 1 is about one light-day from Earth—the distance light travels in 24 hours. That means a radio command takes roughly a day to reach the spacecraft and a reply takes another day to return, which is why the mission is still operated through NASA&\#x27;s Deep Space Network.

**「Community discussion」** Commenters welcomed the project but questioned its production: glimshe said it “appears to be vibecoded” and asked whether AI did most or all of the work and whether it was checked against an authoritative source, while carter-qadenza called it neat but said some things are missing. Gourneau linked a separate Golden Record tribute and a decoder for turning the probes&\#x27; raw audio into images.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Voyager_1">Voyager 1 - Wikipedia</a></li>
<li><a href="https://www.aljazeera.com/news/2026/11/18/nasas-voyager-1-hits-record-one-light-day-distance-50-years-after-launch">NASA’s Voyager 1 hits record one light - day distance , 50... | Al Jazeera</a></li>

</ul>
</details>

**Tags**: `#Voyager`, `#interactive-visualization`, `#computer-hardware`, `#space-technology`, `#technical-education`

---

<a id="item-tech-news-6"></a>
### [Quad9&\#x27;s France exit and the argument against DNS piracy blocking](https://techstackups.com/articles/quad9-leaves-france-dns-blocking/) ⭐️ 7.0/10

Public DNS resolver Quad9&\#x27;s reported exit from France is the hook for a TechStackUps article arguing that DNS resolvers are the wrong place to enforce copyright. The piece is an opinion/analysis argument, not a report of a new resolver capability or an independent measurement, and the supplied material does not include the article text or Quad9&\#x27;s announcement. As a result, the specific French order, its timing, and the scope of the withdrawal are not established here.

hackernews · ritzaco · Nov 18, 13:18 · [Discussion](https://news.ycombinator.com/item?id=50545958)

**「Background」** DNS resolvers translate domain names into IP addresses, and Quad9 is a Swiss non-profit that operates a free public resolver. In October 2026 a Paris court ordered Quad9 to block sites accused of copyright infringement, and the foundation said it would stop serving French users on November 24 rather than comply; TorrentFreak reported it was the second DNS resolver to leave France over such orders.

**「Community discussion」** Commenters disagree over DNS blocking: one calls any anti-piracy effort short of prosecuting pirates a backdoor to speech suppression, while another argues that easier, DRM-free paid access would reduce piracy more than blocking. A separate comment asks whether the French result reflects judges misapplying the law or judges correctly applying a bad statute, which shifts the question to lawmakers.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.cloudflare.com/quad9-withdrawal-from-france/">Quad9’s withdrawal from France: A canary in the coal mine</a></li>
<li><a href="https://torrentfreak.com/dns-resolver-quad9-will-leave-france-after-court-orders-piracy-blocking-penalty/">DNS Resolver Quad9 Will Leave France After Court Orders ...</a></li>
<li><a href="https://www.eff.org/deeplinks/2026/10/french-courts-site-blocking-orders-drive-quad9-out-france">French Court’s Site-Blocking Orders Drive Quad9 Out Of France</a></li>

</ul>
</details>

**Tags**: `#DNS`, `#internet governance`, `#privacy`, `#copyright enforcement`, `#Quad9`

---

<a id="item-tech-news-7"></a>
### [Google DeepMind says Genie 4 is available to eligible AI Ultra subscribers](https://blog.google/innovation-and-ai/models-and-research/google-deepmind/genie-4-now-available-project-genie/) ⭐️ 7.0/10

Google DeepMind announced that Genie 4, the latest version of its generative world model, is now available. According to the announcement as supplied, access is limited to &quot;eligible Google AI Ultra subscribers,&quot; with no technical details on model capabilities, benchmarks, pricing, or supported regions. Commenters reported difficulty confirming eligibility, including a UK user whose Workspace account could not obtain Ultra and whose personal account indicated that Ultra includes Genie 3.

hackernews · leumon · Nov 18, 18:49 · [Discussion](https://news.ycombinator.com/item?id=50550415)

**「Background」** Genie is Google DeepMind’s world-generation model line, aimed at synthesizing interactive simulated environments rather than only static images or video. The Genie 4 model card describes this version as multimodal, with audio such as music, ambient sounds, and interactive dialogue generated simultaneously with the world; DeepMind lists it as a research preview for trusted testers, with access planned for Google AI Ultra subscribers in Project Genie and early-access Gemini API and Google AI Studio partners.

**「Robotics simulation access」** Robotics teams get a vendor-stated path to use Genie 4 with Gemini models as digital practice spaces for robots, while Genie 4 itself generates steerable simulations with real-time sound, music, and dialogue. Because the robot-training pairing is described as a plan and access is limited to eligible Google AI Ultra subscribers, teams should verify entitlement and availability before building it into a workflow.

**「Community discussion」** Commenters focused on access and commercialization: one described confusion over whether Workspace accounts and UK users can pay for Genie 4, while another said the thread dwelt on pricing and capability rather than potential negative consequences. Others discussed whether world models could eventually serve as game engines, with one questioning whether Google would permit recreations of existing games.

<details><summary>References</summary>
<ul>
<li><a href="https://deepmind.google/models/genie/">Genie 4 — Google DeepMind</a></li>
<li><a href="https://deepmind.google/models/model-cards/genie-4/">Genie 4 - Model Card — Google DeepMind</a></li>
<li>Genie 4: Features, Access and How the World Model Works - Schnalz.net</li>
<li>Google Genie 4 Combines With Gemini Models to Build Better ...</li>

</ul>
</details>

**Tags**: `#Google DeepMind`, `#world models`, `#generative AI`, `#product release`, `#AI pricing`

---

<a id="item-tech-news-8"></a>
### [Tencent says WeChat Xiaowei reaches 30M daily users in expanded test](https://mp.weixin.qq.com/s/r3NthxJZQJgztyLADwNV4A) ⭐️ 7.0/10

Tencent’s third-quarter 2026 earnings report says WeChat’s Xiaowei AI assistant has expanded testing to 30 million daily active users and is being gradually integrated into chat, Moments, official accounts, and video accounts. Xiaowei uses a custom WeLM model tuned for cost efficiency, and Tencent claims its inference costs are low and continuing to decline. Tencent also says some inference tasks are expected to run on users’ devices in the future. Those figures and plans are Tencent’s own and were not independently verified in the source.

telegram · zaihuapd · Nov 18, 11:35

**「Background」** Xiaowei is a native WeChat assistant rather than a separate app; an earlier community report described it entering broad gray-scale testing inside the WeChat home page, built primarily on Tencent&\#x27;s in-house WeLM model. Tencent&\#x27;s latest disclosure adds a daily-active-user figure to that staged rollout.

**「Impact」** For users in the expanded test, Xiaowei is being surfaced inside existing WeChat features rather than as a separate app; Tencent has not provided a timeline or device requirements for the planned on-device inference.

<details><summary>References</summary>
<ul>
<li><a href="https://post.smzdm.com/p/a03633d9/">不扎堆做独立AI App...</a></li>

</ul>
</details>

**Tags**: `#WeChat`, `#AI assistant`, `#Tencent`, `#WeLM`, `#on-device inference`

---

<a id="item-tech-news-9"></a>
### [US Weighs Public Disclosure of Chinese AI Use by Firms](https://www.reuters.com/world/china/trump-administration-weighs-forcing-us-firms-disclose-chinese-ai-use-2026-11-18/) ⭐️ 7.0/10

The Trump administration is reportedly considering requiring U.S. companies to publicly disclose their use of Chinese AI models, with the Treasury Department and White House Office of Science and Technology Policy having discussed the idea. Under the proposal, firms such as Airbnb—which uses Alibaba&\#x27;s Qwen model for customer service—would have to post disclosures on their websites. The reported aim is to discourage reliance on cheaper Chinese open-weight models through public naming rather than impose new restrictions; it is not yet an official policy, and it remains unclear whether the proposal has internal support or will advance to formal legislation.

telegram · zaihuapd · Nov 19, 02:30

**「Context: why open-weight models matter here」** Chinese open-weight models such as Alibaba&\#x27;s Qwen can be downloaded and self-hosted, making them cheaper to run than proprietary U.S. alternatives and driving adoption by American companies. The disclosure proposal follows separate congressional scrutiny of that reliance, per Reuters reporting cited by the Economic Times, and reflects a preference for transparency pressure over new legal restrictions.

**「Impact」** If adopted, the rule would require companies such as Airbnb—which self-hosts Alibaba&\#x27;s Qwen model for customer service without a vendor contract—to publicly name that deployment, exposing an otherwise internal procurement choice to customers and competitors. Firms using Chinese open-weight models should inventory self-hosted deployments, since those uses may not surface through vendor contracts.

<details><summary>References</summary>
<ul>
<li><a href="https://www.reuters.com/world/china/trump-administration-weighs-forcing-us-firms-disclose-chinese-ai-use-2026-11-18/">Trump administration weighs forcing US firms to disclose ...</a></li>
<li><a href="https://economictimes.indiatimes.com/ai/ai-insights/trump-administration-weighs-forcing-us-firms-to-disclose-chinese-ai-use/articleshow/135962485.cms">Trump administration weighs forcing US firms to disclose ...</a></li>
<li><a href="https://aiadopters.club/p/airbnb-bet-its-support-desk-on-a">Airbnb Bet Its Support Desk on a Chinese AI Model It Can Drop</a></li>
<li><a href="https://www.gate.com/news/detail/ABNB/us-reviews-disclosure-rule-for-companies-using-chinese-ai-models-25705130">US Reviews Disclosure Rule for Companies Using Chinese AI ...</a></li>

</ul>
</details>

**Tags**: `#AI policy`, `#China AI`, `#open-weight models`, `#AI regulation`, `#corporate disclosure`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Fed minutes show officials expect more rate hikes, flag AI inflation risk](https://www.cnbc.com/2026/11/18/fed-minutes-october-2026.html) ⭐️ 8.0/10

The Federal Reserve&\#x27;s October meeting minutes, released Wednesday, showed officials voted 10-2 to hold the benchmark rate at 3.75%-4%, while almost all participants expected further increases would likely be needed to bring inflation back to 2%. They also identified AI-related demand as a material inflation risk.

rss · CNBC Finance · Nov 18, 19:41

**「Background」** The debate centered on whether inflation shocks from the Iran war and President Donald Trump&\#x27;s tariffs were temporary; October CPI later rose 0.4% and core inflation, which excludes food and energy, rose 0.3%, each 0.1 percentage point above expectations.

**「Impact」** The minutes&\#x27; warning about rapidly growing, opaque and concentrated AI-related debt is a direct concern for investors and lenders exposed to those firms, because losses could be amplified if returns on AI investment disappoint.

**Tags**: `#Federal Reserve`, `#monetary policy`, `#inflation`, `#interest rates`, `#AI financial risk`

---

<a id="item-finance-news-2"></a>
### [Fed Governor Waller says a half-point rate hike may be needed in December](https://www.cnbc.com/2026/11/18/federal-reserve-governor-christopher-waller.html) ⭐️ 8.0/10

Federal Reserve Governor Christopher Waller said Wednesday that the central bank may need to raise its benchmark interest rate by half a percentage point at the Dec. 8-9 policy meeting to &quot;shock people&quot; and bring down inflation, which he said is running higher than he expected. Waller, speaking to CNBC, also said the Fed should reverse the three quarter-point cuts it made in 2025 and may need to raise rates further beyond that.

rss · CNBC Finance · Nov 18, 15:13

**「Background」** The Fed cut rates three times in 2025 on labor-market concerns, then approved its first hike in more than three years in September 2026 and held rates steady in October as inflation reignited, with most readings above 3% after energy prices spiked following U.S. and Israeli strikes on Iran in late February. Futures markets are fully pricing a quarter-point hike in December, according to CME Group&\#x27;s FedWatch gauge, and other officials including New York Fed President John Williams have said the situation does not call for &quot;dramatic action.&quot;

**Tags**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#inflation`, `#Christopher Waller`

---

<a id="item-finance-news-3"></a>
### [Trump, Xi and Putin to gather at APEC summit in Shenzhen as trade truce talks resume](https://www.cnbc.com/2026/11/18/apec-trump-xi-putin-shenzhen.html) ⭐️ 7.0/10

U.S. President Donald Trump and Chinese President Xi Jinping are expected to meet on the sidelines of the APEC summit in Shenzhen on Wednesday and Thursday, with U.S. officials saying the talks will focus on implementing a trade truce of lower tariffs and some rare-earths flows that was extended by two months, to January 2027. Expectations for any breakthrough are low.

rss · CNBC Finance · Nov 18, 06:04

**「Background」** The truce dates from last year&\#x27;s APEC meeting in South Korea, and in September the two sides said they would cut tariffs on $30 billion worth of each other&\#x27;s goods without setting an effective date, while Washington is now tightening loopholes that had given Chinese companies access to American AI technology.

**「Impact」** China said this month it would increase purchases of U.S. agricultural products only if those tariffs are lowered, tying any gain for American farm exporters to a step the U.S. has announced but not yet scheduled.

**Tags**: `#US-China relations`, `#APEC summit`, `#trade policy`, `#geopolitics`, `#AI technology restrictions`

---

<a id="item-finance-news-4"></a>
### [腾讯三季度资本开支升至814亿元，自由现金流为负691亿元](https://api3.cls.cn/share/article/2537922?os=android&amp;amp;sv=8.8.5&amp;amp;app=cailianpress&amp;amp;selected=) ⭐️ 7.0/10

腾讯公布2026年第三季度财报，营收2073亿元人民币，同比增长8%，低于市场预期；归母净利润636亿元，同比增长0.8%。当季资本开支814.33亿元，远超市场预估的554亿元，单季自由现金流为负691亿元；腾讯还称，其WorkBuddy产品的日均Token用量超过100万亿，为国内大语言模型产品最高。

telegram · zaihuapd · Nov 18, 09:20

**「Background」** WorkBuddy is Tencent&\#x27;s AI agent for office work, and token usage measures how much text the model processes, not revenue. Capital expenditure is spending on long-lived assets such as data centers and servers, so a surge in such spending can push free cash flow—operating cash after capex—negative.

<details><summary>References</summary>
<ul>
<li><a href="https://www.workbuddy.ai/">WorkBuddy - AI Agent for Everyday Office Work</a></li>

</ul>
</details>

**Tags**: `#腾讯`, `#财报`, `#AI资本开支`, `#自由现金流`, `#大模型Token用量`

---

<a id="item-finance-news-5"></a>
### [中国与韩国宣布自贸协定服务与投资后续谈判实质性结束](https://x.com/Jaemyung_Lee/status/2122988472994791476) ⭐️ 7.0/10

中国与韩国于11月18日宣布，两国自贸协定服务与投资后续谈判已实质性结束。中方承诺在电影、游戏等领域给予韩国最惠国待遇，并扩大旅游、法律、建筑和金融等领域的市场开放；双方还将视听共同制作范围从电影扩大到电视剧、动画、综艺和纪录片。谈判自2018年3月启动，历时8年8个月，部分技术事项仍留待工作层面协商。

telegram · zaihuapd · Nov 18, 10:02

**「Background」** The follow-up negotiations on services and investment began in March 2018 and were restarted in January 2025 after a four-year pause, Chinese and South Korean officials said at the time.

**「Who is affected」** Once the deal is in force, the sectoral commitments would lower market-access barriers in China for South Korean film, gaming, tourism, legal, construction and financial firms, and would let producers in both countries co-produce TV dramas, animation, variety shows and documentaries as well as films — though some technical points are still to be settled at working level.

<details><summary>References</summary>
<ul>
<li><a href="https://www.zaobao.com.sg/realtime/china/story20250116-5743403">时隔四 年 韩 中 重启 自 贸 协 定 服 贸 投 资 后 续 谈 判 | 联合早报</a></li>

</ul>
</details>

**Tags**: `#China-South Korea FTA`, `#services trade`, `#investment liberalization`, `#audiovisual and gaming`, `#trade policy`

---