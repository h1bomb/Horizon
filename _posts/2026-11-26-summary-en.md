---
layout: default
title: "Horizon Summary: 2026-11-26 (EN)"
date: 2026-11-26
lang: en
---

> From 36 items, 9 important content pieces were selected

---

**Technology News**
1. [1Password says breach exposed customer account metadata, not vaults](#item-tech-news-1) ⭐️ 8.0/10
2. [Shorter Lean version of Anthropic&\#x27;s GRH verification discussed](#item-tech-news-2) ⭐️ 8.0/10
3. [Ubuntu&\#x27;s slow security patching draws migration reports](#item-tech-news-3) ⭐️ 7.0/10
4. [Tencent open-sources Hy4 flash GGUF weights; smallest reportedly runs on 64 GB Mac mini](#item-tech-news-4) ⭐️ 7.0/10
5. [Minecraft Java RCE reported via resource-pack TrueType fonts](#item-tech-news-5) ⭐️ 7.0/10
6. [Samsung and SK Hynix reportedly to license YMTC&\#x27;s Xtacking NAND stacking tech](#item-tech-news-6) ⭐️ 7.0/10
7. [FCC approves SpaceX&\#x27;s 1 million-satellite Starmind data-center constellation](#item-tech-news-7) ⭐️ 7.0/10

**Financial News**
1. [Court Filing: US Commerce Department Pressured Intel for 10% Stake](#item-finance-news-1) ⭐️ 9.0/10
2. [US reportedly plans new Section 301 tariffs on 14 trading partners](#item-finance-news-2) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [1Password says breach exposed customer account metadata, not vaults](https://1password.com/blog/update-on-nov-2026-security-incident) ⭐️ 8.0/10

1Password confirmed a November 2026 security incident in which an attacker used a compromised employee enterprise GitHub account to access source code and push malicious code to backend services, leading to the download of some customer account information. The data included names, email addresses, account identifiers, and account creation and last-login times, according to the company. 1Password says customer vaults and their contents were not affected and has not disclosed how many users were exposed. The company disabled the involved account, rotated or revoked potentially exposed internal credentials, strengthened verification for invitation and recovery emails, and said users do not need to change their accounts but should watch for phishing.

hackernews · lxhrstn · Nov 25, 17:18 · [Discussion](https://news.ycombinator.com/item?id=50644817)

**「Background」** 1Password runs a hosted password-management service, so customers rely on its backend systems, not just the apps they install. In that environment, an employee&\#x27;s GitHub account can carry access to source code and deployment paths, making it a supply-chain entry point: code pushed through it can reach backend services rather than stay confined to a repository.

**「Impact」** 1Password&\#x27;s public update does not state how many customers were affected, so customers cannot use it to determine whether their own account metadata was taken. The company says no account change is required, but advises users to remain alert for phishing.

**「Community discussion」** Commenters focused on compromised employee laptops as a standard SaaS attack path, with tptacek arguing the likelihood rises with headcount and ctidd asking whether branch protection or restrictions on pushing to main failed. qixxiq reported receiving a high-quality phishing email that used some personal details but did not come from an official 1Password domain.

<details><summary>References</summary>
<ul>
<li><a href="https://1password.com/blog/update-on-nov-2026-security-incident">Update on a security incident involving... | 1 Password</a></li>

</ul>
</details>

**Tags**: `#security incident`, `#password manager`, `#supply chain security`, `#SaaS`, `#phishing`

---

<a id="item-tech-news-2"></a>
### [Shorter Lean version of Anthropic&\#x27;s GRH verification discussed](https://github.com/lsernau/grh-lean) ⭐️ 8.0/10

A GitHub repository by lsernau publishes a much shorter Lean formalization of Anthropic&\#x27;s GRH verification, which Hacker News commenters describe as far more readable and heavily documented. Commenters report the proof shrinking from roughly 17 million lines to about 76 thousand, a 99.56% reduction, though another commenter refers to a 300k-line proof, so the precise figures are not verified by the item itself. Commenters also note the rewrite separates &quot;known math&quot; from &quot;new math&quot; and includes human-readable documentation throughout. The item supplies no source content, so the artifact&\#x27;s correctness, completeness, and fidelity to the original formalization remain unestablished here.

hackernews · nb-t · Nov 25, 21:48 · [Discussion](https://news.ycombinator.com/item?id=50648050)

**「Background」** The compact repository is a follow-up to Anthropic&\#x27;s earlier, much larger Lean formalization of a claimed Generalized Riemann Hypothesis proof: the new project covers the same five theorems in about 76,000 lines and requires Lean v4.35.0 and Mathlib at commit 56a00585. NPR had reported that an Anthropic mathematician claimed to have solved a &quot;Holy Grail&quot; math problem with Claude.

**「Impact」** For Lean users and mathematicians attempting to review the result, the practical difference is auditability: a 76k-line proof with inline documentation and an explicit known-math/new-math split is far easier to step through than a multi-million-line formalization, according to commenters. Anyone building on it should still check the repository against the original Anthropic formalization and confirm it compiles in Lean, since nothing in the supplied material independently verifies the proof.

**「Community discussion」** Commenter gre asked whether the shortened, documented proof answers Terence Tao&\#x27;s recent argument that enormous proofs yielding no insight are a problem, or whether smarter LLMs can now &quot;golf&quot; and explain such proofs. AIShill101 argued that Lean code is not a substitute for a conventional mathematical paper, wanting mathematicians who understand the core argument to present it at a conference.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/lsernau/grh-lean">GitHub - lsernau / grh - lean : A short Lean 4 proof of the Generalized...</a></li>
<li><a href="https://www.npr.org/2026/11/21/g-s1-154922/anthropic-worker-claims-to-have-solved-a-holy-grail-of-math-problems-with-the-help-of-ai">Anthropic worker claims to have solved a Holy Grail of math... : NPR</a></li>

</ul>
</details>

**Tags**: `#Lean`, `#formal-verification`, `#theorem-proving`, `#AI-assisted-mathematics`, `#open-source`

---

<a id="item-tech-news-3"></a>
### [Ubuntu&\#x27;s slow security patching draws migration reports](https://www.openwall.com/lists/oss-security/2026/11/25/9) ⭐️ 7.0/10

An oss-security mailing-list post from November 25, 2026, and the Hacker News thread that followed focused on slow Ubuntu security patch turnaround, with commenters describing operational responses rather than any announced change from Canonical. The original mailing-list message was not included in the supplied material, so the specific packages, vulnerabilities, and timelines at issue could not be verified. The concrete evidence here is anecdotal: one commenter says their employer moved all server images from Ubuntu to Debian over the delay, and another says they chose Debian for a generic Linux VM for the first time for the same reason. No Canonical statement, patch-latency measurement, or independent benchmark was available.

hackernews · gslin · Nov 25, 20:38 · [Discussion](https://news.ycombinator.com/item?id=50647181)

**「Background」** The complaint is tied to a specific case: the oss-security post says a fix for CVE-2026-98432, a remote TCP corruption flaw, took Ubuntu multiple weeks to appear. Ubuntu&\#x27;s security tracker publishes per-CVE dates, so the lag can be compared against the disclosure and update records.

**「Impact」** For teams running Ubuntu servers, the thread surfaces two specific operational choices: migrating generic server images to Debian, or widening unattended upgrades from the security pocket to all updates. One commenter reports doing the latter after observing that many security fixes appear in -updates hours before reaching the security repository, accepting the added regression risk in exchange for faster coverage.

**「Community discussion」** Commenters split between treating the delay as unacceptable for a widely used distribution and cautioning that fast patching carries regression risk — one cites Debian bug \#1154101 as an example of a regression slipping through despite good QA. Another quotes a 2025 stable-kernel maintainer argument that selectively cherry-picking patches leaves a system both insecure and buggy, implying that full stable/LTS uptake, not cherry-picking, is the sound approach; this is a quoted opinion, not a measured finding about Ubuntu.

<details><summary>References</summary>
<ul>
<li><a href="https://www.openwall.com/lists/oss-security/2026/11/25/9">oss - security - Slow Ubuntu security response times</a></li>
<li><a href="https://ubuntu.com/security/CVE-2026-8674">CVE- 2026 -8674 | Ubuntu</a></li>

</ul>
</details>

**Tags**: `#Ubuntu`, `#Linux distributions`, `#security patching`, `#open source`, `#Debian`

---

<a id="item-tech-news-4"></a>
### [Tencent open-sources Hy4 flash GGUF weights; smallest reportedly runs on 64 GB Mac mini](https://mp.weixin.qq.com/s/o0xxShVQX6g2UllrrEv1WQ) ⭐️ 7.0/10

Tencent Hunyuan has released GGUF quantized weights for its 224-billion-parameter Hy4 flash model through its AngelSlim compression toolkit. The original weights are about 410.27 GiB, while the smallest IQ2-AH quantized version is 125.73 GiB, roughly 30% of the original, and is reported to run on a 64 GB Mac mini using the Strata offload framework. The release report cites 89 tokens/s at 10K context on a 48 GB VRAM device and 47 tokens/s at 32K context with Q3\_K on an M5 Max with 128 GB, plus a score gap of no more than 0.4 points versus the original on DeepSWE v1.1. These figures come from a Telegram aggregator summary and are not independently verified; no methodology was provided.

telegram · zaihuapd · Nov 25, 09:29

**「Background」** Tencent’s Hugging Face model card describes Hy4 flash as a sparse model that activates only 12B parameters per token, accepts text and image inputs, and supports up to a 1M-token context window \[tool-2-2\]. GGUF is a format for distributing quantized weights for local inference; this release packages Hy4 flash in that format through Tencent’s AngelSlim compression toolkit, and the smallest variant is reported to run via Strata offload.

**「Impact」** For local-inference developers, the practical route to Hy4 flash is now a GGUF build used with Strata offload rather than the full ~410 GiB checkpoint, but the smallest variant still requires a ~126 GiB weight file and enough system memory to offload, and the quoted 32K-context Q3\_K throughput was measured on a 128 GB M5 Max, so smaller machines should expect tighter memory and storage constraints.

<details><summary>References</summary>
<ul>
<li><a href="https://huggingface.co/tencent/Hy4-flash">tencent / Hy 4 - flash · Hugging Face</a></li>

</ul>
</details>

**Tags**: `#open-source models`, `#quantization`, `#local LLM inference`, `#model compression`, `#Tencent Hunyuan`

---

<a id="item-tech-news-5"></a>
### [Minecraft Java RCE reported via resource-pack TrueType fonts](https://github.com/bikini/minecraft2shell) ⭐️ 7.0/10

On November 22, a public proof-of-concept called minecraft2shell reported a high-severity remote code execution flaw in Minecraft Java Edition: a crafted TrueType font delivered through a server resource pack triggers a native out-of-bounds write in FreeType 2.14.3 and earlier and can execute code on a Windows client. The report lists Java 1.20.5 through 1.21.10 and snapshots 26.1 through 26.4 as affected, while 1.20.4 and earlier and Bedrock Edition are not. Mojang still ships lwjgl-freetype 3.4.3 and has no official patch, according to the post; the community m2sfix 1.0.0, published November 24, disables hinting through a Java agent or mod. The claim comes from a Telegram post and a public PoC, not an official advisory, so the exact affected-version and execution details are not independently confirmed here.

telegram · zaihuapd · Nov 25, 12:46

**「Background」** Java Edition renders in-game text through FreeType, and server resource packs can carry custom font files, so a malicious pack reaches the font parser when the client loads it. The public proof of concept targets TrueType hinting during glyph loading, using a crafted composite glyph to trigger a native out-of-bounds write; a LiquidBounce write-up says the demo was published on November 22 without notifying Mojang first.

**「Impact」** Until an official fix ships, the post advises players not to add any resource packs and server operators to disable server resource-pack prompts or install m2sfix 1.0.0. Because the described exposure path is a server-supplied resource pack, joining a server that pushes a malicious pack is the practical concern for affected Java clients.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/bikini/minecraft2shell">GitHub - bikini/ minecraft 2 shell : Minecraft to native RCE · GitHub</a></li>
<li><a href="https://liquidbounce.net/blog/minecraft2shell-vulnerability-AK0X5CE6">Minecraft 2 Shell Vulnerability</a></li>

</ul>
</details>

**Tags**: `#Minecraft`, `#RCE`, `#FreeType`, `#security vulnerability`, `#Java`

---

<a id="item-tech-news-6"></a>
### [Samsung and SK Hynix reportedly to license YMTC&\#x27;s Xtacking NAND stacking tech](https://tech.ifeng.com/c/8yLRPKxQy4L) ⭐️ 7.0/10

Samsung Electronics and SK Hynix have reportedly agreed, through a cross-licensing arrangement, to use parts of Yangtze Memory Technologies&\#x27; Xtacking technology in their 3D NAND flash. All three companies declined to comment, so the scope, terms, and timing of any agreement are unconfirmed. Xtacking builds the memory-cell array and the CMOS control circuitry on two separate wafers and joins them with a bonding step, allowing each part to be manufactured and optimized independently. An Omdia senior analyst cited in the report said this separation lets a manufacturer produce its own memory array while having the logic die made by a foundry on a more advanced process node.

telegram · zaihuapd · Nov 25, 14:33

**「Background」** Xtacking is not new: Yangtze Memory unveiled the architecture at the Flash Memory Summit alongside its 64-layer 3D NAND, separating the memory array and CMOS logic onto two wafers that are then bonded so each half can be produced and optimized independently. As NAND makers push past 300 layers — SK Hynix has disclosed a 321-layer 4D NAND sample — wafer-bonding schemes such as CbA have become a central scaling approach, which is why Xtacking patents now matter to the largest suppliers.

**「Patent leverage in hybrid bonding」** If the reported cross-licensing holds, it signals that hybrid-bonding patents have become a gate for next-generation 3D NAND: industry sources cited by TrendForce count 119 YMTC hybrid-bonding-related patents published between 2017 and January 2024, versus 83 for Samsung and 11 for SK hynix as of 2023. Memory makers shifting to wafer-to-wafer stacking may therefore need YMTC licenses, not just their own process know-how.

<details><summary>References</summary>
<ul>
<li><a href="https://www.icsmart.cn/65336/">长 江 存 储 被制裁一年后， 三 星 、 SK 海 力 士 宣布 3 D NAND 将迈入300...</a></li>
<li><a href="https://www.esmchina.com/news/3936.html">长 江 存 储 首次弯道超车！ 重磅发布 Xtacking 技术，下一代64...</a></li>
<li><a href="https://www.trendforce.com/news/2026/11/25/news-sk-hynix-reportedly-joins-samsung-in-licensing-ymtcs-xtacking-technology-as-nand-race-heats-up/">[News] SK hynix Reportedly Joins Samsung in Licensing...</a></li>

</ul>
</details>

**Tags**: `#semiconductors`, `#3D NAND`, `#Xtacking`, `#Samsung`, `#SK Hynix`

---

<a id="item-tech-news-7"></a>
### [FCC approves SpaceX&\#x27;s 1 million-satellite Starmind data-center constellation](https://www.geekwire.com/2026/fcc-clears-spacex-million-satellites-starmind-data-center/) ⭐️ 7.0/10

The FCC has approved SpaceX to deploy up to 1 million satellites for Starmind, an orbital data-processing network, operating at altitudes of 500 to 1002 kilometers. The regulator called it the first US approval of a space data-center constellation. The authorization carries conditions including communications backup, periodic progress filings, and a detailed orbital-debris mitigation plan; the first satellite must be in operation no later than 2033, and the full constellation must be operating by 2040. The FCC rejected objections from Amazon, Viasat, and the American Astronomical Society.

telegram · zaihuapd · Nov 26, 04:45

**「Background」** The FCC&\#x27;s action is a commercial satellite license, the regulatory step that lets a constellation operate in assigned orbits and frequencies; Starmind would use orbiting satellites as data-processing nodes. The order came after Amazon, Viasat, and the American Astronomical Society opposed the request, and it sets staged milestones: one operational Starmind satellite within seven years, 100,000 by November 2035, and the full 1 million by November 2040.

**「Impact」** SpaceX&\#x27;s 2033 first-satellite and 2040 full-constellation dates, along with the periodic progress reports and debris-mitigation plan, are now binding authorization conditions rather than internal targets. The FCC&\#x27;s rejection of objections from Amazon, Viasat, and the American Astronomical Society means those challenges did not block the approval; the source does not describe the grounds for the objections.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/25/spacex-fcc-satellite-approval.html">SpaceX wins FCC approval for 1 million orbital data center satellites</a></li>
<li><a href="https://arstechnica.com/space/2026/11/the-fcc-has-authorized-spacex-to-deploy-1-million-satellites/">The FCC has authorized SpaceX to deploy 1 million satellites</a></li>

</ul>
</details>

**Tags**: `#SpaceX`, `#FCC`, `#space data centers`, `#satellite constellations`, `#regulatory approval`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Court Filing: US Commerce Department Pressured Intel for 10% Stake](https://www.wired.com/story/inside-trumps-demands-to-another-chips-ceo/) ⭐️ 9.0/10

Court filings show that in August 2025 a U.S. Commerce Department lawyer told Intel’s CFO the board could reject a demand for a 10% equity stake but warned of unpredictable consequences; days later Intel’s board transferred the shares, and President Trump said the government paid nothing for a stake now worth about $11 billion.

telegram · zaihuapd · Nov 25, 13:25

**「Background」** The stake fits a broader pattern of the Trump administration taking equity positions in private companies; an Intel shareholder lawsuit has alleged the government extorted the chipmaker into giving up the 10% holding.

**「Impact」** Intel&\#x27;s other shareholders now share ownership with the U.S. government, whose 10% stake gives it a direct financial interest in — and potential influence over — the chipmaker.

<details><summary>References</summary>
<ul>
<li><a href="https://www.nytimes.com/2026/07/13/business/economy/trump-equity-stakes-ai.html">Trump Administration Is Snapping Up Stakes in Private Companies.</a></li>
<li><a href="https://www.npr.org/2025/08/22/nx-s1-5509673/trump-says-us-government-will-take-stake-intel">Intel will give the U . S . government a 10% stake , Trump says : NPR</a></li>

</ul>
</details>

**Tags**: `#Intel`, `#美国政府`, `#半导体`, `#股权收购`, `#产业政策`

---

<a id="item-finance-news-2"></a>
### [US reportedly plans new Section 301 tariffs on 14 trading partners](https://www.cnbc.com/2026/11/25/us-tariffs-trump-section-301.html) ⭐️ 8.0/10

The US government is reportedly planning new Section 301 tariffs on 14 trading partners, including China and the EU, targeting manufacturing overcapacity; China would face an additional 20% on top of the 25% tariffs imposed in 2018, and the new China tariff could rise to 40% if China does not comply with the October 2025 Busan trade truce.

telegram · zaihuapd · Nov 25, 13:59

**「Background」** Section 301 of the 1974 US Trade Act lets Washington impose tariffs on trading partners found to be engaged in unfair trade practices; this proposal follows an eight-month investigation into subsidised foreign manufacturing and is intended to replace levies the Supreme Court struck down earlier this year. China&\#x27;s extra 20% would sit on top of the 25% added in 2018, and could reach 40% if Beijing does not honour the October 2025 Busan truce between Presidents Trump and Xi in South Korea.

<details><summary>References</summary>
<ul>
<li><a href="https://www.foxbusiness.com/fox-news-global-economy/trump-admin-raise-tariffs-china-eu-other-trading-partners">Trump administration proposes sweeping Section 301 tariffs on...</a></li>
<li><a href="https://www.cnbc.com/2025/10/30/trump-xi-south-korea-rare-earth-tariff-trade-war-nvidia.html">What Trump and Xi agreed to in the U . S .- China trade truce</a></li>
<li><a href="https://www.aa.com.tr/en/americas/us-presses-china-to-immediately-honor-busan-trade-commitments/4114671">Anadolu Ajansı: US presses China to ‘immediately’ honor Busan trade ...</a></li>

</ul>
</details>

**Tags**: `#tariffs`, `#trade policy`, `#Section 301`, `#China-US trade`, `#global trade`

---