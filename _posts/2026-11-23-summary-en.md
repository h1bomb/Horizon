---
layout: default
title: "Horizon Summary: 2026-11-23 (EN)"
date: 2026-11-23
lang: en
---

> From 29 items, 6 important content pieces were selected

---

**Technology News**
1. [OpenAI Argues Lower Perplexity Tracks Greater Model Intelligence](#item-tech-news-1) ⭐️ 7.0/10
2. [FT report alleges Prince Group figure helped smuggle Nvidia chips to China](#item-tech-news-2) ⭐️ 7.0/10
3. [Windows Server 2028 to drop WoW64 by default, 32-bit apps need manual add](#item-tech-news-3) ⭐️ 7.0/10

**Technology Blog**
1. [Deliberate Flailing as a Strategy Under Uncertainty](#item-tech-blog-1) ⭐️ 6.0/10

**Financial News**
1. [U.S. Tech Selloff Met With Asian Market-Stability Measures](#item-finance-news-1) ⭐️ 9.0/10
2. [Ant Group leads $100 million round in Chinese embodied-AI startup Simplexity at $1.6 billion valuation](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [OpenAI Argues Lower Perplexity Tracks Greater Model Intelligence](https://openai.com/index/perplexity-and-intelligence/) ⭐️ 7.0/10

OpenAI published a post arguing that lower next-token perplexity corresponds to greater model intelligence, pitching a simple metric against increasingly complex benchmarks for evaluation-focused readers. The supplied item does not include the article text, and a commenter notes that the post never defines perplexity; the claim is an OpenAI argument, not an independently measured result. Hacker News discussion questioned whether cross-entropy loss remains meaningful as reinforcement learning takes on a larger training role.

hackernews · acossta · Nov 22, 17:06 · [Discussion](https://news.ycombinator.com/item?id=50601525)

**「Background」** The essay is by OpenAI chief scientist Jakub Pachocki, and it draws on the earlier GPT-2 result: OpenAI says GPT-2 set a perplexity state of the art on older datasets and was arguably the first model capable of consistently formulating coherent paragraphs. A commenter on the Hacker News thread adds that the figure under discussion is test-set perplexity for the pretrained next-token predictor, so it measures how well that model performs the task it was trained for rather than a downstream benchmark.

**「Impact」** For teams comparing models, the discussion points to a practical requirement: a perplexity number is only useful for comparison if it comes from the same held-out evaluation set. The thread&\#x27;s disagreement over whether cross-entropy still tracks capability under RL means the score should not be treated as a standalone substitute for task benchmarks.

**「Community Discussion」** Commenters split between finding the perplexity–intelligence link unsurprising—one cited a 2008 compression argument—and being surprised that cross-entropy still tracks capability in the RL era. One commenter criticized the post for never defining perplexity, while another reported that Microsoft&\#x27;s Mustafa Suleyman had added MAI models to the same evaluation chart.

<details><summary>References</summary>
<ul>
<li><a href="https://openai.com/index/perplexity-and-intelligence/">Perplexity and Intelligence | OpenAI</a></li>
<li><a href="https://news.ycombinator.com/item?id=50601525">Perplexity and Intelligence | Hacker News</a></li>

</ul>
</details>

**Tags**: `#llm-evaluation`, `#perplexity`, `#scaling-laws`, `#benchmarking`, `#openai`

---

<a id="item-tech-news-2"></a>
### [FT report alleges Prince Group figure helped smuggle Nvidia chips to China](https://www.ft.com/content/f3ad8a81-3890-4a8a-8853-ff0a94b08ba9?syn-25a6b1a6=1) ⭐️ 7.0/10

A Financial Times report alleges that Hu Xiaowei, identified by the U.S. Treasury Department as the &quot;number two&quot; figure at Cambodia&\#x27;s Prince Group, helped smuggle Nvidia chips into China. Citing people familiar with the matter, the report describes a network involving shell companies, underground financing channels and private jets; Prince Group denied that Hu worked for it and said allegations about an illegal network and private-jet smuggling lacked factual basis. The report also cites trade data showing that Megaspeed&\#x27;s Malaysian subsidiary declared about $4.6 billion in imports between December 2024 and December 2025, with some chips allegedly reaching China&\#x27;s black market.

telegram · zaihuapd · Nov 22, 04:34

**「Background」** The allegations sit inside Washington&\#x27;s export-control regime, which restricts sales of Nvidia&\#x27;s most advanced AI accelerators to China and has pushed some buyers toward grey-market channels. The trade data at issue centers on Megaspeed&\#x27;s Malaysian subsidiary; the FT reported on Nov 10, 2026 that Megaspeed said it had been investigated by US and Malaysian authorities but that there was &quot;no evidence of any violations,&quot; and a related FT investigation tied the distributor to Inspur&\#x27;s unlisted US unit Aivres as a supplier and to an alleged Prince Group figure.

**「Impact」** The report gives export-control enforcers and compliance teams a concrete flow to examine: about $4.6 billion in declared imports by Megaspeed&\#x27;s Malaysian subsidiary, with some chips alleged to have been diverted to China&\#x27;s black market. That scrutiny falls on AI hardware buyers and distributors that source Nvidia GPUs through Southeast Asian intermediaries.

<details><summary>References</summary>
<ul>
<li>Nvidia spy scandal exposes Singapore&#x27;s role in China&#x27;s AI chip trade - Financial Times</li>
<li>FT investigation links Alice Huang&#x27;s Megaspeed to a gaming group, Inspur&#x27;s US unit and an alleged Prince Group figure | MLQ.ai</li>

</ul>
</details>

**Tags**: `#Nvidia`, `#chip smuggling`, `#export controls`, `#AI hardware supply chain`

---

<a id="item-tech-news-3"></a>
### [Windows Server 2028 to drop WoW64 by default, 32-bit apps need manual add](https://www.windowslatest.com/2026/11/23/32-bit-apps-days-are-numbered-as-microsoft-strips-support-bit-by-bit-starting-with-windows-server-2028-but-windows-11-is-safe-for-now/) ⭐️ 7.0/10

Microsoft said at Ignite 2026 that Windows Server 2028 will ship without the WoW64 compatibility subsystem by default, so 32-bit applications will not run out of the box. The release is planned for fall 2027 alongside Windows 11 27H2. Administrators who need 32-bit support can add WoW64 back as a Feature on Demand, typically through PowerShell or DISM on Server Core. Microsoft cited reducing attack surface and blocking 32-bit malware as the rationale; Windows 11 still includes WoW64 and Microsoft has not announced a removal plan for it.

telegram · zaihuapd · Nov 23, 03:03

**「Background」** WoW64 is the compatibility layer that allows 64-bit Windows to run 32-bit applications; without it, the operating system cannot execute those older binaries natively. Windows Server has included WoW64 by default, so administrators could run legacy 32-bit tools without adding a separate optional component.

**「Deployment impact」** Administrators upgrading to Windows Server 2028 will need to inventory 32-bit dependencies and add WoW64 as a Feature on Demand — typically via PowerShell or DISM on Server Core — during or before deployment, since a default installation will not run those applications. Environments that skip this step should expect legacy 32-bit tools and agents to fail after the move.

<details><summary>References</summary>
<ul>
<li><a href="https://www.windowscentral.com/microsoft/windows-11/microsoft-is-removing-32-bit-app-support-from-the-next-version-of-windows-server-wow64-subsystem-to-become-optional-component-to-reduce-malware-attack-surface">Windows Server 2028 to remove 32-bit app support for improved ...</a></li>
<li><a href="https://mezha.net/eng/news/mezha-568ac4f109c1bdf3a06d55a8_32-bit_windows_apps/">32-bit Windows apps won&#x27;t run by default on Windows Server 2028</a></li>

</ul>
</details>

**Tags**: `#Windows Server`, `#WoW64`, `#32-bit compatibility`, `#Microsoft`, `#enterprise IT`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Deliberate Flailing as a Strategy Under Uncertainty](https://seangoedecke.com/when-in-doubt-flail-about/) ⭐️ 6.0/10

rss · Sean Goedecke · Nov 23, 00:00

**「Background」** Sean Goedecke argues that when engineers face an unclear situation—no clear guidance and no obvious path forward—waiting cautiously for better understanding is usually the wrong move.

**「Solution」** His alternative is deliberate “flailing”: try many different things to gain direct contact with reality, pay close attention to feedback from both people and results, and ruthlessly drop approaches that are not working. Trying many options matters because most plans formed under uncertainty will be bad, and having several in play reduces over-investment in any one of them. He applies this to product work, where broad experimentation can uncover unexpected traction—one GitHub Actions token integration on the retired GitHub Models became the seed of “Continuous AI”—and to engineering, where speculative changes to large, tangled systems are more practical than exhaustively studying them first. In organizational work, senior engineers can try a range of interventions to address unclear cross-team problems, but this context carries the greatest reputational risk: dropping a failing plan quickly can build trust, while ignoring feedback can direct others’ frustration at the engineer. Goedecke adds that the process feels like failure from the inside even when managers see a proactive experimenter, so the discomfort should not be mistaken for evidence that the approach is wrong.

**「Takeaway」** Under uncertainty, effective engineers often make progress by experimenting broadly and discarding failures quickly rather than waiting for certainty. The feeling of flailing is a normal cost of learning what actually works.

**Tags**: `#engineering-judgment`, `#experimentation`, `#feedback-loops`, `#product-discovery`, `#organizational-engineering`

---

## Financial News

<a id="item-finance-news-1"></a>
### [U.S. Tech Selloff Met With Asian Market-Stability Measures](https://news.bjd.com.cn/2026/11/22/12039852.shtml) ⭐️ 9.0/10

U.S. tech stocks sold off on Friday, with the Nasdaq down 5.28% and the Philadelphia Semiconductor Index nearly 11%. Mainland China, South Korea, and Taiwan moved to stabilize their markets, including a cut in mainland China&\#x27;s minimum margin-financing ratio to 80%.

telegram · zaihuapd · Nov 22, 13:24

**「Background」** The 80% minimum margin ratio that mainland China restored had last been in force ten months earlier, and it directly sets leverage: at that level, a 1 million yuan deposit supports up to 1.25 million yuan of margin stock purchases.

**「Who is affected」** Taiwan&\#x27;s short sellers and margin traders face higher costs and tighter limits from Nov 23, when shorting below the previous close is banned and margin deposits rise to 150% from 130%, while South Korean listed companies get three months of looser daily buyback limits starting Nov 24.

<details><summary>References</summary>
<ul>
<li><a href="https://finance.eastmoney.com/a/202611223936948742.html">重磅时刻！ A 股 迎三大“新政”！ 影响几何？ 最新解读来了 _ 东方财富网</a></li>
<li><a href="https://www.cls.cn/detail/2541019">三大交易所同时宣布！ 时隔十个 月 融 资 保 证 金 重回 80 %，积极信号明确</a></li>

</ul>
</details>

**Tags**: `#US tech stocks`, `#market selloff`, `#Asia market policy`, `#margin requirements`, `#short-selling restrictions`

---

<a id="item-finance-news-2"></a>
### [Ant Group leads $100 million round in Chinese embodied-AI startup Simplexity at $1.6 billion valuation](https://www.bloomberg.com/news/articles/2026-11-22/ant-group-bets-on-simplexity-to-thrive-in-china-s-humanoid-race) ⭐️ 7.0/10

Ant Group led a $100 million pre-A funding round in Chinese embodied-AI company Simplexity Robotics at a $1.6 billion post-money valuation, co-founder and chairman Wang Kai confirmed to Bloomberg. Existing backers Alibaba, Tencent, HongShan and BlueRun also invested, according to the report.

telegram · zaihuapd · Nov 23, 02:02

**「Background」** Simplexity Robotics was founded in Hangzhou in July 2025 by former Li Auto executives, with Jia Peng as CEO and Wang Kai as chairman. By March 2026 it said it had completed five funding rounds worth 2 billion yuan \(about $290 million\) within six months, at a valuation above $1 billion — the baseline against which the reported $1.6 billion mark is set.

**「Impact」** The capital sharpens competition for Simplexity&\#x27;s larger Chinese rivals such as Unitree and UBTech, in a market where Chinese makers accounted for more than 97% of global humanoid-robot shipments in the first half of 2026, according to market researcher Smart Analytics Global.

<details><summary>References</summary>
<ul>
<li><a href="https://aiweekly.co/alerts/ant-group-leads-100m-pre-a-for-simplexity-at-16b-valuation">Ant Group Leads $100M Pre-A for Simplexity at $1.6B Valuation</a></li>
<li><a href="https://www.caproasia.com/2026/03/14/china-robot-startup-simplexity-robotics-raised-290-million-cny-2-billion-funding-in-last-6-months-with-latest-valuation-at-1-billion-founded-in-2025-by-ex-li-auto-executives-jia-peng-wang-kai/">China Robot Startup Simplexity Robotics Raised $290 Million ...</a></li>
<li><a href="https://global.chinadaily.com.cn/a/202608/11/WS6a7a8b3aa310986e2b46a1a5.html">Chinese humanoid robot makers hold 97% global shipments in H1</a></li>

</ul>
</details>

**Tags**: `#embodied AI`, `#humanoid robotics`, `#venture financing`, `#Ant Group`, `#China tech`

---