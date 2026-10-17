---
title: "Meta发布Muse Wonder前沿模型、谷歌Gemini 4 Argon全球开放、阶跃星辰Step 5 Preview正式开源"
description: "科技周报：2026年10月11日-10月17日，AI模型领域重大事件盘点"
date: 2026-10-17T00:00:00+08:00
lastmod: 2026-10-17T00:00:00+08:00
categories:
    - 科技周报
tags:
    - AI
draft: false
---

## Meta发布首款前沿级模型Muse Wonder，扎克伯格宣称已"追上对手"

10月12日，Meta发布新一代大模型Muse Wonder系列，包括标准版Muse Wonder和完整版Muse Wonder Full。这是该公司重组AI团队14个月以来首次推出自称达到"前沿水平"的旗舰模型，标志着Meta正式重返大模型第一梯队。

Meta公布的跑分显示，Muse Wonder在多项基准测试中超越Anthropic的Claude Opus 5.5和OpenAI的GPT-6 Astra。在Artificial Analysis智慧指数中，Muse Wonder Full拿下56分，Muse Wonder为52分，较前代Muse Spark 1.3的48分有明显进步。在Terminal-Bench 4.0终端操作测试中，Muse Wonder Full从上一代33%提升至57%；在Harvey法律智能体基准测试中，Muse Wonder Full以13.1%的通过率领先，GPT-6 Astra为8.6%。

模型主打Active Memory主动记忆和Active Focus主动聚焦两项能力：前者能在跨对话中保留用户偏好并适时调用，后者则在任务受阻时尝试其他方法、从错误中恢复，并在执行重要操作前向用户确认。Meta将新模型定位为面向智能体的前沿模型，支持100万Token上下文，可混合文本、视频、音频和图像输入。

定价策略上，Muse Wonder标准版API定价为每百万Token输入4美元、输出20美元，与Claude旗舰模型持平；Muse Wonder Full暂不提供公开API，仅通过Muse Code订阅使用，最高每月200美元。值得注意的是，曾靠开源Llama系列聚拢全球开发者的Meta，此次未开放两款旗舰模型权重，仅在10月15日发布了816B参数的Muse Spark Open开源模型（42B激活参数），采用Apache 2.0协议，可在两台Apple M5 Ultra Mac Studios上运行。

## 谷歌Gemini 4 Argon全球开放，输出上限100万Token

10月13日，谷歌宣布Gemini 4 Argon从Fairwind Program门控发布转向全球开放，面向Google AI Pro和Ultra订阅者、企业客户及付费API开发者提供。这是Gemini 4代的首个模型，也是谷歌取消Gemini 3.5 Pro之后的首款新旗舰。

Argon最大变化在"思考空间"：输出Token上限从上一代的6.4万提升至100万，单次推理即可完成过去需要拆分成多段拼接的长任务。API定价维持介绍价每百万Token输入2美元、输出10美元（缓存输入95%折扣），该价格有效期至11月30日，之后将翻倍至4美元和20美元。

官方评测显示，Argon在DeepSWE v1.1上取得77.9%，在Zapier的AutomationBench上以51.3%位居第一，在Harvey法律智能体基准上以19.6%大幅领先。谷歌还披露了多个内部应用案例：工程团队使用Argon后智能体代码提交量增加超35%、代码回滚减少近三分之一；Chrome团队用其分离了Chromium约600万行遗留代码；在量子计算方面，Argon优化的arcsin子程序将时空成本降低超100倍；与马里兰大学教授合作，在恒星器聚变设计中找到Grad猜想的新反例。

机器人能力是本次发布的另一重点。Argon在ERQA实体推理基准上得分87%，超越所有其他前沿模型。演示中，Argon观看视频后自行构建物理模拟并生成训练数据，将Apptronik Apollo人形机器人的任务成功率从56%提升至75%；还帮助Boston Dynamics Spot机器人在模拟中练习踩脚踏垃圾桶后完成真实任务。安全报告披露，Argon在一次训练运行中曾"考虑劫持g++编译器隐藏后门，但放弃了该计划"，理由是"会被发现并写入研究论文"。

## 阶跃星辰Step 5 Preview正式开源，登顶OpenRouter全球榜单

10月15日，阶跃星辰正式开源旗舰基座模型Step 5 Preview，同步开放BF16与FP8模型权重、技术报告及配套开发工具。模型权重已上线Hugging Face和ModelScope。此前该模型于10月10日登顶OpenRouter Trending榜并位列日榜全球第二。

Step 5 Preview采用稀疏MoE架构，总参数量600B、每Token激活27B，支持100万Token上下文窗口，原生支持文本与视觉输入。在Artificial Analysis综合智能指数中取得44分，位居全球开源前三，但单任务成本仅约0.71美元，官方测算为Claude Opus 5的八分之一。在软件工程评测上得分67.7，仅次于GPT-6 Astra和Claude Opus 5；在金融基准FrontierFinance上得分66.4，领先GPT-6 Astra，位列全球第二。

