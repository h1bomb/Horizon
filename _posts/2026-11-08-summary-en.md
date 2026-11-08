---
layout: default
title: "Horizon Summary: 2026-11-08 (EN)"
date: 2026-11-08
lang: en
---

> From 39 items, 13 important content pieces were selected

---

**Technology News**
1. [MaxxBench tests whether DeepSWE scores survive task-spec changes](#item-tech-news-1) ⭐️ 8.0/10
2. [SemiAnalysis tours Envision&\#x27;s 800MW Galaxy AI campus in Inner Mongolia](#item-tech-news-2) ⭐️ 8.0/10
3. [GitHub&\#x27;s Rubicon storage reports 7,200 pushes per second](#item-tech-news-3) ⭐️ 8.0/10
4. [Reported end of Microsoft Research AI Frontiers and Langford&\#x27;s exit](#item-tech-news-4) ⭐️ 7.0/10
5. [Claude Code local settings with secrets found in 1,122 GitHub files](#item-tech-news-5) ⭐️ 7.0/10
6. [Need for Speed: Underground 2 reimplementation runs in browser with multiplayer](#item-tech-news-6) ⭐️ 7.0/10
7. [Asahi Linux 7.3 report: first same-day Fedora Asahi Remix release](#item-tech-news-7) ⭐️ 7.0/10
8. [Coldframe honeypot mimics Danfoss and Dixell refrigeration controllers](#item-tech-news-8) ⭐️ 7.0/10
9. [Researcher claims every Mac since 2022 runs an undocumented personal knowledge graph](#item-tech-news-9) ⭐️ 7.0/10
10. [Claude Code report alleges web requests leaked login emails](#item-tech-news-10) ⭐️ 7.0/10
11. [Apple discloses HALO humanoid control system using two Qwen models](#item-tech-news-11) ⭐️ 7.0/10

**Financial News**
1. [Berkshire more than doubles Q3 buybacks as operating earnings decline](#item-finance-news-1) ⭐️ 7.0/10
2. [SoftBank, ABB Weigh China Carve-Out to Salvage $5.4 Billion Robotics Deal](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [MaxxBench tests whether DeepSWE scores survive task-spec changes](https://maxxbench.unlap.ai/research/why-maxxbench/) ⭐️ 8.0/10

For developers who use DeepSWE to compare coding models, MaxxBench has published a critique arguing that strong scores should not be taken at face value and testing whether they hold when task specifications are varied. The analysis also reports bugs in DeepSWE, and the Hacker News thread debated benchmark validity, score robustness, and whether smaller models are disproportionately affected. The claims come from a single research source and were not independently verified in the supplied material.

hackernews · antiuniverse · Nov 7, 17:19 · [Discussion](https://news.ycombinator.com/item?id=50406222)

**「What MaxxBench tested」** DeepSWE is the coding benchmark whose leaderboard scores the post interrogates, and MaxxBench is a separate evaluation built to probe them. A summary of the work describes MaxxBench as mutating 89 DeepSWE coding tasks by changing instructions or starting code — for example, requiring lowercase filenames or UTC timestamps — while holding the median patch growth to 17 lines, or 3.5%, so each perturbed task remains comparable to its original.

**「Impact」** The practical consequence is that DeepSWE score gaps—especially among smaller or &quot;-flash&quot; variants—should be treated as provisional until checked against perturbed task specs; one commenter also drew a &quot;don&\#x27;t use max mode&quot; takeaway from the analysis.

**「Community discussion」** Commenters largely welcomed the task-spec perturbation as a simple way to test generalisation, with one reporting that in a private benchmark many less capable models failed for reasons other than submitting the wrong answer. Others focused on the chart: smaller &quot;-flash&quot; models appeared to collapse most, while one commenter argued that GLM-5.3 and GLM-5.3-flash are misnamed distinct lineages and so should not be read as a like-for-like pair.

<details><summary>References</summary>
<ul>
<li><a href="https://daily.dev/posts/maxxbench-nice-deepswe-score-but-is-it-true--ue9ulip60">MaxxBench – &quot;Nice DeepSWE score. But is it true?&quot;</a></li>

</ul>
</details>

**Tags**: `#llm-benchmarks`, `#evaluation-methodology`, `#benchmark-validity`, `#ai-software-engineering`, `#hacker-news-discussion`

---

<a id="item-tech-news-2"></a>
### [SemiAnalysis tours Envision&\#x27;s 800MW Galaxy AI campus in Inner Mongolia](https://newsletter.semianalysis.com/p/we-visited-chinas-stargate-in-inner) ⭐️ 8.0/10

SemiAnalysis published a firsthand report on Envision Group&\#x27;s Galaxy datacenter campus in Ulanqab, Inner Mongolia, planned for up to 800MW of IT capacity and built to suit two unnamed internet giants. The first 120MW phase was delivered within a year at one-fifth of US costs, according to the report, while the rest of the campus remained an active construction site. Envision&\#x27;s vertical integration includes building its own wind farms and a dedicated power line, a blade factory across the road, in-house low-voltage power modules and an 800V system, battery storage, and a co-designed prefabricated substation. SemiAnalysis also reported nearly 30,000 construction workers across 22 datacenter projects in the surrounding Chahar High-tech Zone, citing a local report.

rss · Semianalysis · Nov 7, 19:01

**「Background」** SemiAnalysis uses Stargate Abilene, the gigawatt-scale Texas campus built for OpenAI, as the reference point for U.S. AI datacenter buildouts. The report also builds on the outlet&\#x27;s earlier primer on China&\#x27;s datacenter market and frames Inner Mongolia as the country&\#x27;s fastest-growing AI datacenter region.

**「Why it matters」** For companies benchmarking AI datacenter costs and schedules, Galaxy provides a documented Chinese comparison: a 120MW phase delivered in about a year at roughly one-fifth of US costs, supported by Envision&\#x27;s control over power generation, electrical equipment, and construction. The report does not provide a detailed cost breakdown or establish whether this vertically integrated model can be replicated outside China.

**Tags**: `#AI infrastructure`, `#datacenters`, `#China AI`, `#cost efficiency`, `#vertical integration`

---

<a id="item-tech-news-3"></a>
### [GitHub&\#x27;s Rubicon storage reports 7,200 pushes per second](https://github.blog/engineering/architecture-optimization/inside-githubs-new-git-storage-architecture/) ⭐️ 8.0/10

GitHub has introduced Rubicon, a new Git storage architecture designed for large numbers of AI agents operating concurrently on a single repository. In internal testing, it supported 5,000 agents working together and processed 7,200 pushes per second while keeping read latency low; these are vendor-reported results from a limited private preview, not a broadly available or independently measured capability. The architecture stores Git objects in Azure Blob Storage, manages reference state with Ref-CAS, uses virtual replicas for reads and writes, and relies on background nodes to compact packfiles. GitHub says it will gradually expand the preview.

telegram · zaihuapd · Nov 7, 14:12

**「Background」** Git refs are the mutable pointers, such as branches and tags, that determine which commits a repository exposes; updating them safely becomes a coordination problem when many writers act at once. Rubicon separates that reference state from object data: Git objects go to Azure Blob Storage, refs are managed through Ref-CAS, and virtual replicas handle reads and writes while background nodes compact packs.

**「Limited preview」** For now, the 7,200 pushes-per-second and 5,000-agent figures are internal test results, not a service level available to GitHub customers; Rubicon remains in limited private preview, and the source does not describe a public opt-in or migration path. Teams planning highly concurrent agent workloads should continue to design around existing Git and GitHub limits until GitHub widens availability and publishes compatibility details.

<details><summary>References</summary>
<ul>
<li><a href="https://github.blog/engineering/architecture-optimization/inside-githubs-new-git-storage-architecture/">Inside GitHub’s new Git storage architecture - The GitHub Blog</a></li>

</ul>
</details>

**Tags**: `#GitHub`, `#Git storage architecture`, `#AI agents`, `#Azure Blob Storage`, `#distributed systems`

---

<a id="item-tech-news-4"></a>
### [Reported end of Microsoft Research AI Frontiers and Langford&\#x27;s exit](https://hunch.net/?p=13764006) ⭐️ 7.0/10

A Hacker News discussion centers on the reported disbanding of Microsoft Research&\#x27;s AI Frontiers group and the exit of researcher John Langford. Commenters framed the reported change as part of a broader industry narrowing toward transformer scaling and away from exploratory AI research. The submission links to an archived article and a secondary report, and the supplied material does not include Microsoft&\#x27;s own confirmation.

hackernews · srean · Nov 7, 18:02 · [Discussion](https://news.ycombinator.com/item?id=50406563)

**「What AI Frontiers was」** Microsoft Research&\#x27;s AI Frontiers group was founded inside MSR in 2023, after ChatGPT&\#x27;s release, and produced AutoGen, a framework for coordinating AI agents, and Fara, an agent that operates a computer to carry out tasks. Part of the roughly 50-person group also explored ways to improve models without simply scaling them up, and John Langford was the researcher associated with its direction.

**「Impact」** The reported change leaves Microsoft Research without a group described in the discussion as focused on fundamental AI advances, removing a visible institutional home for researchers and collaborators working on approaches outside mainstream scaling. The supplied material does not say whether the group&\#x27;s projects, funding, or staff will be reassigned.

**「Community discussion」** Commenters debated whether the closure reflects a deliberate industry-wide bet on transformer scaling: one argued that large companies now discourage exploratory AI research, while another said research and scaling should not be treated as competing priorities. Another commenter lamented the concentration of billions of dollars in &quot;almost one idea&quot; and the reluctance to fund alternatives such as JEPA.

<details><summary>References</summary>
<ul>
<li><a href="https://www.indiatoday.in/technology/news/story/microsoft-ai-research-clash-john-langford-quits-declares-ai-frontiers-over-3034334-2026-11-07">Microsoft AI research clash: John Langford quits, declares AI ...</a></li>
<li><a href="https://daily.dev/posts/microsoft-researcher-john-langford-exits-ai-frontiers-group-declared-finished-t8nprypt6">Microsoft Researcher John Langford Exits. AI Frontiers Group ...</a></li>

</ul>
</details>

**Tags**: `#AI research`, `#Microsoft Research`, `#AI industry`, `#research culture`, `#transformer models`

---

<a id="item-tech-news-5"></a>
### [Claude Code local settings with secrets found in 1,122 GitHub files](https://apiiro.com/blog/coding-agents-leaking-secrets-github-dont-ask-again) ⭐️ 7.0/10

A security blog post reports finding 1,122 public GitHub files containing Claude Code \`.claude/settings.local.json\` entries where commands approved through “Don&\#x27;t Ask Again” embedded passwords or keys. The exposure is conditional: a developer had to manually create and commit the local settings file and put a secret directly in an approved command; a Claude Code team member identified as Boris said the file is meant to stay local and is auto-gitignored when Claude creates it. Boris said Claude Code has not historically scrubbed secrets but the team is looking into preventing this.

hackernews · shmulc · Nov 7, 20:45 · [Discussion](https://news.ycombinator.com/item?id=50407882)

**「Background」** Claude Code&\#x27;s &quot;Don&\#x27;t Ask Again&quot; option records an approved command in the project&\#x27;s \`.claude/settings.local.json\` file so the agent stops re-prompting for it. That file is designed to stay on the local machine, and a Claude Code team member responding in the discussion said the tool automatically gitignores it when Claude creates it — the reported exposures came from files that were manually created and committed to public repositories, where any secrets written directly into an approved command became readable.

**「Impact」** Developers who committed such a file should remove it from version control and treat any embedded credentials as exposed, since the file is intended to remain local and is auto-gitignored only when Claude creates it.

**「Community discussion」** Commenters disputed the framing: Aurornis argued that pressing “Don&\#x27;t Ask Again” does not by itself expose passwords, and that the finding required committed local settings with manually approved commands containing secrets. Others shared mitigations, including isolating agent tasks in an ephemeral VM behind a restricted API proxy or keeping credentials in 1Password and retrieving them through the \`op\` CLI.

**Tags**: `#Claude Code`, `#security`, `#secret leakage`, `#AI coding agents`, `#GitHub`

---

<a id="item-tech-news-6"></a>
### [Need for Speed: Underground 2 reimplementation runs in browser with multiplayer](https://nfsu2.xyz/) ⭐️ 7.0/10

Need for Speed: Underground 2 has been reimplemented as a browser-playable game at nfsu2.xyz, with working online multiplayer. Commenters say it runs on phones and desktop, and that Linux users need to enable unsafe WebGPU features in Chromium to play. The submission provides no architecture, source, or hosting details, and the site&\#x27;s legal status is unclear; commenters expect a takedown.

hackernews · fluxusars · Nov 7, 09:36 · [Discussion](https://news.ycombinator.com/item?id=50403052)

**「Earlier context」** Need for Speed: Underground 2 is a 2004 racing game that is no longer sold, and one commenter notes that retail copies are largely unplayable on modern PCs. The fan project runs the game in Chrome and Firefox using WebGPU graphics and WebAssembly recompilation, adding free roam and online races with friends.

**「Impact」** Compatibility is gated by WebGPU: the discussion specifically points Linux Chromium users to unsafe WebGPU flags, and no fallback is documented for browsers or GPUs that lack support. Because the project is presented only as a live site, players have no stated way to preserve or self-host the build if it goes offline.

**「Community Discussion」** Commenters are enthusiastic about the nostalgia and multiplayer chaos, with one describing hundreds of cars doing burnouts and honking, while others question the legality of hosting copyrighted content and soliciting donations. A recurring point is that retail copies are largely unplayable on modern PCs, which commenters cite as a preservation argument.

<details><summary>References</summary>
<ul>
<li><a href="https://nfsu2.xyz/">nfsu2.xyz - Underground 2 Revived</a></li>
<li><a href="https://pro-gamer.gg/need-for-speed-underground-2-playable-browser-120-fps-webgpu-multiplayer-free-roam/">Need for Speed: Underground 2 in Browser: 120 FPS &amp; WebGPU ...</a></li>

</ul>
</details>

**Tags**: `#webgpu`, `#browser-gaming`, `#reverse-engineering`, `#abandonware`, `#emulation`

---

<a id="item-tech-news-7"></a>
### [Asahi Linux 7.3 report: first same-day Fedora Asahi Remix release](https://asahilinux.org/2026/11/progress-report-7-3/) ⭐️ 7.0/10

Asahi Linux&\#x27;s 7.3 progress report, as quoted in the discussion, says Fedora Asahi Remix shipped on the same day as Fedora Linux 45 on November 3—the first time the project has achieved same-day release parity with upstream Fedora. The report otherwise covers ongoing Linux development for Apple Silicon, but the available material does not detail specific kernel, graphics, or hardware-support changes.

hackernews · ackyshake · Nov 7, 05:20 · [Discussion](https://news.ycombinator.com/item?id=50401867)

**「背景」** Fedora Asahi Remix 是 Asahi Linux 为 Apple Silicon Mac 发布的主要发行版，它基于 Fedora 构建，并叠加了 Asahi 逆向工程的内核和驱动工作。该报告称，本次发布是 Fedora Asahi Remix 首次在 Fedora 上游版本（Fedora Linux 45）发布当天推出，这意味着此前 Remix 版本要落后于其基于的 Fedora 版本。

**「Impact」** For Fedora Asahi Remix users, same-day availability shortens the gap between the upstream Fedora 45 release and the Apple Silicon remix, making it easier to stay on the current Fedora base. The report excerpt does not establish that this release adds support for previously unsupported Apple Silicon hardware.

**「Community discussion」** Commenters welcomed the same-day release, while one prospective user said missing USB-C display support on a MacBook Air remains a blocker and questioned why support for newer CPUs appears to take priority. Another commenter asked whether the report&\#x27;s licensing warning referred to Omarchy and argued that the project&\#x27;s MIT licensing left it open to exploitation.

**Tags**: `#Asahi Linux`, `#Apple Silicon`, `#Linux`, `#Fedora`, `#Open Source`

---

<a id="item-tech-news-8"></a>
### [Coldframe honeypot mimics Danfoss and Dixell refrigeration controllers](https://github.com/hedgerow-dev/coldframe) ⭐️ 7.0/10

Coldframe is a new open-source Python honeypot that impersonates Danfoss AK-SM 800A and Dixell XWEB supermarket refrigeration controllers, using only the standard library in a single file. Its author tuned the fake interfaces against Shodan records of real units—matching header order, page titles, certificate fields, and TLS versions—and says both personas are currently classified by Shodan as real devices rather than honeypots. The tool recognizes attempts to exploit CVE-2025-41450, Danfoss&\#x27;s &quot;code of the day&quot; login bypass, records whether the submitted code is valid for that day, and tags probes for three other Danfoss CVEs and XWEB vulnerabilities. Default logins open a fake store dashboard with defrost controls, and after one day on two live instances the author reported only generic scanners and Shodan&\#x27;s crawler, refrigerator.census.shodan.io.

hackernews · hedgerow-dev · Nov 7, 17:27 · [Discussion](https://news.ycombinator.com/item?id=50406292)

**「Background」** Danfoss’s March 2025 security advisory described an improper-authentication flaw in its AK-SM8xxA refrigeration controllers that allowed an authentication bypass, with patch 4.2 as the remediation. An October 17, 2026 report on a French supermarket refrigeration cyberattack tied the incident to the AK-SM 800A and CVE-2025-41450, while noting that parts of what happened remained unproven—the context behind Coldframe’s attempt to observe real attacks.

**「Impact」** Security teams studying exposed refrigeration controls can deploy Coldframe without extra dependencies and use its CVE-2025-41450 checks and fake dashboard to observe post-login behavior, but the author&\#x27;s first-day run had not yet captured a targeted exploit.

**「Community discussion」** Commenters questioned the project&\#x27;s evidence base: one warned from experience replicating Wi-Fi cameras that Shodan-derived device data can be unreliable because many exposed units were themselves honeypots or already compromised, and another asked whether the refrigeration incidents were confirmed attacks or just a simultaneous software update.

<details><summary>References</summary>
<ul>
<li><a href="https://www.danfoss.com/en/service-and-support/coordinated-vulnerability-disclosure/danfoss-security-advisories/dsa-2025-03-01/">DSA-2025-03-01 | Danfoss</a></li>
<li><a href="https://thecybersecguru.com/news/french-supermarket-refrigeration-cyberattack/">French Supermarket Cyberattack: Danfoss Refrigeration ...</a></li>

</ul>
</details>

**Tags**: `#honeypot`, `#ICS/OT security`, `#Shodan`, `#CVE-2025-41450`, `#Python`

---

<a id="item-tech-news-9"></a>
### [Researcher claims every Mac since 2022 runs an undocumented personal knowledge graph](https://8rank.ai/game/apple-intelligence-personal-knowledge-graph) ⭐️ 7.0/10

A researcher posting as infwhispers has published an investigation at 8rank.ai arguing that every Mac released since 2022 ships a pair of undocumented daemons that build a personal knowledge graph — who the user is, who they know, how those people relate to each other, and how, where, and when the user communicates with them — including what the title calls a family-member classifier. The author confirmed authorship in the discussion thread and linked follow-up research on the knowledge graph. The claims are the researcher&\#x27;s own reverse-engineering analysis rather than an Apple announcement: no Apple documentation or independent verification of the daemons&\#x27; scope appears in the supplied material, and the post describes a capability that is already shipping rather than a new release.

hackernews · infwhispers · Nov 7, 09:46 · [Discussion](https://news.ycombinator.com/item?id=50403097)

**「Context: on-device personal knowledge graph」** Apple Intelligence features such as resolving which &quot;James&quot; a request means, or who your boss is, rely on an on-device personal knowledge graph rather than a cloud lookup. According to the research cited in coverage of the report, macOS has shipped two daemons — knowledgeconstructiond and intelligenceplatformd — since macOS 13 \(2022\) to build that graph, storing it in ~/Library/IntelligencePlatform as a set of SQLite databases guarded by TCC Full Disk Access, without public documentation from Apple.

**「What the graph is used for」** The concrete function described in the thread is context for local models: a request like &quot;Text James&quot; or &quot;tell my boss I&\#x27;m not coming in tomorrow&quot; only resolves if the system already knows which James and which boss, so the accuracy of the inferred relationships directly affects whether Siri-style requests work. For users, the unresolved issue is inspection and consent — the supplied material cites no Apple documentation or interface for viewing or clearing the inferred relationships, and readers seeking details are pointed to the researcher&\#x27;s write-up and follow-up post.

**「Utility versus ambient recall」** Commenters split between treating the graph as an extension of existing behavior and as a consent problem: one argued that Photos already knows the names and faces of family members and even pets, so a relationship graph should not be surprising, while another said the capability might be useful if opt-in but that ambient recall of conversations changes the social expectations of a chat regardless of consent. The author took part directly, answering questions and linking the follow-up research.

<details><summary>References</summary>
<ul>
<li><a href="https://techplanet.today/post/apples-hidden-personal-knowledge-graph-understanding-macoss-undocumented-family-classifier">Apple&#x27;s Hidden Personal Knowledge Graph: Understanding macOS ...</a></li>
<li><a href="https://techbytes.app/posts/every-mac-comes-with-an-undocumented-family-member-classifier/">Every Mac comes with an (undocumented) family member classifier</a></li>
<li><a href="https://daily.dev/posts/every-mac-comes-with-an-undocumented-family-member-classifier-s3lfxwdun">Every Mac comes with an (undocumented) family member classifier</a></li>

</ul>
</details>

**Tags**: `#Apple Intelligence`, `#privacy`, `#personal knowledge graph`, `#macOS`, `#reverse engineering`

---

<a id="item-tech-news-10"></a>
### [Claude Code report alleges web requests leaked login emails](https://github.com/anthropics/claude-code/issues/107757) ⭐️ 7.0/10

A developer report alleges that Claude Code inserted users&\#x27; login email addresses into outbound web requests, leading to a large volume of scam emails. An Anthropic engineer said the email had been placed in model context to stop Claude inventing author names; the issue was reported in July and emails were sent to sites including Wikipedia and the U.S. Securities and Exchange Commission. Version 2.1.317 added a block, but it can be bypassed with a Python script, and Anthropic plans to remove the login email from model context in the next version.

telegram · zaihuapd · Nov 7, 08:09

**「Background」** Claude Code is Anthropic&\#x27;s agentic coding tool, and it can issue web requests on a user&\#x27;s behalf. According to the report, the login email entered the model context as a workaround for Claude inventing author names, and the resulting exposure was first reported in July, when the address was sent to sites including Wikipedia and the U.S. Securities and Exchange Commission.

**「Exposure risk persists until the planned fix ships」** Users whose Claude Code sessions triggered web searches had their account login email placed in the User-Agent header sent to third-party sites; the reporter of the GitHub issue attributes dozens of scam emails per day to that exposure. Since the 2.1.317 block can be bypassed by Python scripts and removing the login email from model context is only planned for the next release, users on affected versions cannot treat the current mitigation as a complete fix and should watch for the upcoming version.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/anthropics/claude-code/issues/107757">Bug Report: Privacy violation in User-Agent header · Issue # 107757 ...</a></li>

</ul>
</details>

**Tags**: `#Claude Code`, `#privacy`, `#security vulnerability`, `#AI coding tools`, `#Anthropic`

---

<a id="item-tech-news-11"></a>
### [Apple discloses HALO humanoid control system using two Qwen models](https://weibo.com/1642634100/RqjjGllvw) ⭐️ 7.0/10

Apple researchers reported on arXiv on Nov. 4 that they built HALO, a three-layer autonomous control system for humanoid robots, and validated it on a Unitree G1 by transferring motions learned in simulation to an unfamiliar real room. The top layer uses Qwen3.6-35B-A3B to orchestrate tasks, the middle layer uses Qwen3.5-2B to generate motions, and the bottom layer is a reinforcement-learning-trained action tracker. The team released code for data generation, model training, and deployment, according to the report, though the item is a secondary social-media relay and does not supply the arXiv identifier.

telegram · zaihuapd · Nov 7, 13:35

**「Background」** Sim-to-real transfer is the problem of running a control policy trained in simulation on a physical robot despite differences in sensing, dynamics, and environment. HALO&\#x27;s approach, as described in the paper abstract, is to generate egocentric vision-language-motion training data entirely in simulation and then run the resulting policy fully onboard the physical robot; Apple&\#x27;s ml-halo repository hosts the implementation.

**「Impact」** Developers can inspect and potentially reproduce the released data-generation, training, and deployment pipeline on a Unitree G1, but the reported sim-to-real result is a research validation rather than a supported product or a guarantee that the same stack will work on other humanoid platforms.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/html/2611.06908">Perceptive Humanoid Motion from Simulation - arXiv.org</a></li>
<li><a href="https://github.com/apple-aiml-research/ml-halo">GitHub - apple-aiml-research/ml-halo: HALO: Perceptive ...</a></li>

</ul>
</details>

**Tags**: `#humanoid robotics`, `#sim-to-real`, `#LLM robotics`, `#Apple research`, `#open-source code`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Berkshire more than doubles Q3 buybacks as operating earnings decline](https://www.cnbc.com/2026/11/07/berkshire-hathaway-q3-2026-earnings-buybacks.html) ⭐️ 7.0/10

Berkshire Hathaway repurchased $9.6 billion of its own stock in the third quarter, more than double the $4.5 billion bought in the second quarter, even as operating earnings fell 5.8% year over year to $12.705 billion.

rss · CNBC Finance · Nov 7, 15:23

**「Background」** Operating earnings cover Berkshire’s wholly owned businesses and exclude its stock portfolio; including investment gains, overall earnings fell 28% to $22.112 billion.

**Tags**: `#Berkshire Hathaway`, `#share buybacks`, `#earnings`, `#insurance`, `#cash reserves`

---

<a id="item-finance-news-2"></a>
### [SoftBank, ABB Weigh China Carve-Out to Salvage $5.4 Billion Robotics Deal](https://www.bloomberg.com/news/articles/2026-11-07/softbank-abb-weigh-china-carve-out-to-salvage-robotics-deal) ⭐️ 7.0/10

SoftBank and ABB are considering separating ABB&\#x27;s China robotics operations into a standalone entity with different shareholding rights, in an attempt to rescue their $5.4 billion acquisition after China&\#x27;s foreign investment security review office halted the deal on Thursday, Bloomberg reported. People familiar with the matter said the plan may fail and that ABB is also weighing alternatives, including finding another buyer; those people put a possible valuation of $2 billion to $3 billion on the business. Both companies declined to comment, Bloomberg said.

telegram · zaihuapd · Nov 7, 11:24

**「Background」** China&\#x27;s Office of the Working Mechanism for Foreign Investment Security Review, part of the state planner, prohibited SoftBank&\#x27;s $5.4 billion acquisition of ABB&\#x27;s robotics business earlier this week, ABB said, confirming it was told of the decision by SoftBank. The proposed carve-out would separate the Chinese portion of the robotics unit into its own entity so the rest of the transaction could proceed.

<details><summary>References</summary>
<ul>
<li><a href="https://www.abb.com/global/en/news/140154/update-on-divestment-of-abb-robotics">Update on divestment of ABB Robotics</a></li>
<li><a href="https://www.ft.com/content/f10c3e24-45e4-47ff-bde2-24a8de90aec4?syn-25a6b1a6=1">China blocks SoftBank’s $5.4bn takeover of ABB’s robotics ...</a></li>
<li><a href="https://www.reuters.com/business/media-telecom/softbank-abb-explore-china-carve-out-salvage-robotics-deal-bloomberg-news-2026-11-07/">SoftBank, ABB explore China carve-out to salvage robotics ...</a></li>

</ul>
</details>

**Tags**: `#SoftBank`, `#ABB`, `#robotics M&amp;A`, `#China foreign investment review`, `#corporate carve-out`

---