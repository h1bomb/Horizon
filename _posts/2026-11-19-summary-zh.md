---
layout: default
title: "Horizon Summary: 2026-11-19 (ZH)"
date: 2026-11-19
lang: zh
---

> 从 43 条内容中筛选出 14 条重要资讯。

---

**科技新闻**
1. [谷歌发布 Gemini 4 Neon，主打软件工程与科研工作流](#item-tech-news-1) ⭐️ 8.0/10
2. [Nginx HTTP/2 被报未认证远程代码执行漏洞](#item-tech-news-2) ⭐️ 8.0/10
3. [Xint 公开 nginx 漏洞链，称可取得主机 root](#item-tech-news-3) ⭐️ 8.0/10
4. [微软发布七款新 AI 模型，强调可扩展性价比](#item-tech-news-4) ⭐️ 7.0/10
5. [Show HN：拆解旅行者 1 号，细至单颗内存芯片](#item-tech-news-5) ⭐️ 7.0/10
6. [Quad9 退出法国：DNS 解析器不是反盗版执法点](#item-tech-news-6) ⭐️ 7.0/10
7. [Google DeepMind 宣布 Genie 4 可用，适用范围仍不明确](#item-tech-news-7) ⭐️ 7.0/10
8. [微信小微测试日活达 3000 万，接入聊天等场景](#item-tech-news-8) ⭐️ 7.0/10
9. [美政府据报考虑要求企业披露中国 AI 使用](#item-tech-news-9) ⭐️ 7.0/10

**财经新闻**
1. [美联储会议纪要：几乎所有官员认为需进一步加息，并警示 AI 相关风险](#item-finance-news-1) ⭐️ 8.0/10
2. [美联储理事沃勒：12 月或需加息 0.5 个百分点以“震动”市场](#item-finance-news-2) ⭐️ 8.0/10
3. [特朗普、习近平与普京本周齐聚深圳 APEC 峰会](#item-finance-news-3) ⭐️ 7.0/10
4. [腾讯三季度营收增 8%，AI 资本开支飙升、自由现金流转负](#item-finance-news-4) ⭐️ 7.0/10
5. [中韩宣布自贸协定服务与投资后续谈判实质性结束](#item-finance-news-5) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [谷歌发布 Gemini 4 Neon，主打软件工程与科研工作流](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/) ⭐️ 8.0/10

谷歌发布 Gemini 4 Neon，面向复杂软件工程、知识工作与科研工作流的快速端到端执行，已向开发者、企业以及 Google AI Pro/Ultra 订阅用户开放。公布价格为每百万输入 token 3 美元（缓存输入 0.15 美元）、输出 15 美元，支持 100 万 token 上下文。发布材料称其在 Artificial Analysis 编程智能体指数上以 58.6 分排名第一、智能指数 xhigh 档以 61 分位列总榜第三，Terminal-Bench 4.1 得分 65.2%，默认 high 档单任务成本比 Carbon 低 32%。上述分数与成本对比均为发布方给出的数据，现有材料未提供可独立核验的评测细节。

hackernews · yigitdemirag · 11月18日 21:34 · [社区讨论](https://news.ycombinator.com/item?id=50552424)

**「Neon 与 Carbon 的关系」** Gemini 4 Neon 并非独立的新模型家族：Google DeepMind 的模型卡称它改编自 Gemini 4 Carbon，而 Neowin 的报道将 Carbon 称为 Google 的旗舰模型。同一报道还称，Google 表示 Neon 在部分基准上可以超过 Carbon，这说明两者的差异更多是同一代 Gemini 4 内部的定位与取舍，而不是简单的版本号升级。

**「影响」** 对需要在 Neon 与 Carbon 之间做选择的开发者而言，默认 high 档单任务成本比 Carbon 低 32%、以及 100 万 token 上下文，是可以直接换算的选型依据；但评论区指出 Carbon 仍被定位为“长时程”模型，在 CritPt 等研究级推理评测上得分更高，因此仅凭综合总分切换到 Neon 未必适合长周期任务。

**「社区讨论」** 评论者一方面抱怨模型命名难以对应到具体用例，称 Sol、Astra、Neon、Carbon、Opus、Haiku 等名称令人疲劳（stillpointlab），另一方面讨论定位差异：Neon 综合分数更高，但 Carbon 仍被定位为“长时程”模型，在研究级推理评测上更强（declanjackson）。另有用户报告在 OpenRouter 上测得 Neon 约 127 tokens/秒，远快于 Carbon 的 46 tokens/秒，并对此感到困惑（seizethecheese）。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.neowin.net/news/google-launches-gemini-4-neon-claims-its-three-times-faster-than-carbon/">Google launches Gemini 4 Neon , claims it&#x27;s three times... - Neowin</a></li>
<li><a href="https://deepmind.google/models/model-cards/gemini-4-neon/">Gemini 4 Neon - Model Card — Google DeepMind</a></li>

</ul>
</details>

**标签**: `#Gemini 4`, `#LLM releases`, `#Google AI`, `#model benchmarking`, `#AI industry`

---

<a id="item-tech-news-2"></a>
### [Nginx HTTP/2 被报未认证远程代码执行漏洞](https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities) ⭐️ 8.0/10

Wiz 的博客报告 Nginx 的 HTTP/2 处理存在未认证远程代码执行漏洞，关联 CVE-2026-123633 与 CVE-2026-123007。现有材料没有给出受影响版本、修复版本或厂商通告的具体内容，因此漏洞范围和修复状态仍不明确。社区讨论称 HTTP/2 并非 Nginx 默认启用、约 12% 的服务器启用它，并认为实际利用条件较苛刻。

hackernews · speedping · 11月18日 15:19 · [社区讨论](https://news.ycombinator.com/item?id=50547374)

**「背景」** NGINX 对 HTTP/2 的支持并非默认开启，需要在配置中显式启用，因此实际暴露面取决于各站点是否主动开启了该协议。Wiz 的这份报告对应 CVE-2026-123633 和 CVE-2026-123007 两个编号。这也不是 NGINX 今年首次出现严重的远程代码执行问题：搜索结果中的报道显示，2026 年 5 月披露的 CVE-2026-42945 同样被评为严重的远程代码执行漏洞，而本次披露的是与之相互独立的另一个缺陷。

**「影响与应对」** 对启用 Nginx HTTP/2 的运维人员，社区讨论提出的直接缓解是关闭 HTTP/2，使服务回退到 HTTP/1.1；在受影响版本和官方修复信息明确前，应优先核对部署是否开启该功能并关注厂商公告。

**「社区讨论」** 评论者对严重性看法不一：testtestmetest 称利用需要 128GB 的 HTTP/2 流量和特定 CPU 指令，因而认为是“非问题”，fduran 则强调 HTTP/2 未默认开启但仍有约 12% 的服务器暴露。black3r 还批评修复先在开源仓库出现、相关方未提前发布 PSA，认为存在被静默利用的时间窗。

<details><summary>参考链接</summary>
<ul>
<li>18-year-old vulnerability in NGINX leads to remote code execution</li>

</ul>
</details>

**标签**: `#nginx`, `#http2`, `#remote code execution`, `#security vulnerability`, `#CVE`

---

<a id="item-tech-news-3"></a>
### [Xint 公开 nginx 漏洞链，称可取得主机 root](https://nginx2root.com/) ⭐️ 8.0/10

Xint 公开了名为 NGINX2Root 的漏洞链，称 5 个 nginx 漏洞与一个 Linux 内核缺陷串联后，可从 nginx 访客取得主机 root；其中 CVE-2026-123007 被描述为 HTTP/2 流控内存破坏，未认证即可在 worker 进程中执行命令。该披露称 nginx 1.30.7 和 1.31.9 已于 11 月 18 日修复 10 个 CVE，Rapid7 已发布 PoC，但暂无在野利用。上述 CVE 编号、版本与修复细节来自该披露及 Telegram 聚合信息，尚未见独立确认；无法升级者被建议关闭对外 HTTP/2。

telegram · zaihuapd · 11月18日 16:21

**「背景」** 这组漏洞的核心是 nginx HTTP/2 模块中的整数下溢（CVE-2026-123007）：Rapid7 与 Wiz 的分析指出，该缺陷自 2015 年 9 月 22 日发布的 nginx 1.9.5 起就存在于开源代码中，且只有在服务器启用 HTTP/2 时才可被触发。攻击者先利用它在 nginx worker 进程中实现代码执行，再借助一个 Linux 内核 SCTP 缺陷把 worker 权限提升到主机 root，这正是“nginx 2 root”这一名称的由来；对应的修复版本是 nginx 1.31.9 与 1.30.7。

**「影响与处置」** 对把 nginx 暴露在边缘的运维者，最直接的处置是升级到 1.30.7/1.31.9，或在无法升级时关闭对外 HTTP/2；公开 PoC 降低了复现门槛，但“可打到主机 root”仍是披露方描述的串联结果，尚未见独立验证或在野利用证据。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.rapid7.com/blog/post/ve-cve-2026-123007-critical-nginx-http-2-integer-underflow-leads-to-rce-fixed/">Rapid 7 discloses a critical vulnerability affecting NGINX HTTP / 2 that...</a></li>
<li><a href="https://thehackernews.com/2026/11/10-year-old-nginx-http2-flaw-lets.html">10-Year-Old NGINX HTTP / 2 Flaw Lets Unauthenticated Attackers...</a></li>
<li><a href="https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities">Unauthenticated Remote Code Execution in NGINX ... | Wiz Blog</a></li>
<li><a href="https://xint.io/blog/nginx2root-remote-code-execution">NGINX 2 Root : New Remote Code Execution Vulnerabilities in nginx ...</a></li>
<li><a href="https://www.getastra.com/blog/security-advisory/nginx2root/">nginx 2 root : Five nginx RCE Flaws and a Kernel Bug...</a></li>

</ul>
</details>

**标签**: `#nginx`, `#vulnerability disclosure`, `#remote code execution`, `#HTTP/2`, `#patching`

---

<a id="item-tech-news-4"></a>
### [微软发布七款新 AI 模型，强调可扩展性价比](https://microsoft.ai/news/microsoft-ignite-2026/) ⭐️ 7.0/10

微软在 Ignite 2026 上宣布推出七款新 AI 模型，并将可扩展的性价比作为核心卖点。现有材料没有给出这些模型的完整名称、具体定价、开放权重情况或可用时间，因此目前只能确认这是一项产品公告，尚不能视为已全面上市的能力。评论中提到的 MAI Code 2 是来源里出现的具体模型名称，但其规格与兼容性也未在来源中说明。

hackernews · gmays · 11月18日 16:08 · [社区讨论](https://news.ycombinator.com/item?id=50548021)

**「背景」** 微软 Ignite 是微软面向开发者的年度技术大会，其产品与模型发布通常在该场合公布。MAI 是微软自研的模型系列，其已公开售卖的图像模型就按“高精度”与“更快”分成两个层级，例如 MAI-Image-2.7 与 MAI-Image-2.7 Flash；本次七款模型中的 MAI Cyber 2 Flash 沿用了同一命名方式。

**「对编码模型选型与 Copilot 用户的影响」** 对于日常编码任务，微软声称 MAI Code 2 的性能约为 GPT-6.1 Sol 的 98%，成本为 GPT-6.1 Sol 的 40%；约为 Claude Opus 5.5 的 96%，成本为 Claude Opus 5.5 的 5%。MAI Code 2 Flash 相较于 GPT-6 Luna 和 Claude Haiku 5.5 的成本则分别为 65% 和 20%。这些都是微软自行给出的数字，尚无独立基准验证，因此团队在迁移前应先在自己的代码库和任务上做对比测试，而不是只根据价格决定。微软还称 MAI Code 2 正在成为其产品背后的主力模型，这意味着 Copilot 等微软产品的使用者可能在未主动选择的情况下遇到模型变更，需要重新核对输出质量与相关配置。

**「社区讨论」** 有评论者称自己实际试用 MAI Code 2 后体验良好，并认为其表现可与 Opus 或 Sol 相比；另一位评论者则主张，微软若想争取市场份额应开放模型权重或源码，否则可能重演 Windows Phone 的处境。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://microsoft.ai/news/microsoft-ignite-2026/">Seven new world class models at scalable... | Microsoft AI</a></li>
<li><a href="https://ignite.microsoft.com/">Your home for Microsoft Ignite</a></li>
<li><a href="https://openrouter.ai/microsoft/mai-image-2.7">MAI -Image- 2 . 7 - Image Generation API Pricing | OpenRouter</a></li>
<li><a href="https://microsoft.ai/news/introducing-mai-code-2-and-mai-code-2-flash/">MAI Code 2 and Code 2 Flash: Everyday coding at scalable ...</a></li>
<li><a href="https://felloai.com/mai-code-2/">MAI Code 2: Price, Benchmarks and Copilot Plans - felloai.com</a></li>
<li><a href="https://explainx.ai/blog/microsoft-ignite-mai-code-2-seven-models-november-2026">Microsoft Ignite 2026: MAI Code 2, Cyber 2 Flash, and Six ...</a></li>

</ul>
</details>

**标签**: `#Microsoft`, `#AI models`, `#MAI Code 2`, `#LLM pricing`, `#model competition`

---

<a id="item-tech-news-5"></a>
### [Show HN：拆解旅行者 1 号，细至单颗内存芯片](https://rshekhar.com/voyager/) ⭐️ 7.0/10

开发者 raj-shekhar 在 Hacker News 发布了一个交互式网站，能把旅行者 1 号逐层拆到数据计算机的单颗内存芯片，并查看核电池的 24 个钚球、通信系统和金唱片封套。作者称旅行者 1 号在发帖当天距地球达到一光日；站点还显示两艘探测器当前的位置、正在接收信号的深空网络天线，以及它如何通过无线电被修复。作者另制作了一段 4 分钟影片。

hackernews · raj-shekhar · 11月18日 16:18 · [社区讨论](https://news.ycombinator.com/item?id=50548161)

**「背景」** “一光日”在这里是距离单位，指光在 24 小时内行进的距离；旅行者 1 号达到该距离后，地面发出的信号单程约需 24 小时，收到回复约需两天。旅行者 1 号在旅行者 2 号之后 16 天发射，并通过 NASA 深空网络接收常规指令、回传数据。

**「影响」** 对想理解旅行者 1 号硬件层次的读者和教学者，站点提供了从整器到单颗芯片的可点击路径；评论区还补上了核电池、数据计算机内存和命令计算机单比特等难找页面的直达链接，便于按图索骥地讲解或自学。

**「社区讨论」** 有评论者称赞这种可视化，同时提出两类实质追问：项目是否由 AI“vibecoded”生成、是否经过原始研究与权威资料核对，以及 CMOS 存储芯片长期读值出错究竟对应怎样的模拟失效机理。作者则在评论中补发了核电池、内存芯片和单比特等页面的直达链接。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Voyager_1">Voyager 1 - Wikipedia</a></li>
<li><a href="https://science.nasa.gov/mission/voyager/voyager-1/voyager-1-what-is-a-light-day/">Voyager 1 : What Is a Light - Day - NASA Science</a></li>
<li><a href="https://www.aljazeera.com/news/2026/11/18/nasas-voyager-1-hits-record-one-light-day-distance-50-years-after-launch">NASA’s Voyager 1 hits record one light - day distance , 50... | Al Jazeera</a></li>

</ul>
</details>

**标签**: `#Voyager`, `#interactive-visualization`, `#computer-hardware`, `#space-technology`, `#technical-education`

---

<a id="item-tech-news-6"></a>
### [Quad9 退出法国：DNS 解析器不是反盗版执法点](https://techstackups.com/articles/quad9-leaves-france-dns-blocking/) ⭐️ 7.0/10

一篇分析文章以 Quad9 退出法国为案例，论证 DNS 解析器不应成为打击盗版的封锁执行点。文章认为，要求递归解析器在 DNS 层屏蔽被指侵权的站点，会把中立基础设施变成内容审查节点，并影响法国用户对公共解析服务的选择。由于原文未提供法国裁决的具体条款或封锁域名清单，相关法律细节仍不明确。

hackernews · ritzaco · 11月18日 13:18 · [社区讨论](https://news.ycombinator.com/item?id=50545958)

**「背景：Quad9 与法国屏蔽令」** Quad9 是由瑞士非营利基金会运营的免费公共 DNS 解析器。据 TorrentFreak 和 EFF 报道，巴黎法院于 2026 年 10 月裁定 Quad9 必须屏蔽被指控侵犯版权的网站，Quad9 随后宣布自 11 月 24 日起停止为法国用户提供服务，成为第二家因此退出法国的 DNS 解析器。Cloudflare 的博文还提到，比利时法院近期作出裁决，若 Cloudflare、Google 和 Cisco 不在 2027 年 1 月初之前通过其公共解析器屏蔽相关网站，将面临高额罚款。

**「影响」** 对法国用户和把 Quad9 地址写进设备或企业配置的管理员来说，最直接的后果是需要切换到其他解析器或准备备用 DNS，否则在 Quad9 退出法国后可能无法正常解析域名。

**「社区讨论」** 评论者 trentnix 认为，不以起诉盗版者为核心的反盗版措施容易变成政府压制言论的后门；skrebbel 则追问，这是法院的错误裁决，还是法官在忠实适用一条荒唐法律，责任该由法院还是立法者承担。bemtevi 主张用更好的付费观看体验竞争，AppalachianEng 则质疑为何不优先追究商业盗版。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.cloudflare.com/quad9-withdrawal-from-france/">Quad9’s withdrawal from France: A canary in the coal mine</a></li>
<li><a href="https://torrentfreak.com/dns-resolver-quad9-will-leave-france-after-court-orders-piracy-blocking-penalty/">DNS Resolver Quad9 Will Leave France After Court Orders ...</a></li>
<li><a href="https://www.eff.org/deeplinks/2026/10/french-courts-site-blocking-orders-drive-quad9-out-france">French Court’s Site-Blocking Orders Drive Quad9 Out Of France</a></li>

</ul>
</details>

**标签**: `#DNS`, `#internet governance`, `#privacy`, `#copyright enforcement`, `#Quad9`

---

<a id="item-tech-news-7"></a>
### [Google DeepMind 宣布 Genie 4 可用，适用范围仍不明确](https://blog.google/innovation-and-ai/models-and-research/google-deepmind/genie-4-now-available-project-genie/) ⭐️ 7.0/10

Google DeepMind 宣布 Genie 4 已可用，这是其世界模型的新版本；但现有材料没有给出模型参数、生成能力、定价，也没有给出正式的地区和账户适用范围。公告标题只说明“现已可用”，无法据此判断这是全面上线还是有限开放；评论中有人报告，页面把使用资格指向“符合条件的 Google AI Ultra 订阅者”，而该用户的工作区账户无法订阅，非工作区页面又显示 Ultra 对应 Genie 3。该用户怀疑这与英国地区或此前仅限美国有关，实际开放条件仍不明确。

hackernews · leumon · 11月18日 18:49 · [社区讨论](https://news.ycombinator.com/item?id=50550415)

**「背景」** Genie 是 Google DeepMind 的世界模型系列，旨在生成可实时交互的虚拟环境；Genie 4 的模型卡称其可同时生成音乐、环境声和交互对白等音频。Project Genie 是提供该系列模型体验的产品入口，此次更新将 Genie 4 接入其中，但模型页面显示它先面向受信任测试者进行内测，之后才逐步开放给 Google AI Ultra 订阅者及 Gemini API、AI Studio 的早期访问伙伴。

**「访问资格与用途限制」** 对开发者来说，实际门槛首先在访问资格：公告把 Genie 4 限定给“符合资格的 Google AI Ultra 订阅者”，而评论中有英国用户反映其 Ultra 账户仍只显示 Genie 3，工作区账号也无法开通 Ultra。因此，在把 Genie 4 接入工作流前，应先确认所在地区和账号类型是否在支持范围内。Google 还表示，Genie 4 会与 Gemini 模型配合，为机器人构建数字练习空间，但这属于厂商规划，尚非已交付的能力。

**「社区讨论」** 评论区有人认为这类技术可能带来严重的负面后果，表示“我不想要这些”；也有人赞赏 DeepMind 似乎更重技术本身而非盈利，并猜测世界模型未来可能成为游戏引擎、用于重制《GTA》或形成更开放的 Roblox 式平台。关于可用性和付费条件的抱怨同样突出，但这些均属用户经验与观点，不是官方规则。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://deepmind.google/models/genie/">Genie 4 — Google DeepMind</a></li>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/google-deepmind/genie-4-now-available-project-genie/">Project Genie update featuring Genie 4 - The Keyword</a></li>
<li><a href="https://deepmind.google/models/model-cards/genie-4/">Genie 4 - Model Card — Google DeepMind</a></li>
<li>Google Genie 4 Combines With Gemini Models to Build Better ...</li>

</ul>
</details>

**标签**: `#Google DeepMind`, `#world models`, `#generative AI`, `#product release`, `#AI pricing`

---

<a id="item-tech-news-8"></a>
### [微信小微测试日活达 3000 万，接入聊天等场景](https://mp.weixin.qq.com/s/r3NthxJZQJgztyLADwNV4A) ⭐️ 7.0/10

腾讯在 2026 年第三季度财报中称，微信 AI 助手小微的测试范围已扩大，日活跃用户达到 3000 万，并正逐步融入微信聊天、朋友圈、公众号和视频号等场景。小微采用面向成本效率优化的 WeLM 定制模型，腾讯称其推理成本较低且持续下降。腾讯还预计未来部分推理任务将在用户设备端运行，但未披露测试准入条件、正式上线时间或独立性能数据。

telegram · zaihuapd · 11月18日 11:35

**「背景」** 微信小微是直接嵌入微信本体的原生 AI 助手，并非独立 App 或小程序；腾讯为其定制了自研的 WeLM 大模型，并把推理成本作为主要优化目标。此前小微只在小范围测试，本次腾讯在季度财报中首次给出 3000 万日活这一规模数据，说明测试已从灰度阶段扩展到更大范围；有用户帖子提到部分场景还会调用 DeepSeek 辅助，但财报内容未涉及这一点。

**「影响」** 对测试范围内的用户而言，小微正逐步出现在微信的原生场景中，而非仅依赖单独入口；但腾讯尚未说明各场景的具体功能差异、设备兼容要求以及向其他用户全面开放的时间。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://post.smzdm.com/p/a03633d9/">不扎堆做独立AI App...</a></li>

</ul>
</details>

**标签**: `#WeChat`, `#AI assistant`, `#Tencent`, `#WeLM`, `#on-device inference`

---

<a id="item-tech-news-9"></a>
### [美政府据报考虑要求企业披露中国 AI 使用](https://www.reuters.com/world/china/trump-administration-weighs-forcing-us-firms-disclose-chinese-ai-use-2026-11-18/) ⭐️ 7.0/10

据路透社报道，特朗普政府正在考虑要求美国企业公开披露其使用中国 AI 模型的情况；美国财政部与白宫科技政策办公室已讨论该方案。方案若落地，使用阿里 Qwen 支撑客服等业务的企业须在官网公示，报道以 Airbnb 为例。此举意在通过“公开点名”抑制企业对低价中国开放权重模型的依赖，而非出台新的限制；该方案是否获得政府内部支持、是否会进入正式立法程序尚不明朗。

telegram · zaihuapd · 11月19日 02:30

**「背景」** 开放权重模型指厂商公开发布可下载的模型参数，企业可自行部署，成本通常明显低于按调用量计费的闭源 API，这也是 Airbnb 等公司采用阿里 Qwen 的现实动因。据路透社报道，美国国会此前已就相关问题启动调查，这为行政部门酝酿公开披露要求提供了政治铺垫。

**「影响」** 若该披露方案最终实施，Airbnb 这类以自托管阿里 Qwen 支撑客服的美国企业将须在官网公开说明其使用中国 AI 的情况；相关企业需要梳理可公开的模型来源、部署方式和用途清单。方案目前仍处讨论阶段，适用范围与是否进入立法程序尚不明确。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://economictimes.indiatimes.com/ai/ai-insights/trump-administration-weighs-forcing-us-firms-to-disclose-chinese-ai-use/articleshow/135962485.cms">Trump administration weighs forcing US firms to disclose ...</a></li>
<li><a href="https://aiadopters.club/p/airbnb-bet-its-support-desk-on-a">Airbnb Bet Its Support Desk on a Chinese AI Model It Can Drop</a></li>
<li><a href="https://www.gate.com/news/detail/ABNB/us-reviews-disclosure-rule-for-companies-using-chinese-ai-models-25705130">US Reviews Disclosure Rule for Companies Using Chinese AI ...</a></li>

</ul>
</details>

**标签**: `#AI policy`, `#China AI`, `#open-weight models`, `#AI regulation`, `#corporate disclosure`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美联储会议纪要：几乎所有官员认为需进一步加息，并警示 AI 相关风险](https://www.cnbc.com/2026/11/18/fed-minutes-october-2026.html) ⭐️ 8.0/10

美联储周三公布的 10 月会议纪要显示，几乎所有与会者认为，为确保通胀及时回到 2%，进一步上调联邦基金利率目标区间可能是合适的；但当月 FOMC 以 10 比 2 的投票结果将利率维持在 3.75%-4%，库克和哈马克投反对票，主张加息 25 个基点。

rss · CNBC Finance · 11月18日 19:41

**「背景」** 会议以来公布的数据显示，美国 10 月 CPI 环比上涨 0.4%、核心 CPI 上涨 0.3%，均比预期高 0.1 个百分点，通胀仍高于 2%目标；官员们担心伊朗战争和特朗普关税带来的价格上涨可能变得顽固。

**「影响」** 对 AI 相关企业及其投资者而言，纪要显示美联储工作人员指出，表外租赁承诺和循环融资安排可能在 AI 投资回报不及预期时放大损失，且相关敞口正集中于少数企业。

**标签**: `#Federal Reserve`, `#monetary policy`, `#inflation`, `#interest rates`, `#AI financial risk`

---

<a id="item-finance-news-2"></a>
### [美联储理事沃勒：12 月或需加息 0.5 个百分点以“震动”市场](https://www.cnbc.com/2026/11/18/federal-reserve-governor-christopher-waller.html) ⭐️ 8.0/10

美联储理事沃勒（Christopher Waller）11 月 18 日表示，为遏制高于预期的通胀，联邦公开市场委员会（FOMC）在 12 月 8-9 日会议上可能需要加息 0.5 个百分点，以“震动”市场；这是他本人的主张，并非已定政策。目前期货市场完全计入的是 12 月加息 0.25 个百分点。

rss · CNBC Finance · 11月18日 15:13

**「背景」** 美联储 9 月实施了三年多来首次加息，10 月按兵不动；沃勒称还需“收回”2025 年为应对就业市场担忧而降息的三次、每次 0.25 个百分点的“保险式”降息。多数通胀读数目前仍在 3%以上，高于 2%的目标，部分原因是 2 月底美国与以色列对伊朗的军事打击推高能源价格，加上关税影响持续。

**「影响」** 若 12 月真加息 0.5 个百分点，与政策利率挂钩的浮动利率借贷（如信用卡欠款和部分企业贷款）成本会比市场当前预期的 0.25 个百分点上升得更快。

**标签**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#inflation`, `#Christopher Waller`

---

<a id="item-finance-news-3"></a>
### [特朗普、习近平与普京本周齐聚深圳 APEC 峰会](https://www.cnbc.com/2026/11/18/apec-trump-xi-putin-shenzhen.html) ⭐️ 7.0/10

美国总统特朗普、中国国家主席习近平和俄罗斯总统普京本周齐聚深圳出席亚太经合组织（APEC）峰会，特朗普与习近平预计周三至周四会晤并重点讨论落实贸易协议，但外界普遍预期不会有重大突破。

rss · CNBC Finance · 11月18日 06:04

**「背景」** APEC 是亚太经济体的年度论坛；美中在去年韩国 APEC 会晤后达成为期一年的贸易休战，包括下调部分关税和恢复部分稀土流通，该休战已延长两个月至 2027 年 1 月。

**「影响」** 亚洲多国政府将关注深圳会晤，以判断在美中技术竞争加剧时，自己还有多少回旋空间。

**标签**: `#US-China relations`, `#APEC summit`, `#trade policy`, `#geopolitics`, `#AI technology restrictions`

---

<a id="item-finance-news-4"></a>
### [腾讯三季度营收增 8%，AI 资本开支飙升、自由现金流转负](https://api3.cls.cn/share/article/2537922?os=android&amp;amp;sv=8.8.5&amp;amp;app=cailianpress&amp;amp;selected=) ⭐️ 7.0/10

腾讯公布 2026 年第三季度财报，营收 2073 亿元、同比增长 8%，低于市场预期，归母净利润 636 亿元、同比增长 0.8%。当季资本开支 814.33 亿元，远超市场预估的 554 亿元，单季自由现金流为负 691 亿元；腾讯还称其 WorkBuddy 日均 Token 用量超过 100 万亿，为国内大语言模型产品最高。

telegram · zaihuapd · 11月18日 09:20

**「背景」** WorkBuddy 是腾讯面向办公场景的 AI Agent，可自主拆解任务并生成报告、表格等成品；大模型以 Token（文本处理计量单位）计量用量，因此日均 Token 用量被用来展示该产品的使用规模。资本开支是购置服务器等长期资产的现金支出，会直接反映在当期现金流中，这有助于理解 AI 投入增加与自由现金流为负之间的关系。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.workbuddy.ai/">WorkBuddy - AI Agent for Everyday Office Work</a></li>

</ul>
</details>

**标签**: `#腾讯`, `#财报`, `#AI资本开支`, `#自由现金流`, `#大模型Token用量`

---

<a id="item-finance-news-5"></a>
### [中韩宣布自贸协定服务与投资后续谈判实质性结束](https://x.com/Jaemyung_Lee/status/2122988472994791476) ⭐️ 7.0/10

中韩于 11 月 18 日宣布，自贸协定服务与投资后续谈判实质性结束，中国承诺在电影、游戏等领域给予韩国最惠国待遇，并扩大旅游、法律、建筑、金融等领域开放。这轮谈判自 2018 年 3 月启动、历时约 8 年 8 个月，双方同时同意将视听共同制作范围从电影扩大到电视剧、动画、综艺和纪录片，部分技术事项仍留待工作层面协商。

telegram · zaihuapd · 11月18日 10:02

**「背景」** 中韩自贸协定第二阶段（服务与投资）谈判于 2018 年 3 月启动，此前曾中断约四年，直到 2025 年 1 月才重启（tool-1-3）。因此，此次“实质性结束”意味着双方已就主要开放内容达成一致，但仍有部分技术事项留待工作层磋商完成。

**「影响」** 若后续文本签署并生效，韩国电影、游戏、旅游、法律、建筑和金融企业将获得扩大的中国市场准入，双方影视制作公司也可在电视剧、动画、综艺和纪录片合拍上适用更宽范围。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.zaobao.com.sg/realtime/china/story20250116-5743403">时隔四 年 韩 中 重启 自 贸 协 定 服 贸 投 资 后 续 谈 判 | 联合早报</a></li>

</ul>
</details>

**标签**: `#China-South Korea FTA`, `#services trade`, `#investment liberalization`, `#audiovisual and gaming`, `#trade policy`

---