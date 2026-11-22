---
layout: default
title: "Horizon Summary: 2026-11-22 (EN)"
date: 2026-11-22
lang: en
---

> From 24 items, 8 important content pieces were selected

---

**Technology News**
1. [Lean verification of Riemann Hypothesis reported as AI-assisted result](#item-tech-news-1) ⭐️ 9.0/10
2. [Reported GPGME vulnerability affects pre-2.3.0 apps; RCE framing disputed](#item-tech-news-2) ⭐️ 8.0/10
3. [Zhejiang University reports first real-device QRAM on superconducting chip](#item-tech-news-3) ⭐️ 8.0/10
4. [Monitor&\#x27;s USB Ethernet Path Cut Download Speed by 75%](#item-tech-news-4) ⭐️ 7.0/10
5. [Graham Dumpleton introduces Muru, an AI-assisted Rust server for Python](#item-tech-news-5) ⭐️ 7.0/10
6. [Microsoft previews RDMA over USB4 for multi-PC local AI inference](#item-tech-news-6) ⭐️ 7.0/10
7. [OpenRouter warns MiniMax prompts may have been read by third parties](#item-tech-news-7) ⭐️ 7.0/10

**Technology Blog**
1. [Avoiding Blunders Beats Cleverness in Good Coding](#item-tech-blog-1) ⭐️ 6.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Lean verification of Riemann Hypothesis reported as AI-assisted result](https://leanprover-community.github.io/blog/posts/riemann-hypothesis/) ⭐️ 9.0/10

An item on the Lean Prover Community blog presents a Lean verification of the Riemann Hypothesis as an AI-assisted formal-verification result. If accurate, the claim would matter to Lean users and formal-verification researchers because acceptance would rest on Lean&\#x27;s kernel checking the proof rather than on conventional peer review alone. The supplied item includes no source content, formal statement, proof artifact, or independent confirmation, so the result&\#x27;s scope and validity remain unverified here.

hackernews · g-b-r · Nov 21, 14:36 · [Discussion](https://news.ycombinator.com/item?id=50589618)

**「Background」** The item follows Levent Alpöge&\#x27;s November 20, 2026 claim that he and Claude had found a proof of the Riemann Hypothesis and a method for the Generalized Riemann Hypothesis, released as a Lean library. Early coverage reported that the Lean archive compiled and passed Lean&\#x27;s kernel plus the independent nanoda checker, while independent validation of the complete argument was still unsettled.

**「Reproducibility and priority」** Because the claim arrives with a massive Lean code archive, other researchers can recompile and machine-check the proof themselves rather than trusting the author&\#x27;s summary — and that body of formalized code may be reusable regardless of how the Riemann hypothesis question ultimately resolves. The claim also lands alongside a competing human solution to the same problem, so credit and priority will rest on the formal record and its verification.

**「Community discussion」** Commenters disagreed about how much independent kernel checks reduce the risk of a bad proof: one argued that multiple implementations with consistency proofs make a shared bug vanishingly unlikely, while another cited a past fake Collatz refutation that passed an independent checker and said the checkers are less independent than often claimed. Others credited Levent with getting the most out of Claude and described the formalization of a large chunk of modern mathematics as a significant result in its own right.

<details><summary>References</summary>
<ul>
<li><a href="https://explainx.ai/blog/levent-alpoge-anthropic-riemann-hypothesis-claude-lean-proof-claimed-vs-verified-2026">Riemann Hypothesis Proof Claim: Claimed vs Verified ...</a></li>
<li><a href="https://www.unite.ai/levent-alpoges-unverified-riemann-claim-puts-claudes-lean-code-in-focus/">Levent Alpöge’s Unverified Riemann Claim Puts Claude’s Lean ...</a></li>
<li><a href="https://techcrunch.com/2026/11/20/ai-claimed-a-solution-to-the-167-year-old-riemann-hypothesis-and-a-human-did-too/">AI claimed a solution to the 167-year-old Riemann hypothesis — and...</a></li>
<li><a href="https://interestingengineering.com/ai-robotics/anthropic-167-year-old-riemann-hypothesis-claude">Claude helped prove 167-year-old Riemann hypothesis , researcher...</a></li>

</ul>
</details>

**Tags**: `#formal verification`, `#Lean`, `#theorem proving`, `#AI-assisted mathematics`, `#Riemann Hypothesis`

---

<a id="item-tech-news-2"></a>
### [Reported GPGME vulnerability affects pre-2.3.0 apps; RCE framing disputed](https://lists.gnupg.org/pipermail/gnupg-announce/2026q4/000517.html) ⭐️ 8.0/10

A reported vulnerability in GPGME, a library used by GnuPG-related and downstream applications, affects software built against versions before 2.3.0, according to a commenter who listed Gpg4win, GnuPG Desktop, most mail clients, many XMPP clients, Samba, and Flatpak. The same discussion disputes the “RCE” framing, with one commenter describing the flaw as a double-free bug rather than a proven remote-code-execution chain. A commenter said they were informed by GitLab on 2026-11-12 and disclosed the GPGME bug on 2026-11-20, earlier than a planned 2026-11-25 coordinated date because GitLab had to update for the Ruby2Shell bug. Upstream source content was not available, so the affected-version and severity details remain community-reported.

hackernews · gdgghhhhh · Nov 21, 08:32 · [Discussion](https://news.ycombinator.com/item?id=50587208)

**「Background」** GPGME is the library many applications use to call GnuPG for OpenPGP operations, so a flaw in it reaches downstream software such as mail clients, XMPP clients, Samba, and signed-commit tooling. The issue is tracked as CVE-2026-129975, was discovered by Johan Carlsson and reported to the project by GitLab on 2026-11-12, and was disclosed on 2026-11-20 instead of the originally planned 2026-11-25 because the Ruby2Shell bug forced GitLab to update early; the fix is in GPGME 2.3.1, as 2.3.0 was never publicly released.

**「Who needs to act」** Applications that link or bundle GPGME before 2.3.0—including many mail and XMPP clients, Samba, and GitLab’s signed-commit path—need a fixed build; static linking means rebuilding the application, not just replacing a system library. The flaw, tracked as CVE-2026-129975, can be triggered by malicious OpenPGP keys and may expose application data.

**「Community discussion」** Commenters disagreed over severity: one called the issue a double-free bug, not an RCE chain, and questioned whether the report was intentionally overstated, while another said all software using pre-2.3.0 GPGME is affected. A GitLab participant described the coordinated-disclosure timeline and said code execution in the signed-commit path would be especially serious for GitLab.

<details><summary>References</summary>
<ul>
<li><a href="https://lists.gnu.org/archive/html/info-gnu/2026-11/msg00006.html">GnuPG Security Advisory for GPGME (T8557,CVE-2026-129975)</a></li>
<li><a href="https://thehackernews.com/2026/11/gnupg-warns-critical-gpgme-flaw-could.html">GnuPG Warns Critical GPGME Flaw Could Expose App Data via ...</a></li>
<li><a href="https://thehackernews.com/2026/11/gnupg-warns-critical-gpgme-flaw-could.html">GnuPG Warns Critical GPGME Flaw Could Expose App Data via ...</a></li>
<li><a href="https://lists.gnupg.org/pipermail/gnupg-announce/2026q4/000517.html">[Announce] GnuPG Security Advisory for GPGME (T8557,CVE-2026 ...</a></li>

</ul>
</details>

**Tags**: `#security`, `#GnuPG`, `#GPGME`, `#open source`, `#vulnerability disclosure`

---

<a id="item-tech-news-3"></a>
### [Zhejiang University reports first real-device QRAM on superconducting chip](https://finance.sina.com.cn/stock/2026-11-21/doc-iniznhsk3530826.shtml) ⭐️ 8.0/10

Zhejiang University researchers report that they demonstrated quantum random-access memory \(QRAM\) on a self-fabricated superconducting chip called Tianmu-2, describing it as the first real-device implementation and saying the work was published in Nature Physics. The chip ran 4-bit and 8-bit prototypes with 80.9% and 60.4% accuracy, respectively; the team also reports that optimized circuits reduced circuit depth by more than 30% and that the architecture showed local noise resilience. The team&\#x27;s next step is scaling QRAM, but the 8-bit accuracy remains modest and the first-demonstration claim comes from a single source.

telegram · zaihuapd · Nov 21, 08:31

**「Background」** QRAM is a proposed quantum memory architecture in which an algorithm addresses memory locations in superposition, so that one query can return data spread across many addresses — a capability often cited as a prerequisite for quantum algorithms that must load large classical datasets, such as quantum machine-learning routines. Implementing it on real hardware is demanding because the address-decoding logic must be built from deep, error-prone quantum circuits, which is why earlier work has largely been theoretical or confined to small proof-of-principle demonstrations.

**「Impact」** For quantum-software developers, the 8-bit prototype&\#x27;s 60.4% accuracy means QRAM-based algorithms cannot yet be treated as reliable on real hardware; the result is a proof of principle that still depends on improving fidelity and scaling the memory.

**Tags**: `#quantum computing`, `#QRAM`, `#superconducting qubits`, `#quantum hardware`, `#research`

---

<a id="item-tech-news-4"></a>
### [Monitor&\#x27;s USB Ethernet Path Cut Download Speed by 75%](https://blog.tymscar.com/posts/studiodisplayethernet/) ⭐️ 7.0/10

The blog post traces a 75% download-speed loss to the USB networking path built into a monitor, not to the Ethernet link itself. Extra latency through the monitor&\#x27;s USB hub delayed packet acknowledgements; the Ethernet adapter&\#x27;s buffer filled and began dropping packets. A different adapter that required less frequent acknowledgement resolved the problem.

hackernews · soheilpro · Nov 21, 10:36 · [Discussion](https://news.ycombinator.com/item?id=50587875)

**「Background」** A USB hub receives packets on its downstream ports, buffers them, and forwards them upstream one at a time rather than acting as a simple pass-through connection. Here, the monitor’s integrated hub sat between the laptop and the USB Ethernet adapter, and the added latency delayed packet acknowledgements enough to affect throughput.

**「Impact」** For users running USB Ethernet through a monitor or dock, a direct-connection throughput comparison is the practical check; negotiated link speed will not expose acknowledgement-timing bottlenecks. Replacing the adapter or reducing hub latency may be needed when buffer exhaustion is capping downloads.

**「Community Discussion」** Commenters focused on clarifying the mechanism: one summarized that monitor-induced latency delayed acknowledgements, filled the adapter buffer, and caused drops, while another argued the monitor was incidental and the title should refer to the USB network switch. A separate commenter reported a similar year-long problem with a MacBook and Thunderbolt dock and said enabling flow control made it good enough.

<details><summary>References</summary>
<ul>
<li><a href="https://news.ycombinator.com/item?id=50587875">My monitor was cutting my download speed by 75% | Hacker News</a></li>

</ul>
</details>

**Tags**: `#USB`, `#networking`, `#hardware debugging`, `#packet loss`, `#latency`

---

<a id="item-tech-news-5"></a>
### [Graham Dumpleton introduces Muru, an AI-assisted Rust server for Python](https://simonwillison.net/2026/Nov/21/muru/) ⭐️ 7.0/10

Graham Dumpleton, creator of mod\_wsgi, has introduced Muru, an early-stage AI-assisted Rust server for running ASGI and WSGI Python applications in development and production. Muru is not presented as a finished release; Dumpleton has published 18 detailed posts between November 4 and November 21, 2026, covering worker architecture, HTTPS in development, combined WSGI/ASGI support, releases without restarts, canaries, Kubernetes integration, scaling to zero, and tracing. Dumpleton says AI is doing much of the surface work, but that he decides what is not good enough yet, drawing on 20 years of mod\_wsgi experience, and that he will keep polishing Muru until he would trust it.

rss · Simon Willison · Nov 21, 23:56

**「Background」** mod\_wsgi, which Graham Dumpleton started 20 years ago, is an Apache module for hosting Python web applications. WSGI is the older synchronous Python web-server interface, while ASGI adds asynchronous support; Muru aims to serve applications using either interface.

**「Impact for Python web developers」** Muru exposes a \`muru.wsgi\_to\_asgi\` object in the WSGI environ of every WSGI request, whose \`handoff\(\)\` method takes an ASGI application and can report whether a request is a websocket upgrade, giving WSGI apps a documented bridge to ASGI handlers. Because the project is early-stage and self-described as not yet trusted by its author, readers should treat the design write-ups as a preview rather than a migration target for production deployments that currently rely on established WSGI servers.

<details><summary>References</summary>
<ul>
<li><a href="https://grahamdumpleton.me/posts/2026/11/muru-wsgi-and-asgi-together/">Muru : WSGI and ASGI together - Graham Dumpleton</a></li>

</ul>
</details>

**Tags**: `#Python web servers`, `#ASGI`, `#WSGI`, `#Rust`, `#mod\_wsgi`

---

<a id="item-tech-news-6"></a>
### [Microsoft previews RDMA over USB4 for multi-PC local AI inference](https://videocardz.com/newz/microsoft-brings-rdma-over-usb4-to-windows-allowing-multiple-pcs-to-run-one-local-ai-model) ⭐️ 7.0/10

Microsoft released a Windows developer preview of RDMA over USB4 that lets multiple PCs share memory and GPU resources to run a single local AI model without a dedicated network card or switch. In a demo, three systems with AMD Ryzen AI Max+ 395 chips ran 4-bit quantized Qwen3-235B-A22B at about 18.5 tokens per second. Microsoft says the preview will be distributed through Windows Insider.

telegram · zaihuapd · Nov 21, 06:13

**「Background」** RDMA lets one machine access another machine&\#x27;s memory directly, bypassing the usual CPU-heavy network stack, and Windows already exposes it through NetworkDirect for datacenter RDMA adapters. The developer preview applies that same API to USB4 links between PCs, allowing a compatible inference framework to use their combined memory and GPU compute.

**「Impact」** Developers with multiple USB4-equipped PCs could use pooled memory and GPU compute to run models that do not fit on one machine, but the preview is tied to USB4 links and the demonstrated AMD hardware, so broader compatibility and performance are not yet established.

<details><summary>References</summary>
<ul>
<li><a href="https://techcommunity.microsoft.com/blog/microsoftusbblog/introducing-rdma-over-usb4%C2%AE-on-windows-run-larger-local-ai-models-across-pcs/4574602">Introducing RDMA over USB 4 ® on Windows : run larger local AI ...</a></li>

</ul>
</details>

**Tags**: `#local AI`, `#RDMA`, `#USB4`, `#Windows`, `#distributed inference`

---

<a id="item-tech-news-7"></a>
### [OpenRouter warns MiniMax prompts may have been read by third parties](https://news.ycombinator.com/item?id=50585962) ⭐️ 7.0/10

OpenRouter has reportedly notified users that prompts sent to MiniMax models may have been read by third parties, and it removed the &quot;zero data retention&quot; labels from affected MiniMax endpoints and the forwarding providers AtlasCloud, Novita, and StreamLake. The warning says security researchers sent prompts containing test URLs to MiniMax models between July and October 2026 and that third parties accessed those URLs 40 to 130 hours later. OpenRouter advised users who may have exposed sensitive credentials to rotate API keys and passwords, but no primary advisory is available and OpenRouter&\#x27;s website had not published the notice.

telegram · zaihuapd · Nov 21, 06:53

**「How OpenRouter labels data policies」** OpenRouter is a proxy that forwards each request to the model provider that completes it, so prompts pass through provider infrastructure rather than being handled only by OpenRouter. OpenRouter labels endpoints using data-policy tiers including ZDR, Safety Retention, and Retention and Training, which is why removal of a ZDR label changes what users can assume about an endpoint.

**「Rotate credentials, drop ZDR assumptions」** Anyone who sent secrets, API keys, or customer data in prompts to MiniMax models through OpenRouter can no longer treat those endpoints as zero-data-retention: OpenRouter removed the ZDR labels and advised affected users to rotate API keys and passwords. Until a primary advisory clarifies the scope, teams with compliance or data-residency requirements should assume prompts routed via MiniMax, AtlasCloud, Novita, or StreamLake may have been visible to a third party.

<details><summary>References</summary>
<ul>
<li><a href="https://openrouter.ai/docs/faq">OpenRouter FAQ</a></li>

</ul>
</details>

**Tags**: `#AI privacy`, `#API security`, `#LLM providers`, `#data retention`, `#OpenRouter`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Avoiding Blunders Beats Cleverness in Good Coding](https://seangoedecke.com/to-code-well-avoid-blunders/) ⭐️ 6.0/10

rss · Sean Goedecke · Nov 22, 00:00

**「Background」** In Sean Goedecke&\#x27;s essay, he argues that engineers wrongly treat programming as a search for brilliant insights; in his view, the main skill is avoiding catastrophic mistakes, much as steady chess or tennis play beats opponents who blunder. He scopes the advice to large commercial codebases worked on by big teams.

**「Solution」** Programming differs, Goedecke says, because unlike basketball, a lead cannot protect you: one bad decision can turn an elegant codebase janky. He lists characteristic blunders—introducing a parallel system for an existing task, creating a second source of truth, converting safe synchronous code into delicate async code, adding subtle failure points, or complicating a key interface. The underlying sins are inconsistency and unnecessary requirements. Inconsistency destroys trust, forcing engineers to hunt for surprises instead of assuming sensible behavior. Unnecessary requirements persist because later maintainers lack the context to remove them, and they interact combinatorially with each new feature, making large codebases hard to change. His prescription is to place a task in the most normal existing path and trim it to the smallest requirement set, leaving no attention for clever patterns or extra credit. He notes that coding agents match humans on consistency but lag on avoiding unnecessary requirements.

**「Takeaway」** Goedecke&\#x27;s thesis is that great programming depends less on cleverness than on disciplined attention: maintain consistency and refuse unnecessary requirements, because avoiding blunders is the durable advantage.

**Tags**: `#software engineering`, `#code quality`, `#codebase maintainability`, `#consistency`, `#requirements management`

---