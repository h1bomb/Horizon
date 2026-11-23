---
layout: default
title: "Horizon Summary: 2026-11-23 (ZH)"
date: 2026-11-23
lang: zh
---

> 从 29 条内容中筛选出 6 条重要资讯。

---

**科技新闻**
1. [OpenAI 发文主张低困惑度对应更强模型智能](#item-tech-news-1) ⭐️ 7.0/10
2. [英媒指太子集团相关网络涉走私英伟达芯片入华](#item-tech-news-2) ⭐️ 7.0/10
3. [Windows Server 2028 将默认移除 WoW64，32 位应用需手动装回](#item-tech-news-3) ⭐️ 7.0/10

**科技博客**
1. [在不确定中主动试探](#item-tech-blog-1) ⭐️ 6.0/10

**财经新闻**
1. [美股科技股大幅下挫，亚洲多地推出稳市措施](#item-finance-news-1) ⭐️ 9.0/10
2. [蚂蚁集团领投 Simplexity Robotics 1 亿美元 pre-A 轮，投后估值 16 亿美元](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [OpenAI 发文主张低困惑度对应更强模型智能](https://openai.com/index/perplexity-and-intelligence/) ⭐️ 7.0/10

OpenAI 发布一篇概念性文章，主张更低的下一 token 困惑度对应更强的模型智能，并把这一简单指标与日益复杂的模型评测方式相提并论。现有材料没有提供文章全文，也没有显示 OpenAI 同时发布新模型、新数据集或可独立复现的评测结果，因此其具体论据和实验范围仍无法核实。

hackernews · acossta · 11月22日 17:06 · [社区讨论](https://news.ycombinator.com/item?id=50601525)

**「背景」** 困惑度（perplexity）衡量语言模型预测下一个 token 时的平均不确定性：数值越低，表示模型对文本越不“意外”。在 GPT‑2 时期，OpenAI 曾以在旧数据集上刷新困惑度最优成绩来展示其生成连贯段落的能力；如今这篇由首席科学家 Jakub Pachocki 署名的文章再次把预训练模型的测试集困惑度与模型能力联系起来，因而需要区分该指标测的是下一 token 预测器本身的表现。

**「影响」** 对模型评测者而言，这篇文章的实际影响是促使人们重新审视困惑度作为简单、可解释候选指标的适用边界；但要用它做横向比较，必须固定分词方式、词表和评测序列，否则不同模型的数值不可直接对照。

**「社区讨论」** 评论中，hazrmard 指出原文并未定义困惑度，并解释其最差情况等于词表大小、最好情况为 1；jrflo 对强化学习时代交叉熵损失仍显示清晰趋势感到意外，同时欢迎比复杂基准更简单的指标。d\_burfoot 则认为预测率即压缩率，困惑度与智能的对应“事后看理所当然”，并引用自己 2008 年的论文支持这一观点。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/perplexity-and-intelligence/">Perplexity and Intelligence | OpenAI</a></li>
<li><a href="https://news.ycombinator.com/item?id=50601525">Perplexity and Intelligence | Hacker News</a></li>

</ul>
</details>

**标签**: `#llm-evaluation`, `#perplexity`, `#scaling-laws`, `#benchmarking`, `#openai`

---

<a id="item-tech-news-2"></a>
### [英媒指太子集团相关网络涉走私英伟达芯片入华](https://www.ft.com/content/f3ad8a81-3890-4a8a-8853-ff0a94b08ba9?syn-25a6b1a6=1) ⭐️ 7.0/10

英国《金融时报》援引知情人士称，被美国财政部指为柬埔寨太子集团“二号人物”的胡小伟，涉嫌参与将英伟达芯片运入中国；报道还称该集团拥有由空壳公司和地下融资渠道构成的网络，并利用私人飞机走私货物。报道援引贸易数据称，2024 年 12 月至 2025 年 12 月，Megaspeed 马来西亚子公司进口货物的申报价值约 46 亿美元，部分芯片据称流入中国黑市。太子集团否认胡小伟曾为其工作，并称有关非法网络和私人飞机走私的指控缺乏事实依据。

telegram · zaihuapd · 11月22日 04:34

**「背景」** 《金融时报》此前已多次调查英伟达芯片经东南亚转入中国的路径。2026 年 11 月 10 日的报道称，Megaspeed 因相关芯片贸易受到美国和马来西亚当局调查，但该公司表示没有发现违规证据；另一项调查称，芯片通过浪潮（Inspur）未上市的美国子公司 Aivres 作为供应商、Megaspeed 等环节进入中国。

**「合规影响」** 对依赖第三地转运采购英伟达芯片的企业而言，报道中约 46 亿美元的进口申报以及“流入中国黑市”的指控，使最终用户和最终用途核查成为更关键的出口管制合规环节。

<details><summary>参考链接</summary>
<ul>
<li>Nvidia spy scandal exposes Singapore&#x27;s role in China&#x27;s AI chip trade - Financial Times</li>
<li>FT investigation links Alice Huang&#x27;s Megaspeed to a gaming group, Inspur&#x27;s US unit and an alleged Prince Group figure | MLQ.ai</li>

</ul>
</details>

**标签**: `#Nvidia`, `#chip smuggling`, `#export controls`, `#AI hardware supply chain`

---

<a id="item-tech-news-3"></a>
### [Windows Server 2028 将默认移除 WoW64，32 位应用需手动装回](https://www.windowslatest.com/2026/11/23/32-bit-apps-days-are-numbered-as-microsoft-strips-support-bit-by-bit-starting-with-windows-server-2028-but-windows-11-is-safe-for-now/) ⭐️ 7.0/10

微软在 Ignite 2026 上宣布，Windows Server 2028 将默认不包含 WoW64 兼容子系统，因此系统初始状态下无法运行 32 位应用；该版本计划于 2027 年秋季与 Windows 11 27H2 一同发布。需要兼容旧软件的管理员可以通过按需功能（FoD）手动装回 WoW64，在 Server Core 上通常使用 PowerShell 或 DISM 添加。微软给出的理由是缩小攻击面、阻止 32 位恶意软件，但这是否适用于所有部署场景尚未说明。Windows 11 目前仍保留 WoW64，微软未公布移除计划。

telegram · zaihuapd · 11月23日 03:03

**「背景：WoW64 是什么」** WoW64 是 64 位 Windows 中的兼容子系统，负责把 32 位应用的调用转换给 64 位内核，使旧的 x86 程序无需 32 位操作系统即可直接运行。许多企业仍在使用的老旧业务系统、管理代理和安装程序只提供 32 位版本，因此该子系统默认存在，一直是从旧服务器系统升级后老软件还能继续运行的前提。

**「升级前需盘点 32 位依赖」** 计划迁移到 Windows Server 2028 的管理员需要在部署前盘点仍在使用的 32 位应用和代理，例如旧版管理工具、备份或监控代理，因为该系统默认不再包含 WoW64，这些程序启动时会直接失败；可通过按需功能把 WoW64 装回，在 Server Core 上一般用 PowerShell 或 DISM 添加，因此需要把这一步纳入镜像和自动化部署流程。Windows 11 目前仍保留 WoW64，桌面端的 32 位软件暂不受影响。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.windowscentral.com/microsoft/windows-11/microsoft-is-removing-32-bit-app-support-from-the-next-version-of-windows-server-wow64-subsystem-to-become-optional-component-to-reduce-malware-attack-surface">Windows Server 2028 to remove 32-bit app support for improved ...</a></li>

</ul>
</details>

**标签**: `#Windows Server`, `#WoW64`, `#32-bit compatibility`, `#Microsoft`, `#enterprise IT`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [在不确定中主动试探](https://seangoedecke.com/when-in-doubt-flail-about/) ⭐️ 6.0/10

rss · Sean Goedecke · 11月23日 00:00

**「背景」** 在缺乏明确指导、不知道什么有用的情境里，工程师常倾向于谨慎等待，先理解再行动，但作者 Sean Goedecke 认为这往往不是最好的办法，尤其面对模糊的产品、复杂系统或组织问题时。

**「方案」** 他的核心建议是主动“乱撞”：尽可能多地尝试不同做法，直接接触现实，同时因为多数计划本来就会失败，必须非常仔细地读取来自专家和实际结果的反馈。只试一个方案容易押错并过度投入，试十个方案则更可能有一个奏效，也更容易无情丢掉没有正反馈的方案；作者也提醒，做得不好会损害声誉。产品上，他举例说自己在 GitHub Models（现已退役）做过许多不成功的功能和集成，但“用 GitHub Actions token 运行 AI 推理”意外地有粘性，后来成为“Continuous AI”的种子。工程上，他认为现代大型系统太复杂、变化太快，不必先彻底读懂再动手，而应做一批投机性改动，看效果再决定深入或立即放弃，AI 代理可以帮忙生成多个重构候选。组织上，面对团队互不沟通或无人能说清不满根源的局面，可以尝试自动化手工工作、主动接手任务或提出长期方案；这时尤其要敏感于反馈，及时撤回失败举措能建立信任，否则不满可能转向你。

**「启示」** 作者的核心论点是，信息不足时不应等待完全理解，而应提高实验密度、紧贴反馈并快速止损；那种内心像在乱撞的感觉，是有效工程师需要跨过的心理障碍，而不是陷入麻烦的证据。

**标签**: `#engineering-judgment`, `#experimentation`, `#feedback-loops`, `#product-discovery`, `#organizational-engineering`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美股科技股大幅下挫，亚洲多地推出稳市措施](https://news.bjd.com.cn/2026/11/22/12039852.shtml) ⭐️ 9.0/10

美国 AI 科技股周五遭遇大规模抛售，纳斯达克指数单日下跌 5.28%，费城半导体指数重挫近 11%。随后，中国大陆将融资保证金最低比例下调至 80%，韩国放宽上市公司每日回购订单数量限制，中国台湾自 11 月 23 日起全面禁止平盘以下卖空，并将融券保证金比例由 130%提高至 150%。

telegram · zaihuapd · 11月22日 13:24

**「背景」** 据观察者网报道，费城半导体指数自 6 月高点以来累计下跌 43%，投资者转向避险资产；中国内地下调融资保证金最低比例则是时隔十个月重回 80%，该比例指融资买入时保证金与融资金额之比，比例越低，可融资买入的规模越大。

**「影响范围」** 中国内地将融资保证金最低比例下调至 80%，意味着投资者用同样的保证金可以借入更多资金买入股票，直接受影响的是使用融资杠杆的内地投资者；中国台湾地区把融券保证金比例从 130%提高到 150%，并全面禁止平盘以下卖空，则抬高放空成本、压缩做空空间，直接影响当地融券与放空交易者。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.guancha.cn/GuoJi%C2%B7ZhanLue/2026_11_21_909399.shtml">AI恐慌爆发，华尔街震荡， 美 国 科 技 股 跌 入熊市</a></li>
<li><a href="https://finance.eastmoney.com/a/202611223936948742.html">重磅时刻！ A 股 迎三大“新政”！ 影响几何？ 最新解读来了 _ 东方财富网</a></li>
<li><a href="https://www.cls.cn/detail/2541019">三大交易所同时宣布！ 时隔十个 月 融 资 保 证 金 重回 80 %，积极信号明确</a></li>

</ul>
</details>

**标签**: `#US tech stocks`, `#market selloff`, `#Asia market policy`, `#margin requirements`, `#short-selling restrictions`

---

<a id="item-finance-news-2"></a>
### [蚂蚁集团领投 Simplexity Robotics 1 亿美元 pre-A 轮，投后估值 16 亿美元](https://www.bloomberg.com/news/articles/2026-11-22/ant-group-bets-on-simplexity-to-thrive-in-china-s-humanoid-race) ⭐️ 7.0/10

彭博报道，中国具身智能公司 Simplexity Robotics 完成 1 亿美元 pre-A 轮融资，由蚂蚁集团领投，投后估值 16 亿美元；阿里巴巴、腾讯、HongShan（红杉中国）和蓝驰创投跟投，公司董事长兼联合创始人 Wang Kai 已向彭博确认该消息。

telegram · zaihuapd · 11月23日 02:02

**「背景」** Simplexity Robotics 于 2025 年 7 月在杭州成立，核心团队来自理想汽车。公司今年 3 月披露，成立半年内已完成五轮融资、累计融资 20 亿元人民币，当时投后估值已超过 10 亿美元。

**「影响」** 这笔资金将用于与宇树、优必选等更成熟厂商争夺市场；而据研究机构 Smart Analytics Global 数据，2026 年上半年中国人形机器人厂商已占全球出货量的 97% 以上，新资本入场可能进一步加剧这一行业的竞争与产能扩张。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://aiweekly.co/alerts/ant-group-leads-100m-pre-a-for-simplexity-at-16b-valuation">Ant Group Leads $100M Pre-A for Simplexity at $1.6B Valuation</a></li>
<li><a href="https://www.caproasia.com/2026/03/14/china-robot-startup-simplexity-robotics-raised-290-million-cny-2-billion-funding-in-last-6-months-with-latest-valuation-at-1-billion-founded-in-2025-by-ex-li-auto-executives-jia-peng-wang-kai/">China Robot Startup Simplexity Robotics Raised $290 Million ...</a></li>
<li><a href="https://global.chinadaily.com.cn/a/202608/11/WS6a7a8b3aa310986e2b46a1a5.html">Chinese humanoid robot makers hold 97% global shipments in H1</a></li>

</ul>
</details>

**标签**: `#embodied AI`, `#humanoid robotics`, `#venture financing`, `#Ant Group`, `#China tech`

---