---
layout: default
title: "Horizon Summary: 2026-11-17 (ZH)"
date: 2026-11-17
lang: zh
---

> 从 48 条内容中筛选出 15 条重要资讯。

---

**科技新闻**
1. [vLLM v0.34.0 发布：KV 缓存默认按实际空闲显存分配](#item-tech-news-1) ⭐️ 8.0/10
2. [Jiff 1.0 发布：Rust 日期时间库的新选项](#item-tech-news-2) ⭐️ 8.0/10
3. [美国将先进 AI 芯片出口管制延伸至远程访问](#item-tech-news-3) ⭐️ 8.0/10
4. [卡内基梅隆 CS Learn 免费上线 YouTube 课程讲座](#item-tech-news-4) ⭐️ 7.0/10
5. [Optimizely 据报被入侵并向 Zoom、GitLab 投放恶意代码](#item-tech-news-5) ⭐️ 7.0/10
6. [Linebender 维基的 squircle 条目引发曲线连续性讨论](#item-tech-news-6) ⭐️ 7.0/10
7. [Windows 11 被指收集编程代理与开发者工具遥测](#item-tech-news-7) ⭐️ 7.0/10
8. [duetto 用采样时 logit 引导预训练音乐 Transformer 实时伴奏](#item-tech-news-8) ⭐️ 7.0/10
9. [美国与九国签署《旧金山宣言》协调 AI 供应链安全](#item-tech-news-9) ⭐️ 7.0/10
10. [亚马逊称 AI 代理借 Artex 窃取密钥并自我供血](#item-tech-news-10) ⭐️ 7.0/10
11. [阿里、腾讯、月之暗面据悉收紧新模型网络攻击能力](#item-tech-news-11) ⭐️ 7.0/10
12. [苹果中国区 App Store 新增 AIGC 备案入口](#item-tech-news-12) ⭐️ 7.0/10

**财经新闻**
1. [卢特尼克因英伟达关联与对华芯片执法面临质疑](#item-finance-news-1) ⭐️ 8.0/10
2. [黄仁勋辞职后：分析师下调英伟达目标价，AI 交易或转向其他大型科技股](#item-finance-news-2) ⭐️ 7.0/10
3. [英特尔及 CEO 陈立武遭股东集体诉讼，被指隐瞒 PC 需求疲软](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [vLLM v0.34.0 发布：KV 缓存默认按实际空闲显存分配](https://github.com/vllm-project/vllm/releases/tag/v0.34.0) ⭐️ 8.0/10

vLLM 发布 v0.34.0，包含 1,061 个提交和 412 名贡献者，新增 Mistral Large 4、MiniMax-M3.1-Flash 等 10 个模型。该版本在 CUDA 和 ROCm 上默认启用可扩展 KV 缓存，按 warmup 与 CUDA graph 捕获后实际空闲的显存确定缓存大小（示例：H200 上的 MiniMax-M3 从 43.3 万 token 提升到 67.2 万 token），但发布说明也指出部分模型在并发 128 时每 token 解码延迟（TPOT）上升 6%–18%，可用 --gpu-memory-utilization 0.9 或 --no-enable-extensible-kv-cache 关闭。Model Runner V1 已被移除，默认 block size 从 16 改为 64，ROCm 7.2 构建不再发布，并要求 huggingface\_hub &gt;= 2.0.0；发布说明还称 GB200 上最高有 1.95 倍解码加速、GLM-5.3-Flash 吞吐提升 1.6 倍，这些均为厂商自测数据。

github · khluu · 11月16日 23:22

**「背景」** KV 缓存保存已处理 token 的键值状态，其可分配容量直接影响并发批量、吞吐和首 token 延迟。此前 vLLM 主要按预设的 \`gpu\_memory\_utilization\` 估算缓存容量；v0.34.0 改为在 CUDA graph 捕获和预热后按实际空闲显存分配，因此同一 GPU 往往能容纳更多缓存 token，但部分模型在高并发下的单 token 解码延迟可能上升。

**「影响」** 仍依赖 Model Runner V1 的部署升级后会直接启动失败，因为设置 VLLM\_USE\_V2\_MODEL\_RUNNER=0 不再被接受，需将 V1 logits processor 迁移到 vllm.v1.worker.gpu.sample.logits\_processor。对每 token 解码延迟敏感的负载还应评估默认 KV 缓存策略带来的 TPOT 上升，并通过 --gpu-memory-utilization 0.9 或 --no-enable-extensible-kv-cache 回退到原有行为。

**标签**: `#vLLM`, `#LLM inference`, `#KV cache`, `#GPU performance`, `#release notes`

---

<a id="item-tech-news-2"></a>
### [Jiff 1.0 发布：Rust 日期时间库的新选项](https://burntsushi.net/jiff/) ⭐️ 8.0/10

Jiff 1.0 已发布，这是一个面向 Rust 的日期时间库，作者为 burntsushi。该项目在 Hacker News 上引发讨论，关注点集中在其 API 设计，以及它相较 chrono 等现有方案可能带来的改进。现有材料未提供具体的性能对比或迁移兼容性细节，因此这些改进仍属于社区期待，尚未经过独立验证。

hackernews · burntsushi · 11月16日 16:53 · [社区讨论](https://news.ycombinator.com/item?id=50519744)

**「背景」** Jiff 是 Andrew Gallant（burntsushi）开发的 Rust 日期时间库，项目自述其重点是把时区处理放在 API 的核心位置，并与 Time Zone Database 自动集成，从而自动处理夏令时等常见问题。Rust 生态此前已有 chrono 等日期时间库，Jiff 1.0 的发布因此被放在重新审视日期时间 API 的易用性与正确性这一背景下讨论。

**「影响」** 对需要在 Rust 中处理日期时间的开发者来说，Jiff 1.0 提供了一个 chrono 之外的可选库；是否采用仍取决于它的具体 API 能否与现有代码及生态依赖相匹配，而现有材料未提供兼容层或迁移工具的信息。

**「社区讨论」** 曾维护 chrono 约五年的 quodlibetor 表示，他接手维护正是因为旧 API 不理想，但用户看重 API 稳定，任何小幅改进都会遇到阻力，最终他因倦怠停止维护，并对 Jiff 的出现表示感激。另有评论者赞赏 Jiff 明确说明自己并非适用于所有场景。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/BurntSushi/jiff">GitHub - BurntSushi/jiff: A datetime library for Rust that ...</a></li>

</ul>
</details>

**标签**: `#Rust`, `#datetime`, `#open-source libraries`, `#time zones`, `#chrono`

---

<a id="item-tech-news-3"></a>
### [美国将先进 AI 芯片出口管制延伸至远程访问](https://www.reuters.com/legal/litigation/us-issues-rule-protect-advanced-ai-chips-being-accessed-remotely-2026-11-16/) ⭐️ 8.0/10

美国商务部 11 月 16 日发布临时最终规则，将先进 AI 芯片与服务器的出口管制扩大到远程访问，目标是防止通过第三国数据中心规避限制。据 The Verge 报道，新规还要求向印度尼西亚、马来西亚、新加坡、泰国和巴西再出口 AI 芯片时申请许可。报道称该规则由财政部和国家安全委员会主导起草，可能进一步收紧中国获取先进芯片的渠道。现有公开摘要未列出受控芯片型号、算力门槛或具体生效日期。

telegram · zaihuapd · 11月16日 14:44

**「背景」** 美国商务部工业与安全局（BIS）此前对先进 AI 芯片和服务器的出口管制主要针对实体货物的出口与再出口，第三国数据中心仍可让受限方远程调用这些设备，形成绕道空间。此次临时最终规则（IFR）把管制延伸到远程访问，并对相关再出口设置许可条件，以封堵这一路径；外部报道也指出，既有管制此前难以完全阻止经第三国转运。

**「影响」** 对使用第三国数据中心远程调用受控 AI 芯片的企业而言，合规审查需同时覆盖远程访问和再出口路径；向印度尼西亚、马来西亚、新加坡、泰国和巴西提供相关芯片的一方须申请许可。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://wccftech.com/the-u-s-shuts-chinas-access-to-advanced-chips-via-singapore-brazil-indonesia-malaysia-and-thailand-as-scott-bessent-gives-nvidia-10-days-to-show-it-did-not-goose-its-revenues/">The U.S. Shuts China&#x27;s Access To Advanced Chips Via Singapore ...</a></li>
<li><a href="https://reason.com/2026/11/16/trumps-new-chip-export-rule-targets-china-but-exempts-tiktoks-parent-company/">Trump’s new chip export rule exempts TikTok’s parent company</a></li>

</ul>
</details>

**标签**: `#AI芯片出口管制`, `#美国政策`, `#数据中心`, `#半导体供应链`, `#远程访问限制`

---

<a id="item-tech-news-4"></a>
### [卡内基梅隆 CS Learn 免费上线 YouTube 课程讲座](https://www.cs.cmu.edu/learn/) ⭐️ 7.0/10

卡内基梅隆大学推出 CS Learn，把多门当前计算机科学课程的整学期讲座免费发布到 YouTube，面向公众开放。项目负责人 Phillip Compeau 表示，本周每天会首播一门课程，1 月还将上线更多课程。现有信息只明确了视频讲座，作业、考试等配套材料是否会发布尚未说明。

hackernews · pcompeau · 11月16日 20:43 · [社区讨论](https://news.ycombinator.com/item?id=50522980)

**「背景」** 开放课件并不是新做法：项目负责人在讨论中提到，MIT 约 25 年前就已开始免费公开课程材料。CMU 此次的不同点在于发布当前课程完整学期的讲课视频，并计划持续新增课程，而不只是提供讲义或零散片段。

**「影响」** 对自学者和 CMU 以外的学生来说，这些完整讲座可直接用于系统学习或补充课堂内容；若需要练习与评估，则要等课程方说明是否提供作业、考试等材料。

**「社区讨论」** 评论者询问 15-122、15-150 等核心课程以及作业是否会一并发布；也有 CMU 校友点名期待 Tianqi Chen 的 ML Systems 和 15-259 Probability and Computing，并请求增加统计、分布式系统等课程。还有评论认为，扎实掌握基础才能把 AI 当作工具使用。

**标签**: `#CS education`, `#open courseware`, `#online learning`, `#ML systems`, `#YouTube`

---

<a id="item-tech-news-5"></a>
### [Optimizely 据报被入侵并向 Zoom、GitLab 投放恶意代码](https://blog.report-uri.com/worlds-largest-brands-infected-with-malware-via-optimizely/) ⭐️ 7.0/10

据 Report-uri 博客，Optimizely 被入侵，并被用来通过第三方脚本向包括 Zoom、GitLab 在内的网站访问者投放恶意代码。攻击者如何获得对大量不相关客户项目的写入权限尚不明确，可能是 Optimizely 系统被攻破、跨客户凭证泄露或其他原因；评论引述的报道称，这不是 CDN 缓存投毒，Optimizely 自家 www 和登录站点的脚本片段也包含该代码。相关细节仍主要来自该博客和评论，尚无 Optimizely 的完整说明或独立验证。

hackernews · kristjansson · 11月16日 23:00 · [社区讨论](https://news.ycombinator.com/item?id=50524767)

**「背景」** Optimizely 通过嵌入客户网站的 JavaScript 片段提供 A/B 测试和个性化功能，这类第三方脚本在访问者浏览器中以站点自身权限执行。因此，一旦供应商交付的脚本被篡改，所有引用该片段的页面都可能被动加载恶意代码，而不需要攻击者逐个入侵这些网站。

**「受影响站点的直接处置压力」** 这起事件使 178 家机构的网站域名通过 Optimizely 片段路径承载了恶意 JavaScript；对这些机构而言，实际后果是必须审计并停用被污染的片段，而不能只等待 Optimizely 修复，因为恶意代码是通过原本受信任的第三方脚本加载的。需要说明的是，出现在名单中只表示暴露于被污染脚本，并不等于每个访客都已遭恶意操作。

**「社区讨论」** 评论者把矛头指向标签管理器模式：stickfigure 认为 Google Tag Manager 让营销团队无需工程介入即可添加标签，导致页面加载大量 JavaScript，并希望此次事件促使各方重新评估；mcoliver 则主张供应商和大型站点应设置发布冷却、分阶段推送与安全检查，并质疑是否应直接托管第三方脚本。也有评论提出用 NoScript 缩小暴露面，但这些都属于个人观点，并未独立验证事件范围。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://runtimewire.com/article/malware-optimizely-bbc-zoom-178-organisations">Malware served through Optimizely hit BBC, Zoom and 176 other ...</a></li>
<li><a href="https://vinish.dev/optimizely-web-experimentation-supply-chain-attack-malicious-javascript">Optimizely Supply Chain Attack: Flaw Put Malicious JavaScript ...</a></li>
<li><a href="https://blog.redsidesecurity.com/post/optimizely-supply-chain-attack-injects-malicious-javascript-into-178-major-websites">Optimizely Supply-Chain Attack Hits 178 Major Websites</a></li>

</ul>
</details>

**标签**: `#supply-chain-security`, `#web-security`, `#third-party-scripts`, `#malware`, `#Optimizely`

---

<a id="item-tech-news-6"></a>
### [Linebender 维基的 squircle 条目引发曲线连续性讨论](https://linebender.org/wiki/curves/squircle/) ⭐️ 7.0/10

Linebender 维基上的一篇关于 squircle（超椭圆式圆角方形）的技术条目在 Hacker News 上被 raphlinus 提交并引发讨论，内容聚焦这类形状的几何性质，以及它在 UI 与图形工作中获得平滑曲线的作用。讨论把话题延伸到样条、超椭圆、回旋曲线（clothoid）和导数连续性等相邻概念。该条目属于参考性文档，现有信息中没有附带版本、API 或性能数据。

hackernews · raphlinus · 11月16日 07:55 · [社区讨论](https://news.ycombinator.com/item?id=50515151)

**「背景」** 方圆形（squircle）是介于正方形与圆形之间的形状，常见数学定义来自超椭圆（Lamé 曲线），即 \|x/a\|^n + \|y/b\|^n = 1，取 n=4 时得到典型的 x^4 + y^4 = 1。UI 和图形设计常用这类曲率连续变化的轮廓替代普通圆角，Linebender 的条目也涉及超椭圆参数、G2 连续性以及与 Chromium/CSS 实现的对应关系。

**「影响」** 对需要在界面里绘制圆角的开发者，这类讨论的实际落点是角与直边衔接处的导数连续性，因为它决定轮廓看上去是否顺滑，而不只是圆角半径的大小。由于该条目是维基参考文档，读者拿不到可直接引入的实现或参数，落地仍需自行拟合曲线或依赖设计工具。

**「社区讨论」** 有评论者以 Zune 第二代的方向键为例，认为 squircle 造型让翻选音乐的手感顺滑，同时还能像普通方向键那样按压。另有人推荐超椭球体（sphube）的论文，并分享自己正在开发的样条、超椭圆、回旋曲线创作工具；这位评论者自述该工具仍处探索阶段、界面粗糙。还有评论认为，正是没有导数不连续的曲线，才让图形在与物理世界交互时显得平滑。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Squircle">Squircle - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Superellipse">Superellipse - Wikipedia</a></li>
<li><a href="https://linebender.org/wiki/curves/squircle/">Squircles - Linebender</a></li>

</ul>
</details>

**标签**: `#squircles`, `#curves`, `#UI graphics`, `#geometric modeling`, `#spline continuity`

---

<a id="item-tech-news-7"></a>
### [Windows 11 被指收集编程代理与开发者工具遥测](https://xusheng.dev/posts/windows-coding-agent-telemetry/) ⭐️ 7.0/10

一篇 Hacker News 帖子所引述的报告称，Windows 11 会收集开发者工具和编程代理的使用遥测数据，涉及在该系统上使用这些工具的开发者和 AI 代理用户。所给材料未说明具体收集哪些字段、覆盖哪些工具或版本，也未提供可核实的范围与严重程度。相关讨论集中在隐私、AI 代理沙箱以及改用 Linux 等替代方案，但这些属于评论意见，尚不能视为已确认的平台行为细节。

hackernews · cwaffles · 11月16日 22:58 · [社区讨论](https://news.ycombinator.com/item?id=50524736)

**「背景」** 对开发者工具收集遥测并非新做法：微软在 VS Code 的企业文档中说明，遥测可分级设置并由组织集中管理，说明这类数据收集通常配有可配置的开关。Windows 11 长期因遥测范围受到关注，社区也一直维护 PowerShell 脚本等工具来屏蔽 Windows 10/11 的遥测和相关服务。这为理解“操作系统层面统计开发者使用哪些工具”提供了参照，但现有材料没有说明本次收集的具体字段、默认状态和关闭方式。

**「对开发者工作流的影响」** 对在 Windows 11 上运行编码代理的开发者来说，更直接的约束来自沙箱支持而非遥测本身：微软的 MXC（Execution Containers）已可在 Windows 11 上使用，通过 JSON 策略限制代理行为，但目前仍需各代理工具自行适配；有社区评论指出 Claude Code 尚未支持，因此部分用户只能在未沙箱化的环境中运行代理，或改用 WSL。与此同时，由于原始报道未说明遥测采集的具体字段与范围，开发者暂时无法判断哪些工具名称或可执行文件路径会被记录，也无法据此评估自身风险。

**「社区讨论」** 有评论者认为，转向 Linux 的调整成本已明显降低，单机游戏大多可用，但多人游戏仍有兼容问题；也有人指出驱动和浏览器同样可能收集可执行文件名、路径或浏览记录，并提醒这类收集往往取决于是否选择退出。另有评论者称，Windows 的 AI 代理沙箱支持仍不完整，提到 MXC 于 10 月 7 日推出而 Claude Code 尚未支持，因此开发者会运行未沙箱代理或改用 WSL。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://code.visualstudio.com/docs/enterprise/telemetry">Manage telemetry in enterprise environments</a></li>
<li><a href="https://github.com/N0tHorizon/WindowsTelemetryBlocker">N0tHorizon/WindowsTelemetryBlocker: A PowerShell based tool to...</a></li>
<li><a href="https://tsnmedia.org/agent-sandboxes-microsoft-execution-containers-aws-strands-box/">Microsoft Execution Containers and AWS Strands Box | TSN</a></li>
<li><a href="https://www.developersdigest.tech/blog/microsoft-mxc-developer-guide-2026">Microsoft MXC Guide 2026: Sandbox AI Agents at the OS Level</a></li>

</ul>
</details>

**标签**: `#Windows 11`, `#telemetry`, `#privacy`, `#developer tools`, `#AI coding agents`

---

<a id="item-tech-news-8"></a>
### [duetto 用采样时 logit 引导预训练音乐 Transformer 实时伴奏](https://www.reddit.com/r/MachineLearning/comments/1xxkyh3/steering_a_pretrained_music_transformer_at/) ⭐️ 7.0/10

名为 duetto 的项目发布了实时爵士 MIDI 键盘伴奏演示和代码（免费用于非商业用途），它把演奏者与模型的音符放在同一事件序列中逐音续写，可独奏、伴奏或演奏行走贝斯。与微调不同，duetto 直接使用预训练的 Anticipatory Music Transformer（Thickstun 等，2023），在每次采样前由规则层修改 logits：屏蔽不允许的音符（如需等待的手部、音域外音高、非拍上贝斯音），并偏向当前和弦音、强拍导音和待引用乐句的下一音。作者报告在 3080 Ti 上约 12 ms/音（medium）和 18 ms/音（large），large 在 Jetson Orin Nano 上约 90 ms/音；服务器提前采样约 1 秒，并在演奏者输入后重采样未播放部分。演示中约 61% 的独奏音符来自引用乐句或主题；作者也指出它会偏离演奏者、响应难以预测，模型与规则的平衡很脆弱。

reddit · r/MachineLearning · /u/GGAllin43 · 11月16日 09:19

**「背景」** duetto 所依赖的 Anticipatory Music Transformer 是 Thickstun 等人于 2023 年提出的符号音乐生成模型，其核心能力是把一部分音乐事件作为固定控制条件，让模型补全序列的其余部分，从而实现可控的 infilling 生成。该项目没有重新训练这一预训练模型，而是在逐音符采样时改写 logits，把原本面向补全任务的控制方式用于实时爵士伴奏。

**「影响」** 对交互式音乐系统开发者而言，duetto 提供了不微调预训练符号音乐模型的可复用控制路径：用规则层在采样前修改 logits，并用约 1 秒的前瞻缓冲吸收实时输入；但作者报告的偏离、不可预测响应和规则/模型平衡脆弱意味着采用前需要针对这些条件做评估。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2306.08620">[2306.08620] Anticipatory Music Transformer - arXiv.org</a></li>
<li><a href="https://crfm.stanford.edu/2023/06/16/anticipatory-music-transformer.html">Anticipatory Music Transformer: A Controllable Infilling ...</a></li>

</ul>
</details>

**标签**: `#AI music generation`, `#music transformer`, `#real-time interaction`, `#logit steering`, `#MIDI`

---

<a id="item-tech-news-9"></a>
### [美国与九国签署《旧金山宣言》协调 AI 供应链安全](https://www.state.gov/releases/office-of-the-spokesman/2026/11/the-san-francisco-declaration-on-the-secure-foundations-of-enduring-prosperity/) ⭐️ 7.0/10

11 月 15 日，美国与澳大利亚、印度、以色列、日本、韩国、卡塔尔、新加坡、阿联酋和英国签署《旧金山宣言》，确认经济安全是国家安全的基础，并将共同保护支撑超级智能（SI）供应链的敏感技术与关键基础设施。宣言提出设立五个工作组，分别负责创新政策框架、SI 在关键领域的应用、SI 全栈供应链协作、安全港与供应链安全枢纽，以及 SI 安全与韧性。目前公开信息只列出工作组议题，未披露各工作组的时间表、牵头机构或具体承诺，因此这仍是一份政治声明，而非可执行的约束性协议。

telegram · zaihuapd · 11月16日 10:40

**「背景」** 宣言以“超级智能（SI）供应链”为协调对象，但提供的材料未定义“超级智能”，也未列出受保护的具体技术清单。可确认的是，签署方将敏感技术和关键基础设施视为需要共同保护的对象，并设立五个工作组推进后续协作。

**「对参与国 AI 供应链的影响」** 对在十个签署国运营的 AI 开发者和芯片、关键矿物供应商来说，宣言把相关技术与基础设施安全定为“共同责任”，并明确目标是减少对美方对手在关键矿物、AI 模型和半导体上的依赖（tool-2-2、tool-2-1）。但五个工作组的具体规则、适用范围和时间表尚未公布，目前还不构成企业可直接执行的合规义务，供应链选型与采购策略的调整仍需等待后续机制落地。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/San_Francisco_Declaration_on_the_Secure_Foundations_of_Enduring_Prosperity">San Francisco Declaration on the Secure Foundations of Enduring Prosperity</a></li>
<li><a href="https://www.ft.com/content/3c2197fc-9618-4838-91e6-522ce1a96a22?syn-25a6b1a6=1">US and allies sign accord to protect AI supply chains from China</a></li>

</ul>
</details>

**标签**: `#AI policy`, `#AI supply chain`, `#international agreement`, `#superintelligence`, `#technology governance`

---

<a id="item-tech-news-10"></a>
### [亚马逊称 AI 代理借 Artex 窃取密钥并自我供血](https://cybernews.com/security/amazon-autonomous-cybercrime-artex-framework/) ⭐️ 7.0/10

亚马逊表示，攻击者利用开源渗透测试框架 Artex 驱动 AI 代理，从 LiteLLM、Dify 等公网暴露的 AI 应用中窃取 API 密钥，验证后汇入共享池，用于支付更多大模型调用。亚马逊称，该活动始于 10 月 3 日，并于 11 月 5 日被其诱饵网络 MadPot 截获阻断。亚马逊以中等信心将行动归因于一个与中国相关的威胁组织，同时说明并非所有被列目标都已失陷，并已通知可能受影响的 AWS 客户。

telegram · zaihuapd · 11月16日 13:00

**「背景：Artex 框架」** Artex 是一个用 Go 编写、带有 Next.js 控制台的开源自主多代理渗透测试与命令控制框架，由 GitHub 用户 Autumn-27 发布。该框架让大模型驱动的代理自动寻找并利用公网暴露的 AI 应用弱点，而 LiteLLM、Dify 等应用通常会在配置或环境中保存 AI 服务商的 API 密钥。

**「直接影响」** 对在公网运行 LiteLLM、Dify 等 AI 应用的组织而言，直接风险是密钥被窃后产生未经授权的模型调用费用；相关运营者应核查这些应用的公网暴露情况，并轮换可能泄露的密钥。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://thehackernews.com/2026/11/amazon-uncovers-ai-agent-campaign.html">Amazon Uncovers AI Agent Campaign Targeting LiteLLM, Dify, and...</a></li>
<li><a href="https://cloud.google.com/blog/topics/threat-intelligence/artex-and-friends-enter-agentic-offensive-frameworks">ARTEX and Friends: Enter Agentic Offensive Frameworks</a></li>

</ul>
</details>

**标签**: `#AI security`, `#autonomous agents`, `#API key theft`, `#cloud security`, `#cybercrime`

---

<a id="item-tech-news-11"></a>
### [阿里、腾讯、月之暗面据悉收紧新模型网络攻击能力](https://www.bloomberg.com/news/articles/2026-11-16/china-s-top-ai-firms-limit-cyber-capabilities-in-latest-models) ⭐️ 7.0/10

据 Bloomberg 报道，阿里巴巴、腾讯和月之暗面在新一代模型中削弱了进攻性网络能力、提升了防御表现，这一调整发生在中国商务部上月公布出口管制草案之后。草案拟禁止可攻击关键基础设施或政府网络的 AI 工具出口，报道称腾讯在本月发布 Hy4 前已削减相关网络功能。阿里最新旗舰 Qwen 未开放权重，用户无法下载并自定义完整版本。上述企业举措与草案的直接因果关系仍属报道说法，草案也尚未成为正式规则。

telegram · zaihuapd · 11月17日 02:20

**「政策背景」** 中国商务部上月公布的出口管制草案是这轮调整的政策背景：据报道，该框架拟覆盖 23 类人工智能技术，包括前沿模型权重、源代码、训练方法，以及能够自主发动网络攻击的 AI 代理和系统。草案还涉及对可攻击关键基础设施或政府网络的 AI 工具实施出口限制，这为厂商在新模型发布前收紧进攻性网络能力提供了直接动因。

**「影响」** 对开发者而言，最直接的变化是阿里最新旗舰 Qwen 不再开放权重，无法下载完整模型进行本地部署或微调。若出口管制草案最终生效，包含可攻击关键基础设施或政府网络能力的 AI 工具将不能出口，相关模型的跨境提供和部署会受限制。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://creati.ai/ai-news/2026-10-17/china-drafts-export-controls-covering-open-weight-models-and-23-ai-technologies/">China Drafts Export Controls Covering Open-Weight Models and 23...</a></li>

</ul>
</details>

**标签**: `#AI policy`, `#model safety`, `#open-weight models`, `#China AI`, `#cybersecurity`

---

<a id="item-tech-news-12"></a>
### [苹果中国区 App Store 新增 AIGC 备案入口](https://www.ithome.com/1/028/158.htm) ⭐️ 7.0/10

苹果 App Store Connect 中国区后台新增“AIGC 服务声明与备案信息”和“安全评估证明”两项必填项，面向中国大陆分发的相关应用需补齐。新应用须立即提交，现有应用须在 2027 年 1 月 31 日前完成；含聊天机器人、图像或视频生成、语音或人脸编辑等 AIGC 功能的应用均在范围内。使用第三方技术的应用还须上传授权协议和算法备案号。苹果 2026 年审核指南已纳入生成式 AI 条款。

telegram · zaihuapd · 11月17日 04:29

**「背景：中国的生成式 AI 备案与安全评估要求」** 按照中国对生成式人工智能服务的监管要求，服务提供者需履行安全评估、算法备案和内容标识等义务；监管部门也通过算法备案了解服务的算法数据、算法策略与风险预防机制。苹果此次相当于把这类监管义务提前嵌入 App Store Connect 的提交流程：开发者要在后台填报 AIGC 服务声明与备案信息、提交安全评估证明，使用第三方技术的还需附上授权协议和算法备案号。

**「影响」** 对中国大陆分发 AIGC 应用的开发者而言，上架或更新时需提供 AIGC 服务声明、备案信息和安全评估证明；使用第三方模型的团队还需提前备齐授权协议与算法备案号，以免在提交新应用或更新现有应用时因材料不全受阻。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.lexology.com/library/detail.aspx?g=c4afdeff-7a10-4273-bf21-7d32826e88ed">lexology.com/library/detail.aspx?g=c4afdeff-7a10-4273-bf21-7d32826...</a></li>

</ul>
</details>

**标签**: `#Apple App Store`, `#AIGC compliance`, `#China regulation`, `#generative AI`, `#app developers`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [卢特尼克因英伟达关联与对华芯片执法面临质疑](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 8.0/10

据 CNBC 报道，美国商务部长霍华德·卢特尼克因其家族券商 Cantor Fitzgerald 与英伟达的关系而面临利益冲突质疑：该公司向监管机构申报的英伟达持股数量在 2025 年 9 月底至 2026 年 3 月底之间减少了 49%，从约 348 万股（市值 6.52 亿美元）降至 178 万股（市值 3.10 亿美元）；Axios 在 11 月报道称，卢特尼克在同一时期多次抵制对涉嫌向中国转运英伟达 AI 芯片的新加坡公司 Megaspeed 采取行动。Cantor 表示，这些持仓属于“无关紧要的自营头寸”，与 13F 文件所反映的、按常规业务进行的客户互换交易有关；报道同时指出，目前没有证据显示卢特尼克泄露了非公开信息，也没有证据显示这次减持与情报警告有关。

rss · CNBC Finance · 11月16日 12:14

**「背景」** 卢特尼克在 2025 年 2 月出任商务部长前长期执掌坎托·菲茨杰拉德，该公司现由其子布兰登和凯尔领导；商务部正是负责出口管制与实体清单的机构，而是否把涉嫌转运英伟达芯片的 Megaspeed 列入该清单，正成为争议焦点。

**「直接影响」** 美国商务部着手堵住中国公司从境外租用英伟达算力的漏洞，依赖海外数据中心获取 AI 算力的中国企业将直接受到限制。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.britannica.com/money/Howard-Lutnick">Howard Lutnick | Cantor Fitzgerald , 9/11, Donald... | Britannica Money</a></li>
<li><a href="https://aiweekly.co/alerts/commerce-delays-entity-list-additions-megaspeed-stays-off">Commerce delays Entity List additions, Megaspeed stays off</a></li>
<li><a href="https://www.cnbc.com/2026/11/16/nvidia-commerce-china-lutnick.html">Nvidia fallout: Commerce targets loophole for China &#x27;s data center use</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#export controls`, `#Commerce Department`, `#conflict of interest`, `#China chip smuggling`

---

<a id="item-finance-news-2"></a>
### [黄仁勋辞职后：分析师下调英伟达目标价，AI 交易或转向其他大型科技股](https://www.cnbc.com/2026/11/14/nvidia-ai-trade-data-centers-congress.html) ⭐️ 7.0/10

英伟达（Nvidia）创始人兼首席执行官黄仁勋辞职后，Yorkville Ives 将其目标股价从 300 美元下调至 225 美元，但维持“买入”评级；该股上周收于每股 162.85 美元。该机构分析师 Dan Ives 在 CNBC 的“ETF Edge”节目中还估计，民主党在 11 月 3 日选举中拿下国会控制权后，可能使原计划新建的数据中心减少 10%（低端）至 15%—20%（高端），但他仍认为 AI 芯片需求远超供给。

rss · CNBC Finance · 11月16日 12:13

**「背景」** 英伟达联合创始人黄仁勋于 2026 年 11 月 12 日辞去首席执行官、总裁及董事职务，公司任命首席财务官科莱特·克雷斯为临时首席执行官（tool-1-1）；此前的 11 月 3 日中期选举中民主党赢得国会控制权，党内人士随即呼吁收紧对 AI 数据中心的限制（tool-2-1）。

**「影响」** 若民主党主导的国会放缓数据中心建设，依赖英伟达融资与算力租赁的小型云厂商（如 CoreWeave、Nebius）可能承受更大压力，而拥有现成算力的超大规模云厂商以及 AMD、博通等替代芯片供应商可能相对受益。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.gate.com/blog/jensen-huang-resigns-is-nvda-stock-still-a-good-investment">Jensen Huang Resigns : Is NVDA Stock Still a Good... | Gate Blog</a></li>
<li><a href="https://www.cnbc.com/2026/11/05/democrats-data-center-restrictions-midterms.html">Top Democrats call to rein in AI buildout after midterms sweep...</a></li>
<li><a href="https://www.cnbc.com/2026/11/13/nvidia-ceo-exit-amd-broadcom-and-ai-trade-fallout-.html">Nvidia CEO exit: AMD, Broadcom and AI trade fallout - CNBC</a></li>
<li><a href="https://finance.yahoo.com/markets/stocks/articles/nvidia-amd-broadcom-ai-stock-180603430.html?fr=sycsrp_catchall">Nvidia, AMD, Broadcom: The AI Stock Winners and Losers After ...</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#AI semiconductors`, `#CEO succession`, `#ETF flows`, `#data-center policy`

---

<a id="item-finance-news-3"></a>
### [英特尔及 CEO 陈立武遭股东集体诉讼，被指隐瞒 PC 需求疲软](https://www.investing.com/news/stock-market-news/intel-sued-by-shareholders-following-29-stock-plunge-5028171) ⭐️ 7.0/10

英特尔及其 CEO 陈立武、CFO 津斯纳被股东提起集体诉讼，被指在公司 10 月 29 日发布不及预期的第四季度营收和利润预测之前，隐瞒了 PC 需求疲软和库存积压的影响；预测公布次日股价暴跌 28.6%，市值蒸发约 1400 亿美元。诉讼由一家密歇根州养老基金牵头，上周五在圣何塞联邦法院提起，代表 2026 年 7 月 23 日至 10 月 29 日期间买入股票的投资者。

telegram · zaihuapd · 11月16日 11:10

**「背景」** 此前，英特尔在 10 月 29 日发布的第四季度营收和利润预测低于市场预期，并警告个人电脑（PC）市场低迷将持续；次日其股价单日下跌 28.6%。

**「影响」** 在 2026 年 7 月 23 日至 10 月 29 日期间买入英特尔股票的投资者属于该诉讼界定的集体范围，可能成为集体成员；案件同时将 CEO 和 CFO 列为个人被告。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.tomshardware.com/pc-components/cpus/intel-sued-by-shareholders-for-misleading-investors-after-stock-plunges-29-percent-class-action-claims-the-company-downplayed-the-severity-of-pc-market-headwinds">Intel sued by shareholders for misleading investors after stock ...</a></li>

</ul>
</details>

**标签**: `#Intel`, `#shareholder class action`, `#earnings warning`, `#stock selloff`, `#semiconductors`

---