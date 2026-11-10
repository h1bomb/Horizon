---
layout: default
title: "Horizon Summary: 2026-11-10 (ZH)"
date: 2026-11-10
lang: zh
---

> 从 45 条内容中筛选出 11 条重要资讯。

---

**科技新闻**
1. [Anthropic 发布 Claude Fable 5.2 与 Mythos 5.2](#item-tech-news-1) ⭐️ 7.0/10
2. [E-means 宣称以十分之一轮次超越 k-means](#item-tech-news-2) ⭐️ 7.0/10
3. [谷歌发布 TPU 8tx 与 8i Max 两款专用芯片](#item-tech-news-3) ⭐️ 7.0/10
4. [HN 讨论：消费级 Gemini 连接应用数据或经人工审核](#item-tech-news-4) ⭐️ 7.0/10
5. [watched.earth：查询一周内过境卫星及其影像](#item-tech-news-5) ⭐️ 7.0/10
6. [用 Claude Code 造 Beep Locator，多设备定位神秘蜂鸣](#item-tech-news-6) ⭐️ 7.0/10
7. [LingBot-Touch：JEPA 式潜空间预测在触觉预训练中胜过重建](#item-tech-news-7) ⭐️ 7.0/10
8. [字节发布 Seedream 5.5：支持百轮连续编辑与透明素材](#item-tech-news-8) ⭐️ 7.0/10
9. [OPPO、vivo、小米、荣耀上线 ADV 侧载开发者验证并互认结果](#item-tech-news-9) ⭐️ 7.0/10

**财经新闻**
1. [英伟达董事会调查黄仁勋，预测市场认为其近期离职概率低](#item-finance-news-1) ⭐️ 7.0/10
2. [前三季度中国新能源乘用车出口 388.7 万辆，同比增长 138.8%](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Anthropic 发布 Claude Fable 5.2 与 Mythos 5.2](https://www.anthropic.com/claude-fable-and-mythos-5-2) ⭐️ 7.0/10

Anthropic 发布 Claude Fable 5.2 和 Mythos 5.2，面向使用其模型与编程助手的开发者；Hacker News 条目只提供标题和讨论，未附产品规格、价格或可用性信息，具体改动范围无法确认。讨论集中在基准对比方法：有人质疑将 Fable 的 xHigh 档与 Carbon 的 Med 档并列、Carbon 的“努力—智能”曲线异常，以及在 cyber 基准和 robodojo 对比中改用或漏掉特定模型。另有评论给出 Fable 5.2 的早期编程案例，但这些属于个人试用反馈，尚非独立验证。

hackernews · lairv · 11月9日 18:01 · [社区讨论](https://news.ycombinator.com/item?id=50429068)

**「背景」** Anthropic 延续了同一模型发布两种配置的做法：Claude Fable 5.2 面向一般用途，并附加防护以阻止其在生物学、网络安全等高风险双用途领域执行某些任务；Claude Mythos 5.2 则是另一套配置。系统卡称，此前同类模型也采用这种双版本形式。据 CNBC 报道，这两款模型于 11 月 9 日（周一）发布。

**「影响」** 对于依赖 Anthropic 模型选型的团队，有评论者认为 Fable 5.2 与 Opus 5.5 在普通编码任务上的差异并不明显，需要更强的高难度提示才能看出区分；这意味着选型时应按实际高难度任务做对比测试，而不能只看版本号。

**「社区讨论」** 一位开发者称 Fable 5.2 在 60 万行 Fortran 代码库上把材料计算工作加速了 36 倍，并已决定开源结果；另有评论提到 1,000 个 Fable 5.2 智能体用 30 小时完成费马大定理形式化的说法。上述数字和案例均来自评论者自述，未经独立核实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://assets.claude.com/27d60918d218125e7504bc7354c4b4626ec56b11.pdf">Claude Fable 5.2 &amp; Claude Mythos 5.2 System Card</a></li>
<li><a href="https://www.cnbc.com/2026/11/09/anthropic-claude-fable-5-2-mythos-5-2.html">Anthropic releases Claude Fable 5.2 and Claude Mythos 5.2 ...</a></li>

</ul>
</details>

**标签**: `#AI models`, `#Anthropic`, `#LLM benchmarks`, `#coding assistants`, `#Hacker News`

---

<a id="item-tech-news-2"></a>
### [E-means 宣称以十分之一轮次超越 k-means](https://e-means.github.io/) ⭐️ 7.0/10

E-means 项目页面提出一种面向聚类和向量索引的 k-means（Lloyd 算法）替代方法，宣称只需约十分之一的迭代轮次就能取得更好结果。该说法目前主要来自项目自述和早期社区试用，尚不能视为独立验证。已有开发者报告将其适配到 GPU 上的 IVF 索引后获得 146 倍加速，另有项目称索引整体重建快 2.5 倍，但常规增量插入的总耗时变化不大。也有人把它用于球面等面积网格松弛时发现效果反而更差。

hackernews · porridgeraisin · 11月9日 18:45 · [社区讨论](https://news.ycombinator.com/item?id=50429734)

**「背景：Lloyd 迭代与收敛成本」** k-means 的经典 Lloyd 算法交替执行“将样本分配给最近中心”和“用簇内均值更新中心”，并反复扫描数据直到收敛，因此迭代轮数直接决定大数据集上的成本。E-means 将自己定位为这一流程的替代方案，页面标题声称只需约十分之一 epoch 就能超过 k-means；其具体机制与可复现性仍需查看项目材料。

**「影响」** 对考虑替换 Lloyd 算法的团队而言，这些初步报告表明收益取决于工作负载：大规模数据扫描或索引重建可能明显受益，而球面网格等场景可能退化；实际替换前应按自身数据和硬件做基准测试。

**「社区讨论」** 评论者对适用范围存在分歧：real\_faxenoff 和 kingcauchy 报告了显著提速，jlhawn 则在球面网格实验中测得更差，说明至少在该场景并不适用。shiandow 还从理论上将其与期望最大化或模拟退火类比，并指出更新规则会把质心限制在凸包内。

**标签**: `#k-means`, `#clustering`, `#algorithms`, `#machine-learning`, `#performance`

---

<a id="item-tech-news-3"></a>
### [谷歌发布 TPU 8tx 与 8i Max 两款专用芯片](https://blog.google/innovation-and-ai/infrastructure-and-cloud/global-network/tpu-8i-max-and-8tx/) ⭐️ 7.0/10

谷歌宣布推出两款新的张量处理单元：面向政府机构及受严格监管行业、用于处理安全机密数据的 TPU 8tx，以及面向超长上下文窗口 AI 应用的 TPU 8i Max。TPU 8tx 将与 AMD 芯片协同工作；TPU 8i Max 则把两颗 TPU 芯片集成在同一封装内，以提供更强算力和更大内存容量。谷歌今年连续扩充 TPU 产品线，打破过去每两年推出一款新处理器的节奏，来源还提到苹果、Meta、甲骨文和 Anthropic 等已成为客户。现有材料未给出两款芯片的上市时间、价格或能效数据，相关能力仍以谷歌公布的信息为准。

hackernews · \_benx\_ · 11月9日 21:56 · [社区讨论](https://news.ycombinator.com/item?id=50432831)

**「背景」** 这两款产品属于谷歌第八代 TPU 产品线：TPU 8tx 是在 TPU 8t 基础上搭配第五代 AMD EPYC 处理器、并在处理过程中保护数据和模型权重的安全方案，面向政府及高安全要求行业。谷歌过去通常每两年推出一款新 TPU，今年改为按安全推理和超长上下文等场景连续扩充产品线。

**「影响」** 对开发和采购方的直接影响是获取途径与集成成本：TPU 8tx 需与 AMD 芯片协同工作，部署方要为此准备异构硬件与配套软件栈；8i Max 面向超长上下文场景，目前只有谷歌自有基础设施提供，评论中也在追问谷歌为何不直接对外销售。社区还指出，Colab 上能拿到的最强 TPU 仍是 v6e-1，独立开发者短期内难以直接使用新芯片。此次公布没有给出瓦/Token 或美元/Token 数据，采购方无法据此做单位成本比较；第三方分析同样强调，每 Token 成本取决于小时价格、实际吞吐以及迁移和供应商锁定的摊销，而非峰值算力。

**「社区讨论」** 多位评论者询问缺少每 token 功耗与成本数据，并要求与英伟达同价位产品比较；也有人指出 Google Colab 目前可用的最强 TPU 仍是 v6e-1，规模不足以做严肃工作，并追问谷歌为何不直接出售这些芯片。这些是评论者的疑问与使用体验，并非对产品性能的独立验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/infrastructure-and-cloud/global-network/tpu-8i-max-and-8tx/">Introducing TPU 8 tx and TPU 8 i Max</a></li>
<li><a href="https://dzen.ru/a/avHlCl56vGiwEiaH">Google расширила линейку тензорных процессоров ( TPU )... | Дзен</a></li>
<li><a href="https://calcaas.com/blog/tpu-8i-vs-nvidia-rubin-b200-cost-per-token-llm-inference-2026">TPU 8i vs NVIDIA Rubin vs B200: Cost Per Token | Calcaas</a></li>

</ul>
</details>

**标签**: `#TPU`, `#Google Cloud`, `#AI infrastructure`, `#hardware`, `#agentic AI`

---

<a id="item-tech-news-4"></a>
### [HN 讨论：消费级 Gemini 连接应用数据或经人工审核](https://github.com/thisisme6598/gemini_files/) ⭐️ 7.0/10

Hacker News 上的一则讨论称，启用“已连接应用”的消费级 Google Gemini 可能把 Gmail、Drive 等个人数据交由人工标注者查看；该说法目前仅有讨论标题和评论，缺少所附的一手技术材料佐证。评论者指出，Workspace 版 Gemini 及面向企业的 Workspace Intelligence 仍声称不受人工审核约束，因此争议主要落在消费级账户及用户主动授权连接的应用上。讨论还提醒，连接 Gmail 等工具后，Gemini 可调用该工具读取邮件，相关数据是否进入训练或审核流程取决于具体产品条款，不能把消费级与企业级政策混为一谈。

hackernews · gf74918 · 11月9日 18:24 · [社区讨论](https://news.ycombinator.com/item?id=50429426)

**「背景」** Gemini 的 Connected Apps 机制需用户授权，授权后助手可调用 Gmail 等 Google 应用中的数据；在设置中关闭 Google Workspace 连接后，Gemini 就不能再访问邮件。相关报道梳理的 Google 政策显示，免费消费级 Gemini 的对话可能被人工审阅并用于改进产品，而付费 Gemini API、Vertex AI 和 Workspace 层级则称数据不用于训练。

**「对个人账号用户的实际影响」** 对于将个人 Gmail、Drive 连接到消费级 Gemini 的用户，实际风险在于相关内容可能进入人工审核与最长三年的保留流程，且删除后仍可能留存；Workspace 企业用户则可能适用不同的审核和数据保留政策。普通用户应先检查 Gemini 的“已连接应用”授权，避免用工作账号授权个人数据；企业用户则应让管理员确认 Workspace Gemini 的审核与保留设置，而不是沿用消费级产品的默认假设。

**「社区讨论」** 评论中最有用的区分是消费级 Gemini 与 Workspace/企业版政策不同：bri3d 指出 Workspace Gemini 仍声称不受人工审核，而消费级连接应用可能触发数据读取与后续处理。另有评论者 rustyhancock 报告 Gemini 的回答似乎“恰好”贴合其收到的邮件内容，但这是个人经验，不能单独证明人工审核存在；hek2sch 则担忧人工标注者可能接触或泄露数据。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.deai.org/news/does-google-gemini-train-on-your-data">Does Google Gemini Train on Your Data? What the Policy Says (2026)</a></li>
<li><a href="https://tech.yahoo.com/ai/gemini/articles/stop-gemini-accessing-emails-two-103013901.html">Stop Gemini from accessing your emails with these two hidden settings</a></li>
<li><a href="https://www.searchenginejournal.com/google-gemini-privacy-warning/507818/">Google Gemini Warning: Don’t Share Confidential Information Generative AI in Google Workspace Privacy Hub Google Gemini policy change, Gemini Apps Privacy Notice ... Gemini Apps Privacy Notice | Google Gemini | ConductAtlas Google Gemini Routes Personal Drive, Gmail to Human Reviewers</a></li>

</ul>
</details>

**标签**: `#Google Gemini`, `#AI privacy`, `#human annotation`, `#consumer data`, `#Google Workspace`

---

<a id="item-tech-news-5"></a>
### [watched.earth：查询一周内过境卫星及其影像](https://www.watched.earth/) ⭐️ 7.0/10

作者在 Show HN 发布了 watched.earth：用户输入任意地点后，它会在浏览器中用 CelesTrak 目录运行 SGP4，约半秒内找出过去 7 天经过该地上空的卫星，并调取这些过境对应的 Sentinel-2、Landsat 和 NASA 实际影像。作者称过境搜索已针对极点、跨 180° 经线和极窄扫幅与暴力算法核对，漏检为 0；界面把约 1.7 万个在轨物体交给 GPU 渲染，并每帧求解开普勒方程。工具只在确有影像时标记“watched”，并称不存储用户位置；作者还提到 Sentinel-2 时间戳常与实际过境时刻相差 5–10 分钟，已作处理。

hackernews · a585gupt · 11月9日 17:51 · [社区讨论](https://news.ycombinator.com/item?id=50428907)

**「背景知识」** SGP4 是配合 TLE 两行轨道根数使用的标准轨道传播算法，CelesTrak 公开发布这类根数，因此卫星过境预测可以直接在浏览器中完成，而不必依赖后端轨道服务。Sentinel-2（欧空局哥白尼计划）与 Landsat（NASA/USGS）的光学影像免费公开、按拍摄时间与地面条带存档，这正是该工具能够对某地回查一周内“真实拍到”的图像的前提。

**「检索顺序被反转」** 对需要某个具体地点卫星影像的人（例如用其规划徒步路线者），这个工具把检索顺序反了过来：不必先在 Copernicus Browser 或 USGS 的 Landsat 数据入口按场景和条带浏览、再判断是否覆盖目标点，而是先输入地点，由浏览器端 SGP4 在约半秒内列出过去 7 天的过境，并且只在确有 Sentinel-2／Landsat／NASA 影像时才标注“watched”。因此它更像是现有公开档案的一个轻量前置入口而非替代品——影像仍来自这些档案，作者也承认 Sentinel-2 时间戳与实际过境常差 5–10 分钟并需对齐；包括“零漏检”在内的准确性目前仅为作者自述，尚无独立验证。

**「社区讨论」** 评论者普遍称赞其视觉呈现与工程完成度，认为它把轨道、地面轨迹、过境时间序列和多种影像源整合得很顺畅。一位自称从事地理空间的用户表示，能看到卫星实际拍摄的影像使该站区别于常见卫星概览；另一名用于规划背包徒步的评论者称它适合规划路线，并认为比 Copernicus 更易用、数据源更多。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://browser.dataspace.copernicus.eu/">Copernicus Browser</a></li>
<li><a href="https://www.usgs.gov/landsat-missions/landsat-data-access">Landsat Data Access | U.S. Geological Survey - USGS.gov</a></li>

</ul>
</details>

**标签**: `#satellite-imagery`, `#orbital-mechanics`, `#geospatial`, `#gpu-rendering`, `#show-hn`

---

<a id="item-tech-news-6"></a>
### [用 Claude Code 造 Beep Locator，多设备定位神秘蜂鸣](https://simonwillison.net/2026/Nov/9/mysterious-beeps/) ⭐️ 7.0/10

Simon Willison 用 Claude Code 构建了开源项目 Beep Locator：一台机器运行 Python Web 服务器，其他手机、平板和笔记本通过二维码或链接加入，作为浏览器端监听器。监听器持续保留 60 秒音频缓冲，用 FFT 和高通滤波做蜂鸣检测并把事件发给服务器；服务器让往返延迟最低的设备播放一段短 chirp，再要求所有监听器上传蜂鸣前后约 0.6～0.8 秒的片段，用 chirp 对齐各设备录音后三角定位声源。设备互相播音来估算彼此位置的效果不佳，因此他加入“Rough mode”，先手动拖拽设备的大致位置再由声音校正；另设拍手模式用于验证定位能力。最终系统把他家中间歇蜂鸣的位置锁定在约 40 厘米范围内，他据此翻找纸箱，找到一台亟待更换电池的老旧一氧化碳探测器。

rss · Simon Willison · 11月9日 23:57

**「背景」** Claude 在项目初期检索到 2007 年 Chunyi Peng 等人的论文《BeepBeep: A High-Accuracy Acoustic-Based System for Ranging and Localization Using COTS Devices》，该论文只用扬声器、麦克风和设备间通信，通过双向感知、自录音和采样计数实现高精度声学测距。Beep Locator 的“播放 chirp 对齐多设备录音”正是沿用了这一思路。

**「影响」** 对想复用的开发者而言，门槛主要在硬件与现场条件：需要一台跑 Python 服务的机器、若干带麦克风和扬声器且能打开浏览器的设备，并逐台授权麦克风；设备自动测距不可靠，通常得靠 Rough mode 人工给出粗略布局。系统还会在日志中标出“到达时间在物理上不可能”的情况，提示回声或混入了别的声音，这类告警需要人工复核后再确认蜂鸣。

**标签**: `#AI-assisted coding`, `#Claude Code`, `#sound localization`, `#web audio`, `#DIY project`

---

<a id="item-tech-news-7"></a>
### [LingBot-Touch：JEPA 式潜空间预测在触觉预训练中胜过重建](https://www.reddit.com/r/MachineLearning/comments/1xs05uo/latent_prediction_beats_reconstruction_for/) ⭐️ 7.0/10

Robbyant 发布的自监督触觉编码器 LingBot-Touch 采用 JEPA 式训练：预测被遮挡接触区域的潜表征，而不是重建原始传感器信号；推理代码和 checkpoint 已公开。论文在与同规模 MAE、VAE 重建模型同数据对比时报告，1K 小时数据下触觉到视频的 top-5 召回为 32.1%，MAE 为 5.6%、VAE 为 4.4%；到 4K 小时 JEPA 升至 49.3%，MAE 仍低于 9%，VAE 反而降到 3.1%。作者将此归因于触觉片段大部分是接近零的背景，重建损失可以在不学到真实接触的情况下下降；两项关键设计是掩码率在 300 步内从 40% 预热到 80%（初始高掩码会遮住稀疏信号中的全部接触 taxel 并引发梯度爆炸），以及把磁性、压阻、视触觉三种传感器经指尖规范坐标与 5D RoPE（时间、手指、三维位置）送入同一个共享 Transformer。在 26 个真实机器人任务、4 个策略下，冻结编码器特征在 104 个策略与任务组合中的 89 个取得最高分；在预训练中未出现过的磁性手上，LingBot-VLA 从 57.21 提升到 75.04。这些数字来自论文摘要和帖子总结，尚未经独立验证；作者也观察到 Tiny 模型约在 4K 小时趋于饱和，而 Small 仍在提升。

reddit · r/MachineLearning · /u/Zealousideal-War7154 · 11月9日 18:52

**「背景」** 自监督学习常用“掩码重建”路线：遮住部分输入，再还原原始信号（如 MAE、VAE）；JEPA 类方法则改为在潜空间中预测被遮挡部分的目标表示，不要求逐点还原原始读数。触觉片段中大部分时间接近零背景，重建损失可能在无关区域下降，这正是该论文比较两类预训练目标的出发点。

**「对机器人与触觉研究者的直接影响」** 对从事灵巧操作研发的团队而言，这项工作的直接价值在于可以直接把公开的推理代码和检查点当作现成的触觉特征提取器接入已有策略：论文报告冻结编码器在 26 项真机任务与 4 种策略组合成的 104 个组合中有 89 个取得最高分，并把在预训练中从未出现过的磁传感器手上的 LingBot-VLA 成功率从 57.21 提升到 75.04（这些数字均来自论文自述，尚未经独立复现）。需要注意的是，作者报告 Tiny 版本在约 4K 小时数据后趋于饱和，因此数据量更大的团队若继续扩规模，应预期需要改用 Small 及更大版本，而非单纯增加数据。

**标签**: `#self-supervised-learning`, `#tactile-sensing`, `#robotics`, `#representation-learning`, `#JEPA`

---

<a id="item-tech-news-8"></a>
### [字节发布 Seedream 5.5：支持百轮连续编辑与透明素材](https://seed.bytedance.com/zh/blog/%E7%94%9F%E6%88%90%E6%9B%B4%E7%9C%9F%E5%AE%9E-%E7%99%BE%E8%BD%AE%E7%BC%96%E8%BE%91%E6%9B%B4%E7%A8%B3%E5%AE%9A-seedream-5-5-%E5%8F%91%E5%B8%83) ⭐️ 7.0/10

字节跳动发布图像创作模型 Seedream 5.5，支持对同一作品进行最多 100 轮连续编辑，并能原生生成带透明通道的素材，同时提升了图像真实感和文字渲染能力。字节称，在影视、办公场景的评测中，该模型可用率达到上一版本的两倍以上；这一数据来自厂商自述，未提供独立评测结果。该模型正陆续上线即梦、豆包、豆包工作和火山方舟。

telegram · zaihuapd · 11月9日 08:34

**「背景」** 图像编辑模型在多轮反复修改时通常会累积画质损失与主体漂移，因此连续编辑的轮次上限是衡量这类模型实用性的一个指标。透明通道输出以往多依赖生成后再抠图，原生支持可省去这一步。

**「影响」** 对需要反复改图的创作者来说，Seedream 5.5 允许在同一作品上连续修改最多 100 轮，并可直接产出带透明通道的素材；使用前，应按即梦、豆包、豆包工作和火山方舟各自的陆续上线进度确认入口，四个平台并非同时开放。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://seed.bytedance.com/en/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5">Seed News - ByteDance Seed Team</a></li>

</ul>
</details>

**标签**: `#generative AI`, `#image generation`, `#image editing`, `#ByteDance`, `#Seedream`

---

<a id="item-tech-news-9"></a>
### [OPPO、vivo、小米、荣耀上线 ADV 侧载开发者验证并互认结果](https://mp.weixin.qq.com/s/ZiKBASSLzvsZ6WR2AUmFeg) ⭐️ 7.0/10

OPPO、vivo、小米、荣耀在中国大陆联合上线 Android 侧载应用开发者身份验证（ADV），并支持彼此验证结果互认，目的是建立开发者与应用之间的可信关联，帮助用户判断侧载应用来源。已在四家开放平台注册上架的 App 会自动提交验证，无需开发者另行申请；未完成验证的应用在侧载安装时会显示「未验证」提示，用户须手动确认后才能继续安装。现有信息来自一份简要汇总，未说明该机制的具体生效时间、验证所依据的技术标准或各厂商提示文案是否一致。

telegram · zaihuapd · 11月9日 11:44

**「背景」** Android 侧载指用户绕过应用商店、直接安装 APK 等安装包；ADV 即 Android Developer Verification（Android 开发者验证），其核心是把应用与经过验证的开发者身份关联起来。此次四家厂商的机制正是在这一框架下，通过“已验证/未验证”提示帮助用户判断侧载应用的来源。

**「对侧载开发者的直接影响」** 对未在 OPPO、vivo、小米、荣耀四家开放平台注册上架的开发者，其应用通过侧载安装时会触发「未验证」提示，用户必须手动确认才能继续，这会直接增加安装摩擦；已在四家平台注册上架的应用会自动提交验证，且四家互认验证结果，但源文未说明平台外开发者是否有独立验证入口。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.ithome.com/1/024/519.htm">OPPO、vivo、小米、荣耀在中国大陆上线 ADV 开发者验证，支持各方结果...</a></li>
<li><a href="https://news.qq.com/rain/a/20261109A0DWYZ00">OPPO等四家厂商上线ADV开发者验证 结果互认_腾讯新闻</a></li>

</ul>
</details>

**标签**: `#Android`, `#app sideloading`, `#developer verification`, `#mobile security`, `#China tech`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [英伟达董事会调查黄仁勋，预测市场认为其近期离职概率低](https://www.cnbc.com/2026/11/09/jensen-huang-nvidia-exit-prediction-markets.html) ⭐️ 7.0/10

英伟达董事会表示正调查 CEO 黄仁勋，理由是有报道称他成为“外国情报活动”的目标；黄仁勋已承认与一名女性有婚外情，而据《纽约时报》报道，美国情报官员称该女性为中国国家安全部间谍。消息传出后，英伟达股价周一下跌超过 5%，Kalshi 预测市场交易者认为他在 2027 年前离职的概率仅为 17%。

rss · CNBC Finance · 11月9日 18:46

**「背景」** 黄仁勋于 1993 年共同创办英伟达，并自公司成立起一直担任总裁兼首席执行官。对一家由创始人长期掌舵的公司来说，董事会调查现任首席执行官属于罕见情况。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Jensen_Huang">Jensen Huang - Wikipedia</a></li>
<li><a href="https://www.nvidia.com/en-eu/about-nvidia/governance/management-team/jensen-huang/">Jensen Huang - NVIDIA</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#Jensen Huang`, `#corporate governance`, `#prediction markets`, `#national security`

---

<a id="item-finance-news-2"></a>
### [前三季度中国新能源乘用车出口 388.7 万辆，同比增长 138.8%](https://finance.sina.com.cn/tech/roll/2026-10-26/doc-iniwpfnc2438186.shtml) ⭐️ 7.0/10

2026 年前三季度，中国新能源乘用车出口 388.7 万辆，同比增长 138.8%；同期国内零售量为 775.8 万辆，同比下降 12.8%。出口增长成为车企销量增长的重要支撑。

telegram · zaihuapd · 11月10日 02:56

**「背景」** 自 2026 年 1 月 1 日起，中国新能源汽车购置税从全额免征改为减半征收，按 5%税率执行，且单车最高减税不超过 1.5 万元；此前该减免政策已实施十余年，并逐步收窄。文章将国内新能源乘用车零售走弱，与这一优惠退坡及去年同期销量基数较高联系起来。

**「影响」** 文章将国内需求走弱与购车补贴、购置税优惠调整及去年同期销量基数较高联系起来，依赖国内零售的车企销量承压，而出口成为部分车企的增长来源。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://news.qq.com/rain/a/20260204A02ZHY00">2026年新能源汽车购置税“减半”，政策退坡下的市场重构与消费新逻辑</a></li>
<li><a href="https://www.sohu.com/a/954117446_122542760">2026年新能源汽车国补新政落地_搜狐汽车_搜狐网</a></li>

</ul>
</details>

**标签**: `#中国新能源汽车`, `#汽车出口`, `#国内零售`, `#购车补贴与购置税`, `#乘用车市场`

---