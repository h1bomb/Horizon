---
layout: default
title: "Horizon Summary: 2026-11-20 (ZH)"
date: 2026-11-20
lang: zh
---

> 从 33 条内容中筛选出 9 条重要资讯。

---

**科技新闻**
1. [PostgreSQL 19 发布，新增 WAIT FOR LSN 实现从库读己之写](#item-tech-news-1) ⭐️ 9.0/10
2. [Anthropic 登陆纳斯达克，首日收盘较开盘价跌约 13%](#item-tech-news-2) ⭐️ 8.0/10
3. [英国政府被迫承认曾向苹果发出秘密加密令](#item-tech-news-3) ⭐️ 8.0/10
4. [PHP 混合大小写 HTTPS 静默关闭 TLS，修复已发布](#item-tech-news-4) ⭐️ 8.0/10
5. [Anthropic 称 Claude 参与解决两个黑洞物理开放问题](#item-tech-news-5) ⭐️ 7.0/10
6. [OpenJDK PR 32781 关联 Java RCE 报告，披露过程引争议](#item-tech-news-6) ⭐️ 7.0/10
7. [OpenAI 称其模型参与 Jalapeño 芯片设计，AMD GPU IP 的 PPA 最高提升 14%](#item-tech-news-7) ⭐️ 7.0/10
8. [Gemini 在 Mac 上新增电脑操作，可后台运行并暂停](#item-tech-news-8) ⭐️ 7.0/10

**财经新闻**
1. [Anthropic 纳斯达克上市首日开盘涨 34%，市值约 1.5 万亿美元](#item-finance-news-1) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [PostgreSQL 19 发布，新增 WAIT FOR LSN 实现从库读己之写](https://simonwillison.net/2026/Nov/19/postgresql-19/) ⭐️ 9.0/10

PostgreSQL 19 已发布，比通常的 9 月发布窗口晚约两个月；消息称延迟主要与团队需处理大量由 AI 报告的漏洞问题有关。该版本新增 WAIT FOR LSN：从库上的会话可先等待预写日志（WAL）回放到指定日志序列号（LSN），再执行查询，从而读取主库刚写入的数据，实现“读己之写”一致性。用法是先在主库调用 pg\_current\_wal\_insert\_lsn\(\) 取得 LSN，再把该值传给从库的 WAIT FOR LSN，并可选用 WITH \(TIMEOUT &\#x27;0.1s&\#x27;\)；若从库未在时限内追上，则会返回错误。

rss · Simon Willison · 11月19日 20:43

**「背景」** 背景在于，当应用从异步备库读取时，备库回放 WAL 可能落后于主库，因此应用刚在主库完成写入后立刻从备库读取，未必能读到自己的修改。PostgreSQL 19 之前，这类“读己之写”一致性通常要由应用记录 WAL 位点并等待备库追赶，Wikipedia/MediaWiki 就曾基于 MySQL 复制手工实现类似逻辑；WAIT FOR LSN 把这一等待步骤内置到 PostgreSQL 会话中，并可选设置超时。

**「影响」** 对把读请求分流到从库的应用而言，这提供了数据库内建的等待复制追上机制，不再必须自行轮询复制位点。应用需要把主库返回的 LSN 随会话或后续请求保存，并处理 WAIT FOR LSN 超时时的错误，例如决定重试或改走主库。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://clickhouse.com/blog/postgresql-19-wait-for-read-your-writes">Read your writes : WAIT FOR in PostgreSQL 19 | ClickHouse</a></li>
<li><a href="https://rednafi.com/system/pg-wait-for-lsn/">Reading your own writes with WAIT FOR LSN in Postgres 19</a></li>

</ul>
</details>

**标签**: `#PostgreSQL`, `#databases`, `#open source`, `#release`, `#WAIT FOR LSN`

---

<a id="item-tech-news-2"></a>
### [Anthropic 登陆纳斯达克，首日收盘较开盘价跌约 13%](https://www.reuters.com/business/finance/anthropics-historic-debut-put-ais-promise-peril-wall-st-test-2026-11-19/) ⭐️ 8.0/10

据路透社报道，AI 公司 Anthropic 于 11 月 19 日在纳斯达克挂牌上市，成为少数进入公开市场的头部大模型开发商之一。Hacker News 讨论中引述的行情数字显示，其 IPO 发行价为每股 83 美元，开盘报 111.5 美元，收盘 97.17 美元，即较发行价上涨约 17%，但较开盘价下跌约 12.85%。由于本条仅提供标题与链接、没有正文内容，募资规模、上市估值与承销细节均无法从现有材料核实。

hackernews · wslh · 11月19日 17:02 · [社区讨论](https://news.ycombinator.com/item?id=50562754)

**「背景」** IPO 的发行价是公司在挂牌前与承销商确定的售股价，而开盘价由上市后的首笔公开交易形成，二者可能明显不同。Anthropic 的 IPO 以每股 83 美元定价，筹集 813 亿美元，并于 2026 年 11 月 19 日以代码 ANT 在纳斯达克开始交易；其开盘价为 111.50 美元，较发行价高 34%。

**「对同类 AI 公司上市的参照作用」** 对 Anthropic 的持股员工和 IPO 认购者来说，实际回报取决于股价在首日冲高后能否守在发行价之上，而不是开盘那一刻的涨幅。这次上市也为其他考虑 IPO 的 AI 公司提供了估值参照：《财富》报道称，OpenAI 此前被报道正走向约 8520 亿美元估值，但尚未提交 IPO 文件，因此 Anthropic 在公开市场上的定价会成为检验这类私募估值的直接对照。

**「社区讨论」** 评论区对首日走势解读分歧明显：有评论者强调，只有以 83 美元发行价拿到股票的投资者才盈利，在开盘价买入者当日即为浮亏；也有人据此推断，此前市场上流传的更高私募估值（有评论提到 2 万亿美元以上）偏离实际，并认为这对同样在私募市场高估值的 OpenAI 不是好信号。多位资深工程师则从个人经历出发，担忧 AI 编程工具正在压缩初级与中级软件岗位的空间，不过这些属于个人判断而非已证实的事实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.euronews.com/2026/11/19/anthropic-shares-open-34-above-ipo-price-in-nasdaq-debut-after-record-listing">Anthropic shares open 34% above IPO price in Nasdaq debut</a></li>
<li><a href="https://admiralmarkets.com/analytics/traders-blog/anthropic-stock-ant-first-day-trading">Anthropic Stock (ANT): First Day of Trading After $83 IPO</a></li>
<li><a href="https://fortune.com/2026/06/02/anthropic-ipo-openai-valuation-ai-bubble/?trk=article-ssr-frontend-pulse_little-text-block">Top analyst sees &#x27;opening of the floodgates for the IPO market &#x27; after....</a></li>

</ul>
</details>

**标签**: `#Anthropic`, `#Nasdaq listing`, `#AI industry`, `#public markets`, `#technology valuations`

---

<a id="item-tech-news-3"></a>
### [英国政府被迫承认曾向苹果发出秘密加密令](https://macanorak.com/uk-government-forced-to-admit-it-issued-apple-a-secret-encryption-order/) ⭐️ 8.0/10

英国政府被迫承认，曾向苹果发出过一项秘密加密令，但该命令的具体内容目前仍未公开。现有公开信息只确认了这道命令的存在，没有披露它要求苹果采取什么技术措施、覆盖哪些数据类型或适用于哪些用户。由于内容保密，外界尚无法独立判断该命令对苹果加密能力和用户数据保护的实际影响。

hackernews · Terretta · 11月19日 16:21 · [社区讨论](https://news.ycombinator.com/item?id=50562113)

**「背景」** 此次披露源于英国依据《2016 年调查权力法》向苹果发出的技术能力通知（TCN），该通知此前受保密令约束，苹果甚至被禁止披露其存在。据 TechCrunch 报道，这份秘密命令后来被缩小到允许获取存储在苹果加密云中的英国国民数据，苹果也对第二份命令提出了挑战。调查权力法庭随后裁定苹果可以公开该命令；而在 TCN 于 2025 年 2 月首次曝光后，英国政府一直拒绝置评，直到周四才打破沉默。

**「影响」** 对英国的苹果用户和开发者而言，命令内容不公开意味着他们无法判断哪些服务或数据可能受到影响，也无法依据公开信息独立验证苹果的相关安全承诺。

**「社区讨论」** 有评论者认为，苹果已把安全承诺的措辞从“任何人都无法访问你的数据”改为“苹果无法访问你的数据”，并称设备上的密钥可能只是用于解开另一把数据密钥的 KEK，因此这种变化具有误导性；另一名评论者援引调查权力法庭的判决指出，媒体是通过机密安全简报得知该命令的，而不是通过泄露，命令内容目前仍属保密。还有评论批评英国在 mass surveillance（大规模监控）问题上长期不重视隐私。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://techcrunch.com/2026/11/19/u-k-government-forced-to-disclose-secret-apple-backdoor-order/">UK government forced to disclose secret Apple backdoor order</a></li>
<li><a href="https://9to5mac.com/2026/11/19/uk-court-rules-apple-can-share-the-top-secret-order-everyone-already-knew/">UK court rules Apple can share the top secret order everyone already...</a></li>
<li><a href="https://www.ft.com/content/46a5cf3c-a827-477f-b72f-e7415565e729?syn-25a6b1a6=1">UK loses bid to keep Apple ‘backdoor’ order secret</a></li>

</ul>
</details>

**标签**: `#encryption`, `#privacy`, `#Apple`, `#UK government`, `#surveillance`

---

<a id="item-tech-news-4"></a>
### [PHP 混合大小写 HTTPS 静默关闭 TLS，修复已发布](https://x.com/ljachowicz/status/2123477025268924514) ⭐️ 8.0/10

PHP 的 HTTP/FTP 流包装器被曝在识别混合大小写协议名时，只有第五个字符为小写 s 才启用 TLS，因此 HTTPS://、httpS:// 和 FTPS:// 会被当作明文 HTTP/FTP 发出。该漏洞编号为 CVE-2026-128064（GHSA-f6gg-rchx-xw8j），CVSS 4.0 评分为 8.2，可能导致令牌、Basic 认证、Cookie、POST 请求体和 FTP 登录信息在直接请求或第三方重定向场景下暴露。修复已在 PHP 8.2.36、8.3.37、8.4.28、8.5.13 和 8.6.0 发布。8.1 及更早版本已 EOL，不会获得修复，使用者需自行将 URL 协议名统一转换为小写。

telegram · zaihuapd · 11月20日 03:04

**「背景：PHP 流包装器的 scheme 判定」** PHP 的 file\_get\_contents\(\)、fopen\(\) 等函数通过 HTTP/FTP 流包装器访问远程 URL，这类包装器识别 scheme 时不区分大小写。根据漏洞库对 CVE-2026-128064 的描述，包装器只在 scheme 固定位置出现小写 “s” 时才启用 TLS，因此 HTTPS://、FTPS:// 这类混合大小写地址会被当作明文 HTTP/FTP 处理，HTTP 重定向指向此类地址时同样如此。

**「受影响范围与处置」** 由于 PHP 8.1 及更早分支已 EOL（停止支持）且不会获得修复，仍在使用这些版本的部署必须自行把 URL scheme 统一转成小写，包括跟随重定向后得到的地址；否则凭据、Cookie 和 POST 请求体可能以明文发出。受支持分支应升级到 8.2.36、8.3.37、8.4.28、8.5.13 或 8.6.0；CVE-2026-128064 的公开记录目前未列出利用代码，但这不能替代修补。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.rapid7.com/db/vulnerabilities/cve-2026-128064/">CVE-2026-128064: PHP Group PHP: Mixed-case HTTPS and FTPS ...</a></li>
<li><a href="https://cvefeed.io/vuln/detail/CVE-2026-128064">CVE-2026-128064 - Mixed-case HTTPS and FTPS URLs can expose ...</a></li>
<li><a href="https://everycve.com/CVE-2026-128064">CVE - 2026 - 128064 : Mixed-case HTTPS and FTPS URLs can expose...</a></li>

</ul>
</details>

**标签**: `#PHP`, `#TLS`, `#security vulnerability`, `#CVE`, `#web security`

---

<a id="item-tech-news-5"></a>
### [Anthropic 称 Claude 参与解决两个黑洞物理开放问题](https://www.anthropic.com/research/claude-black-hole-physics) ⭐️ 7.0/10

Anthropic 的研究公告称，Claude 参与解决了黑洞物理中的两个开放问题；这是一项面向理论物理研究的厂商声明，所提供的材料没有显示独立验证。公告中的结果被描述为不直接描述我们所在的宇宙，也没有实际应用，只用于量子力学与广义相对论如何统一的理论工作。现有材料也没有说明提示词、人工引导程度或可复现实验细节，因此 Claude 的实际贡献仍无法独立判断。

hackernews · cybermango · 11月19日 17:30 · [社区讨论](https://news.ycombinator.com/item?id=50563148)

**「背景」** 这项工作的起点是 Anthropic 研究员 Hongbin Chen 在 8 月的一次业余测试：他让 Claude 列出一批理论物理中值得研究的开放问题，范围集中在黑洞与“自举”（bootstrap）方法上。自举方法不依赖具体的微观模型，而是用对称性与自洽性条件去限定理论允许的参数范围，因此这类计算往往步骤繁多、容易出错，也需要逐项检验。

**「影响」** 对理论物理研究者而言，当前可用的是一组需要独立复核的候选推导，而不是可直接套用的结论：Anthropic 称 Claude Fable 5.2 发现了物理学家漏掉的数值规律，并为该技巧的最简版本算出精确上限、证明其无法再降低。评论中引用的公告同时承认，两项结果都不直接描述我们的宇宙，也没有实际应用；在提示词与验证细节公开前，这些结果应被视为待检验的理论工作。

**「社区讨论」** 讨论的焦点之一是“Claude 解决了”这一拟人化表述：有评论批评这种说法让人无法判断人类提示与引导起了什么作用，并指出公告、摘要和两篇论文都没有出现“提示词”一词；也有评论认为，第二项结果，即给定中心电荷下的黑洞质量上限，才是更有意义的理论贡献。另有读者指出，当时的 80 多条评论很少真正讨论论文或原始文章，并提到这项成果被列为 Fable 5.2 发布公告中的一个要点。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.anthropic.com/research/claude-black-hole-physics">Claude Fable 5.2 solves two open problems in the physics of black ...</a></li>
<li><a href="https://www.anthropic.com/research/claude-black-hole-physics">Claude Fable 5.2 solves two open problems in the physics of black ...</a></li>

</ul>
</details>

**标签**: `#AI for science`, `#black hole physics`, `#large language models`, `#Anthropic`, `#research validation`

---

<a id="item-tech-news-6"></a>
### [OpenJDK PR 32781 关联 Java RCE 报告，披露过程引争议](https://github.com/openjdk/jdk/pull/32781) ⭐️ 7.0/10

Hacker News 讨论聚焦于 OpenJDK 拉取请求 PR 32781，该 PR 与一份 Java 远程代码执行（RCE）漏洞报告相关；目前可见信息没有给出 CVE 编号、严重级别、受影响版本或修复范围。讨论者主要关注 Oracle 对披露流程的介入，以及 LLM 辅助研究是否独立发现或复现了该问题。由于原始来源没有正文，所给材料不足以确认漏洞是否已经修复及其实际影响。

hackernews · notmine1337 · 11月19日 11:47 · [社区讨论](https://news.ycombinator.com/item?id=50558906)

**「背景」** Java4Shell 即 CVE-2026-114938，是 2026 年 11 月 17 日由 Oracle 与 OpenJDK 漏洞小组披露的 JVM 内存损坏漏洞，问题出在 JVM 编译器的 Base64 解码组件。社区评论引用的 Adoptium 支持 issue 显示，报告者早在 10 月 1 日就表示 Oracle 要求其在获得批准前不要提交 PR，10 月 28 日又称该问题已由 Oracle 接管。该 PR 的讨论正是围绕这一漏洞的修复与披露过程展开。

**「影响与处置」** 据报道，该问题被追踪为 CVE-2026-114938（“Java 4 Shell”），是 OpenJDK Base64 解码器中的漏洞，可导致未认证的远程代码执行；受影响的部署应尽快升级到包含修复的 Java 运行时版本。厂商给出的临时缓解措施是设置 -XX:-UseBASE64Intrinsics 启动参数，并明确 WAF 规则只能作为补丁之外的补充防护，不能替代升级。

**「社区讨论」** 有评论引用 Adoptium issue 1480 称，PR 作者表示 Oracle 曾要求其在获得批准前不要推进 PR，后来又称相关工作已由 Oracle 接管。另有评论者声称自己在披露前通过模糊测试独立发现了该问题，但承认无法排除训练数据包含相关报告的可能；其他人则质疑 LLM 辅助研究是否只是读取了旧报告。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://computingforgeeks.com/java4shell-cve-2026-114938/">Java4Shell CVE-2026-114938: Patch Vulnerable OpenJDK ...</a></li>
<li><a href="https://www.akamai.com/blog/security-research/java4shell-closer-look-patch-analysis-cve-2026-114938">Java4Shell: A Closer Look and Patch Analysis (CVE-2026-114938)</a></li>
<li><a href="https://www.paloaltonetworks.com/blog/cloud-security/java4shell-cve-2026-114938-risks-mitigations/">Java4Shell (CVE-2026-114938): Risks and Mitigations</a></li>
<li><a href="https://www.aikido.dev/blog/java-17-rce-vulnerability-cve-2026-114938">Java 4 Shell RCE : Affected Versions &amp; Fix ( CVE -2026-114938)</a></li>
<li><a href="https://orca.security/resources/research/java4shell-critical-openjdk-base64-decoder-flaw-could-allow-unauthenticated-remote-code-execution/">Java 4 Shell CVE -2026-114938: Affected Versions &amp; Mitigation</a></li>
<li><a href="https://techcommunity.microsoft.com/blog/azurenetworksecurityblog/addressing-java4shell-cve-2026-114938-upgrade-guidance-and-azure-waf-mitigations/4574305">Addressing Java 4 Shell CVE -2026-114938: upgrade guidance and...</a></li>

</ul>
</details>

**标签**: `#Java security`, `#OpenJDK`, `#RCE vulnerability`, `#vulnerability disclosure`, `#LLM-assisted security research`

---

<a id="item-tech-news-7"></a>
### [OpenAI 称其模型参与 Jalapeño 芯片设计，AMD GPU IP 的 PPA 最高提升 14%](https://openai.com/index/advancing-chip-design-with-our-models/) ⭐️ 7.0/10

OpenAI 在官方发布中称，其模型参与了自研推理芯片 Jalapeño 的设计，使向量单元标准单元面积减少约 13%、矩阵单元减少约 10%，相关优化已通过芯片点亮验证。在与 AMD 的合作中，这些模型把旗舰 GPU IP 的功耗、性能、面积（PPA）指标相对原本已高度优化的基线最高提升了 14%，部分改动已进入送厂制造的设计阶段。OpenAI 同时宣布与 Synopsys 合作训练 GPT-Synopsys 模型。上述数字均来自 OpenAI 单方面披露，未附方法论细节，也没有独立验证或同行评审。

telegram · zaihuapd · 11月19日 09:30

**「背景」** EDA（电子设计自动化）工具是芯片从设计、验证到签核的核心软件链。Synopsys 于 2026 年 9 月 30 日宣布与 OpenAI 签署多年协议，共同开发 GPT-Synopsys；该专用模型结合 OpenAI 的前沿模型与 Synopsys 的 EDA 工具及领域知识，目标是理解芯片设计与验证，并直接操作 Synopsys 工具。

**「影响」** 对正在评估 AI 辅助设计流程的芯片团队来说，这些收益是相对“已高度优化基线”取得的，并且 OpenAI 没有公开基线设置与评估方法，因此外界暂时无法复现或判断这些收益能否迁移到自家工艺与设计上；相对可核查的进展是 AMD 部分改动已进入流片设计，以及 Synopsys 合作尚处于模型训练阶段、未有交付时间表。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://news.synopsys.com/2026-09-30-OpenAI-and-Synopsys-Announce-GPT-Synopsys-Frontier-Intelligence-to-Revolutionize-Chip-Design">OpenAI and Synopsys Announce GPT-Synopsys: Frontier ...</a></li>
<li><a href="https://investor.synopsys.com/news/news-details/2026/OpenAI-and-Synopsys-Announce-GPT-Synopsys-Frontier-Intelligence-to-Revolutionize-Chip-Design/default.aspx">Synopsys, Inc. | OpenAI and Synopsys Announce GPT-Synopsys ...</a></li>

</ul>
</details>

**标签**: `#AI for chip design`, `#EDA`, `#OpenAI`, `#AMD`, `#hardware`

---

<a id="item-tech-news-8"></a>
### [Gemini 在 Mac 上新增电脑操作，可后台运行并暂停](https://www.bloomberg.com/news/articles/2026-11-19/google-s-gemini-can-now-control-mac-devices-on-users-behalf) ⭐️ 7.0/10

Google Gemini 新增“电脑操作”功能，可在 Mac 上点击、输入、浏览菜单和填写表单，代用户完成任务。该功能已向美国地区使用 Mac 版 Gemini、并订阅 Google AI Plus、Pro 或 Ultra 的用户开放。用户可让 Gemini 在独立后台窗口运行，同时继续使用主屏幕和光标，还可限制其可访问的应用、实时查看操作、随时暂停，并在关键操作前审批。该信息来自 Telegram 二手摘要，未提供具体版本号或独立验证结果。

telegram · zaihuapd · 11月20日 02:51

**「背景」** Gemini 的 Mac 桌面操作功能属于同类能力的跟进：Bloomberg 报道称，它与其他主流 AI 助手已提供的功能相当，并称这加大了 Apple 面临的压力。TechCrunch 则将该更新描述为把能够整理文件、填写表单和处理多步骤工作流的 AI agent 带到 Mac，说明其定位是桌面任务代理，而非单纯的聊天问答。

**「影响」** 对美国符合条件的 Mac 订阅用户，这意味着点击、输入和表单填写可交给后台代理执行，但使用前应限制 Gemini 可访问的应用，并对关键操作保留人工审批和实时监督。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-19/google-s-gemini-can-now-control-mac-devices-on-users-behalf">Google’s Gemini Can Now Control Mac Devices on Users’ Behalf</a></li>
<li><a href="https://techcrunch.com/2026/11/19/google-gives-gemini-the-ability-to-use-your-mac-for-you/">Google gives Gemini the ability to use your Mac for you</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#Google Gemini`, `#macOS`, `#desktop automation`, `#human-in-the-loop`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [Anthropic 纳斯达克上市首日开盘涨 34%，市值约 1.5 万亿美元](https://www.cls.cn/detail/2539480) ⭐️ 8.0/10

据财联社报道，人工智能公司 Anthropic 在纳斯达克上市首日开盘报 111.5 美元/股，较 83 美元的发行价上涨 34%，按开盘价计算市值约 1.5 万亿美元。该报道同时提到公司通过同步私募配售募集 260 亿美元；相关内容目前仅来自单一 Telegram 转发，尚无独立确认。

telegram · zaihuapd · 11月19日 16:56

**「背景」** 据美联社（AP）报道，Anthropic 于周三将 IPO 定价为每股 83 美元，按发行价计算估值为 1.5 万亿美元，由此成为有史以来规模最大的首次公开募股，超过此前 SpaceX 保持的纪录。这一“史上最大”的定位，是理解本次开盘表现参照的关键。

**「影响」** 谷歌、英伟达、微软、AMD、博通、美光及台积电等战略投资者以 IPO 发行价参与 260 亿美元同步私募配售，这些供应商的投资回报将与 Anthropic 上市后的股价表现直接挂钩。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://apnews.com/article/anthropic-ipo-nasdaq-ai-b6a74b8949021207dc162fcc876c4649">Anthropic to begin trading after pricing its stock at $83 per ...</a></li>
<li><a href="https://techcrunch.com/2026/11/19/anthropics-ipo-puts-ais-circular-financing-boom-to-the-test/">Anthropic &#x27;s IPO puts AI&#x27;s circular financing boom to the... | TechCrun...</a></li>
<li><a href="https://www.gate.com/blog/anthropic-pre-ipo-revaluation-strategic-shareholders">Anthropic ’s Revaluation: Pre- IPO Markets and Strategic... | Gate Blog</a></li>

</ul>
</details>

**标签**: `#IPO`, `#Anthropic`, `#AI`, `#Nasdaq`, `#private placement`

---