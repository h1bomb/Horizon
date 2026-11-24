---
layout: default
title: "Horizon Summary: 2026-11-24 (ZH)"
date: 2026-11-24
lang: zh
---

> 从 38 条内容中筛选出 13 条重要资讯。

---

**科技新闻**
1. [Ladybird 发布首个 Alpha，macOS 和 Linux 可直接安装](#item-tech-news-1) ⭐️ 8.0/10
2. [GLM-5.4 发布：Z.ai 首个循环 Transformer 编程模型](#item-tech-news-2) ⭐️ 8.0/10
3. [Codex2api 疑遭供应链投毒，3.1.11 移除鉴权](#item-tech-news-3) ⭐️ 8.0/10
4. [英伟达董事会重新任命黄仁勋为 CEO](#item-tech-news-4) ⭐️ 7.0/10
5. [NariQ 发布 Qwen3.8-27B 低比特 GGUF 量化](#item-tech-news-5) ⭐️ 7.0/10
6. [黎曼猜想 Lean 证明被指空转，作者承认代码低劣](#item-tech-news-6) ⭐️ 7.0/10
7. [黄循财：新加坡不会成为规避美国芯片管制的通道](#item-tech-news-7) ⭐️ 7.0/10
8. [Anthropic 称 Claude 发现 VP≠VNP，Lean 4 证明待审](#item-tech-news-8) ⭐️ 7.0/10

**科技博客**
1. [vLLM 以插件形式实现 ERNIE 5.5 Flash 的 Day-0 支持](#item-tech-blog-1) ⭐️ 7.0/10

**财经新闻**
1. [威廉姆斯：通胀回落到 2%仍需更多行动，未来或进一步加息](#item-finance-news-1) ⭐️ 8.0/10
2. [AI 抛售令 DeepSeek 与月之暗面上市计划承压](#item-finance-news-2) ⭐️ 8.0/10
3. [上海地铁票价 21 年来首次调整，起步价 3 元](#item-finance-news-3) ⭐️ 7.0/10
4. [马斯克据称承认 SpaceX AI 落后，转而出租算力给 Anthropic 和 Google](#item-finance-news-4) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Ladybird 发布首个 Alpha，macOS 和 Linux 可直接安装](https://ladybird.org/posts/alpha/) ⭐️ 8.0/10

Ladybird 发布了首个 Alpha 版，macOS 和 Linux 用户现在可以直接下载安装，无需自行编译。该项目自行实现 HTML 解析、CSS 引擎、布局、JavaScript 和 WebAssembly，仅复用 HarfBuzz、Skia、ffmpeg、SQLite 等外部组件。官方提醒 Alpha 仍会出现网站不兼容和崩溃，并支持从浏览器内报告故障站点；实测中 ffmpeg/WASM 视频压缩和 Pyodide 可运行，但依赖 service worker 的 Datasette Lite 因缺少 navigator.serviceWorker.startMessages 而失败。

hackernews · janvdberg · 11月23日 16:13 · [社区讨论](https://news.ycombinator.com/item?id=50614249)

**「背景」** Ladybird 源自更早的 SerenityOS 项目，目标是从零实现 HTML 解析、CSS、布局、JavaScript 和 WebAssembly 等浏览器核心，只把文本整形、2D 图形、视频解码和存储交给 HarfBuzz、Skia、ffmpeg、SQLite 等外部库。2026 年 2 月，项目宣布借助 Claude Code 和 Codex 把部分 LibJS 从 C++ 移植为约 2.5 万行 Rust；10 月的月度更新又称，样式与布局已移到独立线程，并加入新的 JavaScript JIT。Alpha 通常指功能不完整、可能崩溃的早期测试阶段。

**「实际影响」** 希望试用独立浏览器引擎的用户现在可以在 macOS 或 Linux 上直接安装，但若 Web 应用依赖 service worker，当前版本可能因 API 缺失而无法运行；开发者需要等待或推动相关接口补齐，普通用户则更适合把它用于兼容性测试并提交崩溃与坏站报告。

**「社区讨论」** 有评论者报告实际渲染超出预期：freakynit 称其测试的网站均正确显示，仅滚动略显卡顿；alentred 称 Proxmox/NoVNC 正常，甚至比 Firefox 更流畅。kvuj 认为采用 Skia、SQLite 等成熟组件帮助很大，但少了早期自研的极客气息；drnick1 则呼吁后续认真处理指纹识别问题并限制网站权限。

**标签**: `#Ladybird`, `#browser engine`, `#open source`, `#alpha release`, `#web compatibility`

---

<a id="item-tech-news-2"></a>
### [GLM-5.4 发布：Z.ai 首个循环 Transformer 编程模型](https://z.ai/blog/glm-5.4) ⭐️ 8.0/10

Z.ai 发布 GLM-5.4，这是其首个采用循环 Transformer（Loop Transformer）架构的模型，定位为通用编程。按 Z.ai 的描述，循环 Transformer 让一组共享权重的层在一次前向传播中多次运行、反复细化隐藏状态，从而在不增加参数量的情况下加深网络。GLM-5.4 目前未以开放权重形式提供，也无法通过常规 API 套餐或 OpenRouter 使用；用户需订阅 Z.ai 的 Coding Plan，其 API key 可访问该模型，端点与常规 API 一样兼容 OpenAI Responses API（https://api.z.ai/api/v1）。Simon Willison 的初步试用显示，其“骑自行车的鹈鹕”SVG 质量与 GLM-5.3 相近，但自行车车架连接有误；这些是个人试用观察，并非独立基准结果。

hackernews · foohis · 11月23日 10:06 · [社区讨论](https://news.ycombinator.com/item?id=50609685)

**「背景」** 标准 Transformer 的每一层在一次前向传播中只运行一次；循环 Transformer 则让一组共享权重的层重复运行多轮，在不增加参数量的情况下增加有效深度，并反复细化隐藏状态。Z.ai 称 GLM-5.4 是其首个采用该架构的模型；此前一周，Thinking Machines Lab 于 11 月 20 日发布的 Inkling 2 Mini 也采用了循环结构，对每个 token 将中间层运行三次。

**「接入与配额影响」** 对开发者而言，当前接入 GLM-5.4 的实际门槛在订阅层级而非接口协议：它尚未通过 OpenRouter 或常规 Z.ai API 套餐提供，需要订阅 Coding Plan，而该套餐的密钥仍可调用同一套 OpenAI 兼容接口。有早期测试者称，部分任务耗时可达 30–60 分钟以上并快速消耗配额，因此对延迟或配额敏感的工作流应先评估成本与等待时间。

**「社区讨论」** Hacker News 评论中，有人称赞 Zhipu 披露的技术细节比西方公司的封闭做法更透明，并认为循环 Transformer 是明显方向但仍有问题待解决；也有用户抱怨部分中国模型的“马拉松式思考”会在简单任务上反复自我怀疑，完成时间明显高于前沿模型。另有评论从内存带宽瓶颈解释循环 Transformer 的潜在收益。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=0dOluS-T4yc">GLM - 5 . 4 is here! looped transformer ?! no benchmarks ?!</a></li>
<li><a href="https://docs.z.ai/guides/llm/glm-5.4">GLM - 5 . 4 - Overview - Z.AI DEVELOPER DOCUMENT</a></li>

</ul>
</details>

**标签**: `#LLMs`, `#loop transformers`, `#GLM-5.4`, `#coding models`, `#model architecture`

---

<a id="item-tech-news-3"></a>
### [Codex2api 疑遭供应链投毒，3.1.11 移除鉴权](https://github.com/WormW/codex2api-incident-2026-11) ⭐️ 8.0/10

据事件复盘，Codex2api 作者账号疑似被黑，攻击者绕过 main 分支推送 tag，使 Release 构建出带后门的版本。被点名的 v3.1.11 移除了鉴权，可被用于无密码远程执行命令；另有 workflow 将仓库的 16 个 GitHub Actions secrets 外传，波及同一账号下至少 21 个仓库。使用 3.1.10–3.1.12 的用户应立即停用并退回 3.1.9，同时轮换 GitHub token、SSH key、数据库和 DeepSeek 等相关密钥。

telegram · zaihuapd · 11月23日 11:21

**「背景机制」** 在 Codex2api 的发布流程中，Release 构建由新建 tag 触发；一旦账号被盗，攻击者就可以绕过 main 分支的审查，直接推送 tag 让 CI 构建并发布带后门的版本。GitHub Actions 工作流还能接触仓库的 secrets，因此工作流被篡改后，其中的令牌和密钥就可能被读取并外传。

**「影响与处置」** 安装或更新过 3.1.10–3.1.12 的用户应立即停用并回退到 3.1.9，因为这些版本存在后门，其中 v3.1.11 移除了鉴权，可被用于无密码远程执行命令。相关 GitHub token、SSH key、数据库及 DeepSeek 等密钥也应全部视为已泄露并尽快轮换；涉事 workflow 曾外传 16 个 Actions secrets，波及同账号下至少 21 个仓库。

**标签**: `#supply-chain security`, `#GitHub Actions`, `#security incident`, `#secrets exfiltration`, `#remote code execution`

---

<a id="item-tech-news-4"></a>
### [英伟达董事会重新任命黄仁勋为 CEO](https://www.cnbc.com/2026/11/23/nvidia-jensen-huang-ceo.html) ⭐️ 7.0/10

Hacker News 上的链接帖称，英伟达董事会重新任命黄仁勋为总裁、CEO 兼董事会成员，帖子同时链接了英伟达新闻稿和 CNBC 报道。评论中引用的新闻稿措辞称，董事会在作出决定前听取了美国联邦政府高层意见，并据此认为黄仁勋复职不构成国家安全风险。所给材料只有链接和社区评论，未包含新闻稿全文或独立核实，因此复职的具体背景、董事会先前是否罢免黄仁勋以及政府介入程度仍不明确。

hackernews · jaz · 11月23日 14:00 · [社区讨论](https://news.ycombinator.com/item?id=50611576)

**「背景」** 这次复职是一次快速反转：据 CNBC 报道，Nvidia 董事会在 11 月 23 日前几天刚拒绝了黄仁勋提出的回归请求。Nvidia 随后于 11 月 23 日发布公告，宣布恢复其总裁、CEO 和董事职务。

**「社区讨论」** 评论者最关注的是政府意见在董事会决定中的分量：有人称这句话是声明中“最关键”的部分，也有人批评美国在要求盟友限制对华芯片出口的同时为英伟达提供政治庇护。另有评论者以 OpenAI 2023 年事件作类比，认为公司的名义治理结构未必等于实际治理结构。

<details><summary>参考链接</summary>
<ul>
<li>NVIDIA Board Reinstates Jensen Huang as President, CEO and ...</li>
<li>Nvidia board reinstates Jensen Huang as CEO just days after rejecting his ...</li>

</ul>
</details>

**标签**: `#Nvidia`, `#tech industry`, `#corporate governance`, `#US politics`, `#semiconductors`

---

<a id="item-tech-news-5"></a>
### [NariQ 发布 Qwen3.8-27B 低比特 GGUF 量化](https://huggingface.co/nari-labs/Qwen3.8-27B-NariQ-GGUF) ⭐️ 7.0/10

NariQ 发布了 Qwen3.8-27B 的 3 位及以下 GGUF 量化版本，面向本地推理用户，并宣称可在 10 GB 文件中保留接近 BF16 的质量，覆盖智能体任务、数学、多语言推理和图像理解。项目方自报的对比中，3-bit 在 DeepSWE、Terminal-Bench 2.1 和 AIME 25+26 上分别为 41.0、63.8 和 98.3，BF16 为 39.8、62.6 和 97.7；2.5-bit 大体接近，而 2-bit 明显下降到 28.6、52.4 和 86.0。这些版本目前需要配套的 nari-llama.cpp 分支运行；项目方称在 RTX PRO 6000 上解码速度与其他量化相当，4K 上下文下 3-bit/2.5-bit/2-bit 为 88.9/99.2/111.7 tok/s，但结果尚未独立复现。

hackernews · toebee · 11月23日 13:42 · [社区讨论](https://news.ycombinator.com/item?id=50611402)

**「背景」** GGUF 是 llama.cpp 生态常用的模型文件格式；量化会把权重从 BF16 等较高精度压缩到 3 位或更低，以显著降低存储和显存占用。27B 模型在 BF16 下约需 54 GB，而 3 位量化可压到约 10 GB，代价通常是长链条推理和智能体任务上的精度下降，这也正是该发布用多项基准检验的核心问题。

**「使用门槛与位宽取舍」** 目前运行这些量化文件必须使用 nari-labs 自行维护的 llama.cpp 分支（nari-llama.cpp），标准 llama.cpp 用户无法直接加载。按作者自报的数据，2-bit 版本在长程智能体与数学任务上已明显退化（DeepSWE 从 BF16 的 39.8 降至 28.6，AIME 25+26 从 97.7 降至 86.0），因此面向这类负载时应停留在 3-bit 或 2.5-bit，而不是为再省几 GB 降到 2-bit。这些数字均为发布方自测，尚无独立复现。

**「社区讨论」** 评论者 rao-v 认为这类高算力量化容易在基准类数据上过拟合，但肯定该项目覆盖多种长程任务并提到“held out”；WithinReason 则依据图表认为大部分增益来自评测框架差异，而非模型本身。另有用户报告在 M3 Pro（18 GB）上 3.0bpw 文件解码约 3.8 tok/s、2.0bpw 约 4.9 tok/s，明显慢于 CUDA。

**标签**: `#quantization`, `#local LLM inference`, `#GGUF`, `#model compression`, `#benchmark evaluation`

---

<a id="item-tech-news-6"></a>
### [黎曼猜想 Lean 证明被指空转，作者承认代码低劣](https://x.com/i/web/status/2124987173439209561) ⭐️ 7.0/10

Alpöge 与 Claude 宣称证明了黎曼猜想及其广义版本，并公开了约 1700 万行 Lean 代码、17.5 万个文件，但没有提供人类可读的证明。Lean 与 Mathlib 社区次日表示，对代码证明了这一命题“有充分信心”。随后有研究者指出，关键定义被写成恒真、几何条件形同虚设，证明可能只是空转。23 日 Alpöge 承认“25 万页是玩笑”，称代码“满是垃圾但能编译”，并认为批评完全合理。

telegram · zaihuapd · 11月24日 01:29

**「背景：Lean 形式化与「空转」风险」** Lean 是交互式定理证明器，其数学库 Mathlib 要求陈述经机器内核逐步检查；但内核通过只说明代码与其写下的陈述一致，若关键定义被写成恒真、条件形同虚设，检查通过并不等于数学命题本身被证明。据滑铁卢大学页面记录，Levent Alpöge 于 2026 年 11 月 20 日宣布与 Anthropic 的 Claude 一同得到黎曼猜想及 Dirichlet L 函数广义黎曼猜想的证明，相关材料为约 1700 万行 Lean 代码（另有报道称六周左右完成），远超任何人可通读的规模。正因如此，外界判断其成立与否只能依赖定义是否忠实，而难以逐行审阅证明本身。

**「影响」** 对 Lean 形式化研究者和审稿方而言，这一事件的具体教训是：代码能够编译、文件规模庞大，并不能证明定理陈述有实质内容；审查时需要核查关键定义是否恒真、几何条件是否被实际使用，以及是否存在可读的定理陈述。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=-Tzliv3mzds">AI Helped Prove the Riemann Hypothesis . Nobody Can... - YouTube</a></li>
<li><a href="https://math.uwaterloo.ca/~mrubinst/alpoge_claude_grh/">Alpöge / Claude proof of the Generalized Riemann Hypothesis</a></li>

</ul>
</details>

**标签**: `#AI proof`, `#Lean`, `#formal verification`, `#Riemann Hypothesis`, `#AI research controversy`

---

<a id="item-tech-news-7"></a>
### [黄循财：新加坡不会成为规避美国芯片管制的通道](https://www.bloomberg.com/news/articles/2026-11-24/singapore-won-t-be-conduit-to-skirt-us-chip-curbs-wong-says) ⭐️ 7.0/10

新加坡总理黄循财表示，新加坡不会允许本国被用作企业规避美国芯片出口管制的通道；当局正在调查 Megaspeed 采购英伟达芯片的交易。此前一天，美国商务部已将 Megaspeed 及另外 6 家东南亚企业列入贸易黑名单；《联邦公报》称，这些企业存在向未获授权用户转移先进计算产品的“重大风险”。名单还涵盖上述企业在马来西亚和泰国的关联实体；路透社报道，阿里巴巴新加坡子公司 Apex Enterprise Solutions 也在名单中，阿里巴巴称其从未转移受管制的先进计算芯片。

telegram · zaihuapd · 11月24日 05:03

**「背景」** 美国对先进计算芯片实施出口管制，英伟达等公司的相关产品出口到特定目的地或用户需符合许可要求。被列入商务部贸易黑名单的企业，从美国供应商采购受控物项时会面临更严格的许可审查；新加坡作为区域贸易与转运节点，其当地交易因此受到关注。

**「影响」** 被列入美国贸易黑名单意味着 Megaspeed 等企业及其在马来西亚、泰国的关联实体获取美国先进计算产品将受到限制；经由新加坡采购或转运英伟达等 AI 芯片的交易也将面临更严格的合规审查和中断风险。

**标签**: `#chip export controls`, `#AI hardware`, `#Singapore`, `#Nvidia`, `#trade policy`

---

<a id="item-tech-news-8"></a>
### [Anthropic 称 Claude 发现 VP≠VNP，Lean 4 证明待审](https://github.com/anthropics/formal-math/blob/main/vp-vnp/README.md) ⭐️ 7.0/10

11 月 24 日，Anthropic 在 GitHub 的 formal-math 仓库公开论文《VP ≠ VNP over every field》及 Lean 4 形式化证明，并称论文、代码和结果均出自内部研究用 Claude 模型。论文声称给出哈密顿圈多项式的超多项式算术电路下界，据此推出 VP 是 VNP 的真子类；若成立，将解决 Valiant 1979 年的代数复杂度猜想，但该结果仅针对算术电路，不涉及 P 与 NP。仓库称证明经三条标准公理审计和独立内核 nanoda 复核，除预留文件外不含 sorry。该结果尚无人类数学家通读，Lean 无法确认形式化陈述与所声称命题一致，附录 Q 列出出入，仍待独立审阅。

telegram · zaihuapd · 11月24日 06:02

**「背景」** VP 与 VNP 是 Valiant 用算术电路定义的代数复杂度类，大致对应布尔复杂度中的 P 与 NP；这类电路由加、减、乘门构成并计算多项式。Valiant 在 1979 年提出的 VP ≠ VNP 猜想至今未解决，而此次声称的结果正是针对这一算术电路模型，并不直接涉及 P 与 NP。

**「审阅重点在陈述而非证明」** 对关注该结果的研究者而言，Lean 内核与 nanoda 复核只能证明“证明与所写陈述相容”，不能确认该陈述就是 Valiant 1979 年猜想所指的 VP≠VNP；正如相关讨论所指出的，得到的是经形式验证的证明，而非经形式验证的定理陈述。因此在人类数学家通读之前，独立审阅应优先逐条比对 Lean 文件中的形式化陈述、附录 Q 列出的出入与论文声称的命题，而不能仅凭“无 sorry”或公理审计通过就把它当作已解决的代数复杂度下界。

<details><summary>参考链接</summary>
<ul>
<li>[PDF] INTERPOLATION IN VALIANT&#x27;S THEORY</li>
<li>[PDF] On the Structure of Valiant&#x27;s Complexity Classes - CiteSeerX</li>
<li>Lies, Damned Lies and Proofs: Formal Methods Are Not Slopless</li>

</ul>
</details>

**标签**: `#complexity theory`, `#Lean 4`, `#formal verification`, `#AI for mathematics`, `#Anthropic`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [vLLM 以插件形式实现 ERNIE 5.5 Flash 的 Day-0 支持](https://vllm.ai/blog/2026-11-24-ernie-5-5-flash-preview) ⭐️ 7.0/10

rss · vLLM Blog · 11月24日 00:00

**「背景」** 百度的 ERNIE 5.5 Flash Preview 是一个 280B 总参数、每 token 激活 14B 的稀疏 MoE 模型，支持 100 万 token 上下文、先思考再作答以及长程 Agent 工具调用。为了让这类新模型不必等待 vLLM 主干合并或 nightly 构建，团队选择以独立插件的形式在发布当天提供支持。

**「方案」** 插件通过 vllm.general\_plugins 入口在启动时注册，模型架构以模块路径而非导入的类登记，因此只有 config.json 命中这些架构时才会导入模型代码，同一环境服务其他模型没有额外开销；注意力、KV cache 管理、投机解码与服务器主体仍来自 vLLM，插件自身的 hook 也只对 ERNIE 架构生效。针对架构中的新结构，团队逐个设计融合 kernel：推理期固定的 VHA 跨头混合参数在加载权重时折叠成单个矩阵，并把下游所需的 FP8 量化放进同一 kernel 在寄存器内完成，省去 BF16 中间结果往返显存；所有 router 权重在加载时拼接，一次 GEMM 产出全部 logits，路由链其余步骤合并为一个 kernel；MultiMax 的四段激活则合并为单次读写。作者报告这些融合比逐算子实现快 1.55×–6.53×，且输出与未融合版本逐位一致。稀疏索引侧，FlashIndexer 用小 head router 按 token 挑选少数索引头并做阈值预过滤，只需冻结主干、以原 DSA 选择为蒸馏目标微调约 10 亿 token 的 router，在 1M 上下文下带来 1.4× 加速。作者也坦承代价：插件修复与特性只能跟随模型的发布节奏，部分 hook 必须限定在 ERNIE 架构上。

**「启示」** 作者的核心论点是：把模型代码与针对性融合 kernel 打包成插件，可以在不改动 vLLM 主干的前提下实现 Day-0 支持，让上游通用能力随版本自然继承。不过文中加速数字均为团队自报，未给出硬件、基线或测量方法，标题所称的端到端加速也缺少吞吐与延迟数据。

**标签**: `#vLLM`, `#MoE inference`, `#kernel fusion`, `#speculative decoding`, `#quantization`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [威廉姆斯：通胀回落到 2%仍需更多行动，未来或进一步加息](https://www.cnbc.com/2026/11/23/john-williams-fed-inflation-rate-hikes.html) ⭐️ 8.0/10

纽约联储主席威廉姆斯表示，要把通胀拉回 2%仍需更多行动，并暗示未来可能随时间推移进一步加息；市场已完全消化 12 月 8 日至 9 日会议加息 0.25 个百分点、将目标区间从 3.75%-4%上调的预期。

rss · CNBC Finance · 11月23日 21:02

**「背景」** 当前通胀仍远高于美联储 2%的目标，威廉姆斯预计通胀将在 2027 年接近目标、次年达标，而美联储内部对加息速度存在分歧。

**「影响」** 若 12 月如市场预期加息 0.25 个百分点，与短期利率挂钩的信用卡、浮动利率贷款和企业融资成本将面临上行压力。

**标签**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#inflation`, `#John Williams`

---

<a id="item-finance-news-2"></a>
### [AI 抛售令 DeepSeek 与月之暗面上市计划承压](https://www.bloomberg.com/news/articles/2026-11-23/china-s-next-ai-deals-clouded-by-selloff-after-anthropic-ipo) ⭐️ 8.0/10

彭博报道，Anthropic 规模 1195 亿美元的 IPO 之后全球 AI 股加速下跌，中国科技股自 6 月底以来累计蒸发 1.7 万亿美元，令 DeepSeek、月之暗面和阶跃星辰正在筹备或考虑的上市计划蒙上阴影。

telegram · zaihuapd · 11月23日 09:31

**「背景」** Anthropic 的创纪录 IPO 被视为这轮全球 AI 股抛售的导火索；DeepSeek、月之暗面和阶跃星辰都是其直接竞争对手，正在筹备或考虑发行股份，这些计划并不完全取决于 Anthropic 的股价，但全球 AI 交易转弱增加了上市的不确定性。

**「影响」** 对 DeepSeek、月之暗面和阶跃星辰的早期投资人与持股员工而言，如果上市窗口因这轮抛售推迟，股份变现时间和估值参照将变得更不确定；这也会影响中国 AI 公司后续上市的定价环境。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-23/china-s-next-ai-deals-clouded-by-selloff-after-anthropic-ipo">China’s Next AI Deals Clouded by Selloff After Anthropic IPO</a></li>
<li><a href="https://www.theedgesingapore.com/news/tech/chinas-next-ai-deals-clouded-selloff-after-anthropic-ipo">China’s next AI deals clouded by selloff after Anthropic IPO</a></li>
<li><a href="https://www.theguardian.com/business/2026/nov/20/global-stock-markets-slump-anthropic-ipo-ai-sell-off">Nasdaq erases all 2026 gains as AI sell - off dampens... | The Guardian</a></li>

</ul>
</details>

**标签**: `#AI selloff`, `#China tech stocks`, `#AI IPOs`, `#Anthropic IPO`, `#market volatility`

---

<a id="item-finance-news-3"></a>
### [上海地铁票价 21 年来首次调整，起步价 3 元](https://weibo.com/1699432410/5368461393397183) ⭐️ 7.0/10

上海轨道交通将于 12 月 1 日起实施 21 年来首次票价调整，起步价 3 元、覆盖 0 至 4 公里，之后按 4、4、4、7、7、10、10 公里加 1 元，50 公里以上每 15 公里加 1 元。同步推出的计次票（35 至 90 次四档，售价 190 元至 390 元，11 月 26 日开售）和同一支付渠道当月累计满 90 元享 9 折等优惠，意在减轻高频出行乘客的负担。

telegram · zaihuapd · 11月23日 10:45

**「背景」** 上海轨道交通现行票价已沿用 21 年，此次调整同时以计次票和满额折扣来减轻高频出行者的负担；据媒体报道，相关票价机制调整方案自 9 月起公布，一直受到市民关注。

**「对通勤者的影响」** 对上海日常通勤者而言，此次 21 年来首次调价使平均每人次票价提高约 1 元左右；而购买计次票的高频乘客，单次出行成本可降至 4.50 元、4.33 元。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://news.qq.com/rain/a/20260908A05NH700">news.qq.com/rain/a/20260908A05NH700</a></li>
<li><a href="https://news.qq.com/rain/a/20260819A0ARAE00">时隔21...</a></li>
<li><a href="https://c.m.163.com/news/a/L4N9D9Q2055040N3.html">c.m.163.com/news/a/L4N9D9Q2055040N3.html</a></li>

</ul>
</details>

**标签**: `#上海地铁`, `#公共交通票价`, `#票价调整`, `#通勤成本`, `#优惠政策`

---

<a id="item-finance-news-4"></a>
### [马斯克据称承认 SpaceX AI 落后，转而出租算力给 Anthropic 和 Google](https://www.nytimes.com/2026/11/23/business/elon-musk-ai-anthropic-google.html) ⭐️ 7.0/10

《纽约时报》11 月 23 日援引三名知情人士报道，SpaceX 自今年 5 月起向 Anthropic、Google 等公司出租数据中心算力，月收入达数十亿美元；马斯克据称向员工承认公司在 AI 上落后，并认为出租算力比自用更赚钱。

telegram · zaihuapd · 11月24日 02:06

**「背景」** 据《纽约时报》报道，SpaceX 拥有自营数据中心，而马斯克同时也在推进自家 AI 业务，因此把算力租给 Anthropic 等竞争对手会挤占自身项目可用的资源。

**「影响」** 直接受影响的是需要大量算力的 AI 开发商：据外部报道，Anthropic 以每月 12.5 亿美元获得约 32.5 万块英伟达 GPU 的使用权，谷歌则承诺每月支付 9.2 亿美元、为期 32 个月，这类长期合约把大客户的算力预算锁定在 SpaceX 的数据中心，也为其上市计划提供了可观的收入来源。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.nytimes.com/2026/11/23/business/elon-musk-ai-anthropic-google.html">Elon Musk Faces an A.I. Dilemma at SpaceX - The New York Times</a></li>
<li><a href="https://fortune.com/2026/07/19/spacex-ai-compute-renting-business-google-anthropic-pentagon-deals-revenue-valuation-elon-musk-colossus-data-centers/">SpaceX is quietly building an AI compute business that may ...</a></li>
<li><a href="https://www.cnbc.com/2026/06/05/google-to-pay-spacex-920-million-a-month-for-xai-compute-capacity.html">Google to pay SpaceX $920 million a month for compute ...</a></li>

</ul>
</details>

**标签**: `#SpaceX`, `#AI compute`, `#data centers`, `#Anthropic`, `#Google`

---