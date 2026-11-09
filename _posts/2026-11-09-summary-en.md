---
layout: default
title: "Horizon Summary: 2026-11-09 (EN)"
date: 2026-11-09
lang: en
---

> From 30 items, 3 important content pieces were selected

---

**Technology News**
1. [KetchUp: an open-source Rust/WebGPU SketchUp alternative for the browser](#item-tech-news-1) ⭐️ 7.0/10
2. [Outlook.com Reportedly Rejects Email From Domains Without DMARC](#item-tech-news-2) ⭐️ 7.0/10
3. [Nvidia Board Reportedly Probes Spying Case Targeting Jensen Huang](#item-tech-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [KetchUp: an open-source Rust/WebGPU SketchUp alternative for the browser](https://ketchup3d.github.io/app/) ⭐️ 7.0/10

KetchUp is an open-source, browser-based SketchUp alternative built with Rust and WebGPU, available at ketchup3d.github.io/app. The Hacker News discussion treats it as an early-stage project: commenters report mouse-only navigation and ask for feature showcases on the landing page. The item provides no version number, release date, or detailed feature list, so its current capabilities and compatibility are not established here.

hackernews · dcoulmbe · Nov 8, 22:35 · [Discussion](https://news.ycombinator.com/item?id=50418176)

**「SketchUp&\#x27;s ownership and licensing shift」** SketchUp, the proprietary modeler KetchUp is named after, was sold by Google to Trimble in 2012; it offers a free web-based version and three paid subscriptions for Windows and macOS \[tool-1-3\].

**「Impact」** For trackpad users, the current input model is a concrete blocker: commenters report the app appears mouse-only, unlike SketchUp, where modifier keys handle pan, zoom, and orbit. Those users may need a mouse to navigate KetchUp until trackpad support is added.

**「Community discussion」** Commenters praised the browser UI and text rendering and welcomed an open-source SketchUp successor; one argued that AI-assisted custom tooling may make learning general-purpose modelers less necessary. The specific complaints were mouse-only controls and a landing page that does not showcase features.

<details><summary>References</summary>
<ul>
<li><a href="https://www.wikiwand.com/en/articles/Google_SketchUp">SketchUp - Wikiwand</a></li>

</ul>
</details>

**Tags**: `#Rust`, `#WebGPU`, `#open source`, `#3D modeling`, `#browser apps`

---

<a id="item-tech-news-2"></a>
### [Outlook.com Reportedly Rejects Email From Domains Without DMARC](https://mailroute.net/blog/outlook-rejecting-email-without-dmarc) ⭐️ 7.0/10

Outlook.com is reportedly rejecting email from domains that do not publish a DMARC record, according to a Mailroute blog post discussed on Hacker News. The reported change affects anyone sending mail to Outlook.com addresses, including operators of their own mail servers and transactional email senders. The supplied material does not establish when enforcement began, how broadly it applies, or whether Microsoft has documented the policy.

hackernews · xmddmx · Nov 8, 19:20 · [Discussion](https://news.ycombinator.com/item?id=50416158)

**「What DMARC requires」** DMARC is the policy layer on top of SPF and DKIM: a domain owner publishes a DNS record telling receiving providers what to do with mail that fails authentication — typically to quarantine or reject it — and where to send aggregate reports. For a provider to apply a reject policy, senders must first align their sending domains with authenticated, signed mail. A commenter in the discussion asks whether Gmail introduced a comparable requirement in 2024, though the thread supplies no documentation for that claim.

**「Impact for senders」** Domains without any DMARC record are now reported to get permanent 5xx failures \(a 550 5.7.1 bounce\) from Outlook.com, Hotmail and Live, so transactional and low-volume mail to those mailboxes will fail outright until a record is published. Publishing a DMARC TXT record — reportedly even with p=none — is described as the fix, meaning senders can restore delivery without immediately enforcing alignment. Passing DMARC does not guarantee inbox placement, though, so senders should still monitor delivery separately.

**「Community Discussion」** Commenters debated the framing: one reported that Outlook.com also blocks mail through non-public blocklists with no clear delisting path, while another argued that rejecting domains without DMARC is reasonable but should not happen silently; a third disputed that it is quiet, saying Outlook returns 5xx permanent delivery failures. Others reported long-standing silent filtering even with SPF, DKIM, and DMARC configured, and asked whether Gmail introduced similar requirements in 2024.

<details><summary>References</summary>
<ul>
<li><a href="https://mailroute.net/blog/outlook-rejecting-email-without-dmarc">Outlook.com Is Quietly Rejecting Email From Domains Without DMARC</a></li>
<li><a href="https://anintent.com/blog/outlook-rejecting-email-dmarc/">Outlook.com Rejecting Email Without DMARC | AnIntent</a></li>
<li><a href="https://tosend.com/articles/outlook-rejects-email-without-dmarc/">Outlook.com now rejects email from domains without DMARC</a></li>

</ul>
</details>

**Tags**: `#email deliverability`, `#DMARC`, `#email security`, `#Microsoft Outlook`, `#SMTP`

---

<a id="item-tech-news-3"></a>
### [Nvidia Board Reportedly Probes Spying Case Targeting Jensen Huang](https://nvidianews.nvidia.com/news/statement-from-nvidia-board-of-directors) ⭐️ 7.0/10

Nvidia&\#x27;s board is reportedly investigating an intelligence operation that targeted CEO Jensen Huang, not investigating Huang himself, according to the submitted report and commenters. One commenter cited a Bloomberg headline saying the board would probe a spying case after Huang admitted infidelity. The supplied source page contained no article text, so the board statement&\#x27;s wording and the investigation&\#x27;s scope could not be independently verified here.

hackernews · vincentchau · Nov 8, 20:26 · [Discussion](https://news.ycombinator.com/item?id=50416801)

**「Earlier development」** The board inquiry follows CEO Jensen Huang’s admission to employees that he was unfaithful to his wife, according to Bloomberg. That admission prompted the board to examine whether Huang had been targeted by a foreign espionage plot.

**「Community Discussion」** Commenters focused first on correcting the submitted headline, with nrmitchi arguing it wrongly implied Huang was the target of Nvidia&\#x27;s investigation. Others cited additional reporting and debated whether a CEO of Huang&\#x27;s prominence would inevitably be targeted by foreign intelligence services, while aigalaxiome stressed that any misconduct by Huang or Nvidia remains unproven.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-08/nvidia-board-to-probe-spying-case-after-ceo-jensen-huang-admits-infidelity">Nvidia Board to Probe Spying Case After CEO Jensen Huang ...</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#Jensen Huang`, `#corporate governance`, `#espionage investigation`, `#tech industry news`

---