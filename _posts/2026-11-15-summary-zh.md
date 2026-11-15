---
layout: default
title: "Horizon Summary: 2026-11-15 (ZH)"
date: 2026-11-15
lang: zh
---

> 从 39 条内容中筛选出 7 条重要资讯。

---

**科技新闻**
1. [Lovable 应用因 RLS 不足泄露护照信息与逾 20 万私信](#item-tech-news-1) ⭐️ 8.0/10
2. [SpaceX 在 Flight 15 任务中完成 Starship 捕捉](#item-tech-news-2) ⭐️ 7.0/10
3. [约 200 行纯 JAX 实现 DeepSeek V3 推理](#item-tech-news-3) ⭐️ 7.0/10
4. [EFF 称科技公司再次试图重塑隐私概念](#item-tech-news-4) ⭐️ 7.0/10
5. [Project Zero 将漏洞披露期限设为 90 天并计划逐步缩短](#item-tech-news-5) ⭐️ 7.0/10
6. [特斯拉 Cybercab 协议曝光：车价 2.999 万美元，强制月订阅 299 美元](#item-tech-news-6) ⭐️ 7.0/10

**财经新闻**
1. [黄仁勋辞职后，分析师下调英伟达目标价，AI 交易格局或生变](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Lovable 应用因 RLS 不足泄露护照信息与逾 20 万私信](https://www.crissyfield.de/research/lovable-en/) ⭐️ 8.0/10

一份安全研究报告称，部分由 Lovable 生成的应用因行级安全（RLS）配置不足，暴露了护照信息和超过 20 万条私信。Lovable 安全负责人 Igor 在 Hacker News 回应称，根因正是其扫描功能要捕捉的 RLS 不足，并称平台会在发布前自动扫描每个应用、向所有用户免费提供更深入的 SAST 扫描，以及“修复”、后台自动修复和发布阻断等选项。上述信息来自研究文章和厂商在讨论中的回应。

hackernews · armcat · 11月14日 17:43 · [社区讨论](https://news.ycombinator.com/item?id=50499017)

**「背景：Supabase 的 RLS 与暴露情况」** Lovable 应用常通过 Supabase 提供数据库；行级安全（RLS）是 Supabase 用来限制不同用户可读写哪些数据行的机制，配置不足会让本应私有的记录可被直接读取。Lovable 文档称会在数据库架构变更后自动检查 RLS 覆盖情况并标记问题，但 Crissy Field 的扫描发现 7,403 个站点无需登录即可读取含邮箱地址的数据库记录。

**「影响」** 如果 RLS 未正确配置，应用即使界面正常，私信和身份信息仍可能通过浏览器网络请求被读取；使用 Lovable 和 Supabase 的开发者因此需要以未登录或普通用户身份逐表验证读取权限，而不能只依赖界面隐藏或平台扫描。

**「社区讨论」** 评论区的争论集中在责任归属：有评论者把部分责任归给 Supabase，称其早年为了降低上手门槛而采用宽松默认值，并提到相关修复据称已在 10 月 30 日完成、但有报告称现有项目仍沿用旧默认值；也有人主张平台应默认拒绝、最小权限并自动测试鉴权，让不安全的 AI 生成部署更难发生。另有评论指出，数据泄露并非 AI 时代才有，但这类应用数量多、攻击门槛低，普通用户往往不知道风险。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://lockship.dev/guides/lovable-exposed-databases-check">7,403 Lovable sites with readable data: what happened and how to...</a></li>
<li><a href="https://docs.lovable.dev/integrations/supabase">Connect to Supabase - Lovable Documentation</a></li>

</ul>
</details>

**标签**: `#security vulnerability`, `#AI app builders`, `#Supabase RLS`, `#data exposure`, `#platform defaults`

---

<a id="item-tech-news-2"></a>
### [SpaceX 在 Flight 15 任务中完成 Starship 捕捉](https://www.spacex.com/launches/starship-flight-15) ⭐️ 7.0/10

SpaceX 的任务页面称，Starship Flight 15 以一次 Starship 捕捉结束，公司同时发布了相关视频链接。提供的材料没有给出捕捉高度、速度、具体飞行器编号或复用周转时间，因此这应视为公司公布的任务结果，尚缺独立测量数据。对关注可复用火箭的人来说，直接变化是飞行器以捕捉方式收尾而非一次性使用；它能否降低发射成本，仍取决于后续复飞和翻修记录。

hackernews · ls612 · 11月14日 21:22 · [社区讨论](https://news.ycombinator.com/item?id=50500963)

**「背景」** 在 Starship 试飞中，“捕获”指返回的箭体在发射塔前悬停、由塔架机械臂夹住，目标是省去着陆腿并加快复用周转。Flight 15 以捕获动作收尾，评论者把“双捕获”和复飞同一艘飞船视为下一道验证关口。

**「完全复用尚未验证」** 此次被机械臂捕获的是 Starship 飞船本体，而 Super Heavy 助推器未能返回发射塔，被改道溅落在墨西哥湾。这意味着“两级全回收”仍未得到验证；在重复使用同一艘飞船、并确认隔热瓦能承受再入之前，载荷方和发射计划仍需按部分复用甚至一次性的条件来安排运力与成本。

**「社区讨论」** 有评论者把 Starship 称为“做对了的航天飞机”，理由是无固体助推器、飞船叠在助推器上方以及流水线制造，认为这更接近完全复用。也有人把热防护视为成败关键，并把“双捕捉”、复飞同一批飞船和再次捕捉列为下一步；ChuckMcM 则评论说，若助推器多带几吨推进剂，或许这次能把两个飞行器都抓住，他还表示最终入轨质量分数仍不清楚。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.zerohedge.com/technology/watch-live-spacex-targets-historic-starship-booster-double-chopsticks-catch">Elon Musk&#x27;s &#x27;Mechazilla&#x27; Catches Starship Rocket In... | ZeroHedg...</a></li>
<li><a href="https://www.cbsnews.com/news/spacex-launches-starship-flight-rocket/">SpaceX launches milestone Starship flight to... - CBS News</a></li>
<li><a href="https://www.youtube.com/watch?v=Ob1oxxIPWzk">Starship Flight 15 launch , ship catch &amp; CNN&#x27;s first... - YouTube</a></li>

</ul>
</details>

**标签**: `#SpaceX`, `#Starship`, `#reusable launch vehicles`, `#spaceflight`, `#Hacker News`

---

<a id="item-tech-news-3"></a>
### [约 200 行纯 JAX 实现 DeepSeek V3 推理](https://github.com/Vaibhaav-Tiwari/deepseek-v3-jax) ⭐️ 7.0/10

项目作者 VaibhaavTiwari 在 Show HN 发布了 deepseek-v3-jax，用约 200 行纯 JAX 代码重实现 DeepSeek V3 推理，定位为便于理解推理流程的精简实现。它是非官方项目，现有材料没有给出与官方实现的速度、显存占用或数值一致性对比，因此目前只能确认其教学与实验价值，不能据此判断生产可用性。仓库已公开在 GitHub，讨论集中在学习体验和硬件兼容性上。

hackernews · VaibhaavTiwari · 11月14日 15:04 · [社区讨论](https://news.ycombinator.com/item?id=50497589)

**「背景」** DeepSeek-V3 是 DeepSeek 推出的混合专家（MoE）语言模型，总参数 671B、每个 token 激活约 37B；其注意力与 MoE 路由结构比稠密模型更绕，因此常被选作「从零手写推理」的教学对象。该 Show HN 讨论帖中提到，这份约 190 行的实现所配套的演示模型只有 36.2M 参数，是在 MacBook Air M5（24 GB）上用 jax-metal 在 207 本旧侦探小说上训练 12,000 步、耗时约 2.6 小时得到的，并非直接加载完整的 671B 权重。

**「实际影响」** 对想在 AMD ROCm 上尝试 DeepSeek V3 推理的开发者，一位使用 RX 7600 XT 16GB 的评论者报告，该项目在其 Fedora/ROCm 环境中首次端到端跑通；但他同时提到需要设置 HSA\_OVERRIDE\_GFX\_VERSION=11.0.0 等环境变量，说明这类兼容性仍依赖手动配置。

**「社区讨论」** 评论者普遍肯定从第一性原理重建模型的教学价值，有人表示要照着复刻，也有人询问系统学习推理的路线图；这些属于主观学习体验，并非对实现正确性或性能的独立验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://news.ycombinator.com/item?id=50497589">Show HN: DeepSeek V 3 in ~200 lines of pure Jax | Hacker News</a></li>
<li><a href="https://github.com/deepseek-ai/DeepSeek-V3">GitHub - deepseek -ai/ DeepSeek - V 3 · GitHub</a></li>

</ul>
</details>

**标签**: `#JAX`, `#DeepSeek-V3`, `#LLM inference`, `#model reimplementation`, `#ROCm`

---

<a id="item-tech-news-4"></a>
### [EFF 称科技公司再次试图重塑隐私概念](https://www.eff.org/deeplinks/2026/11/tech-companies-are-trying-shift-entire-concept-privacy-again) ⭐️ 7.0/10

电子前沿基金会（EFF）发表评论文章，称科技公司正在再次推动对“隐私”概念的重定义。相关 Hacker News 讨论的焦点不在某项具体产品发布，而在 AI 会议记录工具日益进入日常工作场景：有评论者称，专业会议甚至管理者与同事的一对一沟通都会被 AI 记录并上传。现有材料显示这是一篇政策评论，而非具体产品发布或经独立验证的技术突破。

hackernews · gslin · 11月14日 12:45 · [社区讨论](https://news.ycombinator.com/item?id=50496602)

**「背景」** 这篇 EFF 文章把隐私争议重新框定为“旁观者隐私”问题，而不只是设备使用者是否同意：智能眼镜和可穿戴录音、转录设备会在周围人未必知情或同意的情况下采集信息。文章举出的例子包括 Meta 和 Google 的智能眼镜、把 Apple Watch 变成转录设备的 Apple Audio Intelligence，以及 Amazon 的 Bee 设备；这些也是 Hacker News 讨论中围绕 AI 会议记录和录音规范的背景。

**「影响」** 对员工而言，最直接的影响是会议中的同意与退出机制变得关键：有评论者表示，连一对一沟通也被 AI 记录，而拒绝参与可能危及工作。这使得“会前确认是否开启转录、谁能关闭它”成为使用这类工具的组织需要明确说明的实际问题。

**「社区讨论」** 评论者一方面询问如何在不影响就业的情况下减少被 AI 会议记录工具曝光的风险，另一方面也有人指出，实时转录对失聪和重听用户可能具有变革性，并认为本地模型可以做到不保存、不导出数据，因此一概禁用可能伤害无障碍用途。还有评论者引用《世界人权宣言》第 12 条，强调任意干涉隐私不可接受。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://aiweekly.my/items/46520/tech-companies-are-trying-to-shift-the-concept-of-privacy-again">Tech Companies Are Trying to Shift the Concept of Privacy (Again)</a></li>

</ul>
</details>

**标签**: `#privacy`, `#AI surveillance`, `#EFF policy analysis`, `#meeting transcription`, `#tech industry`

---

<a id="item-tech-news-5"></a>
### [Project Zero 将漏洞披露期限设为 90 天并计划逐步缩短](https://projectzero.google/2026/11/disclosure-policy.html) ⭐️ 7.0/10

Project Zero 将漏洞披露窗口设定为向厂商报告后 90 天公开。社区讨论中引述的公告时间表称，这一窗口将在 2027 年 2 月 2 日缩短至 60 天，并在 2028 年 1 月 3 日进一步缩短至 30 天；由于提交材料没有完整政策文本，例外条件和延期机制尚不明确。

hackernews · hacb · 11月14日 11:13 · [社区讨论](https://news.ycombinator.com/item?id=50496051)

**「背景：从「90+30」到「Full 90」」** Project Zero 自 2021 年起实行「90+30」披露政策：先给厂商最多 90 天修复漏洞，再额外留出 30 天「浸泡期」用于补丁分发，目的是既催促厂商加快修复，又保证用户能拿到补丁。新公布的「Full 90」取消了这额外的 30 天缓冲，并计划在 2027 年 2 月 2 日收紧到 60 天、2028 年 1 月 3 日收紧到 30 天；官方将这一转向归因于 AI 辅助的漏洞发现与利用加快了攻击节奏。

**「影响」** 对依赖上游协调的厂商和发行版而言，固定 90 天倒计时压缩了评估、修复、测试与回移植的时间；社区评论以 Ubuntu 为例指出，下游发行版可能需要远超这一窗口的时间，若 30 天阶段如期实施，补丁合并与发布流程需提前调整。

**「社区讨论」** 评论者争论缩短窗口是否现实：一人认为 Ubuntu 等发行版需要远多于 90 天的时间，另一人则主张立即公开，认为只有披露压力才能迫使厂商修复。这些都属于评论者判断，而非公告文本确认的细节。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://projectzero.google/2026/11/disclosure-policy.html">Policy and Disclosure: 2026 Edition - Project Zero</a></li>
<li><a href="https://projectzero.google/vulnerability-disclosure-faq.html">Vulnerability Disclosure FAQ - Project Zero</a></li>

</ul>
</details>

**标签**: `#vulnerability disclosure`, `#Project Zero`, `#security policy`, `#Google`

---

<a id="item-tech-news-6"></a>
### [特斯拉 Cybercab 协议曝光：车价 2.999 万美元，强制月订阅 299 美元](https://www.tesla.com/configurator/api/v4/terms?category=autonomy_subs&amp;amp;locale=en_US&amp;amp;model=cc&amp;amp;saleType=Sale) ⭐️ 7.0/10

一则引用特斯拉配置器条款接口的帖子披露，Cybercab 定价 29,990 美元，车主须每月支付 299 美元自动驾驶订阅费，否则车辆无法运行；特斯拉可提前一个月通知调价。协议还规定，欠费或违规使用可能导致订阅暂停或取消，累计三次警告会停用自动驾驶一周；车辆仅在指定区域内运行，未经授权不得接入网约车、配送或租赁平台。Electrek 指出，Cybercab 与用于 Robotaxi 的 Model Y 采用相同的 AI4 硬件并运行相同的自动驾驶软件，但面向普通车主的 FSD 仍需人类监督。上述内容属于二手摘要，未附协议全文，相关条款尚未得到特斯拉或独立信源确认。

telegram · zaihuapd · 11月15日 01:10

**「背景」** 此前，特斯拉已开始邀请部分客户预订 Cybercab 个人用车，报价为 29,990 美元，并要求每月支付 299 美元的 Autonomy 订阅才能运行车辆；该车为无方向盘、无踏板设计。此次曝光的协议是在这一购买与订阅框架下，进一步列出调价、欠费停用和运营范围等具体条件。

**「影响」** 如果这些条款属实，车主除购车款外每年还需承担 3,588 美元的固定订阅支出，而且车辆被禁止接入第三方网约车、配送或租赁平台，因此很难用于自营营运；潜在买家需要按“车价＋强制订阅＋限定运营范围”重新计算回本模型。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://finance.yahoo.com/technology/ai/articles/tesla-starts-taking-cybercab-orders-012249541.html">Tesla Starts Taking Cybercab Orders From Select Customers</a></li>
<li><a href="https://www.zerohedge.com/technology/tesla-opens-cybercab-orders-select-customers-personal-use">Tesla Opens Cybercab Orders To &quot;Select Customers...&quot; | ZeroHedge</a></li>

</ul>
</details>

**标签**: `#Tesla`, `#Cybercab`, `#自动驾驶`, `#订阅模式`, `#Robotaxi`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [黄仁勋辞职后，分析师下调英伟达目标价，AI 交易格局或生变](https://www.cnbc.com/2026/11/14/nvidia-ai-trade-data-centers-congress.html) ⭐️ 7.0/10

英伟达创始人兼 CEO 黄仁勋辞职后，Yorkville Ives 将其目标价从 300 美元下调至 225 美元，但维持“买入”评级；英伟达股价上周收于每股 162.85 美元。在 CNBC“ETF Edge”节目中，Roundhill 与 Yorkville Ives 的业者表示，若投资者对英伟达失去信心，大型科技公司和其他 AI 芯片厂商可能受益，而民主党掌控国会后对数据中心的阻力也可能影响算力供给。

rss · CNBC Finance · 11月14日 15:50

**「背景」** 英伟达宣布黄仁勋辞去首席执行官职务，由首席财务官科莱特·克雷斯（Colette Kress）出任临时 CEO。此前 11 月 3 日中期选举后民主党赢得国会控制权，民主党人随即呼吁对 AI 数据中心建设施加更严格限制。

**「影响」** 若投资者对英伟达的信任动摇，资金可能流向其他芯片供应商：AMD、博通等芯片设计商，以及为英伟达代工最先进处理器的台积电都可能获得更多关注；台积电的受益不取决于哪家设计商最终胜出。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://investor.nvidia.com/news/press-release-details/2026/NVIDIA-Announces-CEO-Transition/">NVIDIA Corporation - NVIDIA Announces CEO Transition</a></li>
<li><a href="https://finance.yahoo.com/technology/ai/articles/nvidia-ceo-jensen-huang-resigns-110116748.html">Nvidia CEO Jensen Huang Resigns — CFO Collette Kress in as...</a></li>
<li><a href="https://www.cnbc.com/2026/11/05/democrats-data-center-restrictions-midterms.html">Top Democrats call to rein in AI buildout after midterms ...</a></li>
<li><a href="https://www.cnbc.com/2026/11/13/nvidia-jensen-huang-affairs-amd-broadcom-tsmc.html">Nvidia ’s turmoil is prompting a rotation across chip stocks .</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#AI trade`, `#ETFs`, `#semiconductors`, `#data centers`

---