---
layout: default
title: "Horizon Summary: 2026-11-12 (EN)"
date: 2026-11-12
lang: en
---

> From 52 items, 14 important content pieces were selected

---

**Technology News**
1. [AWS Publishes aws-emulator, a Local AWS Clone Built by AI Agents](#item-tech-news-1) ⭐️ 8.0/10
2. [WSJ report says Nvidia is preparing to oust CEO Jensen Huang](#item-tech-news-2) ⭐️ 8.0/10
3. [Voltage Glitching Unlocks Disabled A100 Hardware in Mining Card](#item-tech-news-3) ⭐️ 8.0/10
4. [Report Alleges Alice Huang Helped Move 240,000 Nvidia Chips to China](#item-tech-news-4) ⭐️ 8.0/10
5. [Tim Peters, Zen of Python author and Timsort creator, dies](#item-tech-news-5) ⭐️ 7.0/10
6. [Emacs Essay and HN Thread Debate an LLM-Free Fork](#item-tech-news-6) ⭐️ 7.0/10
7. [Blog Post Asks Whether a Linear Program Can Do Weight-Space Model Editing](#item-tech-news-7) ⭐️ 7.0/10
8. [False Smoke Alarm Nearly Downed Jane Street’s Only NYC Datacenter](#item-tech-news-8) ⭐️ 7.0/10
9. [Google launches Gemini Decisions API for multimodal closed-ended decisions](#item-tech-news-9) ⭐️ 7.0/10
10. [Apple Research Describes Faster Retrieval for RAG](#item-tech-news-10) ⭐️ 7.0/10
11. [LLM 0.37.2 fixes API key leak to third-party endpoints](#item-tech-news-11) ⭐️ 7.0/10
12. [Anthropic&\#x27;s IPO roadshow details multi-chip Claude training across four chip families](#item-tech-news-12) ⭐️ 7.0/10

**Financial News**
1. [Fed&\#x27;s Goolsbee calls October inflation report &\#x27;borderline disturbing&\#x27; as officials weigh more hikes](#item-finance-news-1) ⭐️ 8.0/10
2. [China ends offshore trust income tax transition with over RMB160 billion declared](#item-finance-news-2) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [AWS Publishes aws-emulator, a Local AWS Clone Built by AI Agents](https://github.com/aws/aws-emulator) ⭐️ 8.0/10

AWS has published an official \`aws-emulator\` repository that lets developers run tests against local clones of many AWS services without a paid API key. The emulator is written in Rust and, according to the accompanying account, was produced by a swarm of autonomous agents that generated 29,684 commits in the project&\#x27;s first three weeks; Swami Sivasubramanian describes the effort in a guest post on Werner Vogels&\#x27; blog. On macOS and Windows it currently requires Docker, and the emulator&\#x27;s security documentation says not to use it for IAM policies and permissions boundaries, resource-based policies, KMS key policies, cross-account or cross-Region access, or other security controls.

hackernews · super\_linear · Nov 11, 18:21 · [Discussion](https://news.ycombinator.com/item?id=50456631)

**「Background」** A cloud emulator provides local stand-ins for service APIs so tests can run without provisioning real cloud resources or using paid API access. The AWS item describes an official emulator for testing against a local clone of many AWS services; it is written in Rust and currently requires Docker on macOS and Windows.

**「What it means for local AWS testing」** Teams adopting the emulator for local test suites still need Docker on macOS and Windows, so it cannot yet be dropped in as a single binary across languages and platforms. Its security guidance explicitly excludes IAM policies, resource-based policies such as bucket policies, KMS key policies, and cross-account or cross-Region access, which means tests covering those behaviors must still run against real AWS; alternative local emulators such as Floci instead map a 12-digit access key ID to a separate account and keep resources isolated between accounts.

**「Community discussion」** Commenters were divided on practical value: CharlieDigital said it is unclear whether the emulator is an exercise or a product AWS will ship and maintain, and reported using Floci with Testcontainers instead, while scriptsmith highlighted the security page as a hard limitation for IAM and policy testing. wg0 argued that without AI agents AWS would not have attempted an emulator across its many services, and that this erodes the advantage of third-party local cloud emulators such as LocalStack.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/floci-io/floci">floci -io/ floci : Light, fluffy, and always free - The AWS Local Emulator ...</a></li>

</ul>
</details>

**Tags**: `#AWS`, `#cloud emulation`, `#AI agents`, `#developer tooling`, `#open source`

---

<a id="item-tech-news-2"></a>
### [WSJ report says Nvidia is preparing to oust CEO Jensen Huang](https://www.wsj.com/business/nvidia-is-preparing-to-oust-nvidia-ceo-jensen-huang-30f421ad) ⭐️ 8.0/10

A Wall Street Journal report says Nvidia is preparing to oust CEO Jensen Huang, according to the item&\#x27;s headline and analysis summary. The supplied material contains no article text, Nvidia board statement, or company confirmation, so the reported move and its timing remain unverified. No details on a successor, board vote, or timeline are included.

hackernews · jbredeche · Nov 11, 22:31 · [Discussion](https://news.ycombinator.com/item?id=50459703)

**「Huang&\#x27;s role at Nvidia」** Jensen Huang co-founded Nvidia and has led it as CEO through its expansion from graphics chips into general-purpose GPU computing and AI. That long tenure is the backdrop for the WSJ report, which concerns a reported succession move rather than a confirmed departure.

**「A pending board decision with stock already moving」** The report had an immediate market effect: CNBC&\#x27;s coverage of the same story said Nvidia shares sank, hitting investors before any board decision was announced. According to the Journal&\#x27;s account, the board was preparing to meet as soon as Wednesday to decide Huang&\#x27;s fate, so customers, suppliers, and shareholders face a governance decision that remains pending rather than a completed leadership change.

**「Community discussion」** Commenters debate whether the allegations discussed in the thread make Huang&\#x27;s position untenable, with some emphasizing reported personal-conduct and China-sales claims and others stressing his early backing of CUDA and general-purpose GPU computing as central to Nvidia&\#x27;s AI success. The allegations are presented in comments without independent verification in the supplied material.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/11/nvidia-jensen-huang-affair-employee.html">Nvidia prepares to oust Jensen Huang , WSJ reports — stock sinks</a></li>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-11/nvidia-ceo-had-an-affair-with-health-executive-at-firm-nyt-says">Nvidia Preparing to Oust Jensen Huang After Affairs, WSJ Says</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#Jensen Huang`, `#AI hardware`, `#corporate governance`, `#semiconductor industry`

---

<a id="item-tech-news-3"></a>
### [Voltage Glitching Unlocks Disabled A100 Hardware in Mining Card](https://blog.kate.land/posts/using-voltage-glitching-to-unlock-the-a100/) ⭐️ 8.0/10

A first-hand hardware-hacking write-up reports using voltage glitching to defeat fuse-disabled capabilities in an NVIDIA mining card, presented as a way to unlock A100 hardware. The account describes a physical attack on fuses rather than a software workaround; discussion identifies the card as the 8GB CMP 170HX. It is the author’s experimental result, not an NVIDIA-supported modification or an independently verified finding.

hackernews · lae · Nov 11, 10:48 · [Discussion](https://news.ycombinator.com/item?id=50451903)

**「Background」** The card in the write-up is a CMP 170HX, a mining-oriented board built on the same GA100 die as NVIDIA&\#x27;s A100 datacenter GPU but shipped with much of that silicon switched off: 4,480 shading units versus 6,912 on a fully enabled A100 SXM4 40 GB. NVIDIA implements this kind of product segmentation by blowing on-die fuses, so the premise of the attack is that a precisely timed voltage glitch can disrupt the fuse-reading logic at boot and let the card come up with capabilities it was never sold with.

**「Impact」** Owners of the 8GB CMP 170HX can attempt the conversion, but it requires an irreversible fuse-blowing voltage-glitch procedure on the GA100 die rather than a software toggle, so a botched attempt can leave the card unusable. An HN commenter also claims that most 80GB unlocks suffer from bad RAM, suggesting a card may report the full capacity without being stable under real workloads.

**「Community Discussion」** Commenters debated whether NVIDIA fused off working A100 silicon for market segmentation or was salvaging dies with fabrication faults, with one arguing salvage is more likely because datacenter parts earn more. Others suggested power-cycling only the target card through an external PCIe riser, and one reported two weeks of failed software-only attempts to unlock 80GB on a CMP 170HX.

<details><summary>References</summary>
<ul>
<li><a href="https://www.techpowerup.com/gpu-specs/cmp-170hx-8-gb.c3830">NVIDIA CMP 170HX 8 GB Specs | TechPowerUp GPU Database</a></li>
<li><a href="https://blog.kate.land/posts/using-voltage-glitching-to-unlock-the-a100/">Using voltage glitching to unleash the A 100 in my mining card</a></li>
<li><a href="https://news.ycombinator.com/item?id=50451903">Using voltage glitching to unleash the A 100 in my mining card</a></li>

</ul>
</details>

**Tags**: `#hardware hacking`, `#voltage glitching`, `#GPU`, `#reverse engineering`, `#NVIDIA`

---

<a id="item-tech-news-4"></a>
### [Report Alleges Alice Huang Helped Move 240,000 Nvidia Chips to China](https://www.tomshardware.com/tech-industry/policy/alice-huang-reportedly-instrumental-in-securing-over-usd7-5-billion-of-nvidia-ai-gpu-imports-during-three-year-relationship-with-jensen-huang-helped-move-240-000-banned-chips-into-china-mostly-h100-and-h200) ⭐️ 8.0/10

A report attributed to The Information alleges that Alice Huang helped move about 240,000 restricted Nvidia AI chips into China over a three-year relationship with CEO Jensen Huang, mostly H100 and H200 GPUs. The report ties the imports to roughly $7.5 billion and names Shanghai Century Litong and Singapore-based Megaspeed among the companies involved. These are unverified allegations from a secondary report; the supplied item provides no independent confirmation, Nvidia response, or detail on how the alleged diversion worked.

telegram · zaihuapd · Nov 11, 14:41

**「Background」** The Nvidia H100 and H200 are data-center GPUs covered by US export restrictions on advanced AI chips sold to China. The allegations surfaced alongside an investigation into Singapore-based Megaspeed over suspicions that it was helping China circumvent those restrictions.

<details><summary>References</summary>
<ul>
<li><a href="https://knowyourmeme.com/memes/events/nvidia-ceo-jensen-huang-chinese-spy-cheating-controversy">Nvidia CEO Jensen Huang Chinese Spy Cheating... | Know Your Meme</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#AI chips`, `#export controls`, `#semiconductor industry`, `#China tech policy`

---

<a id="item-tech-news-5"></a>
### [Tim Peters, Zen of Python author and Timsort creator, dies](https://discuss.python.org/t/in-memoriam-tim-peters-1952-2026/110028) ⭐️ 7.0/10

Tim Peters, a Python core developer known for the Zen of Python and the Timsort sorting algorithm, has died; a Python Discourse memorial thread gives his dates as 1952–2026. The thread highlights his influence on Python&\#x27;s design philosophy and standard library. His other noted work includes SpamBayes and the Python Cookbook.

hackernews · ayhanfuat · Nov 11, 07:03 · [Discussion](https://news.ycombinator.com/item?id=50450488)

**「Background」** Peters was a longtime CPython core developer whose influence predates the current Python ecosystem: he wrote the Zen of Python aphorisms returned by \`import this\` and, in 2002, contributed Timsort, the hybrid sorting algorithm used for Python lists and later adopted by Java and Android. The memorial thread credits him with setting an early tone for core development by explaining technical tradeoffs rather than dismissing contributors.

**「Community discussion」** Commenters remembered Peters as “Uncle Timmy,” citing his python-dev and Usenet posts as important learning material, and pointed to his role—alongside Gary Robinson and other contributors—in turning pg&\#x27;s “A Plan for Spam” essay into SpamBayes. Others highlighted his contributions to the second edition of the Python Cookbook and his explanations of programming craft.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Tim_Peters_%28software_engineer%29">Tim Peters (software engineer) - Wikipedia</a></li>
<li><a href="https://discuss.python.org/t/in-memoriam-tim-peters-1952-2026/110028">In Memoriam: Tim Peters 1952–2026 - Core Development ...</a></li>

</ul>
</details>

**Tags**: `#python`, `#open-source-community`, `#obituary`, `#timsort`, `#software-engineering-culture`

---

<a id="item-tech-news-6"></a>
### [Emacs Essay and HN Thread Debate an LLM-Free Fork](https://commandlinesystems.com/magic.txt) ⭐️ 7.0/10

A new essay, “Emacs in the Age of Magic,” and its Hacker News thread are debating an LLM-free Emacs fork. Commenters quote a declaration of intent to use and develop an LLM-free Emacs regardless of GNU policy, pointing to human-emacs.org. That declaration is a stated plan, not a shipped fork; the supplied material reports no code release, version, or GNU policy change.

hackernews · ggcr · Nov 11, 20:26 · [Discussion](https://news.ycombinator.com/item?id=50458208)

**「Earlier context」** GNU Emacs has had a temporary ban on LLM-generated contributions, and a group of Emacs developers and users has organized Human Emacs to reject such contributions on ethical grounds \(freenode.net, Nov. 3, 2026\). In an Oct. 29, 2026 emacs-devel message, the group said it would develop an LLM-free Emacs even if that meant leaving GNU Emacs, while acknowledging that Emacs forks have historically been contentious and had a poor track record.

**「Impact」** If the declared effort proceeds, Emacs users and package maintainers would face a choice between GNU Emacs and a variant with a different contribution policy; the supplied material does not say whether the variant exists or how it would track upstream changes.

**「Community Discussion」** Commenters expressed differing views on the fork and on LLM-generated code: one argued that modular APIs are needed to isolate AI-written chunks for maintainability, another said AI has inverted Stallman’s software-freedom goal because users will not know how the generated code works, and a third reported having stopped opening a code editor at all.

<details><summary>References</summary>
<ul>
<li><a href="https://lists.gnu.org/archive/html/emacs-devel/2026-10/msg00508.html">Human Emacs - lists.gnu.org</a></li>
<li><a href="https://freenode.net/article/emacs-group-vows-fork-if-project-accepts-llm-generated-code">Emacs group vows fork if project accepts LLM-generated code</a></li>

</ul>
</details>

**Tags**: `#Emacs`, `#LLM-generated code`, `#open source governance`, `#software freedom`, `#AI coding`

---

<a id="item-tech-news-7"></a>
### [Blog Post Asks Whether a Linear Program Can Do Weight-Space Model Editing](https://nathan.rs/posts/weight-space-lp/) ⭐️ 7.0/10

A post on nathan.rs poses the question of whether linear programming can be used for weight-space programming — editing a neural network&\#x27;s weights directly to change its behavior — and the Hacker News thread took up how such a method would actually be applied. The framing is exploratory: the supplied material describes an examination of LP as a weight-editing tool and includes no benchmark results, released code, or measured comparison against existing editing methods, so the post&\#x27;s conclusions could not be checked here. Commenters extended the idea in several directions, including weight-space distillation, sparse weight edits, and enforcing the constraints during training rather than after it.

hackernews · emschwartz · Nov 11, 12:30 · [Discussion](https://news.ycombinator.com/item?id=50452655)

**「Background」** Weight-space programming refers to treating a neural network&\#x27;s weights as a medium a language model can read and write directly, taking the place of the optimizer that normally sets parameters during training. The term comes from a November 2026 MIT CSAIL study in which GPT-6 Astra was reported to fix reasoning loops in Qwen3.5-0.8B by editing just 0.016% of its parameters, a change described as lifting MATH-500 from 7.9% to 48.1% and roughly tripling IFEval. The post under discussion revisits that hand-tuned weight search and argues the search can be recast as a linear program solvable in about a minute.

**「Impact」** For practitioners working on model editing, the thread&\#x27;s proposals point to the first questions to test: whether edits expressed as linear constraints on weights remain sparse enough to avoid collateral behavior change, and whether those constraints work better as a training-time regularizer than as a post-hoc weight edit. Commenters also flagged scaling to larger models with multi-objective rewards as unresolved, and the post provides no evidence either way.

**「Community Discussion」** jsw97 read LP solvers as guidance for a weight-editing prompt — expressing &quot;eliminate this behavior, preserve that behavior&quot; as linear constraints — rather than as a replacement for the editing request itself. dansitu argued the simplicity of the idea suggests it should happen during training via regularization, mirekrusin proposed using it for weight-space distillation by discovering behavioral directions and solving for sparse edits, and rbnafo said the discussion was a case for revisiting numerical optimization methods that the field has neglected in favor of LLMs.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Weight-space_programming">Weight-space programming - Wikipedia</a></li>
<li><a href="https://proomt.com/item/can-a-linear-program-do-weight-space-programming-d1a13007-a589-44d0-b87e-067ea543171c">Can a Linear Program Do Weight-Space Programming? · proomt</a></li>
<li><a href="https://elsolitario.org/en/2026/11/02/mit-csail-astra-edits-0-016-of-qwen3-weights/">Weight-Space Programming: How Astra Edits Weights</a></li>
<li><a href="https://explainx.ai/blog/weight-space-programming-gpt-6-astra-edits-qwen3-5-0-8b-weights-math-7-9-to-48-1-mit-csail-2026">GPT-6 Astra Edits Qwen Weights: MATH-500 7.9% to 48.1% ...</a></li>

</ul>
</details>

**Tags**: `#linear programming`, `#model editing`, `#neural networks`, `#optimization`, `#machine learning`

---

<a id="item-tech-news-8"></a>
### [False Smoke Alarm Nearly Downed Jane Street’s Only NYC Datacenter](https://michael.bacarella.com/2026/11/10/false-smoke-alarm-jane-street-datacenter/) ⭐️ 7.0/10

A false smoke alarm nearly took down Jane Street’s only New York City datacenter, according to an incident account by Michael Bacarella. The writeup treats the event as an operational lesson in emergency procedures and datacenter resilience for infrastructure and reliability readers.

hackernews · mbac32768 · Nov 11, 16:38 · [Discussion](https://news.ycombinator.com/item?id=50455394)

**「The smoke-alarm interlock」** Data-center fire systems commonly interlock smoke detection with cooling shutdown and sprinkler release, so a single sensor input can affect both temperature control and water suppression. That design is meant to keep a real fire from spreading, but it also means a false alarm can create a compound failure rather than a harmless alert. The incident account describes a dust-triggered alarm that disabled cooling and pressurized the sprinkler system, forcing staff to cut server power manually.

**「Interlock check for operators」** The actionable item for other infrastructure teams is the smoke-detection interlock itself: commenters described a physical emergency power-off button and automatic de-energization on smoke detection as baseline expectations for a data hall, while another said the sequence of operations written for halls they work on deliberately keeps CRAC units running on a smoke alarm, an allowance they attribute to the International Mechanical Code for air handlers over 2,000 cfm that serve a single space. The account also frames the site as Jane Street&\#x27;s only New York datacenter, so an automatic de-energization there has no sibling facility in the region to absorb the load.

**「Community Discussion」** Commenters questioned why the facility lacked a physical emergency power-off button inside the datacenter and an EPO interlink to smoke alarms that would de-energize equipment automatically. Another commenter said the sequence of operations for data halls they work on deliberately avoids shutting down computer-room air conditioners on a smoke alarm, citing an International Mechanical Code allowance for large air handlers serving a single space.

<details><summary>References</summary>
<ul>
<li><a href="https://o-server.main.jp/hacker-news/en/articles/2026/11/10/false-smoke-alarm-nearly-floods-jane-street-s-nyc-datacenter-50455394.html">False Smoke Alarm Nearly Floods Jane Street&#x27;s NYC Datacenter</a></li>

</ul>
</details>

**Tags**: `#data centers`, `#incident response`, `#site reliability`, `#emergency procedures`

---

<a id="item-tech-news-9"></a>
### [Google launches Gemini Decisions API for multimodal closed-ended decisions](https://blog.google/innovation-and-ai/technology/developers-tools/gemini-decisions-api/) ⭐️ 7.0/10

Google announced the Gemini Decisions API, built on Gemini Decision 1, for closed-ended tasks such as tool selection, policy checks, and model routing. According to the announcement, it accepts text, images, audio, video, and PDFs, can score up to 1,000 questions per call, and returns probabilities and confidence scores with 150–250 ms end-to-end latency. Pricing is $0.10 per million input tokens with no charge for output tokens—a claimed roughly 5x cost reduction versus a Gemini 3.5 Flash-Lite approach—and it is available in Google AI Studio.

hackernews · iamdelirium · Nov 11, 18:32 · [Discussion](https://news.ycombinator.com/item?id=50456791)

**「What decision models are」** Decision models are a specialized interface rather than a chat format: they answer structured questions about an input, such as true/false, multiple choice with up to 255 options, or scoring with up to 255 levels, and return a confidence value for each answer. That makes them suited to closed-ended tasks like tool selection, policy checks, and model routing, where a caller wants a comparable answer rather than generated prose.

**「Developer impact」** Developers building tool selection, model routing, or policy checks can batch up to 1,000 closed-form questions into one call and receive scored probabilities, potentially replacing per-query Flash-Lite prompts at $0.10 per million input tokens with no output-token charge. Before relying on it for production decisions, teams should benchmark its probability calibration and accuracy on their own labeled tasks, since the announcement provides no calibration data and the claimed roughly 5x cost advantage is vendor-reported.

**「Community discussion」** Commenters asked how the model&\#x27;s probability outputs are calibrated and how decision models are used in practice, including in coding harnesses. One said it is more expensive than other decision models in the same category but potentially valuable for audio and video inputs, while another argued that querying hundreds of questions over a large context would be inexpensive.

<details><summary>References</summary>
<ul>
<li><a href="https://openrouter.ai/google/gemini-decision-1">Gemini Decision 1 - API Pricing &amp; Providers | OpenRouter</a></li>

</ul>
</details>

**Tags**: `#Gemini`, `#Google`, `#API`, `#AI models`, `#multimodal AI`

---

<a id="item-tech-news-10"></a>
### [Apple Research Describes Faster Retrieval for RAG](https://machinelearning.apple.com/research/faster-retrieval) ⭐️ 7.0/10

Apple has published a research post describing a faster retrieval approach for retrieval-augmented generation \(RAG\). The supplied item provides no method details, benchmark figures, code, or availability information, so the claimed speedup cannot be independently assessed. The work is aimed at LLM systems that use retrieval, but whether the technique applies beyond Apple&\#x27;s setup is unclear.

hackernews · zerop · Nov 11, 16:57 · [Discussion](https://news.ycombinator.com/item?id=50455633)

**「Context: what the retrieval step costs」** Retrieval-augmented generation hinges on a search step that ranks a query against a large store of embedded documents, which the underlying paper frames as maximum inner product search. Apple&\#x27;s paper is titled &quot;Amortizing Maximum Inner Product Search with Learned Support Functions,&quot; was presented at ICML 2026, and was posted as an Apple Machine Learning Research highlight on November 5, 2026, according to coverage of the publication. The research post frames the work around designing methods tuned to a likely source of inputs rather than to all possible inputs, so that compute is redirected more efficiently.

**「Impact」** Developers evaluating RAG retrieval stacks should treat the claimed speedup as unverified until method details, benchmarks, or code are available; the supplied material offers no basis for comparing its latency or output quality with existing retrievers.

**「Community Discussion」** Commenters debated whether learned retrieval improves RAG in practice: one described Spotify&\#x27;s &quot;Parallel Fusion Router&quot; and argued such learned methods matter mainly at hyperscale, while others said retrieval can bias an LLM toward weaker heuristic rankings and that embeddings often fail to beat grep on codebases. These are practitioner opinions, not measured comparisons of Apple&\#x27;s method.

<details><summary>References</summary>
<ul>
<li><a href="https://machinelearning.apple.com/research/faster-retrieval">Faster Retrieval for Better, More Efficient RAG - Apple ...</a></li>
<li><a href="https://grafy.ai/news/apple-trains-small-neural-nets-to-speed-up-rag-retrieval">Apple trains small neural nets to speed up — Grafy News</a></li>

</ul>
</details>

**Tags**: `#RAG`, `#information retrieval`, `#LLM efficiency`, `#machine learning`, `#Apple`

---

<a id="item-tech-news-11"></a>
### [LLM 0.37.2 fixes API key leak to third-party endpoints](https://simonwillison.net/2026/Nov/11/llm/) ⭐️ 7.0/10

LLM 0.37.2 fixes two security issues, reported by Daniel de Araujo in GHSA-v9h7-jj4g-f862 and GHSA-r639-rr7r-x72w, that could expose a configured OpenAI API key to third-party OpenAI-compatible API providers. The key could be sent if the key named by \`api\_key\_name\` had never been stored, or if a \`responses: true\` model was run with \`-o chat\_completions 1\`. The patch covers the \`extra-openai-models.yaml\` mechanism, now managed by the \`llm openai endpoint add\` command introduced in 0.37.

rss · Simon Willison · Nov 11, 17:19

**「Background」** LLM&\#x27;s \`extra-openai-models.yaml\` configuration lets the CLI send requests to third-party OpenAI-compatible API endpoints, and version 0.37 added the \`llm openai endpoint add\` command to manage those entries. Such entries can identify an API key by name rather than storing the key inline. The two security advisories concerned configuration paths that could send the user&\#x27;s configured OpenAI API key to one of those third-party providers.

**「Impact」** Users of LLM with custom OpenAI-compatible endpoints should upgrade to 0.37.2, especially if they rely on \`api\_key\_name\` or run \`responses\`-capable models with \`chat\_completions\` overrides, to avoid sending their OpenAI API key to a third-party provider.

**Tags**: `#security`, `#llm`, `#open-source`, `#api-keys`, `#cli`

---

<a id="item-tech-news-12"></a>
### [Anthropic&\#x27;s IPO roadshow details multi-chip Claude training across four chip families](https://simonwillison.net/2026/Nov/11/anthropic-ipo-roadshow/) ⭐️ 7.0/10

Anthropic opened its IPO roadshow on November 10, and the accompanying video contains previously unreleased detail on how the company runs its business; Simon Willison highlighted the &quot;Approach to compute&quot; section featuring co-founder Tom Brown. Brown says Anthropic now trains and serves Claude across all four major chip families — AWS Trainium, Google TPUs, NVIDIA GPUs and AMD GPUs — an early multi-chip bet he says many considered not worth the effort because each chip needs its own tailored software and inference stack. As a concrete example, he says Anthropic began working with AMD GPUs this year and that a system called Mythos got Claude running on AMD in three days with &quot;basically no human intervention,&quot; porting or writing almost 100% of the kernels, where adding a new chip platform previously took dozens of engineers months. Brown also frames compute strategy around &quot;compute multipliers&quot; — total effective compute as physical capacity multiplied by discovered multipliers — and claims these stack and could grow faster as Anthropic approaches recursive self-improvement; these are company claims made in a promotional roadshow video, which has no official transcript \(Willison published one he extracted with MacWhisper\).

rss · Simon Willison · Nov 11, 15:11

**「Background」** An earlier Anthropic postmortem of three incidents, cited by Simon Willison, described bugs that affected only its TPU deployments—an early public hint of the company&\#x27;s multi-chip strategy. That strategy is costly to build because each chip family needs its own tailored software and inference stack, which Anthropic says it bet on early.

**「Impact」** If the three-day AMD port is accurate, it implies the engineering cost of adding a new accelerator family has dropped from months of work by dozens of engineers to days of agent-driven kernel porting — a claim worth independent verification, since the account provides no performance numbers, kernel counts, or comparisons against the hand-written stacks used for the other three chip families. Developers and infrastructure buyers assessing Anthropic&\#x27;s compute supply and pricing should treat the multi-chip and compute-multiplier figures as vendor statements from an IPO roadshow rather than measured results.

**Tags**: `#Anthropic`, `#AI infrastructure`, `#AI compute`, `#IPOs`, `#multi-chip`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Fed&\#x27;s Goolsbee calls October inflation report &\#x27;borderline disturbing&\#x27; as officials weigh more hikes](https://www.cnbc.com/2026/11/11/goolsbee-october-inflation-fed-rates-disturbing-distressing.html) ⭐️ 8.0/10

Chicago Fed President Austan Goolsbee called October&\#x27;s inflation report &quot;borderline disturbing&quot; after the consumer price index rose 0.4% on a seasonally adjusted basis, the third straight month of larger-than-expected increases. Fed funds futures now fully expect a rate hike at the December meeting, with 15% odds it comes as a half-point increase, according to CME&\#x27;s FedWatch tool.

rss · CNBC Finance · Nov 11, 16:49

**「Background」** The Fed had raised its benchmark interest rate by a quarter point in September to a range of 3.75%–4% and left it unchanged in October, ahead of its final policy meeting of the year in December.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/11/goolsbee-october-inflation-fed-rates-disturbing-distressing.html">Austan Goolsbee calls inflation report &#x27;borderline disturbing&#x27; as Fed....</a></li>

</ul>
</details>

**Tags**: `#Federal Reserve`, `#monetary policy`, `#inflation`, `#CPI`, `#interest rates`

---

<a id="item-finance-news-2"></a>
### [China ends offshore trust income tax transition with over RMB160 billion declared](https://www.news.cn/20261111/9bcce99c779b4a6197ff45bbbc3e4c50/c.html) ⭐️ 8.0/10

China&\#x27;s tax authority said on November 11 that the 90-day transition period for taxing offshore trust income ended, with more than RMB160 billion in personal income tax declared, including over RMB120 billion collected in October, which it said drove nearly 90% growth in national personal income tax revenue that month. Under a July 24, 2026 notice from the Ministry of Finance and the tax authority, taxpayers who declared and paid within the 90-day window avoid late-payment surcharges.

telegram · zaihuapd · Nov 11, 10:35

**「Background」** A joint announcement by the Ministry of Finance and the tax administration on 24 July 2026 let resident individuals declare income earned by offshore trusts before 1 January 2026 as &quot;interest, dividends and bonuses&quot; within 90 days of the rules taking effect, without late-payment surcharges. The transition period that has now ended was that 90-day window.

**「Impact」** Wealthy individuals with offshore trust income who did not declare or misreported face orders to pay back taxes plus late fees, and the tax authority said unresolved cases will be formally investigated.

<details><summary>References</summary>
<ul>
<li><a href="https://fgk.chinatax.gov.cn/zcfgk/c102416/c5251277/content.html">国家税务总局政策法规库</a></li>
<li><a href="http://beijing.chinatax.gov.cn/bjswj/sszc/zxwj/202607/a28344d9de4640feb6c632d761818ada.shtml">财政部 税务总局关于离岸信托个人所得税有关事项的公告</a></li>

</ul>
</details>

**Tags**: `#offshore trusts`, `#personal income tax`, `#tax enforcement`, `#China fiscal policy`, `#high-net-worth individuals`

---