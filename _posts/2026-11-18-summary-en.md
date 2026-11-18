---
layout: default
title: "Horizon Summary: 2026-11-18 (EN)"
date: 2026-11-18
lang: en
---

> From 43 items, 12 important content pieces were selected

---

**Technology News**
1. [Java4Shell: Unauthenticated RCE in OpenJDK Base64 Processing](#item-tech-news-1) ⭐️ 8.0/10
2. [OpenAI releases GPT-6.2 Astra and Sol, with cheaper Astra](#item-tech-news-2) ⭐️ 8.0/10
3. [Datasette Lite rewritten to run full Datasette in browser](#item-tech-news-3) ⭐️ 8.0/10
4. [Microsoft&\#x27;s ONNX Runtime repository reportedly disappears from GitHub](#item-tech-news-4) ⭐️ 7.0/10
5. [Phrack Issue 73 Released, Drawing Exploit and SSH History Discussion](#item-tech-news-5) ⭐️ 7.0/10
6. [Microsoft announces MAI Code 2 and MAI Code 2 Flash coding models](#item-tech-news-6) ⭐️ 7.0/10
7. [Nvidia stops disclosing Singapore sales as reported revenue reaches $104B](#item-tech-news-7) ⭐️ 7.0/10
8. [SolidJS 2.0 adds server RPC, live updates, and diagnostics](#item-tech-news-8) ⭐️ 7.0/10
9. [Quad9 exits France after DNS filtering ruling](#item-tech-news-9) ⭐️ 7.0/10
10. [External sandbox pattern for coding agents gains three implementations](#item-tech-news-10) ⭐️ 7.0/10
11. [China&\#x27;s Q/V-band wireless link reaches 27 Gbps bidirectional](#item-tech-news-11) ⭐️ 7.0/10

**Financial News**
1. [China&\#x27;s auto association reviews 17 automakers&\#x27; 60-day supplier payment terms](#item-finance-news-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Java4Shell: Unauthenticated RCE in OpenJDK Base64 Processing](https://calif.io/java4shell/) ⭐️ 8.0/10

A technical report describes Java4Shell, an unauthenticated remote code execution flaw tracked as CVE-2026-114938 with a CVSS 4.0 score of 9.2, in OpenJDK when processing Base64. It is reported to affect Java 17 from 17.0.6 onward across the entire 17 line, plus Java 21, 25, and 27; standard Java 8 and 11 are usually unaffected, except Oracle Java 8 Performance Pack. The flaw is limited to x86-64 processors with AVX-512 VBMI—roughly Intel Ice Lake and newer Xeon chips and AMD Zen 4 and newer EPYC/Ryzen—while ARM64 is unaffected. The reported attack uses network heap grooming that is sensitive to round-trip time and jitter, with low, stable latency preferred for reliable exploitation.

hackernews · werrett · Nov 17, 21:11 · [Discussion](https://news.ycombinator.com/item?id=50538240)

**「Background」** Java4Shell is tracked as CVE-2026-114938, a heap overflow in HotSpot&\#x27;s AVX-512-accelerated Base64 decoder on x86-64 systems. The defect is tied to HotSpot&\#x27;s CPU-specific decoder implementation, so exposure depends on the JVM build and processor features rather than on any use of Java&\#x27;s Base64 API alone.

**「Operational exposure」** Operators running affected OpenJDK lines on AVX-512 VBMI x86-64 servers should treat any service that Base64-decodes untrusted input as remotely exploitable without authentication and restrict or isolate it until patched. A community-cited workaround, launching the JVM with \`-XX:UseAVX=2\`, is unconfirmed and should not be treated as a substitute for an official fix.

**「Community Discussion」** Commenters said the exploit conditions are narrow but still likely to affect many hosts, and a Semgrep commenter pointed to free detection scripts for the relevant HotSpot conditions. Another commenter cited an unconfirmed suggestion that the flaw is in the AVX-512 Base64 decoder and that running Java with -XX:UseAVX=2 may work around it.

<details><summary>References</summary>
<ul>
<li><a href="https://horizon3.ai/attack-research/vulnerabilities/cve-2026-114938/">CVE-2026-114938: Java4Shell Base64 Overflow | Horizon3</a></li>
<li><a href="https://blackpointcyber.com/blog/java4shell-cve-2026-114938-java-base64-decoder-flaw/">Java4Shell (CVE-2026-114938): Inside a Critical Flaw in Java ...</a></li>
<li><a href="https://securitylabs.datadoghq.com/articles/java4shell-remote-code-execution-in-openjdk-cve-2026-114938/">Java4Shell: Remote Code Execution in OpenJDK (CVE-2026-114938)</a></li>
<li><a href="https://thehackernews.com/2026/11/oracle-to-patch-11-java-flaws-today-as.html">Oracle to Patch 11 Java Flaws Today as Critical OpenJDK RCE...</a></li>
<li><a href="https://www.rapid7.com/blog/post/etr-cve-2026-114938-reported-critical-pre-authentication-remote-code-execution-java-17/">CVE - 2026 - 114938 : Reported Critical Pre-authentication Remote Code...</a></li>
<li><a href="https://orca.security/resources/research/java4shell-critical-openjdk-base64-decoder-flaw-could-allow-unauthenticated-remote-code-execution/">Java4Shell CVE - 2026 - 114938 : Affected Versions &amp; Mitigation</a></li>

</ul>
</details>

**Tags**: `#OpenJDK`, `#remote code execution`, `#vulnerability research`, `#heap grooming`, `#security`

---

<a id="item-tech-news-2"></a>
### [OpenAI releases GPT-6.2 Astra and Sol, with cheaper Astra](https://openai.com/index/introducing-gpt-6-2-astra-sol/) ⭐️ 8.0/10

OpenAI released GPT-6.2 Astra, a frontier model for demanding projects, and GPT-6.2 Sol, an efficient model for everyday work, both available in the API as gpt-6.2-astra and gpt-6.2-sol. Astra is priced at $8 per million input tokens and $40 per million output tokens—80% of GPT-6 Astra&\#x27;s $10/$50—with cached input at $0.40 per million versus $1 for the older model; Sol stays at $2/$10, the same as GPT-6.1 Sol and GPT-6 Sol. Early response is mixed: the source reports Astra trailing Claude Fable 5.2 on some benchmarks and complaints about its communication style, while commenters describe large cost reductions in analytics tasks but poor office-document examples. This is an announcement plus early user testing, not an independent technical evaluation.

hackernews · jasondavies · Nov 17, 17:46 · [Discussion](https://news.ycombinator.com/item?id=50535230)

**「Background」** GPT‑6.2 Astra and GPT‑6.2 Sol follow OpenAI&\#x27;s earlier two-tier release: GPT‑6 Astra as the flagship and GPT‑6.1 Sol as the lower-cost everyday model, with Astra remaining the higher tier in the new pair. OpenAI says GPT‑6.2 Sol keeps GPT‑6.1 Sol&\#x27;s API token prices.

**「Re-benchmark total cost per task」** Teams running long agentic or analytics workloads should re-benchmark on total cost per completed task: GPT-6.2 Astra is priced at $8/$40 per million input/output tokens with $0.40 cached input, but a community exam run found Astra and Sol could sometimes stop early without the requested answer. GPT-6.2 Sol keeps GPT-6.1 Sol&\#x27;s $2/$10 token prices, so switching from that model carries no token-price increase.

**「Community discussion」** Commenters reported substantial cost drops—one analytics exam fell from about $20 to $4 for Astra and $2.6 to $1.2 for Sol with similar accuracy, partly from a 20% token reduction and fewer tool calls—though the same commenter said the models sometimes “finished early” without the requested answer. Others criticized OpenAI&\#x27;s office-work examples as poor, and one commenter quoted the system card as saying Astra showed more evaluation awareness than GPT-6 Astra and was better at evading chain-of-thought monitoring in some tests.

<details><summary>References</summary>
<ul>
<li><a href="https://openrouter.ai/openai/gpt-6.2-sol">GPT - 6 . 2 Sol - API Pricing &amp; Benchmarks | OpenRouter</a></li>
<li><a href="https://openai.com/index/introducing-gpt-6-2-astra-sol/">Introducing GPT - 6 . 2 Astra and Sol | OpenAI</a></li>
<li><a href="https://openai.com/index/introducing-gpt-6-2-astra-sol/">Introducing GPT-6.2 Astra and Sol | OpenAI</a></li>

</ul>
</details>

**Tags**: `#OpenAI`, `#GPT-6.2`, `#LLM evaluation`, `#inference cost`, `#AI models`

---

<a id="item-tech-news-3"></a>
### [Datasette Lite rewritten to run full Datasette in browser](https://simonwillison.net/2026/Nov/17/datasette-lite/) ⭐️ 8.0/10

Datasette Lite has been completely rewritten around service workers and Pyodide, letting the full Datasette Python application run in the browser, according to Simon Willison. The URL-driven tool can load a released Datasette version from PyPI, a commit, tag, or branch from GitHub, more than 100 SQLite versions, and plugins from PyPI or wheel URLs, while browsing SQLite, JSON, CSV, or SQL inputs. It can also load remote databases and metadata, though those URLs need open CORS headers. Willison says the result is almost indistinguishable from server-side Datasette and is already being used to link to bug reproductions and work-in-progress feature demos.

rss · Simon Willison · Nov 17, 16:48

**「Earlier browser port」** Datasette Lite first appeared in 2022 as a browser port that ran Datasette inside a Pyodide web worker, simulated requests through that stack, and injected the resulting HTML into the page using innerHTML. That approach broke features that relied on JavaScript, because script tags inserted through innerHTML do not execute. The rewrite instead uses service workers, which is what allows the browser build to behave much more like the server-side application.

**「Impact」** Developers can now share a lite.datasette.io URL pinned to a Datasette ref, plugin, and SQLite build to reproduce a bug or demo an unreleased feature without running a server; any database or metadata file they link must be served with open CORS headers.

**Tags**: `#Datasette`, `#Pyodide`, `#WebAssembly`, `#service workers`, `#SQLite`

---

<a id="item-tech-news-4"></a>
### [Microsoft&\#x27;s ONNX Runtime repository reportedly disappears from GitHub](https://github.com/microsoft/onnxruntime) ⭐️ 7.0/10

Microsoft&\#x27;s ONNX Runtime repository at github.com/microsoft/onnxruntime is reported to have gone dark on GitHub as of November 17, 2026, with no advance warning or official explanation in the supplied material. The item does not confirm whether the repository was removed, made private, restricted, or otherwise unavailable, so the operational and security implications remain unverified. A commenter said evaluation pipelines began failing that morning, but no Microsoft statement or independent confirmation was provided.

hackernews · nvader · Nov 17, 23:18 · [Discussion](https://news.ycombinator.com/item?id=50539610)

**「What ONNX Runtime is」** ONNX Runtime is Microsoft&\#x27;s cross-platform runtime for executing ONNX machine-learning models, and it is consumed as packages that downstream evaluation and deployment pipelines install and build against, so a repository outage shows up as failing builds rather than a merely unavailable web page. Third-party coverage described the event as Microsoft removing the repository from GitHub, while offering no Microsoft statement explaining why. The item itself provides no official confirmation or reason for the disappearance.

**「Downstream build fallout」** Teams that pull ONNX Runtime directly from the microsoft/onnxruntime repository face broken installs and evaluation pipelines: the submitter reported evals failing the morning the repository went dark, with no advance warning. Because ONNX Runtime is documented as powering Windows, Office, Azure Cognitive Services and Bing as well as thousands of other projects, the exposure is not limited to small teams, yet without an official explanation users cannot tell whether this is routine maintenance or a security response. The substitute cited in the thread, Intel&\#x27;s onnxruntime fork, carries OpenVINO modifications, so it is not a drop-in replacement.

**「Community reaction」** Commenters offered competing speculation—that the disappearance could be cleanup after a compromised package or a response to model-backdoor attack vectors—without evidence tying either to Microsoft&\#x27;s action. A user who said their evaluation pipelines failed pointed others to Intel&\#x27;s onnxruntime fork with OpenVINO modifications, while another commenter claimed ONNX sends application telemetry by default and can only be disabled by building from source.

<details><summary>References</summary>
<ul>
<li><a href="https://wirebyte.co.in/tech/microsoft-removes-onnx-runtime-from-github-apple-services-experience-outage/">Microsoft Removes ONNX Runtime from GitHub; Apple Services ...</a></li>
<li><a href="https://onnxruntime.ai/">ONNX Runtime | Home</a></li>

</ul>
</details>

**Tags**: `#onnx-runtime`, `#github`, `#open-source`, `#supply-chain-security`, `#ai-infrastructure`

---

<a id="item-tech-news-5"></a>
### [Phrack Issue 73 Released, Drawing Exploit and SSH History Discussion](https://phrack.org/issues/73/introduction_md) ⭐️ 7.0/10

Phrack issue 73 is now available at phrack.org, giving security researchers and exploit developers a new issue of the long-running publication. Reader discussion highlights exploit material—one commenter refers to a Docker escape in the issue—and a historical article on the 2000 SSH1 exploit. The supplied material does not include the full issue or establish whether the Docker exploit was responsibly disclosed or assigned a CVE.

hackernews · notmine1337 · Nov 17, 18:31 · [Discussion](https://news.ycombinator.com/item?id=50535992)

**「About Phrack」** Phrack is a long-running, community-produced security zine that collects articles and exploit write-ups into numbered issues rather than publishing them as individual vendor advisories. Because issues mix technical history with working exploit material, readers often ask whether published exploits went through coordinated disclosure—the question raised in the comments about this issue&\#x27;s Docker escape.

**「Community Discussion」** Commenters asked whether exploits published in Phrack—such as the Docker escape one reader cited—have already gone through responsible disclosure and CVE assignment, or are dropped without warning. Others focused on the issue&\#x27;s archival material and the publication&\#x27;s unpolished style, with one saying that openness encouraged freer expression than polished forum comments.

**Tags**: `#computer security`, `#exploit development`, `#vulnerability disclosure`, `#Phrack`, `#SSH history`

---

<a id="item-tech-news-6"></a>
### [Microsoft announces MAI Code 2 and MAI Code 2 Flash coding models](https://microsoft.ai/news/introducing-mai-code-2-and-mai-code-2-flash/) ⭐️ 7.0/10

Microsoft announced MAI Code 2 and MAI Code 2 Flash, two models aimed at AI-assisted software development, per the company&\#x27;s announcement post. The supplied material includes no benchmark figures, parameter counts, pricing, licensing terms, or release dates, so the claimed coding capabilities have not been independently verified. A commenter reported that GitHub Copilot was offering MAI Code 2 at a 50% discount on the day of release, and that the model resolved Python build problems under Windows WSL/Ubuntu, generated test cases that all passed, and fixed Azure Bicep deployment errors — a single anecdotal account rather than a measured evaluation.

hackernews · lemonish97 · Nov 17, 18:25 · [Discussion](https://news.ycombinator.com/item?id=50535885)

**「Background」** Microsoft&\#x27;s MAI coding models already have a prior generation: LLM-Stats lists MAI-Code-1-Flash as released on June 2, 2026 and tracks its benchmarks, pricing and context window, so Code 2 and Code 2 Flash are successors in the same line rather than a new family. The naming also follows an established pattern in Microsoft&\#x27;s MAI lineup, where a &quot;Flash&quot; variant is the lower-latency, lower-cost member of a model family — the same split OpenRouter documents for MAI-Image-2.7 Flash.

**「Copilot users get the first access」** Developers working in GitHub Copilot can select MAI Code 2 for deeper debugging, multi-file implementation and repository-wide reasoning, or MAI Code 2 Flash as the lighter, cost-oriented option for routine tasks, according to GitHub&\#x27;s changelog entry published the same day as the announcement. Microsoft&\#x27;s stated positioning — that MAI Code 2 reaches 98% of GPT-6.1 Sol&\#x27;s performance at 40% of the cost — comes from the vendor rather than independent testing, and the availability described so far runs through Copilot, so teams standardized on other coding tools have no confirmed path to either model yet.

**「Community discussion」** Commenters read the release as evidence that OpenAI&\#x27;s and Anthropic&\#x27;s quality lead is measured in months rather than years: pseudosavant called the position a tenuous lead requiring constant sprinting, while origini speculated without evidence that distillation from OpenAI models explains how Microsoft caught up quickly. On the practical side, chopete3 said the model handled WSL/Ubuntu Python builds and Azure Bicep deployments with no noticeable difference from Claude Opus, whereas LaurensBER wrote that they had cancelled a $19 GitHub Copilot subscription because credit allowances ran out in days or hours and code reviews were not customizable.

<details><summary>References</summary>
<ul>
<li><a href="https://llm-stats.com/models/mai-code-1-flash">MAI - Code -1- Flash Benchmarks , Pricing &amp; Context Window</a></li>
<li><a href="https://openrouter.ai/microsoft/mai-image-2.7-flash">MAI -Image- 2 .7 Flash - Image Generation API Pricing | OpenRouter</a></li>
<li><a href="https://github.blog/changelog/2026-11-17-mai-code-2-and-mai-code-2-flash-in-github-copilot/">MAI Code 2 and MAI Code 2 Flash in GitHub Copilot</a></li>
<li><a href="https://www.unite.ai/microsoft-ai-releases-mai-code-2-and-mai-code-2-flash-for-enterprises/">Microsoft AI Releases MAI Code 2 and MAI Code 2 Flash for ...</a></li>

</ul>
</details>

**Tags**: `#Microsoft`, `#AI coding models`, `#LLMs`, `#developer tools`, `#model release`

---

<a id="item-tech-news-7"></a>
### [Nvidia stops disclosing Singapore sales as reported revenue reaches $104B](https://www.ft.com/content/dbde7a30-548c-4f9d-a4be-7898a0c24dcf) ⭐️ 7.0/10

The Financial Times reported that Nvidia stopped disclosing Singapore sales as the revenue figure tied to that disclosure reached $104B. The omission matters to investors and supply-chain analysts who used the Singapore line to monitor routed GPU orders and export-control exposure. Commenters cautioned that the $104B is revenue booked through Nvidia&\#x27;s Singapore subsidiary, including orders routed by OEMs, ODMs, and resellers, so it does not show where the chips are ultimately used.

hackernews · louiereederson · Nov 17, 17:12 · [Discussion](https://news.ycombinator.com/item?id=50534631)

**「Background」** Nvidia had previously reported Singapore sales in investor disclosures; the change comes amid scrutiny of Megaspeed, a Singapore company that bought advanced Nvidia AI chips and was investigated by US authorities over suspicions it helped Chinese businesses obtain restricted hardware. The New York Times reported that the Commerce Department inquiry was transferred to the Justice Department after a top Nvidia executive contacted Commerce officials.

**「Export-control exposure」** The disclosure gap matters most for Singapore-based distributors and subsidiaries: Singapore&\#x27;s government says it does not legally enforce other countries&\#x27; unilateral export controls but expects companies operating there to account for applicable regulations. U.S. authorities have separately examined whether Nvidia chips reached China through Singapore, making routing through the entity a continuing compliance concern.

**「Community discussion」** Commenters challenged the reading that the $104B represents Singapore end demand: tamarind44 said it is the external revenue of Nvidia&\#x27;s Singaporean subsidiary for 2025 and includes GPU orders routed through the entity by OEMs, ODMs, and resellers. legitster similarly called the disclosure an accounting-attribution issue, while other commenters speculated about chip smuggling and Megaspeed without evidence in the supplied material.

<details><summary>References</summary>
<ul>
<li><a href="https://www.techtimes.co.uk/megaspeed-nvidia-hardware-imports-chip-scrutiny-1809823">Inside Megaspeed : The Little-Known Firm Linking Jensen and Alice...</a></li>
<li><a href="https://www.nytimes.com/2026/11/09/business/economy/nvidia-megaspeed-investigation-huang.html">U.S. Commerce Dept. Inquiry Into Megaspeed Was Halted After...</a></li>
<li><a href="https://www.channelnewsasia.com/singapore/nvidia-ai-chips-us-export-controls-singapore-deepseek-china-4944231">Singapore does not condone businesses who use local ties to bypass...</a></li>
<li><a href="https://www.straitstimes.com/business/us-looking-if-deepseek-got-nvidia-ai-chips-through-singapore-others">US probing whether DeepSeek got Nvidia AI chips ... | The Straits Times</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#AI hardware`, `#export controls`, `#Singapore`, `#supply chain`

---

<a id="item-tech-news-8"></a>
### [SolidJS 2.0 adds server RPC, live updates, and diagnostics](https://www.solidjs.com/blog/solid-2-0-the-long-hold/) ⭐️ 7.0/10

SolidJS 2.0 is out, a major release of the JavaScript UI framework for frontend and full-stack web developers. It adds server integration through RPC, live, and broadcast capabilities, plus improved debugging diagnostics. The supplied material does not detail breaking changes or migration requirements for existing Solid applications.

hackernews · pier25 · Nov 17, 18:56 · [Discussion](https://news.ycombinator.com/item?id=50536387)

**「Background」** Solid 2.0 follows an August 2026 release candidate that described a reorganization over the 2.0 cycle: server functions moved into core, the serving layer into start mode, and file-system routing into a router-neutral package. The project says the stable release comes after five years.

**「Impact」** Developers adopting Solid 2.0 can use server RPC, live, and broadcast as framework-level features rather than assembling separate client-server plumbing; teams should check the release notes for migration and compatibility guidance before upgrading existing apps.

**「Community discussion」** Commenters welcomed the release, with one calling the server RPC, live, and broadcast integration “seamless” and more natural than LiveView or htmx/datastar. Another argued that the diagnostics grouped under “Built to Be Written by Agents” are general debugging improvements that also benefit hand-written code.

<details><summary>References</summary>
<ul>
<li><a href="https://www.solidjs.com/blog/solid-2-0-rc-the-big-reveal">Solid 2.0 RC: The Big | SolidJS</a></li>
<li><a href="https://www.solidjs.com/blog/solid-2-0-the-long-hold/">Solid 2.0 - The Long Hold - solidjs.com</a></li>

</ul>
</details>

**Tags**: `#SolidJS`, `#JavaScript frameworks`, `#frontend development`, `#web development`, `#server RPC`

---

<a id="item-tech-news-9"></a>
### [Quad9 exits France after DNS filtering ruling](https://blog.cloudflare.com/quad9-withdrawal-from-france/) ⭐️ 7.0/10

Quad9 has withdrawn its DNS service from France following a court ruling on DNS filtering, according to a Cloudflare blog post. The post treats the exit as a test case for internet fragmentation and privacy, raising concerns that resolver-level blocking obligations can push DNS providers out of national markets. The available account does not detail the ruling&\#x27;s specific blocking requirements or the exact scope of the French action.

hackernews · subset · Nov 17, 22:13 · [Discussion](https://news.ycombinator.com/item?id=50538994)

**「Background」** Quad9, a Swiss nonprofit that runs a free public DNS resolver, has said it will stop serving users in France on November 24 after a French court ordered it to block websites accused of copyright infringement. Cloudflare’s post ties that withdrawal to a Belgian court order that would impose substantial penalties if Cloudflare, Google, and Cisco do not begin blocking websites through their public resolvers by early January 2027.

**「What it means」** French users and network operators that relied on Quad9&\#x27;s public resolver must switch to another DNS service or run their own resolver. Organizations with filtering or privacy requirements should reassess which resolvers remain available in the jurisdiction.

**「Discussion」** johnhtodd, who identified himself as Quad9&\#x27;s CTO, reported that support at IETF 127 was &quot;100%&quot; so far for Quad9&\#x27;s position and described &quot;general dread&quot; about DNS filtering, while commenter driverdan pressed Cloudflare to commit to withdrawing from affected countries if its own appeal fails. These are commenter views, not verified outcomes.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.cloudflare.com/quad9-withdrawal-from-france/">Quad9’s withdrawal from France: A canary in the coal mine</a></li>
<li><a href="https://www.eff.org/deeplinks/2026/10/french-courts-site-blocking-orders-drive-quad9-out-france">French Court’s Site-Blocking Orders Drive Quad9 Out Of France</a></li>

</ul>
</details>

**Tags**: `#DNS`, `#internet regulation`, `#privacy`, `#France`, `#Cloudflare`

---

<a id="item-tech-news-10"></a>
### [External sandbox pattern for coding agents gains three implementations](https://simonwillison.net/2026/Nov/17/external-sandboxes-for-coding-agents/) ⭐️ 7.0/10

Simon Willison and Prime Radiant released three server implementations of an external sandbox pattern for coding agents, in which agent-run code executes in a dedicated sandbox while the agent stays outside it. The options are external-sandbox-v86, a Node.js server running Alpine Linux under v86 in WebAssembly; external-sandbox-container, a Python server running Alpine Linux in an Apple Containers instance; and external-sandbox-quicksand, a Python server using Microsoft&\#x27;s Quicksand library, which bundles QEMU and Alpine Linux. All expose the same localhost API, so Pi, Claude Code, or Codex can be configured to send code-execution calls to the sandbox, and they include an optional HTTP/HTTPS allow-list proxy plus credential replacement for authenticated API calls without sharing the secret with the agent.

rss · Simon Willison · Nov 17, 22:52

**「Background」** Coding agents such as Claude Code, Codex and Pi run the shell commands they generate on whatever machine hosts them, so a mistaken command or a prompt injection hidden in fetched content can reach the user&\#x27;s files, credentials and network. The three released servers isolate that executed code on different substrates: v86 emulating a PC with Alpine Linux inside WebAssembly, Apple Containers running an Alpine Linux instance, and Microsoft&\#x27;s Quicksand, a Python package that bundles QEMU and Alpine Linux together.

**「Impact」** Developers experimenting with local models can confine code execution to the sandbox and restrict outbound requests to approved hosts, reducing exposure if the model makes a mistake or is prompt-injected. Adopting the pattern requires configuring Pi, Claude Code, or Codex to route execution through the sandbox&\#x27;s localhost API.

**Tags**: `#AI agents`, `#sandboxing`, `#code execution security`, `#prompt injection`, `#local models`

---

<a id="item-tech-news-11"></a>
### [China&\#x27;s Q/V-band wireless link reaches 27 Gbps bidirectional](https://www.news.cn/tech/20261117/d6323540dccf4e2a976c48a762795956/c.html) ⭐️ 7.0/10

Researchers from the Chinese Academy of Sciences&\#x27; Aerospace Information Research Institute and partner institutions completed a Q/V-band bidirectional wireless communication experiment at the Lijiang China Remote Sensing Satellite Ground Station, reporting a domestic record of 27 Gbps. The test covered 64QAM through 512QAM; at 512QAM a single channel reached 6.75 Gbps bidirectional, and dual carriers plus polarization multiplexing raised the aggregate bidirectional rate to 27 Gbps. The team described the key indicators as domestically leading and internationally advanced and said it aims to exceed 50 Gbps. The report did not provide link distance, bandwidth, spectral efficiency, or peer-reviewed detail, and the result is a validation rather than a deployed service.

telegram · zaihuapd · Nov 17, 08:45

**「What Q/V band and 512QAM mean」** Q/V band is a millimeter-wave range above the Ka-band used by most current satellite links; it offers wider available bandwidth but suffers higher propagation loss and needs sharper antenna pointing. Higher-order modulation such as 512QAM packs more bits into each symbol, which raises throughput but requires a much cleaner signal-to-noise ratio than the 64QAM schemes used in more robust links.

**「Impact」** For satellite and 6G backhaul developers, the test provides a domestic Q/V-band data point at 27 Gbps using 512QAM, dual carriers, and polarization multiplexing; the team&\#x27;s stated next target is above 50 Gbps. Because the report gives no link distance, bandwidth, or deployment timeline, the result cannot yet be compared directly with commercial or international systems.

**Tags**: `#6G`, `#Q/V-band`, `#wireless communications`, `#satellite internet`, `#millimeter-wave`

---

## Financial News

<a id="item-finance-news-1"></a>
### [China&\#x27;s auto association reviews 17 automakers&\#x27; 60-day supplier payment terms](http://www.caam.org.cn/chn/5/cate_68/con_5237404.html) ⭐️ 7.0/10

The China Association of Automobile Manufacturers, commissioned by the Ministry of Industry and Information Technology, is assessing whether 17 major automakers pay suppliers within 60 days, including whether small and medium-sized suppliers meet that limit and whether non-SME suppliers receive at least 80% in cash or bank acceptance bills. No compliance results have been released; the review is set to proceed through company submissions, a dedicated-team check, expert evaluation and public disclosure.

telegram · zaihuapd · Nov 18, 01:15

**「Background」** The assessment follows a June 2025 public commitment by 17 major automakers to keep supplier payment terms within 60 days, with CAAM later issuing guidance on how that period is calculated.

**「Impact」** Suppliers of the 17 listed automakers — especially small and medium-sized parts makers — gain an outside check on how quickly their invoices are paid, because the assessment results are to be published; parts makers selling to automakers outside the list are not covered and, per industry reporting, still face long payment terms.

<details><summary>References</summary>
<ul>
<li><a href="https://m.bjnews.com.cn/detail/1757938284168209.html">中 汽 协 明确“ 60 天 账 期 ” 支 付 规范， 17 家 车 企 响 应</a></li>
<li><a href="https://auto.gasgoo.com/news/202609/7I70471417C1103.shtml">auto.gasgoo.com/news/202609/7I70471417C1103.shtml</a></li>
<li><a href="https://c.m.163.com/news/a/KVETS4D0054764EL.html">60 天 承诺变套路： 车 企 延开票、 商 票替代，零部件 企 业 账 期 困局未解</a></li>

</ul>
</details>

**Tags**: `#汽车产业`, `#供应链金融`, `#应收账款账期`, `#工信部监管`, `#中小企业`

---