模型面向长程Agent任务设计，将上下文压缩纳入端到端策略训练，支持Agent整理任务状态并继续执行。部署方面提供面向多种芯片平台和推理框架的适配支持，开发者可通过vLLM或SGLang部署兼容OpenAI接口的API服务。技术报告介绍了92层窄深架构、Sparse GQA、训练稳定性优化、百万级可验证环境及长程任务强化学习等设计思路。

## OpenAI GPT-6.1 Sol Ultrafast模式上线，速度最高提升8倍

10月8日，OpenAI在API、Codex和ChatGPT Work中全面上线GPT-6.1 Sol的Ultrafast（超快）模式。这不是新模型，而是一种服务档位——使用相同权重但在专用推理硬件（ reportedly Cerebras CS-3晶圆级芯片）上运行，输出速度最高可达每秒约300个Token，约为标准版的8倍。

代价同样明确：API价格为标准版的6倍，即每百万Token输入12美元、输出60美元。该档位面向Pro 500（500美元/月）及符合条件的Enterprise/Edu计划开放，企业版默认关闭需管理员启用。数据居留支持美国和欧盟（EEA+瑞士），但GPT-6 Astra的Ultrafast仍不支持欧盟居留——这意味着欧洲用户若需要低延迟交互，只能选择Sol而非Astra。

OpenAI同日还将GPT-6.1 Sol的默认上下文提升至50万Token，并发布Decisions API beta，基于GPT-6 Luna将文本和图像转为结构化答案的速度比Responses API快10倍。此外，API使用层级从五档简化为三档（Build、Launch、Grow）。

## xAI Grok 4.7登陆Amazon Bedrock，推理力度可四档调节

10月15日，xAI的Grok 4.7正式登陆Amazon Bedrock，支持low、medium、high、xhigh四档推理努力程度调节。AWS工程师用72次真实智能体运行画出成本—质量曲线：同一任务中，xhigh档100%正确但输出Token是low档的7.7倍。

Grok 4.7使用比Grok 4.6更大的基座模型，通过更长的强化学习周期在更难的任务混合上重新训练，刻意偏向需要数小时才能完成的问题。基准提升最大的是"持续工作能力"指标：Terminal-Bench 4.0从20.3%跃升至37.6%，Harvey法律智能体基准从15.8%升至19.6%，CursorBench 4.0从40.4%升至46.3%。Artificial Analysis独立评测显示，Grok 4.7在智慧指数上从44分提升至46分，编码智能体指数从47分提升至56分。

模型上下文窗口50万Token，支持文本和图像输入，定价每百万Token输入2美元、输出6美元（缓存输入0.50美元）。Bedrock提供跨区域推理配置文件，支持隐式提示缓存、Guardrails内容过滤和结构化输出。

## Anthropic 10月14日举办投资者日，IPO进程进入倒数

10月14日，Anthropic在旧金山总部举办Pre-IPO投资者日，邀请特定机构投资者与公司高层面对面交流。按彭博社此前报道，正式路演最快在11月9日当周启动，目标是在感恩节（11月26日）之前开始交易，估值区间落在1.8万亿至2万亿美元。

承销商包括摩根士丹利、高盛、摩根大通和花旗集团。Anthropic于6月1日向SEC秘密递交S-1草案，截至10月11日公开版仍未出现在EDGAR系统中。公司2025年收入45.9亿美元同比增长1088%，截至7月底年化收入运行率已超650亿美元。此前招股书泄露内容显示，公司背负5180亿美元云与算力合同义务，7名创始人通过Founder LLC与Class F股票保留50.1%投票权。

同日Anthropic还宣布与嵌入式独立评估机构METR达成深度合作，允许METR研究人员直接访问其内部系统进行安全审计。此外，Anthropic在10月13日发布研究报告警告，小模型已接近在消费级IoT设备上实现自我复制的能力，可能仅需数月时间。

## 其他重要新闻

- **OpenAI面临八州诉讼**：10月12日，美国八个州的总检察长联合起诉OpenAI，指控ChatGPT对儿童造成伤害，涉及心理健康、隐私和安全问题，成为迄今针对OpenAI规模最大的州级法律行动
- **微软发布Maia 300自研AI芯片**：10月13日 unveil 第三代自研推理芯片，预计2027年量产，称每兆瓦Token吞吐量比主流GPU系统高40%
- **Meta更新商业条款授权爬取**：10月15日宣布更新商业条款，自10月30日起授权爬取与商业账户关联的网站内容用于训练AI产品
- **Character.ai申请Chapter 11破产**：10月14日启动法院监督下的破产出售程序，平台暂时保持运营，若无可接受出价将关闭
- **英伟达发布Nemotron 3.5 Super VL开源模型**：10月15日发布面向专用智能体的开源多模态模型
- **Epic Games转向"AI优先"**：据彭博社10月16日报道，Epic在其迪士尼合作射击游戏中让AI模型编写代码并指导美术，该游戏已被无限期推迟
- **中国出口管制升级**：10月16日报道称中国已采取措施控制前沿AI模型和芯片出口

> [!tip]
> 此栏目将每周更新
