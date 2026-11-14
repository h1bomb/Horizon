---
layout: default
title: "Horizon Summary: 2026-11-14 (ZH)"
date: 2026-11-14
lang: zh
---

> 从 41 条内容中筛选出 8 条重要资讯。

---

**科技新闻**
1. [TorchTitan 在 384 块 GH200 上训练 1T MoE](#item-tech-news-1) ⭐️ 8.0/10
2. [美国联邦航空管理局发布全国范围停飞令](#item-tech-news-2) ⭐️ 7.0/10
3. [Python 早期贡献者 Tim Peters 去世，享年 74 岁](#item-tech-news-3) ⭐️ 7.0/10
4. [微软 Outlook、Teams 与 Copilot 全球宕机逾 12 小时](#item-tech-news-4) ⭐️ 7.0/10
5. [DeepSeek 开放应用 API，支持工具编排与多模态](#item-tech-news-5) ⭐️ 7.0/10
6. [OpenAI 推出 ChatGPT Wallet 令牌化支付钱包](#item-tech-news-6) ⭐️ 7.0/10

**财经新闻**
1. [卢特尼克因英伟达芯片走私问题被质询，其子执掌的公司与英伟达关系深厚](#item-finance-news-1) ⭐️ 8.0/10
2. [芝加哥联储古尔斯比：美联储在通胀问题上“肯定还有工作要做”](#item-finance-news-2) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [TorchTitan 在 384 块 GH200 上训练 1T MoE](https://www.reddit.com/r/MachineLearning/comments/1xvce5h/scaling_to_1t_moe_on_torchtitan_p/) ⭐️ 8.0/10

一份技术报告称，团队与 TorchTitan/PyTorch 维护者合作，在 JUPITER 的 384 块 GH200 上采用 384 路 FSDP 加节点内 4 路专家并行，把约 1T 参数 MoE 的训练吞吐做到约 1,300 tokens/s/GPU，较起点提升 14 倍。报告将初始瓶颈归因于跨节点 InfiniBand 仅约 25 GB/s/GPU：基线每步 84 秒中有 68 秒耗在网络等待。团队采用了全量激活重计算、将检查点激活卸载到 Grace、用 Muon 替代 Adam、用 FlexShard 按完整专家切分，并把专家梯度归约改为 bf16 all-to-all 后在本地以 fp32 累加。他们还向 TorchTitan 提交了让 Newton-Schulz 在 GPU 上运行的修复，称优化器步从 42 秒降到约 2 秒、吞吐提升 35%；这些数字来自该团队的经验报告，并非独立复现。

reddit · r/MachineLearning · /u/f14-bertolotti · 11月13日 16:28

**「背景：为什么要这样切分」** 要把约 1T 参数的 MoE 放到多卡上训练，首先得决定参数和专家如何切分：FSDP 为每张卡保留每层权重的一片、计算前再聚合，专家并行（EP）则让每张卡只负责一部分专家，令牌通过 all-to-all 被送到对应专家。该文选择跳过流水线并行（PP），是因为 PP 需要大量微批来掩盖流水线气泡，会拉长单步时间；在 InfiniBand 带宽远低于 NVLink 的 JUPITER 上，FSDP 聚合和专家 all-to-all 的通信开销因此成为核心约束。

**「影响」** 对在 GH200 这类 Grace-Hopper 平台上训练大 MoE 的团队，报告给出的直接动作是检查 FSDP 的梯度归约是否先把 bf16 梯度上采样成 fp32 再走 InfiniBand；改为 bf16 all-to-all、由接收方本地做 fp32 累加后，报告称跨节点梯度流量减半，数值结果仅受求和顺序影响。

**标签**: `#mixture-of-experts`, `#TorchTitan`, `#distributed training`, `#GH200`, `#FSDP`

---

<a id="item-tech-news-2"></a>
### [美国联邦航空管理局发布全国范围停飞令](https://www.nbcnews.com/news/us-news/faa-orders-nationwide-ground-stop-departing-flights-reasons-safety-rcna609247) ⭐️ 7.0/10

2026 年 11 月 13 日，美国联邦航空管理局（FAA）发布全国性停飞令，暂停所有离港航班；FAA 的通告页面只给出日期与编号，没有公开技术原因。社区评论引述的《华尔街日报》报道称，中断似乎出在 L3Harris Technologies 负责维护的一张电信网络上，该网络承载空管员与飞行员通话所用的关键无线电频率，目前尚不清楚雷达数据是否同样受影响。同日稍晚，有评论引述《纽约时报》称停飞令已经解除，但另有评论引述国土安全部长 Mullin 的说法称这很可能是一次较长时间的中断、“不会在一小时内解决”，两种说法相互矛盾，恢复范围与持续时间仍未获独立确认。整体上，官方披露极少，评论者指出媒体信息主要来自部长在社交平台上的发帖，机场离港信息牌大面积显示延误或取消。

hackernews · zulln · 11月13日 21:05 · [社区讨论](https://news.ycombinator.com/item?id=50489641)

**「背景」** 在此次全国停飞发生三天前，FAA 于 11 月 10 日将 AI 辅助空中交通管理系统 SMART 扩展至全美所有 22 个空管中心，用于优化航路和减少延误。停飞后外界质疑两者是否相关，但 FAA 否认 SMART 是原因，并将事件指向电信网络故障；DHS 部长则未排除这种可能性。

**「对旅客与航司的影响」** 此次通信中断引发的全国停飞使所有待起飞航班被压在地面，据报超过 1.1 万架次航班延误或取消；停飞令约四小时后解除，但航空公司仍需消化积压，旅客应预期后续延误或改签。

**「社区讨论」** 评论者对起因分成两派：一派根据《华尔街日报》的报道指向 L3Harris 承载的空管甚高频通信网络中断，另一派则怀疑与 FAA 前一天宣布在全国 22 个管制中心推广的 SMART 人工智能工具仓促上线有关，但两种说法都没有得到官方证实。多位评论者还抱怨官方信息异常稀少、机场网站因流量过载无法显示离港信息，只能靠零散的社交平台发帖拼凑情况。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/2026_FAA_communication_outage">2026 FAA communication outage - Wikipedia</a></li>
<li><a href="https://explainx.ai/blog/faa-smart-ai-nationwide-rollout-november-2026-ground-stop">FAA SMART AI Nationwide: $875M Tool, Ground Stop Denial ...</a></li>
<li><a href="https://en.wikipedia.org/wiki/2026_FAA_communication_outage">2026 FAA communication outage - Wikipedia</a></li>
<li><a href="https://www.cnbc.com/2026/11/13/faa-ground-stop.html">FAA lifts ground stop after four hours, but flight ... - CNBC</a></li>
<li><a href="https://www.theguardian.com/world/2026/nov/13/faa-nationwide-ground-stop-flights">Nationwide FAA ground stop: nearly 11,000 flights delayed or ...</a></li>

</ul>
</details>

**标签**: `#FAA`, `#air traffic control`, `#critical infrastructure`, `#network outage`, `#AI deployment`

---

<a id="item-tech-news-3"></a>
### [Python 早期贡献者 Tim Peters 去世，享年 74 岁](https://x.com/Itsfoss/status/2120957452937998716) ⭐️ 7.0/10

Python 创造者 Guido van Rossum 宣布，Python 社区早期贡献者 Tim Peters 去世，享年 74 岁。据科技媒体 It&\#x27;s FOSS 转述，Peters 是 Python 的第二位真实用户，撰写了《Python 之禅》（PEP 20），并创作了以他命名的 Timsort 排序算法。他还在 Python 软件基金会董事会任职 13 年。上述身份与任职年限来自 Guido van Rossum 的说明及该条转述，具体去世时间与原因未在材料中披露。

telegram · zaihuapd · 11月13日 09:55

**「背景」** Timsort 是 Python 列表排序所采用的算法，PEP 20 则是他用一系列短箴言总结 Python 设计取向的文档，即通常所说的《Python 之禅》。这两项工作一项进入语言的标准实现，一项进入社区的设计共识，都属于 Python 早期成型阶段的基础性贡献。

**「影响」** 对普通 Python 开发者而言，日常调用列表排序时实际运行的仍是 Timsort 实现，因此这一贡献会随 CPython 继续存在于现有代码路径中；本次消息不涉及版本变更或兼容性调整。

**标签**: `#Python`, `#open source`, `#community`, `#Tim Peters`, `#Timsort`

---

<a id="item-tech-news-4"></a>
### [微软 Outlook、Teams 与 Copilot 全球宕机逾 12 小时](https://www.reuters.com/technology/microsoft-365-outlook-down-thousands-us-users-downdetector-shows-2026-11-12/) ⭐️ 7.0/10

微软 Outlook、Teams 和 Copilot 的全球性故障持续超过 12 小时，截至 11 月 13 日仍未完全恢复，打乱了全球企业与政府的通信。微软将原因归为服务器问题，称未发现恶意活动，并表示已扩大修复范围、看到回稳迹象。据报澳大利亚、日本和美国部分政府机构受影响，Euronext 邮件受阻，台湾一家金融机构改用传真确认交易；这是微软 365 服务今年第二次中断。

telegram · zaihuapd · 11月13日 12:21

**「背景」** Microsoft 365 是微软面向企业提供的云端订阅套件，Outlook、Teams 和 Copilot 等应用依赖其在线服务运行。报道称，这已是微软 365 服务今年第二次中断。

**「业务连续性影响」** 对依赖 Microsoft 365 的机构而言，这次中断不只是邮件延迟：台湾一家金融机构改用传真确认交易，Euronext 的邮件通信也受阻，说明关键业务被迫切换到备用流程。微软虽称已扩大修复范围并看到回稳迹象，但受影响的 IT 团队在服务完全恢复前仍需维持这些替代通道。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/2026_Microsoft_outage">2026 Microsoft outage - Wikipedia</a></li>
<li><a href="https://www.livemint.com/technology/tech-news/microsoft-outage-affects-businesses-government-agencies-and-ai-platforms-full-list-of-services-impacted-11794569033153.html">Microsoft outage affects businesses, government agencies and ...</a></li>

</ul>
</details>

**标签**: `#microsoft-365`, `#cloud-outage`, `#service-reliability`, `#enterprise-software`, `#incident-response`

---

<a id="item-tech-news-5"></a>
### [DeepSeek 开放应用 API，支持工具编排与多模态](https://mp.weixin.qq.com/s/78KBHc4-4N5b2vfL9SkutQ) ⭐️ 7.0/10

据发布信息，DeepSeek 在原有 API 中开放应用级能力：开发者开启相应参数后，可获得深度思考搜索、文件输入、链接阅读和语音等对话能力，工具调用与上下文拼接由服务端完成。V4.1-Flash 模型已在三个接口提供支持，Search、Fetch、OCR、ASR、TTS 也可单独调用；官方同时开源了可导入历史对话的前端 Demo，用于本地部署网页端聊天界面。现有披露未给出定价、配额、限流或完整接口文档细节，全部能力的开放范围与计费方式仍不明确。

telegram · zaihuapd · 11月13日 14:27

**「背景」** DeepSeek 的 API 文档显示，其模型调用采用 OpenAI 兼容格式，开发者可用现有 SDK 和脚本发起请求。服务端工具编排是指平台在对话过程中调用搜索、网页抓取、OCR 或语音等外部能力，并把结果拼回上下文；此次更新把这条流程收进原有 API 的参数开关中。

**「影响」** 对已使用 DeepSeek API 的开发者，开启参数即可复用服务端的搜索、抓取、OCR 和语音工具链，减少自行拼接工具调用与上下文的工作；但在定价、配额和限流尚未披露前，接入方应先确认计费与容量条件，再评估生产环境使用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://api-docs.deepseek.com/">Your First API Call | DeepSeek API Docs</a></li>

</ul>
</details>

**标签**: `#DeepSeek`, `#API`, `#AI agents`, `#multimodal`, `#open source`

---

<a id="item-tech-news-6"></a>
### [OpenAI 推出 ChatGPT Wallet 令牌化支付钱包](https://openai.com/index/introducing-chatgpt-wallet/) ⭐️ 7.0/10

OpenAI 宣布推出 ChatGPT Wallet，并称已与美国运通、万事达和 Visa 合作，使智能体在付款时不接触用户真实卡号，且每笔购买都需安全验证。该功能自发布日起在美国通过 dots 面向 18 岁以上的 ChatGPT Pro 订阅用户开放，并要求使用美国发行的银行卡。用户需逐笔核对商品与金额，并以 Face ID 或指纹确认；支付网络会下发替代真实卡号的支付令牌。

telegram · zaihuapd · 11月13日 15:43

**「背景：代理支付与令牌化」** ChatGPT Wallet 接入的是 OpenAI 的“dots”智能体，这类智能体可代用户执行购物等任务。代理支付的关键在于不把真实卡号交给智能体：支付网络下发替代令牌，用户再用 Face ID 或指纹逐笔确认商品和金额，钱包把这套授权流程接入了 ChatGPT。

**「使用限制」** 目前该钱包仅向美国 18 岁以上的 ChatGPT Pro 用户开放，并要求使用美国发行的卡；每笔购买还需用户核对商品与金额、再用 Face ID 或指纹确认，因此它适用于逐笔授权的智能体代付，尚不能用于无人值守的自动结账。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://tech.yahoo.com/ai/chatgpt/articles/openai-launches-chatgpt-wallet-ai-164615852.html">OpenAI Launches ChatGPT Wallet. AI Agents Can Now Shop And ...</a></li>

</ul>
</details>

**标签**: `#OpenAI`, `#AI agents`, `#digital payments`, `#tokenization`, `#product launch`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [卢特尼克因英伟达芯片走私问题被质询，其子执掌的公司与英伟达关系深厚](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 8.0/10

据 CNBC 报道，美国商务部长霍华德·卢特尼克因处理英伟达先进 AI 芯片疑似走私至中国一事的方式面临质询；与此同时，他两个儿子执掌的 Cantor Fitzgerald 在 2025 年 9 月至 2026 年 3 月期间，申报持有的英伟达股票数量减少了 49%，从 352 万股降至 178 万股。报道称，Cantor 在 10 月 3 日的研报中仍维持对英伟达的“增持”评级和 350 美元目标价；一位伦理专家表示，没有证据表明卢特尼克向该公司分享了非公开信息，但“观感不佳”。

rss · CNBC Finance · 11月13日 23:42

**「背景」** 英伟达 CEO 黄仁勋周四辞职；此前有报道称，一份情报备忘录警告他与一名疑似中国间谍关系密切。美国商务部负责执行出口管制并维护实体清单，而卢特尼克于 2025 年 2 月离开 Cantor Fitzgerald 出任商务部长，该公司现由他的儿子布兰登和凯尔经营。

**「影响」** 争议的核心之一是是否把新加坡的 Megaspeed 列入商务部实体清单：被列入这份限制名单的企业，几乎无法获得美国先进技术出口许可，因此这一决定会直接影响 Nvidia 芯片经由第三方渠道的出货，以及相关客户的供货前景。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.theguardian.com/technology/2026/nov/12/jensen-huang-affair-timeline">A timeline of the affair scandal that sank Nvidia ’s Jensen Huang</a></li>
<li><a href="https://www.thestreet.com/technology/scott-bessent-and-lutnick-clash-over-nvidia-chips-and-china">Scott Bessent and Lutnick clash over Nvidia chips and... - TheStreet</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#U.S. export controls`, `#Howard Lutnick`, `#Cantor Fitzgerald`, `#corporate governance`

---

<a id="item-finance-news-2"></a>
### [芝加哥联储古尔斯比：美联储在通胀问题上“肯定还有工作要做”](https://www.cnbc.com/2026/11/13/chicago-feds-goolsbee-says-central-bank-has-definitely-got-work-to-do-on-inflation.html) ⭐️ 8.0/10

芝加哥联储主席古尔斯比（Austan Goolsbee）11 月 13 日对 CNBC 表示，美联储“肯定还有工作要做，以继续重建其公信力”。此前公布的数据显示，10 月生产者价格指数（PPI，衡量批发价格的指标）同比上涨 6.5%，为 2022 年 11 月以来最高；市场根据芝商所 FedWatch 期货指标，已完全计入 12 月 8 日至 9 日会议加息 25 个基点的预期。

rss · CNBC Finance · 11月13日 14:22

**「背景」** 美联储的长期通胀目标是 2%，以个人消费支出（PCE）价格指数衡量；目前联邦基金利率目标区间为 3.75%–4.00%，这是 2026 年 9 月加息后的水平。Goolsbee 目前不是联邦公开市场委员会（FOMC）投票委员，要到 2027 年才有投票权。

**「影响」** 若美联储如市场目前定价那样在 12 月加息，信用卡、浮动利率房贷等与基准利率挂钩的债务成本将随之上行，浮动利率贷款的小企业也会直接感受到利息负担加重。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.federalreserve.gov/economy-at-a-glance-inflation-pce.htm">The Fed - Inflation (PCE) - Federal Reserve Board</a></li>
<li><a href="https://wealthvieu.com/banking/interest-rates/federal-funds-rate/">Current Federal Funds Rate 2026 — Fed Rate History, FOMC ...</a></li>

</ul>
</details>

**标签**: `#Federal Reserve`, `#inflation`, `#monetary policy`, `#PPI`, `#interest rates`

---