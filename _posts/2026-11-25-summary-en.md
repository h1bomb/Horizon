---
layout: default
title: "Horizon Summary: 2026-11-25 (EN)"
date: 2026-11-25
lang: en
---

> From 27 items, 8 important content pieces were selected

---

**Technology News**
1. [Broadcom patches 23 VMware flaws, including 9.8 vCenter auth bypass](#item-tech-news-1) ⭐️ 8.0/10
2. [Unverified preprint claims matrix-multiplication exponent of 9/4](#item-tech-news-2) ⭐️ 7.0/10
3. [Ternary Bonsai 2.5 27B: local speed reports, benchmark questions](#item-tech-news-3) ⭐️ 7.0/10
4. [OpenAI claims GPT-6.2 protein-design capability, commenters dispute &\#x27;intrinsic&\#x27; label](#item-tech-news-4) ⭐️ 7.0/10
5. [GreyNoise reports active intrusion campaign against Check Point management servers](#item-tech-news-5) ⭐️ 7.0/10
6. [Simon Willison traces three LLM inflection points in twelve months](#item-tech-news-6) ⭐️ 7.0/10
7. [GPT-6.2 Astra Identifies Creator of 1808 Yale Sketchbook](#item-tech-news-7) ⭐️ 7.0/10

**Financial News**
1. [Williams Says Fed Has More Work to Do on Inflation](#item-finance-news-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Broadcom patches 23 VMware flaws, including 9.8 vCenter auth bypass](https://thehackernews.com/2026/11/vmware-vcenter-hit-by-another-critical.html) ⭐️ 8.0/10

Broadcom released patches for 23 vulnerabilities across its VMware product line, centered on an authentication bypass in vCenter&\#x27;s directory service \(vmdir\) tracked as CVE-2026-123903 and rated 9.8. According to the supplied report, anyone who can reach vCenter over the network can bypass authentication and get into the system without credentials. The same report says the flaw was exploited as a zero-day only days before it was disclosed, a claim attributed to the reporting rather than independently confirmed here. Administrators running vCenter should treat the vmdir authentication bypass as the priority item in this patch set.

telegram · zaihuapd · Nov 24, 14:50

**「Why vCenter&\#x27;s directory service matters」** vCenter is the central management plane for VMware virtual infrastructure, and its vmdir directory service handles authentication functions for the product. A bypass in vmdir is therefore significant because access to vCenter can give an attacker control over the virtual estate rather than exposing only an isolated service.

**「Remediation scope」** Teams running reachable vCenter instances should inventory them and move to the fixed builds identified for CVE-2026-123903, since an attacker who can reach the service can bypass authentication without credentials. Broadcom’s VMSA-2026-0011 also addresses two 9.8-rated ESX code-execution flaws, so remediation should cover both vCenter and ESX rather than vCenter alone.

<details><summary>References</summary>
<ul>
<li><a href="https://brandefense.io/knowledge-hub/vulnerabilities/cve-2026-123903/">CVE-2026-123903: vCenter Auth Bypass, Fix Status</a></li>
<li><a href="https://www.rescana.com/post/vmware-vcenter-cve-2026-123903-auth-bypass-and-esx-code-execution-patch-now">VMware vCenter Auth Bypass CVE-2026-123903 and ESX Code ...</a></li>

</ul>
</details>

**Tags**: `#security`, `#VMware`, `#vCenter`, `#vulnerabilities`, `#zero-day`

---

<a id="item-tech-news-2"></a>
### [Unverified preprint claims matrix-multiplication exponent of 9/4](https://github.com/openai/math/blob/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/paper.pdf) ⭐️ 7.0/10

An unverified preprint hosted on GitHub, titled &quot;The matrix multiplication exponent is nine fourths,&quot; claims the matrix-multiplication exponent is 9/4, or Θ\(n^2.25\), over every field. Commenters link it to OpenAI&\#x27;s four new papers and say it addresses open problem \#25 by refuting a conjecture, but the posting has no disclosed peer review, methodology, or model recipe. If the claim holds, it would be a landmark complexity-theory result; as posted, it has not been independently validated.

hackernews · E-Reverance · Nov 25, 01:19 · [Discussion](https://news.ycombinator.com/item?id=50637220)

**「Background」** The matrix-multiplication exponent ω is the infimum of exponents τ such that, for every ε&gt;0, two n×n matrices over a field can be multiplied using O\(n^\(τ+ε\)\) arithmetic operations, making it the standard measure of the asymptotic cost of matrix multiplication. The preprint follows an earlier OpenAI claim, reported roughly seven weeks before the paper, that an internal model had found a dramatically faster theoretical method; the new work says it establishes that no better exponent than 9/4 is possible.

**「Impact」** For complexity researchers, a verified Θ\(n^2.25\) bound would rule out matrix-multiplication algorithms with an exponent below 2.25 and would make a recently reported O\(n^2.25\) algorithm asymptotically optimal; until validation, it should not be treated as an established bound.

**「Community discussion」** Commenters disagree about what the preprint actually establishes: one says the title&\#x27;s O\(n^2.25\) is wrong and should be Θ\(n^2.25\), while another describes the result as a lower bound Ω\(n^2.25\) and says an O\(n^2.25\) algorithm was already known. Others focus on provenance, speculating that OpenAI withheld a stronger model and did not disclose the recipe.

<details><summary>References</summary>
<ul>
<li><a href="https://mathworld.wolfram.com/MatrixMultiplicationExponent.html">Matrix Multiplication Exponent -- from Wolfram MathWorld</a></li>
<li><a href="https://officechai.com/ai/openai-says-it-has-pinned-down-the-exact-speed-limit-for-matrix-multiplication-9-4/">OpenAI Says It Has Pinned Down The Exact Speed Limit For ...</a></li>

</ul>
</details>

**Tags**: `#complexity-theory`, `#matrix-multiplication`, `#ai-for-math`, `#openai`, `#research-preprint`

---

<a id="item-tech-news-3"></a>
### [Ternary Bonsai 2.5 27B: local speed reports, benchmark questions](https://prismml.com/news/bonsai-2-5-27b) ⭐️ 7.0/10

Ternary Bonsai 2.5 27B is a new 27B ternary-quantized model for local inference, with a reported 128k context window; the supplied item has no vendor page content, so availability and official benchmark results are not independently confirmed. The concrete performance evidence in the supplied material is anecdotal: one commenter measured about 22–25 tokens/s on a Mac Mini M5 Pro with 24 GB RAM, 222.9 tokens/s prompt processing, and 2.12 s to first token on a Python prompt, and said 128k context fit in memory. Another commenter&\#x27;s long-horizon local test reported Bonsai 2.5 passing 5 of 8 tasks in 76 minutes versus Bonsai2&\#x27;s 5 of 8 in 107 minutes. Claims that the model matches Opus 4.6 on SWE-bench Verified are community speculation and explicitly questioned, not independently verified here.

hackernews · b0m · Nov 24, 20:08 · [Discussion](https://news.ycombinator.com/item?id=50633922)

**「Background」** Ternary quantization restricts a model&\#x27;s weights to three values \(commonly -1, 0, and 1\), which is how a 27B-parameter model can be offered in a roughly 5.9 GB footprint. PrismML distributes Bonsai 2.5 27B in GGUF format for local inference runtimes.

**「Impact」** For developers running local models on 24 GB Apple silicon, the reported footprint makes 128k-context agentic-coding experiments plausible at roughly 22–25 tokens/s, but that speed comes from one commenter’s measurement and should be treated as anecdotal.

**「Community discussion」** Commenters welcomed the local speed and long context but questioned the evidence: one asked for direct comparisons against equivalently small Qwen3.8 Q1/Q2 or other 1B–10B models, while another suspected the claimed SWE-bench Verified parity with Opus 4.6 might reflect benchmark overfitting, benchmark drift, or both. A separate long-horizon local test reported Bonsai 2.5 completing 5 of 8 tasks 29% faster than Bonsai2 with 17% fewer steps.

<details><summary>References</summary>
<ul>
<li><a href="https://prismml.com/news/bonsai-2-5-27b">PrismML — Introducing Ternary Bonsai 2 . 5 27 B : Powering Agentic...</a></li>
<li><a href="https://huggingface.co/prism-ml/Ternary-Bonsai-2.5-27B-GGUF">prism - ml / Ternary - Bonsai - 2 . 5 - 27 B -GGUF · Hugging Face</a></li>

</ul>
</details>

**Tags**: `#ternary quantization`, `#local LLMs`, `#model release`, `#GGUF`, `#agentic coding`

---

<a id="item-tech-news-4"></a>
### [OpenAI claims GPT-6.2 protein-design capability, commenters dispute &\#x27;intrinsic&\#x27; label](https://openai.com/index/gpt-6-models-demonstrate-intrinsic-protein-design-capabilities/) ⭐️ 7.0/10

OpenAI claims its GPT-6 models can perform protein-design tasks, saying GPT-6.2 was given the 3D structures of five target proteins and attachment sites and then wrote code to generate 3D minibinder designs without specialized protein AI models. The account also says OpenAI used SolubleMPNN to suggest amino-acid sequences for those designs and other specialized protein models to select candidates predicted to fold and bind at the intended site. Commenters therefore dispute the &\#x27;intrinsic&\#x27; framing, asking what GPT-6.2 actually designed if sequence generation and screening depended on specialized tools.

hackernews · acossta · Nov 24, 21:02 · [Discussion](https://news.ycombinator.com/item?id=50634658)

**「Background」** Protein design is typically split into separate computational steps: proposing a 3D backbone, finding an amino acid sequence that folds into it, and filtering candidates for folding and target binding. Specialized models have been built for those steps, and in the workflow quoted in the source discussion, SolubleMPNN was used to suggest sequences while other protein models helped screen designs. OpenAI&\#x27;s report claims GPT-6.2 can design both a minibinder&\#x27;s structure and its sequence, which is the “intrinsic” step the discussion is contesting.

**「Impact」** For protein-design teams, the reported workflow still requires SolubleMPNN and other specialized models to turn GPT-6.2&\#x27;s 3D designs into testable sequences, so evaluations of &\#x27;intrinsic&\#x27; capability should separate structure generation from sequence design and candidate filtering.

**「Community Discussion」** Commenters questioned the &\#x27;beyond specialized models&\#x27; framing: fabian2k asked what GPT-6.2 actually designed when SolubleMPNN supplied the sequences, and plaidfuji described the model as a &\#x27;glue layer&\#x27; between specialized tools that can outperform them at some subtasks. joe-esquibel said the evidence was light on laboratory controls and heavy on computational exploration.

<details><summary>References</summary>
<ul>
<li><a href="https://openai.com/index/gpt-6-models-demonstrate-intrinsic-protein-design-capabilities/">GPT - 6 models demonstrate intrinsic protein - design ... | OpenAI</a></li>

</ul>
</details>

**Tags**: `#AI for biology`, `#protein design`, `#GPT-6`, `#OpenAI`, `#specialized models`

---

<a id="item-tech-news-5"></a>
### [GreyNoise reports active intrusion campaign against Check Point management servers](https://www.greynoise.io/blog/check-point-security-management-servers-intrusion-campaign) ⭐️ 7.0/10

GreyNoise reports an active intrusion campaign against Check Point security management servers, with attackers targeting the HFS loginSrp1 endpoint to obtain signed session cookies. Each login returned a new &quot;sid&quot; generated with JavaScript&\#x27;s Math.random\(\); by collecting several, the actor reconstructed the Node.js V8 PRNG state, recovered an HFS session-cookie signing key, and forged an admin session cookie. The account leaves the initial-access step unresolved; a commenter suggests CVE-2026-16232 as the likely vector and asks whether affected organizations exposed their management servers to the internet.

hackernews · louiereederson · Nov 24, 16:32 · [Discussion](https://news.ycombinator.com/item?id=50630594)

**「Earlier Check Point vulnerability」** Check Point previously disclosed CVE-2026-16232, an authentication bypass in its Security Management Server that could be exploited remotely when the server IP was reachable from the internet and Trusted Clients were not restricted. Check Point said the vulnerability was already being exploited against a very small number of customers, providing the earlier exposure context for the current management-server campaign.

**「What defenders should do」** Because the link between multiple victim organizations points to CVE-2026-16232 as the probable initial vector, the practical exposure concern is Check Point Security Management Servers reachable from the internet — the circumstance one commenter explicitly questions — so operators should audit and restrict that management-plane access rather than assume endpoint patching alone covers the campaign. The session-forgery step is also a reusable pattern for Node.js services: researchers describe collecting a small number of login responses, reconstructing the V8 PRNG state, recovering the signing key and forging a valid administrator cookie that leads to remote code execution, which means cookie-signing secrets derived from \`Math.random\(\)\` need to be replaced with a cryptographically secure source and rotated, not just patched around.

**「Community discussion」** One commenter asks how the attackers gained initial access and whether the suspected CVE-2026-16232 vector means affected organizations had internet-facing Check Point Security Management Servers. Another argues that Math.random\(\) itself should be made more secure rather than treating the weakness solely as a failure of the many applications that misuse it.

<details><summary>References</summary>
<ul>
<li><a href="https://support.checkpoint.com/results/sk/sk185169">sk185169 - CVE-2026-16232 - Authentication bypass with ...</a></li>
<li><a href="https://nvd.nist.gov/vuln/detail/cve-2026-16232">NVD-CVE-2026-16232</a></li>
<li><a href="https://dev.to/anoymask/rejetto-hfs-cve-2026-61500-predictable-signing-key-enables-admin-session-forgery-and-rce-477g">Rejetto HFS CVE-2026-61500: Predictable Signing Key Enables ...</a></li>
<li><a href="https://thehackernews.com/2026/10/attackers-target-rejetto-hfs-flaw-that.html">Attackers Target Rejetto HFS Flaw That Enables Admin Session ...</a></li>

</ul>
</details>

**Tags**: `#security`, `#vulnerability-research`, `#Node.js`, `#PRNG`, `#exploitation`

---

<a id="item-tech-news-6"></a>
### [Simon Willison traces three LLM inflection points in twelve months](https://simonwillison.net/2026/Nov/24/llm-inflection-points/) ⭐️ 7.0/10

Simon Willison&\#x27;s retrospective, published on the one-year anniversary of Claude Opus 4.5, argues that LLM and coding-agent capability crossed three inflection points in twelve months. He credits Claude Opus 4.5 and OpenAI&\#x27;s GPT-5.1 family \(Instant, Thinking, GPT-5.1-Codex and GPT-5.1-Codex-Max\) with making coding agents reliably useful for his daily work in late 2025, then Claude Fable 5 in June 2026 with defining &quot;Fable class&quot; models that can pursue a defined goal with tools, a group he extends to Fable 5/5.1/5.2, Opus 5.5, GPT-6 Astra and possibly Gemini 4 Neon. He identifies a third inflection in September–October 2026, when frontier models became notably better at 3D modeling and game development, citing Opus 5.5&\#x27;s response to a request to make a game &quot;a LOT more fun&quot; after 12 hours of playtesting. These are the author&\#x27;s experience-based judgments rather than independent benchmarks, and the supplied post cuts off before his discussion of Fable 5.2.

rss · Simon Willison · Nov 24, 23:02

**「Background」** Claude Code was introduced alongside Claude 3.7 Sonnet on February 24, 2025, about nine months before Claude Opus 4.5 shipped on November 24, 2025. Willison&\#x27;s retrospective is anchored to that model&\#x27;s one-year anniversary because, in his account, Opus 4.5 was the first model whose default Claude Code output was generally correct for his daily coding work.

**「Availability risk for agent-dependent teams」** Developers who shifted to coding agents as daily drivers after the Opus 4.5 and GPT-5.1 releases now depend on access to a specific model class rather than a generic capability. Willison&\#x27;s account of Claude Fable 5 being pulled under US export controls for roughly three days, and not returning until July 1st, shows that this dependency can be interrupted by policy rather than by technical failure, which argues for keeping a working fallback model configured.

**Tags**: `#LLM`, `#coding agents`, `#AI engineering`, `#software development`, `#Anthropic Claude`

---

<a id="item-tech-news-7"></a>
### [GPT-6.2 Astra Identifies Creator of 1808 Yale Sketchbook](https://simonwillison.net/2026/Nov/24/astra-historical-mystery/) ⭐️ 7.0/10

History professor Mark Humphries reports that GPT-6.2 Astra, given minimal prompting, autonomously identified the creator of an anonymous 1808 sketchbook held at Yale’s Beinecke Library in 22 minutes using public primary and secondary sources. According to the account, the model found a diary reference to a visit by the vicomte de Chabot five days before a date in the sketchbook and predicted that Chabot’s travel journal, available only by order from Cleveland State University, would confirm the attribution. Humphries says the journal did confirm it and is itself a significant find for Canadian and fur-trade historians; the short write-up does not detail the prompts, search steps, or verification method.

rss · Simon Willison · Nov 24, 16:53

**「Background」** Attributing an anonymous historical object usually means tying details in the object to independent archival records, such as diaries, correspondence, or travel journals. The 1808 sketchbook is held at Yale&\#x27;s Beinecke Library and has been digitized; the confirming document Astra identified was Vicomte de Chabot&\#x27;s travel journal, which the source says is available only by order from Cleveland State University.

**「Impact」** For Canadian and fur-trade historians, the newly surfaced Chabot journal is itself a significant archival find, according to Humphries, so the case’s practical result extends beyond the sketchbook attribution.

**Tags**: `#AI agents`, `#LLM applications`, `#autonomous research`, `#digital humanities`, `#historical research`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Williams Says Fed Has More Work to Do on Inflation](https://www.cnbc.com/2026/11/23/john-williams-fed-inflation-rate-hikes.html) ⭐️ 7.0/10

New York Fed President John Williams said the Fed still has work to do to return inflation to its 2% target and indicated further rate increases can unfold over time, ahead of the Dec. 8-9 policy meeting where markets fully price a quarter-point increase from the current 3.75%-4% range.

rss · CNBC Finance · Nov 24, 13:33

**「Background」** Inflation has remained well above the Fed&\#x27;s 2% goal even as the economy grows, and officials have differed over how quickly to raise rates; Williams has emphasized a measured approach.

**Tags**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#inflation`, `#FOMC`

---