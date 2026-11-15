---
layout: default
title: "Horizon Summary: 2026-11-15 (EN)"
date: 2026-11-15
lang: en
---

> From 39 items, 7 important content pieces were selected

---

**Technology News**
1. [Lovable-built apps exposed passport data, 200K messages via weak RLS](#item-tech-news-1) ⭐️ 8.0/10
2. [SpaceX ends Starship Flight 15 with a catch](#item-tech-news-2) ⭐️ 7.0/10
3. [Show HN: DeepSeek V3 inference reimplemented in ~200 lines of JAX](#item-tech-news-3) ⭐️ 7.0/10
4. [EFF argues tech companies are trying to redefine privacy again](#item-tech-news-4) ⭐️ 7.0/10
5. [Project Zero sets 90-day vulnerability disclosure, moving to 60 and 30](#item-tech-news-5) ⭐️ 7.0/10
6. [Tesla Cybercab terms reportedly require $299 monthly autonomy subscription](#item-tech-news-6) ⭐️ 7.0/10

**Financial News**
1. [Nvidia CEO Jensen Huang resigns; analysts weigh AI trade shift](#item-finance-news-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Lovable-built apps exposed passport data, 200K messages via weak RLS](https://www.crissyfield.de/research/lovable-en/) ⭐️ 8.0/10

A security report found that apps built with Lovable exposed passport details and more than 200,000 private messages because their databases lacked sufficient Row-Level Security \(RLS\). Lovable&\#x27;s head of security confirmed that insufficient RLS was the root cause and said the platform automatically scans every app before publishing, offers a free deeper SAST scan, and lets users apply fixes or enable auto-fix. The report and discussion focus on whether underlying defaults, including Supabase&\#x27;s, make such exposure too easy for AI-generated apps.

hackernews · armcat · Nov 14, 17:43 · [Discussion](https://news.ycombinator.com/item?id=50499017)

**「Why Supabase RLS matters here」** Lovable builds full-stack apps on Supabase, a Postgres-based backend whose Row-Level Security policies determine which rows an unauthenticated client can read; a table with RLS left off is readable by anyone holding the project&\#x27;s public anon key. Lovable&\#x27;s documentation states that its Supabase integration runs automated security checks against database configuration, including RLS coverage, and flags issues after schema changes.

**「Impact」** For owners of Lovable-built apps, the practical consequence is that generated schemas and client code can be public while sensitive rows remain reachable unless RLS policies are explicitly verified; the discussion says the reported exposure could be found by inspecting network calls. App owners should audit Supabase RLS policies and test unauthenticated access before treating an app as safe to publish.

**「Community discussion」** The report&\#x27;s author said the post had been submitted earlier but gained little traction, while Lovable&\#x27;s security lead used the thread to describe the platform&\#x27;s pre-publish and SAST scanning. Commenters disagreed over responsibility, with one arguing Supabase&\#x27;s permissive defaults were a major factor and another saying AI-generated apps mainly make old data-exposure mistakes easier to find and more numerous.

<details><summary>References</summary>
<ul>
<li><a href="https://docs.lovable.dev/integrations/supabase">Connect to Supabase - Lovable Documentation</a></li>

</ul>
</details>

**Tags**: `#security vulnerability`, `#AI app builders`, `#Supabase RLS`, `#data exposure`, `#platform defaults`

---

<a id="item-tech-news-2"></a>
### [SpaceX ends Starship Flight 15 with a catch](https://www.spacex.com/launches/starship-flight-15) ⭐️ 7.0/10

SpaceX&\#x27;s Starship Flight 15 ended with a catch of a returning vehicle, a reusability step toward the company&\#x27;s goal of a fully reusable launch system. The submitted item consists of SpaceX&\#x27;s launch-page link and a livestream link, so it does not provide flight telemetry, the condition of the caught hardware, or a technical explanation of the maneuver. Community discussion treats the catch as progress toward reflight and lower payload costs, but those outcomes are not established by the submitted material.

hackernews · ls612 · Nov 14, 21:22 · [Discussion](https://news.ycombinator.com/item?id=50500963)

**「Background」** Starship is SpaceX&\#x27;s reusable launch system, and the program is designed around recovering and reflying hardware rather than expending it after each launch. Flight 15 is part of that test campaign, so the booster catch is a step toward the reusability the vehicle is meant to enable.

**「Reuse implications」** SpaceX caught Starship at the launch tower, but the Super Heavy booster&\#x27;s catch attempt failed and it was redirected to a splashdown in the Gulf. The recovered Ship gives engineers hardware to examine, but Flight 15 did not demonstrate recovery of both stages, which full reuse depends on.

**「Community discussion」** Commenters treated the catch as a reusability milestone: one argued Starship is essentially the Space Shuttle done right because it uses a fully reusable booster and stacks the upper stage on top rather than beside it, while another said the heat shield and a future double catch followed by reflight of the same vehicles will determine whether payload costs fall. A separate commenter cautioned that the final mass fraction to orbit remains unclear and noted that the flight did not catch both vehicles.

<details><summary>References</summary>
<ul>
<li><a href="https://www.zerohedge.com/technology/watch-live-spacex-targets-historic-starship-booster-double-chopsticks-catch">Elon Musk&#x27;s &#x27;Mechazilla&#x27; Catches Starship Rocket In... | ZeroHedg...</a></li>
<li><a href="https://www.youtube.com/watch?v=Ob1oxxIPWzk">Starship Flight 15 launch , ship catch &amp; CNN&#x27;s first... - YouTube</a></li>

</ul>
</details>

**Tags**: `#SpaceX`, `#Starship`, `#reusable launch vehicles`, `#spaceflight`, `#Hacker News`

---

<a id="item-tech-news-3"></a>
### [Show HN: DeepSeek V3 inference reimplemented in ~200 lines of JAX](https://github.com/Vaibhaav-Tiwari/deepseek-v3-jax) ⭐️ 7.0/10

A Show HN project by VaibhaavTiwari reimplements DeepSeek V3 inference in roughly 200 lines of pure JAX. The code is presented as a readable, from-scratch reference rather than a production serving stack, and commenters singled out its educational clarity. Because it targets JAX rather than CUDA-specific tooling, readers also report using it as a starting point on AMD GPUs via ROCm, though that compatibility comes from user reports rather than a stated support commitment in the project description.

hackernews · VaibhaavTiwari · Nov 14, 15:04 · [Discussion](https://news.ycombinator.com/item?id=50497589)

**「Context」** DeepSeek V3 is a mixture-of-experts language model with 671B total parameters, of which 37B are activated per token. The Show HN project is not that model at full scale: a comment on the Hacker News thread describes it as a roughly 190-line, 36.2M-parameter version trained from scratch on 207 old detective novels using jax-metal on a MacBook Air M5 with 24 GB of memory, completing 12,000 steps in about 2.6 hours.

**「Impact」** For developers without CUDA hardware, the project appears to offer a usable entry point: one commenter reported that it was the first project to run end-to-end on an RX 7600 XT 16GB under ROCm, after setting HSA\_OVERRIDE\_GFX\_VERSION=11.0.0 so JAX&\#x27;s plugin would accept the GPU. That is a single user&\#x27;s experience, not a documented support matrix, so others on similar cards should expect to tune environment variables before it works.

**「Community Discussion」** Commenters responded positively to the from-scratch approach, with one saying such posts motivate them to understand how inference actually works and another planning to recreate it for learning. A reader comfortable with Java and Python but new to the area asked whether a roadmap exists for building the relevant intuition, and no such resource was cited in the supplied comments.

<details><summary>References</summary>
<ul>
<li><a href="https://news.ycombinator.com/item?id=50497589">Show HN: DeepSeek V 3 in ~200 lines of pure Jax | Hacker News</a></li>
<li><a href="https://github.com/deepseek-ai/DeepSeek-V3">GitHub - deepseek -ai/ DeepSeek - V 3 · GitHub</a></li>

</ul>
</details>

**Tags**: `#JAX`, `#DeepSeek-V3`, `#LLM inference`, `#model reimplementation`, `#ROCm`

---

<a id="item-tech-news-4"></a>
### [EFF argues tech companies are trying to redefine privacy again](https://www.eff.org/deeplinks/2026/11/tech-companies-are-trying-shift-entire-concept-privacy-again) ⭐️ 7.0/10

The Electronic Frontier Foundation published a deeplink on November 14, 2026 arguing that technology companies are once again attempting to shift the entire concept of privacy. The piece is policy advocacy and analysis rather than a report of a shipped product, court ruling, or measured technical result, and the supplied material does not include the article&\#x27;s full text or the specific companies and proposals it names. Hacker News readers picked up the argument chiefly through the case of AI meeting notetakers, which the discussion treated as an example of surveillance becoming a workplace default.

hackernews · gslin · Nov 14, 12:45 · [Discussion](https://news.ycombinator.com/item?id=50496602)

**「Background」** The EFF post frames the issue as a recurring one: privacy is being redefined from a matter of personal consent to a problem of bystanders being recorded by devices others wear or bring into meetings. It cites Meta and Google smart glasses that can record what the wearer sees and use AI to describe it, Apple&\#x27;s Audio Intelligence feature turning Apple Watch into a transcription device, and Amazon&\#x27;s Bee devices as examples of recording and transcription becoming embedded in everyday hardware.

**「Community Discussion」** Commenter toddmorey described AI notetakers recording nearly every professional meeting, including one-on-one manager conversations, and said opting out seems impossible without jeopardizing employment, asking whether others have normalized requesting the tools be turned off. abecedarius pushed back on blanket bans by noting that live transcription done well could be transformative for deaf and hard-of-hearing users and could run on a local model that saves nothing, while conceding the same system is &quot;one if-statement away from retention.&quot;

<details><summary>References</summary>
<ul>
<li><a href="https://aiweekly.my/items/46520/tech-companies-are-trying-to-shift-the-concept-of-privacy-again">Tech Companies Are Trying to Shift the Concept of Privacy (Again)</a></li>

</ul>
</details>

**Tags**: `#privacy`, `#AI surveillance`, `#EFF policy analysis`, `#meeting transcription`, `#tech industry`

---

<a id="item-tech-news-5"></a>
### [Project Zero sets 90-day vulnerability disclosure, moving to 60 and 30](https://projectzero.google/2026/11/disclosure-policy.html) ⭐️ 7.0/10

Google&\#x27;s Project Zero announced that it will disclose vulnerabilities 90 days after reporting them to vendors under a policy it calls &quot;Full 90,&quot; effective immediately. The team plans to shorten that window to 60 days on February 2, 2027, and to 30 days on January 3, 2028. The change applies to the security team&\#x27;s disclosure practice, not a new product, and compresses the time vendors and maintainers have to patch before details become public.

hackernews · hacb · Nov 14, 11:13 · [Discussion](https://news.ycombinator.com/item?id=50496051)

**「Background」** Since 2021, Project Zero had used a “90 + 30” policy that gave vendors up to 90 days to remediate a vulnerability plus an additional 30-day soak period for patch rollout before disclosure. The new “Full X” schedule removes that separation and shortens the disclosure deadline over time, which Project Zero links to AI-assisted vulnerability discovery and exploitation accelerating the threat landscape.

**「Impact」** Vendors, security teams, and open-source maintainers now have 90 days to fix reported flaws before Project Zero publishes them, with the deadline falling to 60 and then 30 days under the announced schedule. Organizations that rely on coordinated disclosure should plan for shorter patch windows and may need to negotiate earlier fixes or mitigations.

**「Community discussion」** Commenters debated whether even 90 days is workable: one said Ubuntu would need &quot;a LOT more time,&quot; while another argued for immediate release because, in their view, nothing else compels vendors to fix flaws. A separate concern was that companies finding bugs should give vendors access to the AI products used in discovery, so disclosure does not become leverage to drive adoption of those products.

<details><summary>References</summary>
<ul>
<li><a href="https://projectzero.google/2026/11/disclosure-policy.html">Policy and Disclosure: 2026 Edition - Project Zero</a></li>
<li><a href="https://www.verisq.ai/intelligence/policy-and-disclosure-2026-edition-72908">Google Project Zero Shifts to Full 90 Disclosure, Plans Full ...</a></li>

</ul>
</details>

**Tags**: `#vulnerability disclosure`, `#Project Zero`, `#security policy`, `#Google`

---

<a id="item-tech-news-6"></a>
### [Tesla Cybercab terms reportedly require $299 monthly autonomy subscription](https://www.tesla.com/configurator/api/v4/terms?category=autonomy_subs&amp;amp;locale=en_US&amp;amp;model=cc&amp;amp;saleType=Sale) ⭐️ 7.0/10

A secondary report says Tesla&\#x27;s Cybercab terms pair a $29,990 vehicle price with a mandatory $299-per-month autonomous-driving subscription that must remain active for the car to operate. The terms reportedly let Tesla change the subscription price with one month&\#x27;s notice and suspend or cancel service for nonpayment or misuse; three accumulated warnings disable autonomous driving for a week. They also restrict the car to designated operating areas and prohibit connecting it to ride-hailing, delivery, or rental platforms without authorization. The report does not include the full agreement or independent verification; Electrek notes that Cybercab and the robotaxi Model Y share AI4 hardware and autonomous software, while consumer FSD still requires human supervision.

telegram · zaihuapd · Nov 15, 01:10

**「Context」** Tesla&\#x27;s consumer FSD remains a supervised driver-assistance feature, while Cybercab is a purpose-built driverless vehicle with no steering wheel or pedals; Electrek notes it shares AI4 hardware and autonomous software with Tesla&\#x27;s robotaxi Model Y. Reports say Tesla recently began inviting select customers to order a personal-use Cybercab, the arrangement the newly circulated subscription terms now govern.

**「Impact」** For buyers, the $299 monthly charge is a condition of operation rather than an optional add-on, so vehicle usability depends on keeping the Tesla subscription active and avoiding the three-warning threshold that triggers a one-week autonomous-driving lockout. The geofence and platform restrictions also mean a privately purchased Cybercab cannot be used for unauthorized ride-hailing, delivery, or rental work.

<details><summary>References</summary>
<ul>
<li><a href="https://finance.yahoo.com/technology/ai/articles/tesla-starts-taking-cybercab-orders-012249541.html">Tesla Starts Taking Cybercab Orders From Select Customers</a></li>
<li><a href="https://www.zerohedge.com/technology/tesla-opens-cybercab-orders-select-customers-personal-use">Tesla Opens Cybercab Orders To &quot;Select Customers...&quot; | ZeroHedge</a></li>

</ul>
</details>

**Tags**: `#Tesla`, `#Cybercab`, `#自动驾驶`, `#订阅模式`, `#Robotaxi`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Nvidia CEO Jensen Huang resigns; analysts weigh AI trade shift](https://www.cnbc.com/2026/11/14/nvidia-ai-trade-data-centers-congress.html) ⭐️ 7.0/10

Nvidia founder and CEO Jensen Huang resigned, and Yorkville Ives cut its price target on the chipmaker to $225 from $300 while keeping a buy rating, with shares closing the week at $162.85. On CNBC&\#x27;s &quot;ETF Edge,&quot; Roundhill&\#x27;s Dave Mazza and Yorkville Ives&\#x27; Dan Ives argued other Big Tech and AI chip names could gain if investors lose confidence in Nvidia, and Ives estimated a Democratic-controlled Congress could prevent 10% to 20% of planned data centers from being built.

rss · CNBC Finance · Nov 14, 15:50

**「Background」** Nvidia CEO Jensen Huang resigned and CFO Colette Kress was named interim CEO, while Democratic midterm gains led to calls to tighten limits on data centers.

**「Impact」** Investors are rotating from Nvidia into AMD, Broadcom and TSMC, while analysts estimate a Democratic-controlled Congress could keep 10% to 20% of planned data centers from being built and make existing computing capacity more valuable.

<details><summary>References</summary>
<ul>
<li><a href="https://investor.nvidia.com/news/press-release-details/2026/NVIDIA-Announces-CEO-Transition/">NVIDIA Corporation - NVIDIA Announces CEO Transition</a></li>
<li><a href="https://www.cnbc.com/2026/11/05/democrats-data-center-restrictions-midterms.html">Top Democrats call to rein in AI buildout after midterms ...</a></li>
<li><a href="https://www.cnbc.com/2026/11/13/nvidia-jensen-huang-affairs-amd-broadcom-tsmc.html">Nvidia ’s turmoil is prompting a rotation across chip stocks .</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#AI trade`, `#ETFs`, `#semiconductors`, `#data centers`

---