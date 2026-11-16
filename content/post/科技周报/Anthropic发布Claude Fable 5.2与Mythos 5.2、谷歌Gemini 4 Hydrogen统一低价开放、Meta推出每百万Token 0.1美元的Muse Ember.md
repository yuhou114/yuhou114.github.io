---
title: "Anthropic发布Claude Fable 5.2与Mythos 5.2、谷歌Gemini 4 Hydrogen统一低价开放、Meta推出每百万Token 0.1美元的Muse Ember"
description: "科技周报：2026年11月8日-11月14日，AI模型领域重大事件盘点"
date: 2026-11-14T00:00:00+08:00
lastmod: 2026-11-14T00:00:00+08:00
categories:
    - 科技周报
tags:
    - AI
draft: false
---

## Anthropic发布Claude Fable 5.2与Mythos 5.2，价格下调20%

11月9日，Anthropic发布Claude Fable 5.2与Claude Mythos 5.2。两者是同一底层模型的两套配置：Fable带网络安全与生物领域护栏，面向所有用户开放；Mythos则仅通过Cyber与Life Sciences验证计划向受审查组织提供。标准定价为每百万Token输入8美元、输出40美元，较5.1系列的10/50美元下降20%；输出速度提升至多30%，另可选2.5倍速的fast模式（16/80美元）。上下文1M Token、最大输出128K，知识截止2026年6月。

跑分上，Fable 5.2在FrontierCode 2.0（Xhigh档）拿到49.1%，远超5.1的32.4%，也高于Opus 5.5的45.5%、GPT-6 Astra的42.8%与Gemini 4 Carbon的41.1%；FrontierSWE v2为69.9%，OSWorld 2.1（离线部分集）89.3%，带工具的Humanity's Last Exam 74.2%。Mythos 5.2在10月针对1829个CVE的CVE Rediscovery评测中达89.6%（5.1为78.3%），发现的漏洞比Opus 5.5多10.2%。

真正引人注意的是发布前的长程实验：一个Fable 5.2实例从空目录出发，协调1000多个子智能体、用8天写出一个能在笔记本上启动的原型操作系统（含存储、驱动、窗口、登录界面与安装器）；另一组智能体把Anthropic一个生产服务从Python迁移到Rust，启动速度提升约26倍；与电路板厂商Diode合作，模型从零设计了三款可用电子设备（语音助手中枢、USB免提音箱、掌上电子宠物），电路板、外壳与软件全包，三次打样均无需电气改版即可工作。科研侧，模型声称解决两个黑洞物理开放问题（论文已公开、尚未同行评审），并用约1000个智能体在30小时内完成了费马大定理的Lean形式化——同样的工作9月花了11天。安全方面，沙箱逃逸评测中Mythos 5.2在3.1%的场景使用了沙箱外凭据或文件（Mythos 5为39%、5.1为21%）；护栏误拦较5.1减少约55%，反蒸馏技术使被窃取数据减少90%至99%。

## 谷歌Gemini 4 Hydrogen发布，Carbon同周转正并预告涨价

11月12日，谷歌发布Gemini 4 Hydrogen，定位"让所有人用上Gemini 4"的高效执行模型。它在完整的100万Token上下文窗口上实行统一价：每百万Token输入1.50美元、输出7.50美元（缓存0.075），并开放免费层——这是Gemini 4系列首次进入免费档。默认高思考档下Artificial Analysis智能指数51分（xhigh档54），略高于Argon的50；较Gemini 3.8 Flash任务完成速度快2.5倍，Terminal-Bench 4.1从18.2%跃升至57%，虚构陈述减少5倍以上，间接提示注入抵抗力提升2.3倍以上。专业任务上，HLE-Diamond 58.8%、Vals税务智能体榜第一（52.3%）、法律研究榜并列第一（55.8%）、Agent Arena第五。

产品落地几乎同步：发布当天Hydrogen即成为Google搜索的默认模型，并进入Gemini应用、Gemini for business的模型菜单与Google Sheets（面向符合条件的企业订阅）。谷歌称这是"搜索迄今最大的一次模型升级"。Antigravity同步上线Orchestrator，可在同一会话中在Carbon与Hydrogen之间动态切换——Terminal-Bench 4.0上达到接近Carbon的成功率，同时平均少用24%配额、快19%。

价格曲线更值得关注：11月10日Gemini 4 Carbon正式GA，付费开发者可用，但介绍价每百万输入2美元、输出10美元仅维持到11月30日，12月1日起翻倍至4/20美元，Argon同步上调。也就是说，Hydrogen的1.50/7.50在12月1日后将比Carbon便宜62.5%。谷歌用"前沿模型负责深度推理、Hydrogen负责高频执行"的分层，正面回应企业智能体的成本焦虑。

## Meta发布Muse Ember，每百万输入0.1美元切入智能体"体力活"

11月9日，Meta Superintelligence Labs发布Muse Ember，这是Muse家族第四款模型（前有4月的Spark、8月开源的Glimmer、10月的Wonder），也是其最轻、最便宜的模型：每百万Token输入0.10美元、输出0.50美元，通过Meta Model API（muse-ember-1.0）与Muse Code提供，权重闭源。

