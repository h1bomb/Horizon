---
layout: default
title: "Horizon Summary: 2026-11-26 (ZH)"
date: 2026-11-26
lang: zh
---

> 从 36 条内容中筛选出 9 条重要资讯。

---

**科技新闻**
1. [1Password 确认安全事件，部分客户账户信息被窃](#item-tech-news-1) ⭐️ 8.0/10
2. [GRH Lean 验证出现约 7.6 万行精简版](#item-tech-news-2) ⭐️ 8.0/10
3. [Ubuntu 安全补丁响应缓慢引发迁移与 QA 争论](#item-tech-news-3) ⭐️ 7.0/10
4. [腾讯开源 Hy4 flash 量化权重，最小版经 Strata 可跑于 64 GB Mac mini](#item-tech-news-4) ⭐️ 7.0/10
5. [Minecraft Java 版曝字体 RCE 漏洞，1.20.5 起受影响](#item-tech-news-5) ⭐️ 7.0/10
6. [三星与 SK 海力士据报交叉许可长江存储 Xtacking 技术](#item-tech-news-6) ⭐️ 7.0/10
7. [FCC 批准 SpaceX 部署百万颗 Starmind 数据中心卫星](#item-tech-news-7) ⭐️ 7.0/10

**财经新闻**
1. [法庭文件：美商务部施压英特尔交出 10%股权](#item-finance-news-1) ⭐️ 9.0/10
2. [美国拟对中国、欧盟等 14 个贸易伙伴加征新关税](#item-finance-news-2) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [1Password 确认安全事件，部分客户账户信息被窃](https://1password.com/blog/update-on-nov-2026-security-incident) ⭐️ 8.0/10

1Password 确认发生安全事件，攻击者访问其内部系统并窃取了部分客户的姓名、邮箱地址、账户标识以及账户创建和最近登录时间；公司表示客户保险库及其中的内容未受影响。公司于 11 月 19 日开始调查员工企业 GitHub 账户被入侵的迹象，攻击者借该账户访问源代码并向后台服务推送恶意代码，导致上述信息被下载。1Password 尚未披露受影响用户数量，已停用涉事账户、轮换或撤销可能暴露的内部凭证，并加强邀请和恢复邮件验证码。公司称用户无需更改账户，但应警惕钓鱼邮件。

hackernews · lxhrstn · 11月25日 17:18 · [社区讨论](https://news.ycombinator.com/item?id=50644817)

**「背景」** 1Password 是广泛使用的密码管理器，用户数据存放在加密保险库中，账户管理数据则由后台服务处理。此次披露中被窃取的是姓名、邮箱、账户标识及创建和最近登录时间等账户信息，保险库及其内容未受影响。

**「影响」** 对使用 1Password 托管保险库的客户而言，官方称无需更改账户，但仍需警惕伪装成保险库共享、邀请或恢复验证码等主题的钓鱼邮件。

**「社区讨论」** 评论中，tptacek 认为员工笔记本被入侵后向 GitHub 推送代码并被部署，是 SaaS 公司长期存在且日益突出的标准攻击路径；ctidd 则批评公告未说明是否缺少分支保护规则或规则如何被绕过。另有用户称收到包含部分个人细节的高质量钓鱼邮件，也有人讨论仅使用本地保险库能否降低此类供应链风险。

**标签**: `#security incident`, `#password manager`, `#supply chain security`, `#SaaS`, `#phishing`

---

<a id="item-tech-news-2"></a>
### [GRH Lean 验证出现约 7.6 万行精简版](https://github.com/lsernau/grh-lean) ⭐️ 8.0/10

GitHub 仓库 lsernau/grh-lean 提供了一个更短的 Anthropic GRH Lean 验证版本，Hacker News 讨论称它比原始形式化更易读并配有文档。讨论中同时出现约 30 万行的可读版本，以及从约 1700 万行降至约 7.6 万行（减少 99.56%）两种说法；所给材料不足以判断它们是否指同一构建。该版本据称区分“已知数学”和“新数学”，但现有材料没有说明它是否与原验证形式等价、依赖哪些公理，也没有独立核实其正确性。

hackernews · nb-t · 11月25日 21:48 · [社区讨论](https://news.ycombinator.com/item?id=50648050)

**「背景」** 广义黎曼猜想（GRH）是黎曼猜想的推广形式，要对其进行形式化验证，就必须把论证改写成机器可以逐步检查的 Lean 代码。此前有报道称，Anthropic 的一位数学家借助 Claude 宣称解决了这一难题（NPR，2026 年 11 月 21 日），而当时的 Lean 形式化体量极为庞大，社区评论提到约 1700 万行。这个新仓库把同样的五个定理收纳进约 7.6 万行的 grh-compact 目录，其中每个目录都是独立的 Lake 项目，并各自带有 README；构建需要 Lean v4.35.0，以及 Mathlib 的 56a00585 提交。

**「影响」** 对需要审阅这份形式化的 Lean 用户和数学研究者，较小的代码库与文档据称降低了阅读门槛；但在缺少等价性检查和公理依赖说明的情况下，直接复用或引用前仍需自行核对构建结果。

**「社区讨论」** 有评论者欢迎更清晰的文档和“已知数学/新数学”分区，并追问这是否回应了 Tao 一个月前关于“巨大但缺乏洞见的形式化证明”的批评。另有人希望数学家真正理解核心论证，写出传统数学论文并在会议上讲解，而不是只留下 Lean 代码。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/lsernau/grh-lean">GitHub - lsernau / grh - lean : A short Lean 4 proof of the Generalized...</a></li>
<li><a href="https://www.npr.org/2026/11/21/g-s1-154922/anthropic-worker-claims-to-have-solved-a-holy-grail-of-math-problems-with-the-help-of-ai">Anthropic worker claims to have solved a Holy Grail of math... : NPR</a></li>

</ul>
</details>

**标签**: `#Lean`, `#formal-verification`, `#theorem-proving`, `#AI-assisted-mathematics`, `#open-source`

---

<a id="item-tech-news-3"></a>
### [Ubuntu 安全补丁响应缓慢引发迁移与 QA 争论](https://www.openwall.com/lists/oss-security/2026/11/25/9) ⭐️ 7.0/10

Hacker News 上的一则讨论聚焦 oss-security 帖子所指的 Ubuntu 安全响应缓慢问题，核心是用户对补丁延迟的不满。由于帖子正文未提供，具体延迟时长、受影响版本以及 Ubuntu 官方回应都无法确认。评论中，有用户称已将服务器镜像从 Ubuntu 迁至 Debian；另有用户提醒，补丁速度需要与回归测试权衡。

hackernews · gslin · 11月25日 20:38 · [社区讨论](https://news.ycombinator.com/item?id=50647181)

**「背景」** 这轮讨论围绕 Ubuntu 对严重安全漏洞的修复节奏展开。oss-security 邮件给出的具体案例是远程 TCP 数据破坏漏洞 CVE-2026-98432；发帖者称，Ubuntu 在漏洞披露后数周才提供修复。对依赖发行版安全更新的服务器用户而言，这一案例提供了判断响应是否及时的直接参照。

**「运维影响」** 对依赖无人值守升级的服务器运维者，评论者报告的实际调整是不再只从 security 仓库安装更新，而是安装全部更新并接受系统被破坏的风险；这说明补丁发布节奏会直接影响升级策略。

**「社区讨论」** 评论中的主要分歧是补丁速度与稳定性：一方认为 Ubuntu 的慢响应不可接受并称已迁往 Debian，另一方强调 Debian 等发行版的 QA 资源有限，回归风险确实存在。还有评论者引用稳定内核维护者 2025 年的说法，警告随意挑选补丁会留下已知和未知问题。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.openwall.com/lists/oss-security/2026/11/25/9">oss - security - Slow Ubuntu security response times</a></li>

</ul>
</details>

**标签**: `#Ubuntu`, `#Linux distributions`, `#security patching`, `#open source`, `#Debian`

---

<a id="item-tech-news-4"></a>
### [腾讯开源 Hy4 flash 量化权重，最小版经 Strata 可跑于 64 GB Mac mini](https://mp.weixin.qq.com/s/o0xxShVQX6g2UllrrEv1WQ) ⭐️ 7.0/10

腾讯混元通过 AngelSlim 开源了 224B 参数模型 Hy4 flash 的 GGUF 量化权重：原权重约 410.27 GiB，最小 IQ2-AH 版为 125.73 GiB，约为原版的 30%。腾讯称，借助 Strata offload 框架，64 GB Mac mini 可运行这一最小版本。来源给出的数据还显示，48 GB 显存设备在 10K 上下文下达到 89 token/s，M5 Max 128 GB 上的 Q3\_K 版在 32K 上下文下为 47 token/s，Q3\_K 与原始模型在 DeepSWE v1.1 等评测中的分差不超过 0.4 分。上述性能与评测数字均为来源转述，未提供测试方法或独立验证。

telegram · zaihuapd · 11月25日 09:29

**「背景」** Hy4 flash 是腾讯混元的 MoE 模型，官方模型卡称其总参数约 220B（含 64B Engram 参数）、每个 token 仅激活 12B，并支持最长 1M token 的上下文。GGUF 是本地推理工具常用的模型文件格式，IQ2-AH 属于约 2 bit 级的低位宽量化，用一定精度损失换取更小的权重体积；当压缩后的权重仍超过设备可用内存时，Strata offload 通过分层加载避免模型必须全部常驻内存。

**「影响」** 对本地推理用户而言，最小版本仍约 125.73 GiB，远超 64 GB 统一内存，因此能否运行取决于 Strata offload 的卸载机制；来源未给出 Mac mini 上的实际生成速度，部署前需把这一性能不确定性计入预期。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/tencent/Hy4-flash">tencent / Hy 4 - flash · Hugging Face</a></li>

</ul>
</details>

**标签**: `#open-source models`, `#quantization`, `#local LLM inference`, `#model compression`, `#Tencent Hunyuan`

---

<a id="item-tech-news-5"></a>
### [Minecraft Java 版曝字体 RCE 漏洞，1.20.5 起受影响](https://github.com/bikini/minecraft2shell) ⭐️ 7.0/10

一个名为 minecraft2shell 的项目于 11 月 22 日公开，称 Minecraft Java 版可通过服务器资源包中的特制 TrueType 字体触发 FreeType 2.14.3 及更早版本的原生越界写，并在 Java 版 26.3 的 Windows 客户端上执行任意代码。该帖称 1.20.5 至 1.21.10 以及 26.1 至 26.4 快照受影响，1.20.4 及更早版本和基岩版不受影响；目前 Mojang 仍使用 lwjgl-freetype 3.4.3，尚无官方补丁。由于信息来自 Telegram 投稿、未见官方公告，且部分版本表述存在不一致，漏洞范围和修复状态仍需以官方确认为准。

telegram · zaihuapd · 11月25日 12:46

**「背景」** Minecraft Java 版通过 LWJGL 调用 FreeType 来渲染游戏内文字，而资源包允许服务器向客户端提供自定义字体文件，因此客户端在加载资源包时会解析其中的 TrueType 字体。LiquidBounce 的说明称，GitHub 用户 bikini 于 11 月 22 日公开了可工作的演示，且事先未通知 Mojang；该演示把触发点定位在 FreeType 加载字形时的 TrueType hinting 阶段。

**「临时应对」** 在官方补丁发布前，多人服务器管理员应避免加载不受信任的资源包，并按投稿建议将资源包权限设为“禁用”，或安装 11 月 24 日发布的社区修复 m2sfix 1.0.0；该修复通过 Java agent 或 mod 关闭字体 hinting，属于临时缓解而非官方修复。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/bikini/minecraft2shell">GitHub - bikini/ minecraft 2 shell : Minecraft to native RCE · GitHub</a></li>
<li><a href="https://liquidbounce.net/blog/minecraft2shell-vulnerability-AK0X5CE6">Minecraft 2 Shell Vulnerability</a></li>

</ul>
</details>

**标签**: `#Minecraft`, `#RCE`, `#FreeType`, `#security vulnerability`, `#Java`

---

<a id="item-tech-news-6"></a>
### [三星与 SK 海力士据报交叉许可长江存储 Xtacking 技术](https://tech.ifeng.com/c/8yLRPKxQy4L) ⭐️ 7.0/10

据凤凰网报道，三星电子和 SK 海力士已通过交叉许可协议，同意在 3D NAND 闪存中采用长江存储 Xtacking 堆叠技术的部分内容；但三家公司均拒绝置评，相关安排尚未得到确认。Xtacking 将存储单元与控制电路（CMOS）分别制作在两片晶圆上，再通过键合工艺合为一体，使两部分能够独立生产和优化。报道还引述 Omdia 高级分析师称，这种分工可让厂商自行生产存储阵列，并将逻辑电路交由晶圆代工厂，从而采用更先进的制程。

telegram · zaihuapd · 11月25日 14:33

**「背景」** 长江存储曾在 Flash Memory Summit 上公布 Xtacking 技术，并用 64 层 3D NAND 芯片展示其效果。该架构将存储阵列与 CMOS 逻辑电路分别制造在两片晶圆上，再通过键合合为一颗芯片，使两部分可以独立选择制程并分别优化。

**「影响」** 若许可协议属实，三星与 SK 海力士可在 3D NAND 生产中把存储阵列与外围逻辑电路分开制造、再经混合键合合并，逻辑部分还可交由晶圆代工厂用更先进制程生产，从而绕开单片晶圆上两类电路工艺难以兼顾的限制。据 TrendForce 引述行业数据，长江存储在 2017 年至 2024 年 1 月间公开了 119 项混合键合相关专利，而截至 2023 年三星为 83 项、SK 海力士仅 11 项，这一专利差距是两家韩企寻求许可的现实动因。不过三方均拒绝置评，许可范围、费用与导入的产品型号均未披露，实际落地时间仍无法确认。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.esmchina.com/news/3936.html">长 江 存 储 首次弯道超车！ 重磅发布 Xtacking 技术，下一代64...</a></li>
<li><a href="https://www.techpowerup.com/355199/samsung-and-sk-hynix-to-license-ymtcs-xtacking-technology">Samsung and SK hynix to License YMTC&#x27;s Xtacking ... | TechPowerUp</a></li>
<li><a href="https://www.trendforce.com/news/2026/11/25/news-sk-hynix-reportedly-joins-samsung-in-licensing-ymtcs-xtacking-technology-as-nand-race-heats-up/">[News] SK hynix Reportedly Joins Samsung in Licensing...</a></li>

</ul>
</details>

**标签**: `#semiconductors`, `#3D NAND`, `#Xtacking`, `#Samsung`, `#SK Hynix`

---

<a id="item-tech-news-7"></a>
### [FCC 批准 SpaceX 部署百万颗 Starmind 数据中心卫星](https://www.geekwire.com/2026/fcc-clears-spacex-million-satellites-starmind-data-center/) ⭐️ 7.0/10

美国联邦通信委员会（FCC）批准 SpaceX 最多部署 100 万颗 Starmind 卫星，用于构建在轨数据处理网络；FCC 称这是美国首次批准太空数据中心星座，卫星运行高度为 500 至 1002 公里。授权附带通信备份、定期提交进展和轨道碎片减缓详细方案等条件，并要求首颗卫星不晚于 2033 年投入运行、整个星座在 2040 年前全部运行。FCC 在审批中驳回了亚马逊、Viasat 和美国天文学会的反对意见。

telegram · zaihuapd · 11月26日 04:45

**「背景」** Starmind 是 SpaceX 拟建的在轨数据处理星座，FCC 此次给出的是卫星频率与轨道授权，而非已完成的部署。Ars Technica 报道，命令要求 SpaceX 在七年内让首颗可运行 Starmind 卫星入轨，并在 2035 年 11 月前部署 10 万颗可运行卫星。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arstechnica.com/space/2026/11/the-fcc-has-authorized-spacex-to-deploy-1-million-satellites/">The FCC has authorized SpaceX to deploy 1 million satellites</a></li>

</ul>
</details>

**标签**: `#SpaceX`, `#FCC`, `#space data centers`, `#satellite constellations`, `#regulatory approval`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [法庭文件：美商务部施压英特尔交出 10%股权](https://www.wired.com/story/inside-trumps-demands-to-another-chips-ceo/) ⭐️ 9.0/10

据 WIRED 报道，法庭文件显示，2025 年 8 月美国商务部律师在与英特尔首席财务官的通话中称，英特尔不要“误以为这是一场谈判”，并提醒董事会虽可拒绝，但会带来无法预测的后果。几天后英特尔董事会交出这部分股权，特朗普称美国政府未付钱即“完全拥有并控制英特尔 10%的股份”，这批股份现值约 110 亿美元。

telegram · zaihuapd · 11月25日 13:25

**「背景」** 据《纽约时报》2026 年 7 月报道，特朗普政府已入股多家私营企业；2026 年 3 月，一名英特尔股东提起诉讼，称政府胁迫公司交出这 10%股份。

**「影响」** 据 NPR 和 The Verge 报道，美方所得 10%股份对应约 89 亿美元原本应支付给英特尔的联邦芯片补贴资金；这种“补贴转股权”的安排使美国政府成为英特尔股东，原有股东的持股比例相应被摊薄，政府也可借股东身份介入公司治理。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.nytimes.com/2026/07/13/business/economy/trump-equity-stakes-ai.html">Trump Administration Is Snapping Up Stakes in Private Companies.</a></li>
<li><a href="https://www.npr.org/2025/08/22/nx-s1-5509673/trump-says-us-government-will-take-stake-intel">Intel will give the U . S . government a 10% stake , Trump says : NPR</a></li>
<li><a href="https://www.theverge.com/news/764480/intel-donald-trump-lip-bu-tan-deal">US government takes 10 percent stake in Intel in... | The Verge</a></li>

</ul>
</details>

**标签**: `#Intel`, `#美国政府`, `#半导体`, `#股权收购`, `#产业政策`

---

<a id="item-finance-news-2"></a>
### [美国拟对中国、欧盟等 14 个贸易伙伴加征新关税](https://www.cnbc.com/2026/11/25/us-tariffs-trump-section-301.html) ⭐️ 8.0/10

据 CNBC 报道，美国政府拟依据 1974 年《贸易法》第 301 条——一项允许对不公平贸易做法加征关税的法律——对欧盟、日本、印度等 14 个贸易伙伴加征新关税，税率按国别设定。对中国，新关税将在 2018 年已加征的 25%之上再加征 20%；若中国未遵守 2025 年 10 月在韩国釜山达成的贸易休战协议，税率可能升至 40%。

telegram · zaihuapd · 11月25日 13:59

**「背景」** 本轮拟议关税依据 1974 年《贸易法》第 301 条；据福克斯商业频道报道，它源自一项为期八个月的调查，并旨在替代今年早些时候被最高法院推翻的关税。对华税率还与美国和中国在 2025 年 10 月 30 日于韩国釜山达成的贸易休战协议挂钩。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.foxbusiness.com/fox-news-global-economy/trump-admin-raise-tariffs-china-eu-other-trading-partners">Trump administration proposes sweeping Section 301 tariffs on...</a></li>
<li><a href="https://www.cnbc.com/2025/10/30/trump-xi-south-korea-rare-earth-tariff-trade-war-nvidia.html">What Trump and Xi agreed to in the U . S .- China trade truce</a></li>

</ul>
</details>

**标签**: `#tariffs`, `#trade policy`, `#Section 301`, `#China-US trade`, `#global trade`

---