---
layout: default
title: "Horizon Summary: 2026-11-08 (ZH)"
date: 2026-11-08
lang: zh
---

> 从 39 条内容中筛选出 13 条重要资讯。

---

**科技新闻**
1. [MaxxBench 质疑 DeepSWE 编码基准的分数稳健性](#item-tech-news-1) ⭐️ 8.0/10
2. [SemiAnalysis 探访内蒙古 Galaxy 数据中心：规划 800MW，首期成本约为美国五分之一](#item-tech-news-2) ⭐️ 8.0/10
3. [GitHub 新 Git 存储架构 Rubicon 开启有限私有预览](#item-tech-news-3) ⭐️ 8.0/10
4. [微软研究院 AI Frontiers 小组据报结束，John Langford 离职](#item-tech-news-4) ⭐️ 7.0/10
5. [Claude Code 本地设置文件被提交，1,122 个公开 GitHub 文件暴露密钥](#item-tech-news-5) ⭐️ 7.0/10
6. [《极品飞车：地下狂飙 2》浏览器重实现支持在线多人](#item-tech-news-6) ⭐️ 7.0/10
7. [Asahi Linux 7.3 进度报告：Fedora Asahi Remix 首次同日跟进](#item-tech-news-7) ⭐️ 7.0/10
8. [Coldframe：伪装超市制冷控制器的 Python 蜜罐](#item-tech-news-8) ⭐️ 7.0/10
9. [Mac 被指内置未公开的家庭成员分类器](#item-tech-news-9) ⭐️ 7.0/10
10. [Claude Code 被指联网请求泄露登录邮箱，拦截可被绕过](#item-tech-news-10) ⭐️ 7.0/10
11. [苹果 HALO 人形机器人系统采用两个千问模型](#item-tech-news-11) ⭐️ 7.0/10

**财经新闻**
1. [伯克希尔第三季度回购规模翻倍至 96 亿美元，营业利润下降 5.8%](#item-finance-news-1) ⭐️ 7.0/10
2. [软银与 ABB 考虑分拆中国机器人业务以挽救 54 亿美元收购](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [MaxxBench 质疑 DeepSWE 编码基准的分数稳健性](https://maxxbench.unlap.ai/research/why-maxxbench/) ⭐️ 8.0/10

MaxxBench 在其研究页面发布分析，质疑 DeepSWE 编码基准的高分在任务描述被改动后是否依然成立：其做法是系统性地扰动任务规格，观察分数随之变化的幅度，并称在 DeepSWE 中发现若干缺陷。文章面向依赖 LLM 编码评测的开发者与评测机构，核心主张是单一基准分数不足以代表模型的真实能力。需要说明的是，这些结论目前仅出自 MaxxBench 一家来源，本文未获得原文内容，也没有独立复现或验证。

hackernews · antiuniverse · 11月7日 17:19 · [社区讨论](https://news.ycombinator.com/item?id=50406222)

**「背景」** DeepSWE 是用于比较 LLM 编码能力的基准，其排行榜分数常被直接当作模型实力的证据。MaxxBench 的这项分析对 89 个 DeepSWE 任务做指令或初始代码扰动（例如要求小写文件名、UTC 时间戳），中位补丁改动仅 17 行（3.5%），以此检验分数在任务表述稍变时是否仍然成立。

**「影响」** 对依据 DeepSWE 排名来挑选编码模型的团队来说，这意味着模型间的分差可能随任务描述的措辞而改变，被指出的基准缺陷也可能干扰跨版本、跨模型的比较；在把分数当作选型或上线依据之前，宜在自建的任务变体上重测一遍。

**「社区讨论」** 评论者普遍认可“只改一个参数、看分数漂移多少”这类检验思路，有人据此指出图中分数下滑最明显的是较小的 -flash 类模型，但同时提醒其中部分同名系列其实属于不同代际，不能一概而论。也有评论者认为根源在于实验室构建强化学习环境时不够严谨，而非直接针对基准训练，并对一个使用广泛的基准至今仍存在缺陷表示意外。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://daily.dev/posts/maxxbench-nice-deepswe-score-but-is-it-true--ue9ulip60">MaxxBench – &quot;Nice DeepSWE score. But is it true?&quot;</a></li>

</ul>
</details>

**标签**: `#llm-benchmarks`, `#evaluation-methodology`, `#benchmark-validity`, `#ai-software-engineering`, `#hacker-news-discussion`

---

<a id="item-tech-news-2"></a>
### [SemiAnalysis 探访内蒙古 Galaxy 数据中心：规划 800MW，首期成本约为美国五分之一](https://newsletter.semianalysis.com/p/we-visited-chinas-stargate-in-inner) ⭐️ 8.0/10

SemiAnalysis 于 9 月实地探访了内蒙古乌兰察布的 Galaxy 数据中心园区。该园区由可再生能源系统集成商 Envision Group 拥有，规划 IT 容量最高 800MW，规模约相当于美国 Abilene 的核心园区。报道称，首个 120MW 阶段在一年内交付，成本约为美国同类项目的五分之一；四个阶段均为两家互联网巨头定制建设，探访时园区其余部分仍在施工。该报道把这种快交付与低成本归因于深度垂直整合：Envision 自建风电场和专用供电线路，叶片工厂就在园区对面，并自行设计集成低压功率模块与 800V 系统、制造用于平滑负载的电池储能、共同设计预制变电站。报道还援引当地消息称，周边察哈尔高新区 22 个数据中心项目现场有近 3 万名建筑工人。上述成本对比来自 SemiAnalysis 的实地观察和其中国数据中心模型，尚非独立审计结果。

rss · Semianalysis · 11月7日 19:01

**「背景」** Stargate Abilene 是 OpenAI 在德州平原建设的吉瓦级园区，已成为美国 AI 基建扩张的标杆，也是 SemiAnalysis 此行对比的基准。SemiAnalysis 在此前发布的中国数据中心市场入门报告中曾指出，中国因劳动力供给充足而很少采用全模块化建造方式，但建设成本仍在持续下降，本次实地考察正是对这一判断的检验。园区业主远景集团以风电业务起家，全球风电装机超过 100GW，并从能源管理切入数据中心，这解释了它为何能自建风场、专用输电线路与储能设施。

**「影响」** 对希望借鉴这一模式的开发商来说，SemiAnalysis 的记述意味着成本优势与自建电源、专用供电线路、储能和预制变电站等环节绑定，而不是主要来自全模块化施工；报道指出当地劳动力充足，中国数据中心很少采用完全模块化方案。因此在劳动力供给和并网条件不同的市场，仅比较每兆瓦造价不足以判断该模式能否复制。

**标签**: `#AI infrastructure`, `#datacenters`, `#China AI`, `#cost efficiency`, `#vertical integration`

---

<a id="item-tech-news-3"></a>
### [GitHub 新 Git 存储架构 Rubicon 开启有限私有预览](https://github.blog/engineering/architecture-optimization/inside-githubs-new-git-storage-architecture/) ⭐️ 8.0/10

GitHub 推出代号 Rubicon 的新 Git 存储架构，面向大量 AI 智能体并发读写同一仓库的场景，目前处于有限私有预览阶段。按 GitHub 公布的信息，内部测试中 5000 个智能体同时协作时，系统每秒处理 7200 次推送，读取延迟保持在较低水平。该架构把 Git 对象存入 Azure Blob Storage，由 Ref-CAS 管理引用状态，并用虚拟副本处理读写、后台节点压缩数据包。这些数字来自内部测试，GitHub 尚未说明广泛开放时间或提供外部验证结果。

telegram · zaihuapd · 11月7日 14:12

**「背景」** Git 仓库由不可变的对象和可变的引用组成，推送时需要原子更新引用；当大量智能体同时读写同一仓库时，引用争用和对象存储容易成为并发瓶颈。Rubicon 把对象存入 Azure Blob Storage、用 Ref-CAS 管理引用状态，正是针对这种高并发访问模式做出的拆分。

**「影响」** 对依赖多个 AI 智能体并发写入同一仓库的团队来说，7,200 次/秒和 5,000 个智能体目前只是 GitHub 的内部测试结果，新架构也仅处于有限私有预览，尚不能作为容量规划或服务等级承诺的依据。现有用户和集成的兼容性影响在材料中未说明，需要等待 GitHub 扩大预览范围并公布启用或迁移条件。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.blog/engineering/architecture-optimization/inside-githubs-new-git-storage-architecture/">Inside GitHub’s new Git storage architecture - The GitHub Blog</a></li>

</ul>
</details>

**标签**: `#GitHub`, `#Git storage architecture`, `#AI agents`, `#Azure Blob Storage`, `#distributed systems`

---

<a id="item-tech-news-4"></a>
### [微软研究院 AI Frontiers 小组据报结束，John Langford 离职](https://hunch.net/?p=13764006) ⭐️ 7.0/10

据 Hacker News 帖子所引用的报道，微软研究院旗下的 AI Frontiers 研究小组据称已结束，研究员 John Langford 也已离开。现有材料只有博文和报道链接，未包含微软官方声明确认解散，也没有说明小组成员去向或项目是否转移。

hackernews · srean · 11月7日 18:02 · [社区讨论](https://news.ycombinator.com/item?id=50406563)

**「背景：AI Frontiers 的由来」** 公开报道显示，AI Frontiers 是 2023 年 ChatGPT 发布后在微软研究院内部成立的团队，约有 50 名研究人员，开发了用于协调 AI 智能体的 AutoGen 框架和可操作计算机完成任务的 Fara 智能体。该团队部分成员还探索不单纯依赖扩大模型规模来改进模型的方法。

**「影响」** 如果解散属实，对在微软研究院从事探索性 AI 研究的人员及合作者而言，最直接的后果是该小组提供的组织依托消失，相关项目的延续性、人员安置和资助方向都成为待解问题；现有材料没有给出这些安排。

**「社区讨论」** 多条评论把此事放在大公司集中押注 transformer 规模扩展、压缩探索性研究的背景下：有人称这类转向在每家大型公司都在发生，也有人惋惜数十亿美元涌向单一思路，并提到 JEPA 等替代方向。还有评论称微软研究院“做好工作就有好结果”的默契已被现任领导层打破，认为这会破坏研究文化；另一位评论者则主张研究与规模扩展应同时推进，不能让一方挤压另一方。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://daily.dev/posts/microsoft-researcher-john-langford-exits-ai-frontiers-group-declared-finished-t8nprypt6">Microsoft Researcher John Langford Exits. AI Frontiers Group ...</a></li>

</ul>
</details>

**标签**: `#AI research`, `#Microsoft Research`, `#AI industry`, `#research culture`, `#transformer models`

---

<a id="item-tech-news-5"></a>
### [Claude Code 本地设置文件被提交，1,122 个公开 GitHub 文件暴露密钥](https://apiiro.com/blog/coding-agents-leaking-secrets-github-dont-ask-again) ⭐️ 7.0/10

安全厂商 Apiiro 的博客称，它在公开 GitHub 仓库中扫描到 1,122 个含密钥的文件；这些密钥出现在 Claude Code 的 .claude/settings.local.json 中被批准的条目里：用户点击“Don&\#x27;t Ask Again”后，含明文密码或 API key 的整条命令会被写入该文件。Claude Code 团队的 Boris 在讨论中回应，该文件本应只留在本地，由 Claude 创建时会被自动写入 .gitignore；此次涉及的仓库是用户手动创建并手动提交的文件，他还承认 Claude Code 此前不做密钥清理，正在研究如何防止此类情况。报道中的数字来自单一厂商的扫描，泄露需同时满足“命令中直接写入密钥”和“仓库公开”两个条件，因此标题暗示的“点一下按钮就泄露”并不成立。

hackernews · shmulc · 11月7日 20:45 · [社区讨论](https://news.ycombinator.com/item?id=50407882)

**「背景」** Claude Code 的“不再询问”会把用户批准的完整命令写入项目内的 \`.claude/settings.local.json\` 权限允许列表。该文件按设计只应留在本地：Claude Code 团队成员在讨论中说明，当 Claude 自动创建此文件时会将其加入 \`.gitignore\`，但手动创建并提交到仓库的情况不受保护。此次暴露的前提正是开发者把该本地设置文件提交到公开仓库，而其中保存的命令又直接包含密码或密钥。

**「影响」** 对已将 .claude/settings.local.json 提交到公开仓库的开发者，应尽快轮换曾出现在其中的凭据，并把该文件移出版本控制、加入 .gitignore；仅删除当前文件不够，因为明文命令仍留在 Git 历史中可被检索。

**「社区讨论」** 评论者 Aurornis 认为标题有误导性：单按“Don&\#x27;t Ask Again”不会泄露，必须是用户把含密钥命令的本地设置提交并公开仓库。tsergiu 表示对 agent 权限十分警惕，采用每个任务一个隔离网络的临时虚拟机、开启 --dangerously-skip-permissions，并配合 API 代理限制其访问的外部服务；binarymax 则把凭据放在 1Password，由 Claude 调用 op CLI 并在需要时用指纹授权。

**标签**: `#Claude Code`, `#security`, `#secret leakage`, `#AI coding agents`, `#GitHub`

---

<a id="item-tech-news-6"></a>
### [《极品飞车：地下狂飙 2》浏览器重实现支持在线多人](https://nfsu2.xyz/) ⭐️ 7.0/10

玩家现在可以在浏览器中运行《极品飞车：地下狂飙 2》的重实现版本，并参与在线多人比赛。该实现依赖 WebGPU；有评论者报告，Linux 上的 Chromium 需要启用不安全的 WebGPU 功能，而在手机上可以正常游玩。站点目前只提供入口，没有公开架构说明或源码信息，因此具体实现方式仍不清楚。评论者还指出，这款游戏已属于不再可得的 abandonware，站点使用受版权保护内容的法律地位不稳。

hackernews · fluxusars · 11月7日 09:36 · [社区讨论](https://news.ycombinator.com/item?id=50403052)

**「背景」** 《Need for Speed: Underground 2》是 2004 年的赛车游戏，此次受到关注的 nfsu2.xyz 是爱好者制作的浏览器版本，并非官方发行。据项目页面和相关报道，它通过静态 WebAssembly 重编译把原游戏搬进 Chrome 与 Firefox，图形渲染依赖 WebGPU，并提供最高 120 fps 的宽屏画面、手柄支持以及联机自由漫游和好友对战。

**「影响」** 对想尝试的玩家来说，首要门槛是浏览器图形支持：Linux 上的 Chromium 用户据评论需启用不安全的 WebGPU 功能，移动端已有可正常游玩的报告。由于游戏已不再可得、站点又依赖受版权保护的内容，其可访问性和联机服务能否持续没有保障。

**「社区讨论」** 评论者分享了实际体验：有人在手机上顺利游玩，有人称联机地图上大量车辆同时生成、互相鸣笛和烧胎，场面混乱。讨论中也出现分歧，一方希望这类已停售游戏被保留下来，另一方则认为为受版权保护内容募捐“非常可疑”，并预计它走红后会收到下架通知。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://nfsu2.xyz/">nfsu2.xyz - Underground 2 Revived</a></li>
<li><a href="https://pro-gamer.gg/need-for-speed-underground-2-playable-browser-120-fps-webgpu-multiplayer-free-roam/">Need for Speed: Underground 2 in Browser: 120 FPS &amp; WebGPU ...</a></li>
<li><a href="https://www.gsmdome.com/need-for-speed-underground-2-gets-a-webgpu-browser-port-with-online-multiplayer">Need for Speed: Underground 2 Gets a WebGPU Browser Port With ...</a></li>

</ul>
</details>

**标签**: `#webgpu`, `#browser-gaming`, `#reverse-engineering`, `#abandonware`, `#emulation`

---

<a id="item-tech-news-7"></a>
### [Asahi Linux 7.3 进度报告：Fedora Asahi Remix 首次同日跟进](https://asahilinux.org/2026/11/progress-report-7-3/) ⭐️ 7.0/10

Asahi Linux 发布 7.3 进度报告，核心变化是 Fedora Asahi Remix 的发布节奏：评论中引用的报告内容称，Fedora Linux 45 于 11 月 3 日发布，Remix 当天跟进，这是该项目首次实现与上游 Fedora 同日发布。报告同时覆盖 Apple Silicon 上 Linux 支持的持续开发，但现有材料没有给出完整硬件兼容清单或独立性能测试结果。对 Fedora Asahi Remix 用户来说，同日跟进意味着可更快获得新上游版本；实际可用性仍取决于具体机型的硬件支持。

hackernews · ackyshake · 11月7日 05:20 · [社区讨论](https://news.ycombinator.com/item?id=50401867)

**「背景」** Asahi Linux 是一个把 Linux 移植到 Apple Silicon Mac 上的开源项目，其面向这些机型的官方发行版 Fedora Asahi Remix 由项目与 Fedora 社区协作维护；项目平时以进度报告的形式披露内核、驱动与发行版的同步情况。据社区评论引述，本期报告提到上游 Fedora Linux 45 于 11 月 3 日发布，而 Fedora Asahi Remix 首次做到同日跟进；评论中讨论的 USB-C 外接显示器支持缺口，以及项目对宽松许可证被第三方利用的担忧，都是报告涉及的具体议题。

**「影响」** 希望留在 Fedora 生态的 Apple Silicon 用户可更快获得 Fedora 45 的更新，减少下游重构建造成的版本滞后；但采用前仍应按具体 Mac 机型核查外设兼容性，尤其是评论中提到的 USB-C 外接显示器支持。

**「社区讨论」** 评论中，一位用户称 USB-C 外接显示器支持是他多次考虑安装 Asahi Linux 却始终放弃的唯一阻塞点；另一位评论者则追问报告提到的“利用宽松许可证劫持项目”是否指 Omarchy，并对项目曾采用 MIT 许可证表示意外。上述均为评论者个人说法，现有材料未给出报告原文对应细节。

**标签**: `#Asahi Linux`, `#Apple Silicon`, `#Linux`, `#Fedora`, `#Open Source`

---

<a id="item-tech-news-8"></a>
### [Coldframe：伪装超市制冷控制器的 Python 蜜罐](https://github.com/hedgerow-dev/coldframe) ⭐️ 7.0/10

作者在 Show HN 发布了 Coldframe：一个只用 Python 标准库、单文件实现的蜜罐，伪装成 Danfoss AK-SM 800A 和 Dixell XWEB 超市制冷控制器。作者称其按 Shodan 上的真实设备记录匹配响应头顺序、页面标题、证书字段和 TLS 版本，因此两个实例被 Shodan 识别为真实设备而非蜜罐，并能识别 CVE-2025-41450“当日代码”登录绕过及另外三个 Danfoss CVE 和 XWEB 漏洞的尝试。默认口令会进入一个带除霜按钮的假门店面板，以观察攻击者的后续操作；但两个实例仅上线一天，目前只看到通用扫描器和 Shodan 爬虫 refrigerator.census.shodan.io，尚无真实攻击样本。

hackernews · hedgerow-dev · 11月7日 17:27 · [社区讨论](https://news.ycombinator.com/item?id=50406292)

**「背景：Danfoss 冷柜控制器的认证绕过漏洞」** Coldframe 模仿的 Danfoss AK-SM 800A 是超市制冷系统常用的远程控制器；Danfoss 于 2025 年 3 月发布的安全公告 DSA-2025-03-01 指出 AK-SM8xxA 系列存在“不当认证”问题，可导致认证绕过，并建议安装 4.2 版补丁修复（tool-2-1），该漏洞编号为 CVE-2025-41450，NVD 记录显示其尚未被优先纳入富化处理（tool-2-2）。作者所说的“过去几周工业冷柜安装事件”，指 2026 年 10 月报道的法国超市制冷系统遭攻击事件；相关报道把 AK-SM 800A 与 CVE-2025-41450、CVE-2025-41451、CVE-2025-41452 放在一起讨论，但这些漏洞如何组合利用、实际发生了什么，仍有未证实之处（tool-2-3）。

**「影响」** 对 OT/ICS 安全研究者而言，这个单文件、无第三方依赖的诱饵可用于捕获默认登录后的第二阶段行为，并记录提交的“当日代码”是否正确，而不只是统计扫描量。不过，当前公开证据只覆盖一天的两个实例和通用扫描流量，Shodan 指纹匹配也不能证明它能骗过定向攻击者，部署者不应把其识别结果当作生产设备暴露面的完整评估。

**「社区讨论」** 有评论者质疑用 Shodan 数据校准设备指纹的可靠性，称自己制作摄像头蜜罐时发现网上大量设备本身就是蜜罐或已被入侵，建议改用真实漏洞设备进行探测验证。作者则回应称超市通常没有安全团队，若制冷控制器需要打补丁、VPN 和强密码才安全，这些工作应由厂商或安装商默认提供。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.danfoss.com/en/service-and-support/coordinated-vulnerability-disclosure/danfoss-security-advisories/dsa-2025-03-01/">DSA-2025-03-01 | Danfoss</a></li>
<li><a href="https://nvd.nist.gov/vuln/detail/cve-2025-41450">NVD-CVE-2025-41450</a></li>
<li><a href="https://thecybersecguru.com/news/french-supermarket-refrigeration-cyberattack/">French Supermarket Cyberattack: Danfoss Refrigeration ...</a></li>

</ul>
</details>

**标签**: `#honeypot`, `#ICS/OT security`, `#Shodan`, `#CVE-2025-41450`, `#Python`

---

<a id="item-tech-news-9"></a>
### [Mac 被指内置未公开的家庭成员分类器](https://8rank.ai/game/apple-intelligence-personal-knowledge-graph) ⭐️ 7.0/10

一篇发布在 8rank.ai 的调查文章声称，自 2022 年起的每台 Mac 都内置了未公开的守护进程，用来构建关于用户本人、联系人和家庭成员关系的个人知识图谱；文章作者在 Hacker News 评论区确认了自己的研究者身份。该文把其中一个组件描述为家庭成员分类器，讨论随之集中在本地关系推断的隐私影响，以及它可能为 Siri 等本地 LLM 提供消歧上下文；由于目前只有标题、分析摘要和评论、没有正文，具体技术证据和分类准确度无法独立核实。

hackernews · infwhispers · 11月7日 09:46 · [社区讨论](https://news.ycombinator.com/item?id=50403097)

**「背景」** Apple Intelligence 的个性化功能依赖设备端的数据索引，但外界此前并不清楚这些索引如何组织，以及它与联系人、照片人物识别等已有数据之间的关系。此次研究称，macOS 13（2022 年）以来的系统内置 knowledgeconstructiond 与 intelligenceplatformd 两个守护进程，共同在本地构建“个人知识图谱”，数据存放在 ~/Library/IntelligencePlatform 下约 51 个明文 SQLite 数据库中，并受 TCC 完全磁盘访问权限保护。研究者是在对 macOS 26 的 Apple Intelligence 组件做安全分析时发现这套架构的。

**「影响」** 若该机制确实存在并默认运行，受影响的将是相关 macOS 版本上的 Mac 用户：现有材料没有说明这些守护进程是否默认启用、关系图是否可由用户查看或删除，这使用户难以判断哪些家庭关系数据已被推断和保留。

**「社区讨论」** 有评论者认为这类数据若为选择性加入会很有趣，但如今令人疲惫，并担心日常交谈被系统记录会改变社交默契；也有人表示并不意外，因为 Photos 早已识别人脸和宠物，并引用乔布斯 2010 年关于隐私要“用平实语言反复告知用户”的说法。另有评论从功能角度指出，这种关系图是为本地 LLM 提供上下文，以便在“给 James 发消息”或“告诉老板”时判断指代对象。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://techbytes.app/posts/every-mac-comes-with-an-undocumented-family-member-classifier/">Every Mac comes with an (undocumented) family member classifier</a></li>
<li><a href="https://daily.dev/posts/every-mac-comes-with-an-undocumented-family-member-classifier-s3lfxwdun">Every Mac comes with an (undocumented) family member classifier</a></li>

</ul>
</details>

**标签**: `#Apple Intelligence`, `#privacy`, `#personal knowledge graph`, `#macOS`, `#reverse engineering`

---

<a id="item-tech-news-10"></a>
### [Claude Code 被指联网请求泄露登录邮箱，拦截可被绕过](https://github.com/anthropics/claude-code/issues/107757) ⭐️ 7.0/10

Claude Code 被指在联网请求中携带用户登录邮箱，一名开发者投诉称因此每天收到大量诈骗邮件，并称邮箱曾被发送给 Wikipedia、美国证券交易委员会等站点；该问题早在今年 7 月就有人报告。Anthropic 工程师表示，把登录邮箱放入模型上下文原本是为了解决 Claude 乱填作者名的问题；2.1.317 版已加入拦截，但可用 Python 脚本绕过。公司计划在下一版本从模型上下文中移除登录邮箱，但目前尚无已发布版本完成这一修复。

telegram · zaihuapd · 11月7日 08:09

**「背景」** Claude Code 的联网请求会携带模型上下文中的信息；据 Anthropic 工程师在 issue 中的说法，登录邮箱最初被放入上下文，是为了避免模型在需要填写作者名等字段时随意编造。该问题早在今年 7 月就有人报告，涉及邮箱被发送至 Wikipedia、美国证券交易委员会等站点。

**「实际影响」** 对依赖 Claude Code 进行网页检索的开发者而言，登录邮箱会出现在发往第三方的请求头中，已有用户报告因此每天收到大量诈骗邮件。由于 2.1.317 版的拦截可被 Python 脚本绕过，升级到该版本并不等于消除暴露；在下一版本移除模型上下文中的登录邮箱前，涉及外部网页抓取的工作流仍需按邮箱可能已泄露来评估风险。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/anthropics/claude-code/issues/107757">Bug Report: Privacy violation in User-Agent header · Issue # 107757 ...</a></li>

</ul>
</details>

**标签**: `#Claude Code`, `#privacy`, `#security vulnerability`, `#AI coding tools`, `#Anthropic`

---

<a id="item-tech-news-11"></a>
### [苹果 HALO 人形机器人系统采用两个千问模型](https://weibo.com/1642634100/RqjjGllvw) ⭐️ 7.0/10

据社交媒体转述，苹果研究团队在 11 月 4 日提交至 arXiv 的论文中披露了人形机器人自主控制系统 HALO，并在宇树 G1 上验证了从仿真到陌生真实房间的动作迁移。系统分为三层：上层用 Qwen3.6-35B-A3B 负责任务编排，中层用 Qwen3.5-2B 生成动作，底层是经强化学习训练的动作跟踪器。转述还称，团队已公开数据生成、模型训练与部署代码。该消息未附 arXiv 链接，论文和代码发布情况尚待独立核对。

telegram · zaihuapd · 11月7日 13:35

**「背景」** 人形机器人的“仿真到现实”（sim-to-real）指先在仿真环境中生成数据、训练策略，再迁移到真实硬件；难点在于真实房间的光照、布局和接触条件与仿真不同。HALO 的全称是 Humanoid Autonomy, Learned in simulation, running Onboard，其数据管线在仿真中生成第一视角的视觉—语言—动作数据，训练出的策略完全在机器人本机运行。

**「影响」** 对开发者而言，若公开代码的链接和许可证可用，可参照其数据生成、训练与部署流程，在宇树 G1 等平台上评估“LLM 规划加强化学习动作跟踪”的组合；采用前需核对许可证及真实硬件的适配范围。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/html/2611.06908">Perceptive Humanoid Motion from Simulation - arXiv.org</a></li>

</ul>
</details>

**标签**: `#humanoid robotics`, `#sim-to-real`, `#LLM robotics`, `#Apple research`, `#open-source code`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [伯克希尔第三季度回购规模翻倍至 96 亿美元，营业利润下降 5.8%](https://www.cnbc.com/2026/11/07/berkshire-hathaway-q3-2026-earnings-buybacks.html) ⭐️ 7.0/10

伯克希尔·哈撒韦（Berkshire Hathaway）在 2026 年第三季度回购了价值 96 亿美元的自有股票，超过第二季度 45 亿美元回购额的两倍；同期营业利润为 127.05 亿美元，较去年同期的 134.85 亿美元下降 5.8%。

rss · CNBC Finance · 11月7日 15:23

**「背景」** 营业利润只统计伯克希尔全资经营的业务，而公司整体利润还包含其股票投资组合的账面收益；第三季度投资利得减少近 50%至 94.07 亿美元，因此整体利润 133.12 亿美元，同比降幅扩大到 28%（上年同期为 307.96 亿美元）。拖累营业利润的主要是保险业务：保险承保利润同比下降 43%至 13.52 亿美元。

**标签**: `#Berkshire Hathaway`, `#share buybacks`, `#earnings`, `#insurance`, `#cash reserves`

---

<a id="item-finance-news-2"></a>
### [软银与 ABB 考虑分拆中国机器人业务以挽救 54 亿美元收购](https://www.bloomberg.com/news/articles/2026-11-07/softbank-abb-weigh-china-carve-out-to-salvage-robotics-deal) ⭐️ 7.0/10

软银与 ABB 正考虑把 ABB 机器人业务的中国部分分拆为股权结构不同的独立实体，以挽救已被中国监管机构叫停的 54 亿美元收购；知情人士称该方案由软银主导，可能失败，ABB 也在评估另寻买家等其他选项。

telegram · zaihuapd · 11月7日 11:24

**「背景」** 中国的外商投资安全审查机制办公室本周叫停了软银以 54 亿美元收购 ABB 机器人业务的交易，ABB 确认已收到软银关于该收购在中国被禁止的通知。该审查是中国监管部门对外资并购是否影响国家安全进行的评估，此前知情人士曾预计交易会获得批准。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.reuters.com/business/media-telecom/china-blocks-softbanks-54-billion-takeover-abbs-robotics-division-ft-reports-2026-11-05/">China blocks SoftBank’s $5.4 billion takeover of ABB’s ...</a></li>
<li><a href="https://www.abb.com/global/en/news/140154/update-on-divestment-of-abb-robotics">Update on divestment of ABB Robotics</a></li>
<li><a href="https://www.ft.com/content/f10c3e24-45e4-47ff-bde2-24a8de90aec4?syn-25a6b1a6=1">China blocks SoftBank’s $5.4bn takeover of ABB’s robotics ...</a></li>

</ul>
</details>

**标签**: `#SoftBank`, `#ABB`, `#robotics M&amp;A`, `#China foreign investment review`, `#corporate carve-out`

---