它的定位不是"更聪明的模型"，而是智能体每天重复的活儿——工具调用、编码子任务、路由、信息抽取、长文档解析。Meta给出的成本叙事很直白："Muse Wonder负责规划，Muse Ember负责走量。"在Artificial Analysis综合指数上，Ember约36分、单任务成本约0.14美元，与Claude Haiku分数相当而成本约为其三分之一；这一价格已与DeepSeek V4.1 Flash、GLM-5.3 Flash等开源模型处于同一区间。规格上支持1M上下文，原生接受文本、图像、音频与视频输入，可直接读截图、图表、扫描件或从会议录音、视频中工作，无需额外路由模型；它也是Meta首个用Muse Wonder Full参与训练的模型，能根据截图操作桌面应用。不过Meta自报的FrontierCode 2.0成绩仍落后Haiku，官方叙事应视为厂商开场白而非定论。

## 英伟达CEO更替：黄仁勋辞职，CFO临时接任

11月12日，英伟达宣布董事会已接受黄仁勋辞任CEO，CFO Colette Kress出任临时CEO，Harvey C. Jones被任命为公司史上首位董事会主席。消息公布后英伟达股价收跌4.34%，而博通、AMD涨逾5%——市场第一时间把这次人事变动解读为竞争格局的变量。黄仁勋自1993年联合创办英伟达，主导了CUDA生态与过去三年的AI算力周期，其离任是AI基础设施领域近年来最大的一次权力交接，临时CEO能否延续产品节奏与客户关系，将直接影响明年的算力供应预期。

## 国产与开源：百度ERNIE 5.5 Flash、阿里Qwen4预告、Inkling 2 Small开源

11月13日，百度发布ERNIE 5.5 Flash Preview：280B总参/14B激活的MoE，1M上下文，定价每百万Token输入1元、输出4元（约0.14/0.56美元），并承诺11月25日前以Apache 2.0开放权重。11月11日，阿里预告Qwen4并开放Qwen4-Max预览（Token Plan渠道），支持1M上下文、最长约39.3万Token输出，尚未公布跑分与定价。开源侧，Thinking Machines于11月12日兑现承诺，以Apache 2.0开放Inkling 2 Small全量权重（594B总参/17B激活，AA指数31）。此外World Labs于11月13日向所有开发者开放Atlas世界模型的完整API，支持单图生成世界、最多64张输入重建与splat导出；英伟达研究团队9日发布GR00T 2机器人基础世界-动作模型，代码将于12月开放。

## 安全事件：Claude Code密钥泄露、Railway被盗密钥74万美元

11月8日，安全公司Apiiro披露Claude Code的"don't ask again"审批机制会把被批准的命令逐字写入项目设置文件——包括其中的密钥。Apiiro在公开GitHub仓库中找到1122份含至少一个秘密的该文件，计入历史版本、共享设置与聊天日志后共2539个秘密，涉及开发者密码与API密钥。11月10日，Railway公布10月20-21日入侵事件的完整报告：攻击者的主要目标是AI供应商密钥，被盗密钥产生的费用约74万美元；Railway最初告知客户无法退款，后改口称将承担供应商不予承担的部分。11月13日，Notion确认部分AI聊天内容在Fireworks AI的泄露事件中被暴露。同日谷歌披露Gemini 4 Hydrogen对间接提示注入的抵抗力提升2.3倍，安全能力正成为模型发布的标准叙事。

## 其他重要新闻

- **Anthropic IPO获约6倍超额认购**：11月12日媒体报道，认购需求已达发行股份约6倍，承销商告知现有投资者优先配售，为提价留出空间
- **OpenAI融资累计150亿美元**：11月12日报道称本轮已募约150亿美元、估值1.25万亿美元，较最初"至少300亿、1.4万亿估值"明显收缩
- **ChatGPT Wallet上线**：11月13日向部分美国Pro用户开放，智能体可用支付令牌完成购买，每笔需生物识别，智能体与商家均看不到卡号
- **谷歌Gemini Decisions API**：11月11日发布Gemini Decision 1，对二选一、多选与评分规则类问题返回校准结果，单请求最多1000个问题，仅按输入计费0.10美元/百万Token、不收输出费
- **OpenAI解散独立机器人团队**：11月13日确认将机器人研究人员并入主线研究团队、应用与硬件人员转入Applied部门，理由是GPT-6 Astra等通用模型已可直接驱动机器人
- **联合航空禁止第三方AI智能体订票**：11月12日起限制智能体代客预订航班
- **Gemini进入CarPlay、智能眼镜开启预售**：11月12日Gemini登陆苹果CarPlay；13日Gemini智能眼镜预售，起价395美元
- **企业Token支出增速骤降**：Ramp数据显示8-9月企业AI Token支出仅增长1.5%（7月为42%），9月23日至10月23日回升8.9%——降价与用量管控正在压低单客支出
- **DeepMind智能体加速密码分析**：11月8日披露两个RSA-1024弱点，1024位分解速度较此前提升3.5倍

> [!tip]
> 此栏目将每周更新
