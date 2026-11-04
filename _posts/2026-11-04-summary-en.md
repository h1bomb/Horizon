---
layout: default
title: "Horizon Summary: 2026-11-04 (EN)"
date: 2026-11-04
lang: en
---

> From 41 items, 12 important content pieces were selected

---

**Technology News**
1. [Postman accused of auto-installing AI plugins and sending API data to its servers](#item-tech-news-1) ⭐️ 8.0/10
2. [Blog post disputes claim that Astra weight editing improves Qwen](#item-tech-news-2) ⭐️ 7.0/10
3. [Qwen 3.8 27B identifies games from raw weights on a laptop](#item-tech-news-3) ⭐️ 7.0/10
4. [Could a Modern Engine on a Pentium Have Beaten Kasparov?](#item-tech-news-4) ⭐️ 7.0/10
5. [Nikkei: US tech AI obligations jump 90% to $3.2T](#item-tech-news-5) ⭐️ 7.0/10
6. [Mac at Any Scale: Workarounds for macOS Data-Center CI](#item-tech-news-6) ⭐️ 7.0/10
7. [Safari 27.3 Adds Adaptive Dark Mode for Unsupported Sites](#item-tech-news-7) ⭐️ 7.0/10
8. [Aircraft noise plus ADS-B data can geolocate a video, OSINT demo shows](#item-tech-news-8) ⭐️ 7.0/10
9. [New York Times sues Brave over alleged scraping and AI data sales](#item-tech-news-9) ⭐️ 7.0/10
10. [Report: Nvidia Said to Cap Chinese Business at 49% for New Data-Center Contracts](#item-tech-news-10) ⭐️ 7.0/10

**Financial News**
1. [China Regulator Reportedly Suspends IPOs and Large Shareholder Sales to Stabilize Slumping Stocks](#item-finance-news-1) ⭐️ 8.0/10
2. [Anthropic&\#x27;s revised IPO filing shows $1.7 billion in quarterly personnel costs](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Postman accused of auto-installing AI plugins and sending API data to its servers](https://github.com/postmanlabs/postman-app-support/issues/14370) ⭐️ 8.0/10

A GitHub issue filed against postmanlabs/postman-app-support \(\#14370\) alleges that Postman silently installs AI plugins and transmits API request data to its own servers, including the resolved values of templated variables such as \`\{\{some\_secret\}\}\` used in query parameters. Commenters in the associated Hacker News thread \(roughly 993 points and 329 comments\) report that blocking traffic to the logging endpoint breaks the application, and that the tool does not meet HIPAA requirements. The claims come from the issue and community discussion and were not independently verified in the supplied material, and Postman has not responded in the available evidence. Some developers say they have already moved to the Git-friendly alternative Bruno as a result.

hackernews · sidgarimella · Nov 3, 17:22 · [Discussion](https://news.ycombinator.com/item?id=50354960)

**「Background」** The allegations trace to GitHub issue \#14370, opened on October 25, 2026, which reported that launching Postman on a Mac produced a user-wide Postman plugin, a startup instruction hook, a remote MCP connection, a Claude Code plugin, and a separately installed Postman CLI. A subsequent report identified the affected build as Postman 12.33.4 on macOS and the auto-installed plugins as Codex 1.1.0 and Claude Code 2.0.1.

**「What teams handling sensitive data should check」** For teams whose requests carry credentials or PHI, the practical consequence is that templated values such as \`\{\{some\_secret\}\}\` may leave the machine as part of request logging, and per the community reports, firewalling the logging endpoint breaks the client rather than cleanly disabling telemetry — so a network-level workaround is not a drop-in fix. External assessments of Postman&\#x27;s HIPAA posture conflict, with one vendor analysis attributing the risk to its data sync feature and an open GitHub issue still requesting HIPAA compliance, so organizations should verify logging and sync behavior against their own data-handling requirements before sending production secrets or patient data through it.

**「Community discussion」** Commenters describing themselves as practitioners said their security teams decertified Postman over the data handling — one healthcare worker said their team switched to Bruno &quot;overnight&quot; — and several cited performance bloat and forced logins as separate reasons to leave. Others pushed back on the framing by pointing to the tool&\#x27;s venture funding and valuation, arguing that subscription, login, and AI features exist to justify it, though that is opinion rather than documented fact.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/postmanlabs/postman-app-support/issues/14370">[SEVERE] Desktop auto-installs Codex/Claude plugins ... - GitHub</a></li>
<li><a href="https://braindetox.kr/en/posts/postman_ai_plugin_auto_install_report.html">Postman 12.33.4 Plugin Report - Issue 14370 Log and Checks</a></li>
<li><a href="https://www.stedi.com/blog/postman-is-probably-not-hipaa-compliant">Postman is probably not HIPAA - compliant - Stedi</a></li>
<li><a href="https://github.com/postmanlabs/postman-app-support/issues/8104">Postman HIPAA Compliance · Issue #8104...</a></li>

</ul>
</details>

**Tags**: `#postman`, `#privacy`, `#security`, `#api-tools`, `#telemetry`

---

<a id="item-tech-news-2"></a>
### [Blog post disputes claim that Astra weight editing improves Qwen](https://honnibal.dev/blog/astra-read-write-misleading) ⭐️ 7.0/10

A Hacker News–discussed blog post contends that claims about Astra reading and writing model weights to improve Qwen are misleading, arguing that the demonstrated effect is narrower than the framing implies. The critique&\#x27;s central point, as summarized in the discussion, is that the key result reduces reasoning loops—cases where the model assigns too little probability to the token that ends its reasoning—rather than making Qwen better at math. Commenters working in mechanistic interpretability say such loops can be addressed with simple steering vectors, while others note that the original post already described some of these limits and that the techniques resemble prior published work.

hackernews · syllogism · Nov 3, 12:21 · [Discussion](https://news.ycombinator.com/item?id=50351111)

**「Background」** Mechanistic interpretability looks for internal directions or features in a model’s activations, and “steering” typically adds such a vector during inference instead of retraining the model. The disputed Astra claim concerns editing Qwen’s stored weights; the rebuttal turns on whether the observed effect is a general capability improvement or the narrower removal of reasoning loops, where the model assigns too little probability to the token that ends its reasoning.

**「What practitioners should check」** Developers weighing weight-space editing as a substitute for fine-tuning or simple activation steering should treat the reported MATH-500 jump from 7.9% to 48.1% on Qwen3.5-0.8B as unverified until the critique&\#x27;s objections are answered, since the rebuttal argues the headline framing overstates what the edit demonstrates. Commenters working in mechanistic interpretability say the underlying effect looks like reduced reasoning loops, which they note can be addressed by cheaper steering methods that raise the probability of the closing \`&lt;/think&gt;\` token. Before adopting such a workflow, ask for comparisons against those baselines and for the exact evaluation setup behind the 0.016%-of-weights change.

**「Community Discussion」** Commenters split between agreeing that the original claim was oversold—x313, a mechanistic-interpretability researcher, called the key result a reasoning-loop fix achievable with simple steering—and arguing that the critique is partly redundant, with phoghed noting the original post explicitly explained the same limitations. neom added that the weight-editing approach resembles earlier published techniques, reinforcing the framing dispute rather than establishing a new capability.

<details><summary>References</summary>
<ul>
<li><a href="https://honnibal.dev/blog/astra-read-write-misleading">The &#x27;Astra can read and write weights to improve Qwen&#x27; post ...</a></li>
<li><a href="https://explainx.ai/blog/weight-space-programming-gpt-6-astra-edits-qwen3-5-0-8b-weights-math-7-9-to-48-1-mit-csail-2026">GPT-6 Astra Edits Qwen Weights: MATH-500 7.9% to 48.1% ...</a></li>

</ul>
</details>

**Tags**: `#AI research criticism`, `#mechanistic interpretability`, `#LLM steering`, `#Qwen`, `#Hacker News discussion`

---

<a id="item-tech-news-3"></a>
### [Qwen 3.8 27B identifies games from raw weights on a laptop](https://simonwillison.net/2026/Nov/3/qwen-can-interpret-model-weights/) ⭐️ 7.0/10

Simon Willison reports that Qwen 3.8 27B, running locally in LM Studio from a 17GB Q4\_K\_M build, identified Pac-Man from a prompt containing raw policy-network weights, answering after 46m12s and 43,506 reasoning tokens with 72% stated confidence; he also reports it identified Pong. The prompt comes from &\#x27;Sparks of Weight-Space Programming,&\#x27; a paper-shaped blog post by Rikiya Takehi, Jayden Teoh, Alex Zhang, and Omar Khattab that claims frontier models, especially GPT-6 Astra, can interpret raw weights and, in one example, edit 0.016% of Qwen3.5-0.8B&\#x27;s weights to raise MATH-500 from 7.9% to 48.1%. Those claims are contested: Matthew Honnibal called the paper misleading for conflating tool-free weight reading with code-assisted model updates, and Sean Goedecke argued the Qwen3.5-0.8B edit follows steps a human ML researcher would take. Willison&\#x27;s laptop results are informal, individually reported runs of the game-identification experiment, not independent confirmation of the paper&\#x27;s broader editing claims.

rss · Simon Willison · Nov 3, 16:29 · [Discussion](https://news.ycombinator.com/item?id=50355251)

**「Prior work」** The test replicates an example from “Sparks of Weight-Space Programming,” a paper-shaped blog post by Rikiya Takehi, Jayden Teoh, Alex Zhang, and Omar Khattab that coined the term for LLMs reading and writing raw neural-network weights. The post separates no-tool weight inspection from code-assisted weight editing; spaCy author Matthew Honnibal argued that framing was misleading because the experiments use different techniques.

**「Impact」** For developers, the game-identification prompt can be tried without a frontier API—the prompt files are self-contained and Willison runs them with the LLM CLI—but local runs needed context above LM Studio&\#x27;s 8192 default and a raised timeout, with Qwen&\#x27;s answer taking 46 minutes, so this is experimental rather than interactive.

**「Community Discussion」** Commenters debate whether the demonstrations show real weight understanding. variaga asks whether a model&\#x27;s interpretation of weights will actually be correct; data-ottawa asks whether Qwen 3.8 can modify its own generation&\#x27;s weights and how much the result reflects training data versus genuine weight comprehension, citing known neurons, steering vectors, and LoRAs.

<details><summary>References</summary>
<ul>
<li><a href="https://rikiyat.github.io/blog/weight-space-programming/">Sparks of Weight - Space Programming : LLMs can natively read...</a></li>
<li><a href="https://honnibal.dev/blog/astra-read-write-misleading">The &#x27; Astra can read and write weights to improve Qwen &#x27; post is...</a></li>

</ul>
</details>

**Tags**: `#weight-space programming`, `#LLM interpretability`, `#model weights`, `#Qwen`, `#research replication`

---

<a id="item-tech-news-4"></a>
### [Could a Modern Engine on a Pentium Have Beaten Kasparov?](https://nicholas.carlini.com/writing/2026/algorithmic-improvements-chess.html) ⭐️ 7.0/10

A new article examines whether a modern chess engine running on 1990s Pentium-class hardware could have defeated Garry Kasparov in 1996. It uses the counterfactual to explore how much of modern chess-engine strength comes from algorithmic improvements in evaluation and search versus gains from raw hardware performance.

hackernews · markusw · Nov 3, 07:56 · [Discussion](https://news.ycombinator.com/item?id=50349276)

**「Background」** The question is framed by IBM&\#x27;s Deep Blue, the purpose-built chess machine that played Garry Kasparov in a six-game match in 1996; Kasparov won that match 4–2, and Deep Blue won the 1997 rematch 3½–2½. The 1996 contest is the baseline the counterfactual re-examines: how a modern engine running on 1990s consumer hardware, rather than custom hardware, would have fared against Kasparov.

**「Community Discussion」** Commenters largely accepted that modern engines benefit heavily from better evaluation and search, but k2052 argued that a version constrained to 1990s hardware would have exploitable weaknesses at low search depth that Kasparov and his team could target. FartyMcFarter also disputed the article’s claim that grandmasters analyze roughly the same number of moves as amateurs, saying grandmasters examine more branches and go deeper.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Deep_Blue_versus_Garry_Kasparov">Deep Blue versus Garry Kasparov - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#chess engines`, `#AI algorithms`, `#hardware performance`, `#search algorithms`, `#Hacker News discussion`

---

<a id="item-tech-news-5"></a>
### [Nikkei: US tech AI obligations jump 90% to $3.2T](https://asia.nikkei.com/business/technology/artificial-intelligence/us-tech-giants-hidden-ai-debt-swells-90-to-3.2tn-in-6-months) ⭐️ 7.0/10

A Nikkei report says US technology companies&\#x27; AI-related obligations rose 90% over six months to $3.2 trillion, a figure the report frames as hidden AI debt. The &quot;debt&quot; label is contested because the total reportedly includes signed future-spending contracts, data-center leases, and power payments, not only borrowed money, and the contract terms are not detailed. The report&\#x27;s significance lies in the scale and rapid growth of commitments tied to AI infrastructure and in how much exposure may sit outside conventional debt measures.

hackernews · angry\_impala · Nov 3, 21:26 · [Discussion](https://news.ycombinator.com/item?id=50358422)

**「Background」** Nikkei Asia had previously estimated that hidden debt at five large US tech companies had grown eightfold in about four years to $1.65 trillion, with Meta alone carrying roughly $420 billion in off-balance-sheet obligations—nearly triple its transparent debt. The new report&\#x27;s $3.2 trillion total, after a 90% rise in six months, is a sharp escalation of that same off-balance-sheet AI-financing estimate.

**「Impact」** For investors and creditors, the practical issue is comparability: if much of the $3.2 trillion consists of future purchase and lease commitments rather than borrowings, treating it as equivalent to reported debt could misstate a company&\#x27;s leverage and liquidity risk.

**「Community discussion」** Commenters disputed the &quot;debt&quot; label, arguing that signed future-spending contracts—potentially cancellable on short notice—differ from borrowed money with interest and repayment, while others said the commitments still expose companies to serious risk in a higher-rate environment. Several focused on unknown contract terms and the inclusion of multi-decade data-center leases and power payments as reasons the headline figure is misleading.

<details><summary>References</summary>
<ul>
<li><a href="https://asia.nikkei.com/business/technology/five-us-tech-giants-hidden-debts-soar-to-1.65tn-on-opaque-ai-funding">Five US tech giants &#x27; hidden debts soar to $1.65tn on... - Nikkei Asia</a></li>

</ul>
</details>

**Tags**: `#AI infrastructure`, `#tech finance`, `#cloud computing`, `#data centers`, `#industry analysis`

---

<a id="item-tech-news-6"></a>
### [Mac at Any Scale: Workarounds for macOS Data-Center CI](https://namespace.so/blog/mac-at-any-scale) ⭐️ 7.0/10

Namespace published “Mac at Any Scale,” a practitioner account of the engineering needed to run Macs at data-center scale, particularly for macOS CI and testing. The article focuses on workarounds for Apple platform limitations rather than a new Apple server product or a measured performance breakthrough. The supplied comments add operational detail but do not independently verify the article’s specific implementations.

hackernews · anner\_ · Nov 3, 14:53 · [Discussion](https://news.ycombinator.com/item?id=50352758)

**「Background」** Racking Macs means adapting consumer hardware: Namespace notes that the Mac mini has only rudimentary remote management, no redundant power, and a case that makes cooling difficult in racks. A Russian-language report said Namespace racked hundreds of MacBooks instead after Mac minis ordered in January arrived only in July, while customers needed newer processors sooner.

**「Impact」** For teams running Mac-based CI, the practical consequence is that Linux-style remote administration assumptions do not carry over: commenters cite a boot-time password gate on a Mac mini server and battery swelling in racked iOS devices as operational hazards.

**「Community Discussion」** Commenters criticized Apple’s server and automation support, with one calling Xcode Cloud “a joke” and another arguing that a new Xserve would still sell at twice the Mac mini’s price because data-center operations are expensive. A testing vendor said it had deployed Mac mini M6 instances via Virtualization.Framework for automated macOS testing and warned about battery swelling in racked iOS devices.

<details><summary>References</summary>
<ul>
<li><a href="https://namespace.so/blog/mac-at-any-scale">Mac at any scale | Namespace</a></li>
<li><a href="https://dzen.ru/b/auobbcRL2iIDzEZm">Namespace поставила сотни MacBook в стойки вместо Mac mini ...</a></li>

</ul>
</details>

**Tags**: `#macOS`, `#infrastructure`, `#CI/CD`, `#Apple`, `#data centers`

---

<a id="item-tech-news-7"></a>
### [Safari 27.3 Adds Adaptive Dark Mode for Unsupported Sites](https://webkit.org/blog/18541/introducing-adaptive-dark-mode/) ⭐️ 7.0/10

Safari 27.3 introduces Adaptive Dark Mode, a WebKit feature that automatically adapts websites lacking dark themes. The capability affects Safari users and frontend developers on sites that have not implemented dark mode. The supplied item does not state availability beyond the version number or explain how the adaptation works.

hackernews · paddingtone · Nov 3, 21:39 · [Discussion](https://news.ycombinator.com/item?id=50358562)

**「Background」** Adaptive Dark Mode is a Safari-level override that turns light websites dark when the user has a dark system appearance, while leaving sites that declare dark-mode support unchanged. WebKit exposes \`color-scheme: light only\` as an opt-out, though the \`only\` keyword is not supported in Safari 27.3 beta 1, so the escape hatch remains incomplete during the beta.

**「Testing before opting out」** Developers who maintain light-only designs should test their pages under Adaptive Dark Mode; prior forced-dark implementations, such as Samsung Internet&\#x27;s, have left text nearly invisible when the browser adjusted text color but not the background. Sites that must remain light can declare \`color-scheme: light only\`, which commenters note Safari respects.

**「Community Discussion」** Commenters broadly welcomed the feature for sites and back-office tools where dark mode is an afterthought, with one describing it as a reasonable way to avoid maintaining two designs. Others raised design and accessibility concerns, noting that some light-designed sites may break, that \`color-scheme: light only\` exists as an opt-out, and that one commenter with astigmatism wants the reverse conversion from dark to light.

<details><summary>References</summary>
<ul>
<li><a href="https://webkit.org/blog/18541/introducing-adaptive-dark-mode/">Introducing Adaptive Dark Mode | WebKit</a></li>
<li><a href="https://www.technobezz.com/news/safari-beta-adds-adaptive-dark-mode">Safari 27.3 Beta Adds Adaptive Dark Mode for Light Websites</a></li>
<li><a href="https://www.v01.io/posts/2024/04/samsung-internet-dark-mode/">Dear Samsung Internet: Please Fix Your Forced Dark Mode !</a></li>

</ul>
</details>

**Tags**: `#Safari`, `#WebKit`, `#dark mode`, `#web development`, `#CSS`

---

<a id="item-tech-news-8"></a>
### [Aircraft noise plus ADS-B data can geolocate a video, OSINT demo shows](https://simonwillison.net/2026/Nov/3/a-sound-that-leaks-your-exact-location/) ⭐️ 7.0/10

In a YouTube video, researcher Colsto demonstrates an OSINT technique that extracts nearly imperceptible aircraft background noise from a video&\#x27;s soundtrack, derives the planes&\#x27; Doppler curves, and cross-references them against ADS-B flight data. By combining speed, distance, and the gaps between different overflights, the method can narrow a recording to a specific location, according to Simon Willison&\#x27;s link post, which calls it a &quot;genius piece of OSINT.&quot; The post is brief and points to the video rather than independently verifying the result, so the exact-location claim rests on the demonstration itself.

rss · Simon Willison · Nov 3, 05:32

**「How the aircraft-sound technique works」** The method depends on the Doppler effect: as a plane passes, the pitch of its engine noise shifts in a predictable way, producing a Doppler curve in the recording&\#x27;s spectrogram. ADS-B flight data supplies aircraft positions and speeds, allowing candidate locations to be tested by modelling the Doppler curve each one would produce and comparing it with the audio; Colsto reportedly narrowed a recording to within roughly 100 metres this way.

**「Impact」** For anyone publishing video with ambient audio, stripping embedded location metadata is not sufficient: the recording itself can retain faint aircraft noise that, combined with public flight data, may allow the recording&\#x27;s location to be reconstructed. ADS-B position data is broadcast unencrypted and aggregated by third-party apps and websites, so programs that limit the FAA&\#x27;s redistribution of aircraft data do not remove the source material this technique relies on.

<details><summary>References</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=UytYrhYLOKI">I discovered a sound that leaks your exact location ... - YouTube</a></li>
<li><a href="https://digg.com/">Digg - News, before it trends</a></li>
<li><a href="https://www.honeywellaerospace.com/us/en/insights/articles/ads-b-privacy">ADS-B Privacy - honeywellaerospace.com</a></li>
<li><a href="https://e3aviationassociation.com/aviation-articles/ads-b-privacy-concerns/">ADS-B Privacy Concerns: Navigating New Challenges - E3 Aviation</a></li>

</ul>
</details>

**Tags**: `#OSINT`, `#privacy`, `#geolocation`, `#ADS-B`, `#audio analysis`

---

<a id="item-tech-news-9"></a>
### [New York Times sues Brave over alleged scraping and AI data sales](https://techcrunch.com/2026/11/02/new-york-times-and-other-outlets-sue-web-browser-brave-over-alleged-content-scraping/) ⭐️ 7.0/10

The New York Times sued Brave, alleging that the privacy-browser maker used an undisclosed crawler to scrape copyrighted news content, bypass paywalls, and sell the data to AI companies including Anthropic, Perplexity, Mistral, xAI and Cohere. The suit, filed in Manhattan federal court, seeks an injunction and damages; the New York Daily News, Chicago Tribune and other outlets filed similar suits the same day. The complaint claims Brave built an index of more than 30 billion webpages and blocked publisher ads, and Brave had not responded publicly when the report was published.

telegram · zaihuapd · Nov 3, 06:50

**「Context: privacy browser, publisher paywalls」** Brave markets itself as a privacy-focused browser, yet the index behind its search product is built by crawling the same publisher pages that subscription paywalls are meant to gate. The filings, as summarized by Reuters and The Verge, test two distinct claims at once: that the crawling fed AI training data, and that Brave&\#x27;s paywall circumvention separately harmed the outlets&\#x27; subscription businesses.

**「Impact」** The requested injunction could force Brave to change how its crawler indexes publisher pages and how it packages that material for AI customers, while the damages claim puts revenue from those data arrangements at risk.

<details><summary>References</summary>
<ul>
<li><a href="https://www.theverge.com/tech/1024588/brave-lawsuit-ai-scraping-new-york-times">The New York Times sues Brave web browser for AI scraping and...</a></li>

</ul>
</details>

**Tags**: `#AI copyright`, `#web scraping`, `#Brave browser`, `#AI training data`, `#publishing industry`

---

<a id="item-tech-news-10"></a>
### [Report: Nvidia Said to Cap Chinese Business at 49% for New Data-Center Contracts](https://www.tomshardware.com/tech-industry/data-centers/nvidia-tells-data-center-operators-to-limit-business-from-chinese-customers-with-new-global-restrictions-report-claims-allegedly-restricted-to-49-percent-of-the-total-ensuring-51-percent-are-non-chinese-outfits) ⭐️ 7.0/10

According to a Financial Times report relayed by Tom&\#x27;s Hardware, Nvidia has informally asked data-center operators worldwide to keep business from Chinese customers below 49% of new contracts, so that at least 51% comes from non-Chinese companies. The guidance reportedly applies globally and only to new and future contracts, not existing leases, and was conveyed orally by sales and regional teams without a formal document, leaving it unconfirmed. Nvidia defended current U.S. policy, saying U.S. chips underpin the global competitiveness of American model and application providers and that the policy encourages cloud providers to accept business from various regions on U.S. infrastructure.

telegram · zaihuapd · Nov 3, 16:19

**「Context」** The reported guidance is informal: it was said to be passed orally by Nvidia’s sales and regional teams, with no formal document, and it covers only new or future contracts, not existing leases. Nvidia framed the issue in terms of US policy, saying US chips underpin the global competitiveness of US model and application vendors and that current policy encourages cloud providers to accept business worldwide on US infrastructure.

**「Operational impact」** According to the report, data-center operators serving Chinese companies would need to track the Chinese share of their overall business and keep it at or below 49% when signing new contracts, while already-signed leases would not be affected. This creates a contract-level compliance and accounting burden for global operators rather than a requirement to change existing agreements.

<details><summary>References</summary>
<ul>
<li><a href="https://finance.yahoo.com/technology/ai/articles/nvidia-tells-data-center-operators-133111048.html?fr=sycsrp_catchall">Nvidia tells data center operators to limit business from ...</a></li>
<li><a href="https://www.gate.com/news/detail/NVDA/nvidia-sets-49-limit-on-chinese-data-center-customer-business-25384198">Nvidia Sets 49% Limit on Chinese Data Center Customer ...</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#China`, `#data centers`, `#AI infrastructure`, `#export controls`

---

## Financial News

<a id="item-finance-news-1"></a>
### [China Regulator Reportedly Suspends IPOs and Large Shareholder Sales to Stabilize Slumping Stocks](https://www.ft.com/content/fec5981d-0c31-4f21-9a37-a1dd1526f530) ⭐️ 8.0/10

China&\#x27;s securities regulator reportedly used &quot;window guidance&quot; to ask brokers to suspend IPOs and large shareholder stock sales until the market recovers. The intervention followed an 8.5% fall in the CSI 300 in October, its worst monthly performance in more than a decade, leaving the index down about 14% year to date.

telegram · zaihuapd · Nov 3, 08:01

**「Background」** &quot;Window guidance&quot; means informal instructions from regulators rather than published rules; the China Securities Regulatory Commission conveyed the IPO pause in meetings with investment banks, according to people familiar with the discussions. Earlier measures — state-fund buying, limits on shareholder sales, buyback financing support and a cut in the relending rate to 1% — had failed to lift the market.

**「Impact」** Companies waiting to list, including memory-chip maker Yangtze Memory, face delayed fundraising, and major shareholders are temporarily unable to sell large stakes, cutting off a key exit route for investors in China&\#x27;s equity market.

<details><summary>References</summary>
<ul>
<li><a href="https://www.ft.com/content/fec5981d-0c31-4f21-9a37-a1dd1526f530?syn-25a6b1a6=1">CSI 300 index posted worst month in more than a decade in October</a></li>
<li><a href="https://en.wikipedia.org/wiki/Yangtze_Memory_Technologies">Yangtze Memory Technologies - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#China stocks`, `#IPO suspension`, `#securities regulation`, `#CSI 300`, `#shareholder reductions`

---

<a id="item-finance-news-2"></a>
### [Anthropic&\#x27;s revised IPO filing shows $1.7 billion in quarterly personnel costs](https://www.businessinsider.com/anthropic-ipo-filing-q3-personnel-costs-2026-11) ⭐️ 7.0/10

Anthropic&\#x27;s revised S-1 filing shows personnel costs of $1.7 billion in July–September 2026 for 5,300 employees, including $1.1 billion in stock-based compensation, according to Business Insider. That works out to roughly $322,000 per employee for the quarter, or more than $100,000 a month, ahead of an IPO the report says is expected this month.

telegram · zaihuapd · Nov 3, 13:23

**「Background」** Anthropic publicly filed its initial IPO prospectus \(Form S-1\) with the US Securities and Exchange Commission on 26 October 2026, planning to list on Nasdaq under the ticker &quot;ANT&quot;. The personnel figures come from an amended S-1 in which the company added third-quarter financials.

**「What it means」** Investors considering the expected IPO would be buying into a company that, per the filing summary, still had more than $32 billion of stock-based compensation not yet recognized as of end-September, costs that would be recorded in later periods.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/02/anthropic-ant-s-1-quarter-financials.html">Anthropic releases amended IPO prospectus with Q 3 financials</a></li>
<li><a href="https://roo.beehiiv.com/p/anthropic-ipo-s-1-filing">Anthropic IPO S-1 Filing Is Public: What the Prospectus Shows</a></li>
<li><a href="https://www.businessinsider.com/anthropic-ipo-filing-q3-personnel-costs-2026-11">Anthropic Employees Cost Over $100K a Month on... - Business Insider</a></li>

</ul>
</details>

**Tags**: `#Anthropic`, `#IPO filing`, `#AI industry`, `#employee compensation`, `#stock-based compensation`

---