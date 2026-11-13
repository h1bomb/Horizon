---
layout: default
title: "Horizon Summary: 2026-11-13 (EN)"
date: 2026-11-13
lang: en
---

> From 45 items, 15 important content pieces were selected

---

**Technology News**
1. [Rust 1.100 stabilizes never type and custom allocators, adds Cargo cooldowns](#item-tech-news-1) ⭐️ 8.0/10
2. [Hacker News post alleges Jensen Huang has resigned as NVIDIA CEO](#item-tech-news-2) ⭐️ 8.0/10
3. [Anthropic IPO page lists $70–78 price range, ~$968B implied valuation](#item-tech-news-3) ⭐️ 8.0/10
4. [PostgreSQL type-confusion primitive chained into RCE in CVE-2026-6460](#item-tech-news-4) ⭐️ 8.0/10
5. [UMAP 0.6 adds recursive init, new optimizers, faster search](#item-tech-news-5) ⭐️ 8.0/10
6. [Google releases Gemini 4 Hydrogen, claims 2.5× speedup and unified pricing](#item-tech-news-6) ⭐️ 8.0/10
7. [Chips and Cheese Interviews AMD’s Mike Clark on Zen 6](#item-tech-news-7) ⭐️ 7.0/10
8. [Microsoft 365 degradation leaves some email down for hours](#item-tech-news-8) ⭐️ 7.0/10
9. [smolmaxxing publishes kernels for LLMs on sub-1GB devices](#item-tech-news-9) ⭐️ 7.0/10
10. [Reddit audit of TRIBE v2 finds motion selectivity but no retinotopy/tonotopy](#item-tech-news-10) ⭐️ 7.0/10
11. [US Commerce finalizing rule to block Chinese AI remote chip access](#item-tech-news-11) ⭐️ 7.0/10
12. [Apple details Secure Exclaves audio/video privacy and recording-indicator checks](#item-tech-news-12) ⭐️ 7.0/10

**Financial News**
1. [Fed to Skip Rate Vote at October 2027 Meeting](#item-finance-news-1) ⭐️ 7.0/10
2. [Oil prices climb after Trump says no Iran deal needed](#item-finance-news-2) ⭐️ 7.0/10
3. [礼来口服减重药在中国获批，成为国内首个口服 GLP-1](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Rust 1.100 stabilizes never type and custom allocators, adds Cargo cooldowns](https://blog.rust-lang.org/2026/11/12/Rust-1.100.0/) ⭐️ 8.0/10

Rust 1.100 stabilizes the never type and custom allocators, and adds Cargo dependency cooldowns that let the resolver ignore crate versions published more recently than a configured minimum age unless those versions are already in Cargo.lock. Cargo also begins warning about unused dependencies, with \`cargo::unused\_dependencies\` set to \`warn\` by default. The release makes \`cargo install\` use the lockfile inside the \`.crate\` tarball by default, so \`--locked\` becomes a no-op.

hackernews · mbStavola · Nov 12, 18:39 · [Discussion](https://news.ycombinator.com/item?id=50472038)

**「Context: two long-unstable features and a resolver RFC」** The never type — written \`\!\` and used for expressions such as \`panic\!\` that never produce a value — and the \`Allocator\` trait, which lets collections and smart pointers draw memory from a user-supplied allocator instead of the global one, had until now been reachable only through unstable feature gates. Cargo&\#x27;s dependency cooldowns implement RFC 3923: when the age threshold is configured, the resolver skips crate versions published more recently than that limit unless they are already recorded in \`Cargo.lock\`.

**「Impact」** Projects that configure a minimum publish age will not resolve crates newer than that threshold unless Cargo.lock already pins them, so teams get a buffer against freshly published versions at the cost of delayed access to new releases; teams relying on the setting should plan for that delay when an urgent fix lands.

**「Community discussion」** Commenters welcomed the release, and some pointed out stabilized APIs not mentioned in the post, including \`bool::toggle\(\)\`, \`Box::map\(\)\`, and \`str::trim\_prefix\(\)\`. One user questioned whether compiler speed had improved and reported needing frequent \`cargo clean\` runs to clear 90 GB of temporary files; no measured performance result was provided.

<details><summary>References</summary>
<ul>
<li><a href="https://releases.rs/docs/1.100.0/">1.100.0 | Rust Changelogs - releases.rs</a></li>
<li><a href="https://braindetox.kr/en/posts/rust_1_100_never_type_allocator.html">Rust 1.100.0: never type, Allocator API and Cargo cooldowns</a></li>

</ul>
</details>

**Tags**: `#Rust`, `#programming languages`, `#Cargo`, `#language features`, `#open source`

---

<a id="item-tech-news-2"></a>
### [Hacker News post alleges Jensen Huang has resigned as NVIDIA CEO](https://apnews.com/article/nvidia-megaspeed-china-singapore-huang-5403f152a601cf82ce939f1d24fffa0f) ⭐️ 8.0/10

A Hacker News submission posted on 12 November 2026 links to reports alleging that Jensen Huang has stepped down as NVIDIA&\#x27;s CEO, including a Reuters live page describing a board meeting over &quot;affair reports&quot; and a New York Times live page headlined &quot;Nvidia: Jensen Huang resigns.&quot; The submission itself is link-only: no NVIDIA announcement text, board vote, successor name, or effective date is included, and the cited URLs are future-dated, so the resignation could not be verified from the supplied material. The AP News link&\#x27;s URL slug references China and Singapore, hinting at the export-control angle commenters focused on, but the AP article body was not provided. Readers should treat the claim as an unconfirmed report circulating on Hacker News rather than an established fact.

hackernews · lldb · Nov 12, 13:52 · [Discussion](https://news.ycombinator.com/item?id=50467087)

**「Background」** The resignation followed congressional pressure: CNBC reported that members of Congress were calling on Huang to resign and that momentum was building to subpoena him. USA Today reported that the board acted amid a probe into his relationship with a Singapore-based tech executive whom U.S. officials suspect of spying for China, and CBS News reported that the board announced the resignation effective immediately on Thursday.

**「Interim leadership at NVIDIA」** NVIDIA&\#x27;s board announced Huang&\#x27;s resignation and named an interim president and CEO rather than a permanent successor, so cloud providers and AI developers whose capacity plans assume continuity in NVIDIA&\#x27;s GPU roadmap now face a key supplier in leadership transition. The supplied reports do not say whether existing product commitments or the company&\#x27;s export-licensing posture will change, leaving buyers to watch for board guidance before adjusting procurement.

**「Community discussion」** Several commenters accepted the resignation as fact and instead debated its cause and timing, with one asking &quot;why now?&quot; and who benefits from supplying the story to the New York Times, while another argued that a CEO&\#x27;s perceived stability matters unusually much for a company the AI economy depends on. Others disputed the affair framing, asserting that NVIDIA&\#x27;s alleged skirting of export bans is the real issue, and one commenter shared a speculative X post claiming Huang planned to push NVIDIA into frontier open models; these are commenters&\#x27; opinions and theories, not verified findings.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/11/nvidia-jensen-huang-congress-resign-ai-chips.html">Jensen Huang affair in DC: Resignation calls and moves to ...</a></li>
<li><a href="https://www.cbsnews.com/news/nvidia-ceo-jensen-huang-resigns/">Nvidia CEO Jensen Huang resigns in wake of affair with woman ...</a></li>
<li><a href="https://www.usatoday.com/story/tech/2026/11/12/jensen-huang-nvidia-ceo-resigns-affair-investigation/92734431007/">Jensen Huang resigns as Nvidia CEO amid affair probe</a></li>
<li><a href="https://www.theverge.com/ai-artificial-intelligence/1031689/jensen-huang-nvidia-ceo-resigns">Nvidia CEO Jensen Huang resigns amid spy, affair... | The Verge</a></li>
<li><a href="https://theconservativetreehouse.com/blog/2026/11/12/nvidia-board-announces-jensen-huang-resignation-interim-president-ceo-appointed/">Nvidia Board Announces Jensen Huang Resignation - Interim...</a></li>

</ul>
</details>

**Tags**: `#NVIDIA`, `#Jensen Huang`, `#AI hardware`, `#export controls`, `#Hacker News`

---

<a id="item-tech-news-3"></a>
### [Anthropic IPO page lists $70–78 price range, ~$968B implied valuation](https://ipo.anthropic.com/us/) ⭐️ 8.0/10

An Anthropic IPO page drew Hacker News attention, and a commenter summarizing the linked documents cited a $70–78 per-share price range \(roughly $74 midpoint\), an $85.3B gross deal size including a $26B private placement, and an implied market capitalization near $968B at 13.09B shares, trading as ANT on Nasdaq. The same commenter&\#x27;s reading listed Q3 2026 revenue of $17.0B, up 1,127% year over year, a run-rate of about $81B as of October 2026, and $900.9B in compute commitments through 2045. It also counted 11,900+ customers with at least $100K in trailing revenue, 1,900+ above $1M and roughly 250 above $10M, alongside about 40 million customers below $100K. These figures come from a Hacker News commenter&\#x27;s summary of the filing documents rather than independently verified reporting, and the item supplied no source content of its own.

hackernews · josephljohnston · Nov 12, 11:46 · [Discussion](https://news.ycombinator.com/item?id=50465829)

**「Background」** Anthropic has so far been funded through private venture rounds; commenters in the thread refer to Series E, F and H valuations, but those figures come from discussion rather than a verified filing. An IPO would shift the company from private backing to public shareholders, making the offer price and implied market capitalization the central points of comparison with those earlier rounds.

**「Counterparty risk for Claude buyers」** Commenters reading the filing cite $900.9 billion in compute commitments through 2045 against roughly $81 billion in run-rate revenue as of October 2026, with an implied valuation near $968 billion at the $74 midpoint of the $70–$78 price range. For organizations standardizing on Claude, the practical consequence is counterparty risk: those compute obligations are contractual and persist regardless of demand, so buyers negotiating multi-year API or enterprise agreements should weigh service continuity and future pricing leverage alongside model quality. The disclosed customer mix — roughly 250 accounts above $10M in trailing revenue versus about 40 million below $100K — also indicates that enterprise contracts, rather than individual developer usage, will drive roadmap and pricing decisions. Note that these figures come from commenters&\#x27; reading of the filing rather than independent reporting.

**「Community discussion」** Commenters questioned both the timing and the durability of the business: one argued that if Anthropic&\#x27;s models were capable of recursive self-improvement, investors would have pushed to delay the IPO for clearer market dominance instead of accepting dilution now, while another said LLM demand is easy to switch away from because most applications do not need frontier models. A third commenter contended that local models are already good enough for most users and will improve, and a fourth worried that earlier rounds such as Series H could already be underwater at the low end of the price range.

<details><summary>References</summary>
<ul>
<li><a href="https://www.gate.com/blog/gate-anthropic-ipo-valuation-subscription-and-outlook">Gate Anthropic IPO : Valuation , Subscription and Outlook | Gate Blog</a></li>

</ul>
</details>

**Tags**: `#Anthropic`, `#IPO`, `#AI industry`, `#LLM business model`, `#Hacker News`

---

<a id="item-tech-news-4"></a>
### [PostgreSQL type-confusion primitive chained into RCE in CVE-2026-6460](https://mehmetince.net/part-3-6-how-i-ended-up-turning-a-22-year-old-postgresql-type-confusion-primitive-into-rce-cve-2026-6460/) ⭐️ 8.0/10

A new technical write-up describes CVE-2026-6460, tracing a PostgreSQL type-confusion primitive back 22 years and walking through an exploit chain that turns it into remote code execution. The author presents exploit-development research rather than a vendor advisory, so the RCE claim rests on the write-up&\#x27;s chain. The main dispute in discussion is whether &quot;RCE&quot; is the right label: commenters argue the starting point appears to be an authenticated SQL or database account, making it privilege escalation in practice.

hackernews · ozirus · Nov 12, 18:22 · [Discussion](https://news.ycombinator.com/item?id=50471761)

**「Background」** PostgreSQL represents internal values as Datums whose type is tracked separately; CVE-2026-6460 stems from inadequate tracking of those typed values, letting an authenticated user who can create or alter database objects trigger type confusion through data-definition commands such as changing a column&\#x27;s data type \(tool-2-1, tool-2-3\). The write-up starts from that longstanding primitive and builds an exploit chain that reaches code execution as the operating-system user running the database.

**「Impact」** If the chain works as described, PostgreSQL operators should treat a compromised or malicious database account as a possible path to host-level execution, not as an isolated SQL privilege. Multi-tenant deployments have the clearest exposure because one tenant&\#x27;s database access could cross into the server.

**「Community discussion」** Commenters including logophobia and jmuguy argue the finding is better classified as privilege escalation than RCE, because it appears to begin with authenticated SQL or database access and matters most for multi-tenant databases. Another commenter calls PostgreSQL&\#x27;s Datum design a &quot;code reek,&quot; questioning the separation of a value that may be a pointer from its type tag.

<details><summary>References</summary>
<ul>
<li><a href="https://access.redhat.com/security/cve/cve-2026-6460">CVE-2026-6460 - Red Hat Customer Portal</a></li>
<li><a href="https://app.opencve.io/cve/CVE-2026-6460">CVE-2026-6460 - Vulnerability Details - OpenCVE</a></li>

</ul>
</details>

**Tags**: `#PostgreSQL`, `#vulnerability research`, `#type confusion`, `#CVE`, `#exploit development`

---

<a id="item-tech-news-5"></a>
### [UMAP 0.6 adds recursive init, new optimizers, faster search](https://www.reddit.com/r/MachineLearning/comments/1xudaah/umap_06_new_initialization_new_optimizers_and/) ⭐️ 8.0/10

UMAP 0.6 is released with a recursive initialization scheme, new optimizers using hard-negative mining, and nearest-neighbor search the maintainer says is about 4x faster through better use of PyNNDescent. The maintainer reports that on 3 million arXiv papers a full run finishes in under 5 minutes with the new optimizers, versus 52 minutes for a seeded UMAP 0.5 run that was single-threaded, and that seeded 0.6 runs are reproducible while using all cores. The new initialization and optimizers are said to improve million-scale cluster detail, but they are opt-in via compatibility\_layout=False because they change the output; future versions are planned to make them default.

reddit · r/MachineLearning · /u/lmcinnes · Nov 12, 13:51

**「Background」** UMAP is a dimensionality-reduction library that lays out high-dimensional data in a lower-dimensional space. The previous 0.5 release used spectral or PCA initialization, and a seeded 0.5 run was single-threaded. UMAP 0.6 replaces both the initialization and optimizer, but the new path is opt-in via compatibility\_layout=False because it changes the output.

**「Impact」** Users who need stable existing layouts should keep the default compatibility behavior and test before enabling compatibility\_layout=False; those who opt in should expect different embeddings and are being asked to report results before the new behavior becomes the default.

**Tags**: `#UMAP`, `#dimensionality reduction`, `#machine learning`, `#open source`, `#performance optimization`

---

<a id="item-tech-news-6"></a>
### [Google releases Gemini 4 Hydrogen, claims 2.5× speedup and unified pricing](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-hydrogen/) ⭐️ 8.0/10

Google released Gemini 4 Hydrogen, a model aimed at fast execution for everyday coding and agent workflows, according to a Telegram brief; it is described as available to developers, enterprises, and general users. The brief lists unified pricing of $1.50 per million input tokens and $7.50 per million output tokens. It also claims a 2.5× speedup over Gemini 3.8 Flash, raising Terminal-Bench 4.1 from 18.2% to 57%, and says the default tier beats Argon on the Artificial Analysis index. These figures come from the release brief and have not been independently verified in the supplied material.

telegram · zaihuapd · Nov 13, 02:02

**「Background」** Gemini 3.8 Flash is the prior fast tier against which the brief measures Hydrogen; the reported Terminal-Bench 4.1 jump from 18.2% to 57% is the comparison presented in the brief, not an independent result. A separate report says Google&\#x27;s Orchestrator combines Carbon&\#x27;s reasoning with Hydrogen&\#x27;s faster execution and uses 24% less quota, indicating Hydrogen is positioned as an execution layer in a two-model setup.

**「Impact」** For coding-agent users, the claimed Terminal-Bench 4.1 increase from 18.2% to 57% is the relevant operational change, but the brief does not specify the harness, attempts, or task subset behind the score. Teams should treat the benchmark and speed figures as vendor claims until they can reproduce them in their own workflows.

**「Community discussion」** Commenters questioned the “Hydrogen” naming after it appeared in place of Gemini 3.8 Flash, and one argued that the listed pricing is higher than current discounted 3.8 Flash or 3.5 Flash Lite rates, making the entry-level positioning unclear. Those are user interpretations, not confirmed details from Google.

<details><summary>References</summary>
<ul>
<li><a href="https://interestingengineering.com/ai-robotics/google-gemini-4-hydrogen-coding-benchmark">Google launches Gemini 4 Hydrogen for faster coding and agentic...</a></li>

</ul>
</details>

**Tags**: `#Google Gemini`, `#AI model release`, `#LLM pricing`, `#agentic coding`, `#benchmarks`

---

<a id="item-tech-news-7"></a>
### [Chips and Cheese Interviews AMD’s Mike Clark on Zen 6](https://chipsandcheese.com/p/talking-zen-6-with-mike-clark-at) ⭐️ 7.0/10

Chips and Cheese has published an in-depth interview with AMD’s Mike Clark about Zen 6, aimed at hardware and systems readers who follow CPU architecture. The item is presented as a technical conversation with an AMD designer, not as a product launch or specification disclosure. The supplied material does not include Zen 6 core configurations, process node, performance claims, compatibility details, or a release date.

hackernews · dverlaeckt80 · Nov 12, 14:12 · [Discussion](https://news.ycombinator.com/item?id=50467460)

**「Background」** Zen 6 is AMD&\#x27;s next-generation CPU core, and it has already been announced as the basis of the EPYC Embedded 9006 line, which AMD describes as scaling to 256 cores with PCIe Gen 6 and CXL 3.1 connectivity. Clark and AMD corporate vice president Madhu Rangarajan have separately told media that Zen 6 was not designed specifically for agentic AI, a response to Nvidia and Arm describing their Vera and AGI data-center CPUs as purpose-built for that workload — context that makes a design-focused interview with Clark a useful check on how AMD is framing the architecture&\#x27;s priorities.

**「Community Discussion」** One Hacker News commenter praised the article for the rare depth of access to a CPU designer, calling such detailed discussions uncommon.

<details><summary>References</summary>
<ul>
<li><a href="https://www.techpowerup.com/news-tags/AMD">News Posts matching &#x27; AMD &#x27; | TechPowerUp</a></li>
<li><a href="https://mezha.net/eng/news/mezha-385a51640a816c08fe1be1d3_amd_executives_say/">AMD executives say Zen 6 was not designed specifically for... | Межа</a></li>

</ul>
</details>

**Tags**: `#AMD Zen 6`, `#CPU architecture`, `#semiconductors`, `#hardware engineering`, `#technical interview`

---

<a id="item-tech-news-8"></a>
### [Microsoft 365 degradation leaves some email down for hours](https://status.cloud.microsoft/) ⭐️ 7.0/10

On Nov. 12, Microsoft 365 users reported a service degradation that left email unavailable for hours for some organizations. Status updates relayed in the discussion said Microsoft had validated an alternative health check on a subset of affected infrastructure and was applying it more broadly; a later 10 p.m. ET update said the change was not taking as expected. Commenters reported email down for 5.5 to 8 hours—including one organization with more than 15,000 employees—while Teams chat and meetings and Azure infrastructure appeared unaffected.

hackernews · dkpk · Nov 12, 18:20 · [Discussion](https://news.ycombinator.com/item?id=50471731)

**「Background」** Microsoft&\#x27;s service health dashboard at status.cloud.microsoft is the vendor&\#x27;s official channel for posting incident updates, and it offers an RSS feed for subscribers. During this event, a commenter reported that the status page itself was not working well but that the RSS feed continued to publish periodic updates, which helps explain why the linked status page is central to tracking the incident.

**「Impact」** For affected organizations, the outage meant multi-hour loss of work email—one commenter cited more than 15,000 employees—while Teams remained usable as a coordination fallback; the status page was itself unreliable enough that one administrator relied on its RSS feed for updates.

**「Community discussion」** Commenters described an unusually long outage—one said it was the worst for their organization since adopting Microsoft 365 in 2019—and reported that email was down while Teams and Azure kept working. Another commenter blamed Microsoft&\#x27;s AI investment for broad reliability problems across GitHub, Xbox, Azure, and other services, an opinion not supported by the outage details in the thread.

**Tags**: `#Microsoft 365`, `#service outage`, `#cloud reliability`, `#incident response`

---

<a id="item-tech-news-9"></a>
### [smolmaxxing publishes kernels for LLMs on sub-1GB devices](https://github.com/hyperionaidev/smolmaxxing/) ⭐️ 7.0/10

The open-source smolmaxxing project has published custom kernels and modified model weights aimed at running LLMs on devices with less than 1GB of usable memory. Its author reports reaching 16B-parameter models on a first-generation iPad Air and a Xiaomi TV box, claiming &quot;decent speeds&quot; but providing no benchmark numbers in the supplied material. The work is offered for reproduction through GitHub and Hugging Face, but the memory, speed, and compatibility claims have not been independently verified here.

hackernews · mrashad74 · Nov 12, 15:23 · [Discussion](https://news.ycombinator.com/item?id=50468888)

**「Why low-memory inference is hard」** Running an 8B or 16B model normally means holding its weights in RAM or VRAM, which puts sub-1GB devices out of reach. The smolmaxxing project instead keeps only part of each mixture-of-experts model resident and reads the remainder from flash as needed, trading storage I/O for memory capacity.

**「Impact」** Developers experimenting with local inference on old or memory-constrained hardware can inspect and try to reproduce the kernels and modified models, but should treat the 16B-on-sub-1GB result as an author-reported demonstration until independent benchmarks and supported-device details are available.

**「Community discussion」** Commenters welcomed the trend toward smaller and more optimized local models, with one describing progress from a fine-tuned Qwen 2.5 0.5B model to a locally trained 6.5M-parameter model that handles reasoning and math, and another expressing interest in running agentic workloads on older Maxwell and Pascal GPUs. One commenter argued that modern coding agents can already generate much of an inference engine, making access to old hardware the harder constraint; that is an opinion, not a measured result from the project.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/hyperionaidev/smolmaxxing/">GitHub - hyperionaidev / smolmaxxing : maxxing the ability to run...</a></li>

</ul>
</details>

**Tags**: `#local LLMs`, `#edge inference`, `#model optimization`, `#open source`, `#low-memory hardware`

---

<a id="item-tech-news-10"></a>
### [Reddit audit of TRIBE v2 finds motion selectivity but no retinotopy/tonotopy](https://www.reddit.com/r/MachineLearning/comments/1xuillf/does_metas_brainresponse_model_tribe_v2_actually/) ⭐️ 7.0/10

A researcher on Reddit reports running classic retinotopy, tonotopy, and motion-localizer stimuli through Meta&\#x27;s TRIBE v2 fMRI prediction model and fitting standard topographic models. They report no significant retinotopic map \(d=0.05\) or tonotopic map \(ρ=-0.07, even with loudness controlled\), but strong motion selectivity in MT+ \(d=4.31, 52× enrichment over chance\). An eccentricity effect became significant and &quot;correct&quot; only under three stimulus-geometry controls, which the author interprets as an image-statistics confound rather than a positional code. The work is a self-funded solo project posted with code and a paper link, not peer-reviewed; according to the post, TRIBE v2&\#x27;s own paper did not test these topographic maps.

reddit · r/MachineLearning · /u/Own\_Tank1283 · Nov 12, 17:16

**「Background」** Meta released TRIBE v2 on March 26, 2026, as a deep multimodal brain-encoding model that predicts fMRI responses to video, audio, and text by mapping text, audio, and video representations onto the cortical surface; Meta published the model, codebase, paper, and a demo. The Reddit audit tests whether that naturalistic-stimulus model also reproduces classical topographic maps—retinotopy for visual-field position and tonotopy for sound frequency—using standard mapping stimuli.

**「Evaluation implication」** For researchers using TRIBE v2 as a brain-encoding model, the reported results argue against treating its predictions as a readout of retinotopic or tonotopic organization without synthetic ground-truth checks and stimulus-geometry controls; MT+ motion selectivity is the one reported topographic signature that survived.

<details><summary>References</summary>
<ul>
<li><a href="https://ai.meta.com/blog/tribe-v2-brain-predictive-foundation-model/">Introducing TRIBE v2: A Predictive Foundation Model Trained ...</a></li>
<li><a href="https://github.com/facebookresearch/tribev2">GitHub - facebookresearch/tribev2: This repository contains ...</a></li>

</ul>
</details>

**Tags**: `#TRIBE v2`, `#fMRI decoding`, `#model evaluation`, `#retinotopy`, `#neuroAI`

---

<a id="item-tech-news-11"></a>
### [US Commerce finalizing rule to block Chinese AI remote chip access](https://www.theinformation.com/articles/commerce-department-finalizing-long-awaited-ai-remote-access-rule) ⭐️ 7.0/10

The US Commerce Department is finalizing a rule that would bar Chinese AI companies from remotely using advanced AI chips through data centers outside China, according to The Information. The measure would extend existing semiconductor export restrictions to seven countries, including Malaysia, Singapore and Thailand, to close remote-access and smuggling gaps. Commerce is consulting other agencies and could publish the rule as soon as this month, but the report gives no rule text, effective date or exemption details. Nvidia reportedly lobbied against closing the remote-access gap, arguing that US AI infrastructure needs to win globally.

telegram · zaihuapd · Nov 12, 03:42

**「Background」** The rule is aimed at a gap left after Commerce rescinded the Biden-era &quot;know your customer&quot; requirement; an August 2026 report said data centers in Thailand, Singapore, Malaysia and Japan were then free to provision Nvidia GPU access without verifying the ultimate user. Commerce now plans to add Singapore, Malaysia and five other countries to a license list that requires end-user reporting, extending existing BIS semiconductor controls.

**「Impact」** For Chinese AI developers that rely on overseas data centers, and for operators in the seven newly covered countries, the rule could turn a previously indirect route to advanced compute into a compliance risk; until Commerce publishes the text, they cannot determine which services, entities or chips are covered or when obligations begin.

<details><summary>References</summary>
<ul>
<li><a href="https://www.techtimes.com/articles/325957/20260829/commerce-drafts-ai-chip-rule-loophole-it-created-rescinding-biden-know-your-customer.htm">Commerce Drafts AI Chip Rule for Loophole It Created by ...</a></li>
<li><a href="https://biz.chosun.com/en/en-international/2026/11/12/M2ICNVHJPVCFLJDLAGG5IP4VDE/">US to widen AI chip export controls to seven nations, curb ...</a></li>

</ul>
</details>

**Tags**: `#出口管制`, `#AI芯片`, `#半导体供应链`, `#美中科技政策`, `#数据中心`

---

<a id="item-tech-news-12"></a>
### [Apple details Secure Exclaves audio/video privacy and recording-indicator checks](https://security.apple.com/blog/secure-exclaves/) ⭐️ 7.0/10

Apple published a Nov. 12 explainer on Secure Exclaves, an isolated security environment that processes audio and video so the main system and apps in ambient-sensing modes receive only the recognition results they need rather than raw data. Apple says the architecture is used in HomeView&\#x27;s face and sound recognition and in the iPhone 18 Pro privacy indicator. On the iPhone 18 Pro, Apple says dedicated hardware verifies the microphone dot&\#x27;s color, brightness, and visibility before audio can enter the main system, and that relevant Siri audio sessions must keep the dot displayed for at least three seconds. These are Apple&\#x27;s described mechanisms; the supplied report does not include independent verification or API-level details.

telegram · zaihuapd · Nov 12, 09:13

**「Background」** Apple&\#x27;s Secure Enclave is a separate, hardware-isolated processor that handles sensitive data such as biometrics outside the main operating system. Secure Exclaves apply that isolation model to sensor pipelines: audio and video are processed inside a hardware compartment built into the silicon, separately from the rest of the system, so raw feeds are never exposed to the main OS. Apple has already used exclaves for Audio Intelligence on Apple Watch&\#x27;s S11 chip and for HomeView, which identifies up to six people in a home and also protects the device&\#x27;s camera LED indicator.

**「Impact」** For iPhone 18 Pro users, the microphone indicator is described as an enforcement condition rather than only a warning: if the hardware check does not confirm the dot is visible, audio is not allowed into the main system.

<details><summary>References</summary>
<ul>
<li><a href="https://www.macrumors.com/">MacRumors: Apple News and Rumors</a></li>
<li><a href="https://support.apple.com/en-us/148354">About Audio Intelligence features on Apple Watch... - Apple Support</a></li>

</ul>
</details>

**Tags**: `#Apple`, `#security architecture`, `#privacy`, `#secure enclaves`, `#audio/video`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Fed to Skip Rate Vote at October 2027 Meeting](https://www.cnbc.com/2026/11/12/in-policy-switch-fed-says-its-october-2027-meeting-will-not-see-a-vote-on-interest-rates.html) ⭐️ 7.0/10

The Federal Reserve, under Chairman Kevin Warsh, said its Oct. 26-27, 2027, meeting will be a nonvoting strategy session, reducing 2027 to seven rate-voting meetings from the usual eight. The change is part of a communication overhaul that has already shortened post-meeting statements and press briefings.

rss · CNBC Finance · Nov 12, 19:05

**「Background」** The Fed typically holds eight policy meetings a year, each ending in an interest-rate vote, a statement and a chair’s news conference. The October 2027 change is part of Chairman Kevin Warsh’s broader effort to shorten those communications, which he has said can constrain policymakers before decisions are made.

**「Impact」** Investors and businesses that rely on the Fed&\#x27;s post-meeting statements to gauge the path of interest rates will get one fewer voting decision in 2027 and no statement after the Oct. 26-27, 2027 session—a gap that New York Fed research links to wider errors in market-implied policy expectations.

<details><summary>References</summary>
<ul>
<li><a href="https://tradersunion.com/news/regulators/show/4220251-fed-october-2027-meeting-nonvoting/">Federal Reserve to make October 2027 meeting nonvoting as ...</a></li>
<li><a href="https://www.nytimes.com/2026/11/12/business/economy/fed-warsh-october.html">Fed Will Not Hold Policy Vote at October 2027 Meeting</a></li>
<li><a href="https://www.newyorkfed.org/medialibrary/media/research/staff_reports/sr1081.pdf">Fed Transparency and Policy Expectation Errors: A Text ...</a></li>
<li><a href="https://www.newyorkfed.org/research/staff_reports/sr1081">Fed Transparency and Policy Expectation Errors: A Text ...</a></li>
<li><a href="https://www.federalreserve.gov/monetarypolicy/fomc.htm">The Fed - Federal Open Market Committee - Federal Reserve Board FOMC Policy on External Communications of Committee ... Fed designated October 2027 as its first no-vote strategy meeting Voting Right Rotation, Behavior of Committee Members and ... Voting Right Rotation, Behavior of Committee Members and ...</a></li>

</ul>
</details>

**Tags**: `#Federal Reserve`, `#monetary policy`, `#FOMC`, `#central bank communication`, `#meeting schedule`

---

<a id="item-finance-news-2"></a>
### [Oil prices climb after Trump says no Iran deal needed](https://www.cnbc.com/2026/11/12/oil-prices-jump-after-trump-says-no-iran-deal-needed-weve-got-their-strait.html) ⭐️ 7.0/10

Brent crude settled 3.3% higher at $95.82 a barrel and West Texas Intermediate rose 2.6% to $88.74 on Thursday, after President Donald Trump said in a Truth Social post that the U.S. does not need a deal with Iran and claimed, &quot;We&\#x27;ve got their Strait\!&quot;

rss · CNBC Finance · Nov 13, 00:01

**「Background」** The Strait of Hormuz is the Gulf’s main oil export route: in 2024 about 20 million barrels a day passed through it—roughly a fifth of global petroleum liquids consumption—and there are few alternative routes, so threats to shipping there can quickly affect crude prices.

**「Impact」** Oil consumers and shipping operators face higher costs if the security premium persists: analysts cited high insurance and tanker rates already keeping longer-dated contracts elevated and warned that renewed attacks on shipping could prolong supply disruptions.

<details><summary>References</summary>
<ul>
<li><a href="https://www.eia.gov/todayinenergy/detail.php?id=65504">Amid regional conflict, the Strait of Hormuz remains critical oil ...</a></li>
<li><a href="https://www.iea.org/about/oil-security-and-emergency-response/strait-of-hormuz">Strait of Hormuz - About - IEA</a></li>

</ul>
</details>

**Tags**: `#oil prices`, `#Iran`, `#Strait of Hormuz`, `#geopolitical risk`, `#energy markets`

---

<a id="item-finance-news-3"></a>
### [礼来口服减重药在中国获批，成为国内首个口服 GLP-1](https://www.reuters.com/business/healthcare-pharmaceuticals/china-approves-eli-lillys-weight-loss-pill-orforglipron-2026-11-12/) ⭐️ 7.0/10

中国国家药品监督管理局于11月12日批准了礼来公司的每日一次口服 GLP-1 减重药奥氟格列隆钙片（商品名穆优达），使其成为国内首个获批用于肥胖或超重且伴有至少一种体重相关合并症的成人的口服 GLP-1 疗法；礼来未公布价格和上市时间，且该药的 2 型糖尿病适应证仍在审评中。

telegram · zaihuapd · Nov 12, 10:09

**「Background」** Orforglipron is a non-peptide, small-molecule GLP-1 receptor agonist — a pill version of the gut-hormone drugs that until now have reached Chinese obesity patients mainly as weekly injections — developed by Eli Lilly as a weight-loss treatment.

**「Who is affected」** For Chinese adults who are obese or overweight with at least one weight-related condition, the approval adds a once-daily oral option alongside the weekly injections already sold by Novo Nordisk, Pfizer and Innovent, offering a treatment that does not require an injection — though with price and launch date undisclosed, patient cost remains unknown.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Orforglipron">Orforglipron - Wikipedia</a></li>
<li><a href="https://www.reuters.com/business/healthcare-pharmaceuticals/china-approves-eli-lillys-weight-loss-pill-orforglipron-2026-11-12/">Eli Lilly becomes first drugmaker to have a GLP-1 weight-loss ...</a></li>
<li><a href="https://www.pharmaceutical-technology.com/news/eli-lilly-oral-glp1-ra-foundayo-nmpa-approval-weight-management/">Eli Lilly beats Novo to oral China GLP-1RA market on NMPA ...</a></li>

</ul>
</details>

**Tags**: `#pharmaceutical regulation`, `#GLP-1`, `#Eli Lilly`, `#China healthcare`, `#obesity treatment`

---