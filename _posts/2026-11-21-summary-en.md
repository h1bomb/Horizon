---
layout: default
title: "Horizon Summary: 2026-11-21 (EN)"
date: 2026-11-21
lang: en
---

> From 39 items, 15 important content pieces were selected

---

**Technology News**
1. [Inkling 2 Mini: open-weight small model uses looped transformer](#item-tech-news-1) ⭐️ 8.0/10
2. [Alessandro Masullo&\#x27;s proposed GRH proof announced for expert review](#item-tech-news-2) ⭐️ 8.0/10
3. [KVM CVE-2026-99312 lets VMs read AMD host memory](#item-tech-news-3) ⭐️ 8.0/10
4. [TSMC reportedly halts 16nm-and-below orders from Chinese firms](#item-tech-news-4) ⭐️ 8.0/10
5. [Levent Alpöge claims proof of Generalized Riemann Hypothesis](#item-tech-news-5) ⭐️ 7.0/10
6. [Terry Tao Links Unforced Navier–Stokes Singularities to the Generalized Riemann Hypothesis](#item-tech-news-6) ⭐️ 7.0/10
7. [arXiv Paper Claims LLMs Can Rewrite Their Own Weights](#item-tech-news-7) ⭐️ 7.0/10
8. [Aaronson Blog Examines Claims of AI Mathematical Breakthroughs](#item-tech-news-8) ⭐️ 7.0/10
9. [Signal outlines limits on AI agents capturing mobile data](#item-tech-news-9) ⭐️ 7.0/10
10. [US Tightens Chip Exports; India Sees AI Compute Opening](#item-tech-news-10) ⭐️ 7.0/10
11. [OpenAI API adds background mode with 2h/8h windows and token discounts](#item-tech-news-11) ⭐️ 7.0/10

**Technology Blog**
1. [Why Caching Visible LLM Outputs Saves Little](#item-tech-blog-1) ⭐️ 6.0/10

**Financial News**
1. [U.S. companies switch from buybacks to net share issuance](#item-finance-news-1) ⭐️ 8.0/10
2. [Fed officials speak more as Warsh avoids rate guidance](#item-finance-news-2) ⭐️ 7.0/10
3. [Beijing Draft Lease Rules Would Bar Deposit Deductions for Normal Wear and Tear](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Inkling 2 Mini: open-weight small model uses looped transformer](https://thinkingmachines.ai/news/inkling-2-mini/) ⭐️ 8.0/10

Thinking Machines has released Inkling 2 Mini, an open-weight small model that uses a looped transformer architecture. The release is positioned for local use, with commenters reporting it runs through llama.cpp: one measured about 27 tokens/s decoding on a Ryzen 395 with Vulkan, and another about 10 tokens/s on a 32GB M1 Pro using q4 xl quantization. Benchmark claims circulating with the release put it near a model referred to as Qwen3.8-27B, but those results have not been independently verified in the supplied material. Local users also note unmerged llama.cpp pull requests and a small patch that one report says gives roughly a 30% speed boost.

hackernews · jasondavies · Nov 20, 20:12 · [Discussion](https://news.ycombinator.com/item?id=50581260)

**「Prior context」** Thinking Machines&\#x27; announcement describes a looped transformer as one that runs the middle layers of the model three times for every token, a design meant to buy more reasoning per token rather than more parameters. The release follows Inkling 2 Small, which the lab announced on November 5, 2026, and positioned as an improvement on the earlier Inkling Small while still trailing the open-weight frontier on agentic cyber benchmarks. Artificial Analysis lists Inkling 2 Mini as a 26B-total, 5.4B-active mixture-of-experts model.

**「Local inference caveats」** For local users, the practical path is not plug-and-play: one commenter reports about 27 tokens/s decode on a Ryzen 395 with llama.cpp Vulkan, while noting several unmerged PRs \(32694, 32657, 32429, 32704\) and a small patch claimed to add roughly 30% speed; another reports about 10 tokens/s on a 32GB M1 Pro at q4. That makes patch tracking and backend choice a compatibility concern for anyone expecting the model&\#x27;s benchmark positioning to translate directly to out-of-the-box throughput.

**「Community discussion」** Commenters reacted positively but conditionally: one called the benchmark results “bonkers good if these benchmarks hold up in real-world scenarios,” while another reported promising quick coding tests with llama.cpp. Firsthand speed reports ranged from about 27 tokens/s on a Ryzen 395 with Vulkan to about 10 tokens/s on a 32GB M1 Pro, with one user saying an additional small patch yielded roughly a 30% speed boost.

<details><summary>References</summary>
<ul>
<li><a href="https://thinkingmachines.ai/news/inkling-2-mini/">Introducing Inkling 2 Mini - Thinking Machines Lab</a></li>
<li><a href="https://artificialanalysis.ai/articles/inkling-2-mini">Thinking Machines has released Inkling 2 Mini, an open ...</a></li>
<li><a href="https://thinkingmachines.ai/news/inkling-2-small/">Introducing Inkling 2 Small - Thinking Machines Lab</a></li>

</ul>
</details>

**Tags**: `#open-weight models`, `#looped transformers`, `#local LLM inference`, `#llama.cpp`, `#model release`

---

<a id="item-tech-news-2"></a>
### [Alessandro Masullo&\#x27;s proposed GRH proof announced for expert review](https://simonwillison.net/2026/Nov/20/ravi-vakil/) ⭐️ 8.0/10

Ravi Vakil announced that Alessandro Masullo has a proposed proof of the Generalized Riemann Hypothesis and that the current draft is being put out now rather than after further polishing. Vakil says Brian Conrad has examined it closely for months and provided extensive feedback that is being incorporated, and that the work is &quot;so far looking good.&quot; He also states that the work is entirely human, with no AI. The announcement does not present a verified proof; it releases a draft for mathematicians to scrutinize.

rss · Simon Willison · Nov 20, 19:21

**「What the GRH claims」** The Generalized Riemann Hypothesis extends the original Riemann Hypothesis — that every non-trivial zero of the Riemann zeta function has real part 1/2 — to a broader family of L-functions, and many results in number theory hold only conditionally on it. Masullo&\#x27;s draft, titled The Music of the Primes, runs roughly 940 pages and took about 12 years to assemble, which helps explain why checking it is a lengthy process.

**「Still conditional」** Number theorists weighing GRH-conditional results should continue to treat them as conditional: Vakil says the draft is still incorporating extensive feedback and is being released before the planned polishing and circulation, so the proof has not been independently verified.

<details><summary>References</summary>
<ul>
<li><a href="https://xenospectrum.com/en/masullo-riemann-proof-draft-release/">Draft Proof of the Generalized Riemann Hypothesis, 12 Years ...</a></li>

</ul>
</details>

**Tags**: `#mathematics`, `#Generalized Riemann Hypothesis`, `#proof verification`, `#research announcement`

---

<a id="item-tech-news-3"></a>
### [KVM CVE-2026-99312 lets VMs read AMD host memory](https://thehackernews.com/2026/11/new-linux-kvm-flaw-cve-2026-99312-lets.html) ⭐️ 8.0/10

A Linux KVM vulnerability, CVE-2026-99312, allows a guest to read host memory on AMD systems when nested virtualization is enabled, according to The Hacker News. Researchers reported reading about 127 GB of host memory from inside a virtual machine on DigitalOcean. An upstream fix shipped on November 18 in stable kernel 7.3.5 and related releases, but Debian, Ubuntu, and other distribution kernels remain unpatched, the report says. Until patches arrive, affected operators can disable nested virtualization.

telegram · zaihuapd · Nov 20, 14:23

**「Background」** KVM is the hypervisor built into the Linux kernel, and nested virtualization — letting a guest VM run its own hypervisor — requires KVM to emulate AMD&\#x27;s virtualization extensions for that guest. CVE-2026-99312 is a stale-pointer bug in that nested path; Terra Security reports it had been in the kernel for just under four years, introduced by an earlier security fix, and DigitalOcean notes it only affects AMD hosts with nested virtualization enabled.

**「Impact」** Operators running AMD hosts with nested virtualization on affected Debian or Ubuntu kernels should disable nested virtualization or restrict untrusted guests until their distribution ships the fix; installing upstream kernel 7.3.5 does not by itself patch a distribution kernel.

<details><summary>References</summary>
<ul>
<li><a href="https://www.digitalocean.com/blog/cve-2026-99312-kvm-patch">Virtualization , Responsible Disclosure, and CVE - 2026 - 99312</a></li>
<li><a href="https://www.terra.security/blog/kvm-guest-to-host-escape">KVM Guest-to-Host Escape | Terra Security Research</a></li>

</ul>
</details>

**Tags**: `#KVM`, `#Linux内核`, `#CVE-2026-99312`, `#AMD`, `#虚拟化安全`

---

<a id="item-tech-news-4"></a>
### [TSMC reportedly halts 16nm-and-below orders from Chinese firms](https://appleinsider.com/articles/26/11/20/apple-supplier-tsmc-cuts-off-china-chip-orders-amid-tighter-export-controls) ⭐️ 8.0/10

TSMC has reportedly paused orders from Chinese companies for 16nm-and-below chips and told customers that supplying them now requires a prior U.S. export license or exemption under tightened U.S. semiconductor rules. The report says Chinese firms are consequently limited to older 28nm and 40nm processes and cannot obtain the high-bandwidth memory used in AI data centers. Previously TSMC could assess exemption eligibility itself; customers must now apply in advance, and the U.S. approved list includes Apple, AMD and Nvidia but no Chinese companies. TSMC said it will comply with the new rules.

telegram · zaihuapd · Nov 21, 02:01

**「Background」** The move follows a change in how U.S. export exemptions are handled: TSMC previously could assess whether a Chinese customer’s design qualified, but under the tightened rules customers must obtain U.S. approval or an exemption before shipment. TrendForce separately reported that TSMC and Samsung had paused some shipments to Chinese customers under the new controls, with effects potentially reaching consumer chips as well as AI processors.

**「Impact」** Chinese chip designers needing 16nm or below would need to secure a U.S. license or shift to 28nm/40nm; the report says no Chinese company is on the U.S. approved list, leaving AI data-center HBM access constrained.

<details><summary>References</summary>
<ul>
<li><a href="https://www.trendforce.com/news/2026/11/20/news-tsmc-samsung-reportedly-pause-china-consumer-chip-shipments-under-new-u-s-rules-16nm-orders-affected/">[News] TSMC , Samsung Reportedly Pause China Consumer Chip...</a></li>

</ul>
</details>

**Tags**: `#semiconductors`, `#TSMC`, `#export controls`, `#AI hardware`, `#China tech`

---

<a id="item-tech-news-5"></a>
### [Levent Alpöge claims proof of Generalized Riemann Hypothesis](https://alpo.ge/remark.pdf) ⭐️ 7.0/10

Levent Alpöge, described in the supplied account as an Anthropic mathematician, has posted a personal PDF claiming a proof of the Generalized Riemann Hypothesis and says the argument was encoded in Lean with help from Claude. The account describes a manuscript exceeding 250,000 pages; commenters report a roughly 1.3 GB Lean archive containing about 15 million lines. The claim has not been independently confirmed, and commenters link both a purported separate human proof and verification work that was still in progress.

hackernews · iamronaldo · Nov 20, 14:16 · [Discussion](https://news.ycombinator.com/item?id=50574968)

**「Background」** The Riemann Hypothesis, posed by Bernhard Riemann in 1859, conjectures that every nontrivial zero of the Riemann zeta function lies on the line with real part 1/2, which would pin down key features of prime distribution. The Generalized Riemann Hypothesis extends that assertion to Dirichlet L-functions and related zeta functions. Lean is a proof assistant that mechanically checks each step of a formal proof, so a completed Lean development is intended to be machine-verifiable in a way that a PDF argument alone is not.

**「Who bears the verification burden」** If it holds, mathematicians would gain the generalized Riemann hypothesis, which extends Riemann&\#x27;s conjecture to a much wider class of functions tied to the primes and underpins results on primes in arithmetic progressions. The immediate burden falls on anyone trying to check the claim: the Lean artifact is described in discussion as roughly 1.3 GB and about 15 million lines, so independent verification demands substantial compute and Lean expertise before any downstream theorem can be treated as established.

**「Community discussion」** One commenter argued that multiple formal-verification routes left “no doubt” the proof is correct, while others pointed to a purported separate human proof and quoted Terence Tao’s earlier skepticism that current AI systems could solve the problem. Reported checks by Andrew Sutherland using Claude Code were still running when the linked page was last updated.

<details><summary>References</summary>
<ul>
<li><a href="https://www.unite.ai/levent-alpoges-unverified-riemann-claim-puts-claudes-lean-code-in-focus/">Levent Alpöge’s Unverified Riemann Claim Puts Claude’s Lean ...</a></li>
<li><a href="https://explainx.ai/blog/levent-alpoge-anthropic-riemann-hypothesis-claude-lean-proof-claimed-vs-verified-2026">Riemann Hypothesis Proof Claim: Claimed vs Verified ...</a></li>
<li><a href="https://en.wikipedia.org/wiki/Generalized_Riemann_hypothesis">Generalized Riemann hypothesis - Wikipedia</a></li>
<li><a href="https://www.scientificamerican.com/article/what-the-riemann-hypothesis-proof-really-means-about-ai-and-the-future/">What the Riemann hypothesis proof really... | Scientific American</a></li>

</ul>
</details>

**Tags**: `#Riemann Hypothesis`, `#formal verification`, `#Lean`, `#mathematics`, `#AI theorem proving`

---

<a id="item-tech-news-6"></a>
### [Terry Tao Links Unforced Navier–Stokes Singularities to the Generalized Riemann Hypothesis](https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/) ⭐️ 7.0/10

Terry Tao has published a blog post, dated November 20, titled &quot;Unforced Euler Singularity, Unforced Navier–Stokes Singularity, and the Generalized Riemann Hypothesis,&quot; connecting unforced singularity constructions in the Euler and Navier–Stokes equations with the Generalized Riemann Hypothesis. The supplied material includes only the title and URL, not the post body, so the precise statement, whether a new theorem is claimed, and how the two subjects are linked cannot be confirmed here. The Hacker News thread treated the post as consequential and focused on formal proof verification and on what AI-driven proof generation means for mathematical research.

hackernews · archon1410 · Nov 20, 17:21 · [Discussion](https://news.ycombinator.com/item?id=50578358)

**「Background」** The Navier–Stokes existence and smoothness problem asks whether smooth initial data for the three-dimensional incompressible Navier–Stokes equations can evolve into a singularity in finite time or whether solutions remain smooth; it is a Clay Millennium Prize problem with a $1 million award. Terence Tao&\#x27;s post examines “unforced” singularity versions of the problem and links them to the Generalized Riemann Hypothesis.

**「Community Discussion」** Commenters debated whether AI systems that are effective at recombining existing abstractions, such as the Langlands program, can also create new mathematical concepts, and several described anxiety about the future of human research careers. One commenter reported that two independent kernels accept a formalized result, arguing this makes a kernel bug an unlikely explanation — a community claim about machine-checking, not independent mathematical review.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_existence_and_smoothness">Navier – Stokes existence and smoothness - Wikipedia</a></li>
<li><a href="https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/">Unforced Euler singularity , unforced Navier - Stokes singularity , and...</a></li>
<li><a href="https://www.youtube.com/watch?v=9gcTWy2pNFU">$1 million dollar unsolved math problem: Navier – Stokes singularity ...</a></li>

</ul>
</details>

**Tags**: `#mathematics`, `#Navier-Stokes`, `#Generalized Riemann Hypothesis`, `#formal verification`, `#theorem proving`

---

<a id="item-tech-news-7"></a>
### [arXiv Paper Claims LLMs Can Rewrite Their Own Weights](https://arxiv.org/abs/2611.21885) ⭐️ 7.0/10

An arXiv preprint titled “Language Models Can Rewrite Their Own Weights” claims a model can edit its own weights through its own reasoning, without gradients or training, according to an abstract quoted in the Hacker News discussion. That quoted abstract says the model tests edits on practice problems, submits only working ones, and improves accuracy across eight consecutive sessions; the submission provides no paper text, so these claims are not independently verified here. Commenters note the demonstrated self-improvement was narrow—shortening reasoning traces to avoid a token limit—and compare it with prior weight-space programming and Google’s “sleep” work.

hackernews · lwhsiao · Nov 20, 16:29 · [Discussion](https://news.ycombinator.com/item?id=50577265)

**「Background」** Conventionally, a language model is trained once and then frozen: making it better requires another training run, or a prompt, harness, or extra inference-time computation that disappears when the task ends. The arXiv preprint proposes a third route it calls &quot;self-rewriting,&quot; in which the model acts as its own optimizer; according to the authors, a 27B model diagnoses its errors and edits its own weights without gradients or training, and improves on unseen tasks.

**「What it means in practice」** Developers weighing self-editing as an alternative to fine-tuning should treat it as an unverified preprint claim: the reported self-improvement was limited to shortening reasoning traces that were hitting the token limit, an obvious defect rather than a general capability gain. Until independent results show broader improvements, the technique is not a validated substitute for gradient-based training or for existing weight-editing methods.

**「Community Discussion」** Commenters disputed novelty, with one saying the only self-edit was shortening reasoning traces to avoid token limits and linking prior weight-space work, while another cited Google’s “sleep” framework as precedent. A third argued autonomous weight editing is especially dangerous because a model could suppress safety-related activations, and others questioned whether selecting only successful edits is effectively training.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2611.21885">[2611.21885] Language Models Can Rewrite Their Own Weights</a></li>
<li><a href="https://arxiv.org/pdf/2611.21885v2">Language Models Can Rewrite Their Own Weights - arXiv.org</a></li>
<li><a href="https://arxivb.org/abs/2611.21885">Language Models Can Rewrite Their Own Weights</a></li>

</ul>
</details>

**Tags**: `#self-modifying models`, `#weight editing`, `#LLM research`, `#AI safety`, `#arXiv preprint`

---

<a id="item-tech-news-8"></a>
### [Aaronson Blog Examines Claims of AI Mathematical Breakthroughs](https://scottaaronson.blog/?p=10344) ⭐️ 7.0/10

A Scott Aaronson blog post, discussed on Hacker News, examines claims that “stochastic parrot” AI systems have produced mathematical breakthroughs, framed around an apparent proof of the Riemann Hypothesis. The supplied item contains no article body or independent verification, so it does not establish that a proof exists or identify the systems involved. The post’s broader question is what such AI-generated results would mean for machine reasoning and human understanding.

hackernews · stratos123 · Nov 20, 20:03 · [Discussion](https://news.ycombinator.com/item?id=50581084)

**「Background」** The Riemann Hypothesis dates to Bernhard Riemann&\#x27;s 1859 paper; it asserts that all “non-obvious” zeros of the zeta function are complex numbers with real part 1/2, a property tied to the distribution of prime numbers. The Clay Mathematics Institute includes it among its Millennium Prize Problems.

**「Community discussion」** Commenters focused on whether AI-generated mathematical results would be understandable to humans: one compared chess-engine evaluations to an unsatisfying aggregate of calculations built atop a neural evaluator, while another asked how many mathematicians could reach similar breakthroughs with near-infinite compute. Another commenter worried that people may become increasingly unable to contribute to science and engineering, though the thread did not establish a consensus.

<details><summary>References</summary>
<ul>
<li><a href="https://www.claymath.org/millennium/riemann-hypothesis/">Riemann Hypothesis - Clay Mathematics Institute</a></li>

</ul>
</details>

**Tags**: `#AI mathematics`, `#LLM reasoning`, `#AI epistemology`, `#mathematical proof`, `#Hacker News discussion`

---

<a id="item-tech-news-9"></a>
### [Signal outlines limits on AI agents capturing mobile data](https://signal.org/blog/protecting-your-privacy/) ⭐️ 7.0/10

Signal published a blog post outlining restrictions on AI agents and mobile operating-system platforms capturing user data. The post focuses on app-level access and device privacy, but the supplied material does not identify a specific technical mechanism, version, or ship date. It is therefore a stated privacy position rather than independently verified protection.

hackernews · dotcoma · Nov 20, 09:42 · [Discussion](https://news.ycombinator.com/item?id=50572348)

**「Earlier precedent」** Signal has relied on screenshot blocking before: SecurityWeek reported that it shipped a feature automatically blocking screenshots of its Windows chat window, positioned against Microsoft&\#x27;s Recall, which logs on-screen activity for AI search. The current move extends that same mechanism to mobile, where The Verge reports Signal is blocking screenshots on iOS 27 and Android to keep Siri, Gemini, and other assistants from reading on-screen content.

**「Practical effect」** Signal users on Android can no longer have in-app screen content captured by AI assistants, and screenshots inside the app are blocked on iOS 27 — a change in app behavior rather than a policy statement alone. The tradeoff is that screenshots stop working as a quick way to save or share a conversation, a limitation one commenter says is already frustrating for basic tasks such as sending a document.

**「Community Discussion」** Commenters welcomed Signal&\#x27;s attention to AI apps&\#x27; access but debated the remedy: one called for warning users about spyware and recommending GrapheneOS or Linux, while another asked Signal to publish its forensic findings so smaller developers could benefit. A separate thread criticized screenshot blocking on Windows as breaking a basic feature, and another reported that Signal&\#x27;s VPN and captcha friction pushes high-risk users to other apps.

<details><summary>References</summary>
<ul>
<li><a href="https://www.theverge.com/ai-artificial-intelligence/1038390/signal-blocking-ai-agent-screenshots-mobile-app">Signal is blocking Gemini and Siri AI from reading your... | The Verge</a></li>
<li><a href="https://www.securityweek.com/signal-adds-screenshot-blocker-to-thwart-windows-recall/">Signal Adds Screenshot - Blocker to Thwart ‘Windows... - SecurityWeek</a></li>
<li><a href="https://www.theverge.com/ai-artificial-intelligence/1038390/signal-blocking-ai-agent-screenshots-mobile-app">Signal is blocking Gemini and Siri AI from reading your... | The Verge</a></li>
<li><a href="https://signal.org/blog/protecting-your-privacy/">Signal &gt;&gt; Blog &gt;&gt; Signal is Serious About Protecting Your Privacy</a></li>

</ul>
</details>

**Tags**: `#privacy`, `#AI agents`, `#mobile security`, `#Signal`, `#platform policy`

---

<a id="item-tech-news-10"></a>
### [US Tightens Chip Exports; India Sees AI Compute Opening](https://www.bloomberg.com/news/articles/2026-11-20/nvidia-scandal-fallout-india-ai-yotta-ambani-adani-am-intelligence-e2e-networks) ⭐️ 7.0/10

The United States has tightened exports of advanced chips to Malaysia, Thailand and Singapore, and India&\#x27;s AI industry sees the restrictions as an opening to absorb spillover demand. Yotta says it will add about 100,000 GPUs over the next year, roughly a 10% increase over India&\#x27;s existing compute, though that is a stated plan rather than installed capacity. India currently has 153 data centers, ranking 14th globally; Reliance has pledged up to $110 billion and Adani $100 billion for AI infrastructure, while the country has long faced compute shortages and capital constraints.

telegram · zaihuapd · Nov 20, 07:31

**「Earlier Indian AI infrastructure pledges」** India&\#x27;s starting point is a comparatively thin compute base: the country hosts 153 data centers, ranking 14th globally. The capital behind the current expansion was pledged earlier — Reliance committed $110 billion over seven years in February 2026, Adani announced $100 billion through 2035 for renewable-powered data centers, and Tata partnered with OpenAI on AI-ready capacity — leaving the question of whether tighter U.S. export rules redirect near-term GPU supply toward those projects.

**「Impact」** For India&\#x27;s AI sector, the practical effect depends on whether Yotta&\#x27;s claimed 100,000 GPUs and the Reliance and Adani pledges become installed capacity; the source identifies infrastructure shortages and capital constraints as persistent drags.

<details><summary>References</summary>
<ul>
<li><a href="https://economictimes.indiatimes.com/tech/artificial-intelligence/reliance-puts-110-billion-on-table-joins-adani-tata-in-big-ticket-ai-buildout/articleshow/128589413.cms">Reliance puts $110 billion on table, joins Adani &amp; Tata in ...</a></li>
<li><a href="https://www.forbes.com/sites/yessarrosendar/2026/09/30/the-billionaires-backing-indias-massive-ai-infrastructure-buildout/">The Billionaires Backing India’s Massive AI Infrastructure ...</a></li>

</ul>
</details>

**Tags**: `#AI infrastructure`, `#chip export controls`, `#India AI`, `#GPU capacity`, `#data centers`

---

<a id="item-tech-news-11"></a>
### [OpenAI API adds background mode with 2h/8h windows and token discounts](https://developers.openai.com/api/docs/guides/background) ⭐️ 7.0/10

OpenAI has reportedly added a background mode that moves long-running API requests to asynchronous execution: developers set \`background: true\` and choose a completion window of 2h or 8h via \`background\_options.completion\_window\`, paying token rates 30% and 40% below standard respectively. Leaving the window unset uses a default \`soonest\` mode with no discount. The discounts are described as a public beta on GPT-6.2 Astra, GPT-6.2 Sol, GPT-6.1 Terra and GPT-6 Luna, model names that come only from this secondary Telegram report and are not independently verified. The report also notes that background mode temporarily stores response data even when \`store\` is set to false or zero data retention is enabled.

telegram · zaihuapd · Nov 20, 11:15

**「How background mode fits existing async options」** Background mode works by setting \`background: true\` on a request and polling the returned response object for status instead of holding a connection open. For workloads that can wait, OpenAI&\#x27;s cost guidance already pointed developers to the Batch API and Flex processing as the discounted routes; the 30% and 40% background rates now add an option tied to fixed 2-hour and 8-hour completion windows for GPT-6.2 Astra, GPT-6.2 Sol, GPT-6.1 Terra and GPT-6 Luna.

**「Impact」** Developers with zero-data-retention or \`store: false\` requirements should not assume those settings carry over to background requests, since the report says responses are temporarily retained regardless; workloads handling regulated data would need to stay on the standard synchronous path. For eligible teams, the trade-off is explicit: accepting a 2h or 8h completion window in exchange for 30–40% lower token cost, and leaving the window at the default \`soonest\` forfeits the discount entirely.

<details><summary>References</summary>
<ul>
<li><a href="https://developers.openai.com/api/docs/guides/background">Background mode | OpenAI API</a></li>
<li><a href="https://developers.openai.com/api/docs/pricing">Pricing | OpenAI API</a></li>
<li><a href="https://developers.openai.com/api/docs/guides/cost-optimization">Cost optimization | OpenAI API</a></li>

</ul>
</details>

**Tags**: `#OpenAI API`, `#background processing`, `#async inference`, `#API pricing`, `#data retention`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Why Caching Visible LLM Outputs Saves Little](https://seangoedecke.com/why-output-caching-doesnt-work/) ⭐️ 6.0/10

rss · Sean Goedecke · Nov 21, 00:00

**「Background」** LLM inference cost work usually focuses on caching inputs so conversation history is not recomputed on every message. Sean Goedecke asks whether repeated visible model output—such as quoted code or evidence—should be cached or referenced instead, especially since output tokens are more expensive than input tokens.

**「Solution」** The author acknowledges real repetition in agent workflows: agents restate code snippets or quote long evidence documents, and prompting or fine-tuning them to emit references that the harness expands could eliminate some of it. But he argues this only touches the visible slice of output. From his own agent histories, he estimates about 6% of output tokens are visible, with 50% spent on reasoning and 44% on tool calls. Under Amdahl&\#x27;s law, even an implausible two-thirds saving in visible output would cut total output tokens by only about 4%. The real target is the invisible 94%, which largely depends on intelligence: a smarter model may cost 5x more per token but need 6x fewer tokens, making it cheaper overall. The author flags the 6% figure as anecdotal and is only moderately confident that frontier models rarely repeat themselves in chain of thought; possible repetition inside tool calls remains an open question.

**「Takeaway」** For the author, caching or de-duplicating visible LLM output is a bounded optimization; meaningful cost savings come from reducing reasoning and tool-call tokens through more capable models and more token-efficient harnesses.

**Tags**: `#LLM inference costs`, `#output token caching`, `#agent workflows`, `#Amdahl&\#x27;s law`

---

## Financial News

<a id="item-finance-news-1"></a>
### [U.S. companies switch from buybacks to net share issuance](https://www.cnbc.com/2026/11/20/equity-issuance-bull-market-problem.html) ⭐️ 8.0/10

U.S. companies have shifted from net share repurchases in 2024 to net equity issuance, with Acadian Asset Management calculating net new share issuance at 3.1% of total market capitalization as of late last week.

rss · CNBC Finance · Nov 20, 14:15

**「Background」** Through 2024, U.S. companies were net buyers of their own shares, and buybacks shrink the number of shares in circulation, which can support prices and lift earnings per share by lowering that ratio&\#x27;s denominator. A 2000 study by Malcolm Baker and Jeffrey Wurgler found that when firms issued relatively more equity than debt, periods of low U.S. stock market returns tended to follow, though Lamont&\#x27;s reading of their equity-share measure shows it below its 2021 peak of about 18%.

**「Impact」** The reversal adds shares for the market to absorb, which the source describes as a potential headwind for the four-year bull market.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/20/equity-issuance-bull-market-problem.html">equity issuance bull market problem</a></li>
<li><a href="https://www.semanticscholar.org/paper/The-Equity-Share-in-New-Issues-and-Aggregate-Stock-Baker-Wurgler/14be014490dc773638650618a432fbc7d50a13c5">[PDF] The Equity Share in New Issues and Aggregate Stock Returns</a></li>

</ul>
</details>

**Tags**: `#equity issuance`, `#buybacks`, `#IPO market`, `#AI infrastructure`, `#market liquidity`

---

<a id="item-finance-news-2"></a>
### [Fed officials speak more as Warsh avoids rate guidance](https://www.cnbc.com/2026/11/20/warsh-fed-forward-guidance-rate-hikes.html) ⭐️ 7.0/10

Federal Reserve officials are speaking more frequently and splitting over rate increases while Chair Kevin Warsh avoids forward guidance, with traders pricing a 100% chance of at least a quarter-point hike in December, according to CME Group&\#x27;s FedWatch.

rss · CNBC Finance · Nov 20, 21:10

**「Background」** The Fed held its benchmark rate steady at its October meeting; Warsh has argued that forward guidance—public signals about future policy—can lock policymakers in before they decide.

**「Impact」** If the Fed raises rates in December, borrowing costs would rise for households and businesses with loans tied to its benchmark rate, and Bank of America economist Aditya Bhave said the public back-and-forth is causing “undue rates volatility.”

**Tags**: `#Federal Reserve`, `#interest rates`, `#monetary policy`, `#FOMC`, `#forward guidance`

---

<a id="item-finance-news-3"></a>
### [Beijing Draft Lease Rules Would Bar Deposit Deductions for Normal Wear and Tear](https://mp.weixin.qq.com/s/PmGxh5knIyxiBRhpRoJnoQ) ⭐️ 7.0/10

Beijing opened public comment on a revised model housing lease that would state tenants are not liable for normal wear and tear from ordinary use and bar landlords from deducting such damage from deposits; it would also require rental companies that sublet to pay rent and deposits into supervised accounts.

telegram · zaihuapd · Nov 20, 13:46

**「Background」** The document is a &quot;model contract&quot; — a template drafted by Beijing&\#x27;s housing commission and market regulator that landlords and tenants can choose to use — and it is only a consultation draft, open for public comment from the 20th, so its wording could still change before it is finalized.

**「Who is affected」** If adopted, the draft would apply to Beijing landlords and their tenants, who could no longer have deposits docked for ordinary wear and tear, and to rental companies that sublet flats, which would have to route rent and deposits through supervised accounts rather than holding the money themselves.

**Tags**: `#housing rental regulation`, `#tenant rights`, `#deposit protection`, `#Beijing policy`, `#rental market`

---