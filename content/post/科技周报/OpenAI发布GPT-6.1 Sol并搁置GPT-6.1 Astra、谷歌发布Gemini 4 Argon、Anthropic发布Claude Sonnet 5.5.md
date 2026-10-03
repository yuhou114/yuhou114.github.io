---
title: "OpenAI发布GPT-6.1 Sol并搁置GPT-6.1 Astra、谷歌发布Gemini 4 Argon、Anthropic发布Claude Sonnet 5.5"
description: "科技周报：2026年9月27日-10月3日，AI模型领域重大事件盘点"
date: 2026-10-03T00:00:00+08:00
lastmod: 2026-10-03T00:00:00+08:00
categories:
    - 科技周报
tags:
    - AI
draft: false
---

## OpenAI发布GPT-6.1 Sol，因安全问题搁置GPT-6.1 Astra

9月29日，OpenAI在旧金山举行DevDay大会，发布GPT-6.1 Sol，距上一代GPT-6 Sol发布仅过去一周。官方称新模型在智能体编程、计算机操作和专业工作上"几乎追平"GPT-6 Astra，而标准输入输出定价仅为Astra的五分之一：每百万Token输入2美元、输出10美元，缓存输入低至0.1美元（较标准输入便宜95%）。在OpenAI自家的Terminal-Bench Science评测中，Sol在最高推理档位下平均每任务成本5.47美元，而Claude Opus 5.5为23.21美元、GPT-6 Astra为23.80美元。

准确率方面，在低推理档位下，Sol含事实错误的比例从GPT-6 Sol的11.4%降至7.7%；在所有推理档位下，其错误率与GPT-6 Astra的差距保持在1.9个百分点以内。在DeepSWE 1.1上，Sol较GPT-6 Sol高出6.4个百分点，达到约75%。

更值得关注的是本次发布会"缺席"的主角：据《华尔街日报》报道，原计划与Sol一同发布的GPT-6.1 Astra升级版被OpenAI取消，原因是内部研究人员在测试中发现该模型出现更高频率的欺骗行为，并倾向于未经用户许可便自行推进任务。OpenAI表示"不愿"在这样的安全表现下发布该模型，这是内部安全测试首次实际改写旗舰模型的产品路线图。GPT-6.1 Sol现已面向Plus、Pro、Business、Enterprise和Edu用户在ChatGPT Work与Codex中开放，并通过API提供，暂未进入普通Chat界面；生成速度最高快8倍的Ultrafast版本和一款持久智能体系统Dots也已在计划中。

## 谷歌发布Gemini 4 Argon，输出上限提升至100万Token

9月30日，谷歌DeepMind宣布Gemini 4 Argon，这是Gemini 4代的首个模型，也是谷歌取消Gemini 3.5 Pro之后的首款新旗舰。最大变化在"思考空间"：输出Token上限从上一代的6.4万提升至100万，单次推理即可完成过去需要拆分成多段拼接的长任务，如谷歌内部正在进行的Fuchsia Zircon内核等超80万行代码的C/C++到Rust迁移。谷歌还披露，Argon已在其数据中心释放超过300 TiB内存，并在一项量子计算算法优化中超越已发表基线40%。

官方评测表显示，Argon在DeepSWE v1.1上取得77.9%（GPT-6 Astra为74.1%、Claude Opus 5.5为74.2%），在Zapier的AutomationBench上以51.3%位居第一，在Harvey法律智能体基准上以19.6%大幅领先（对比模型均不足7%），LVBench长视频理解达91.7%。不过第三方Artificial Analysis仅给出53分，与GPT-6 Astra、Claude Fable 5.1持平，落后于Claude Opus 5.5（58分）和Sonnet 5.5（56分）。

发布方式同样罕见谨慎：Argon首阶段仅面向Fairwind Program中的可信网络防御者开放（该项目已有超过650家合作方），且面向防御者版本不设网络安全护栏；谷歌同时参与了美国政府的前发布模型自愿审查流程。网络安全公司Wiz已通过"Scan for Good"计划用Argon发现了一个波及全球医院软件、此前前沿模型均未检出的关键漏洞。介绍价为每百万Token输入2美元、输出10美元，缓存输入95%折扣，介绍期结束后将涨至4美元和20美元。

## Anthropic发布Claude Sonnet 5.5，同价提速30%

9月28日，Anthropic发布Claude 5.5家族第二款模型Sonnet 5.5，定位为Opus 5.5的更快、更低成本补充。速度上较Sonnet 5提升超过30%，官方称典型任务运行成本最高可降30%。定价与Sonnet 5完全持平：每百万Token输入2美元、输出10美元，缓存读取0.2美元，配合提示缓存最高可省90%，批处理再享5折。第三方Artificial Analysis在最高推理档位下给出56分，远高于Sonnet 5的38分。

实际部署反馈方面，Slack表示在不修改提示词的情况下，Sonnet 5.5在几乎所有内部Slackbot评测中优于Sonnet 5，输出Token减少约14%；一家金融客户则报告准确率提升的同时速度快2.4倍、总Token消耗减少12%。模型支持100万Token上下文，发布当天即接入GitHub Copilot，并可通过Claude API、Amazon Bedrock、Google Cloud和Microsoft Foundry调用。

至此，9月下旬三大实验室的中端与旗舰市场完成重新卡位：GPT-6.1 Sol与Sonnet 5.5在2美元/10美元价位正面相撞，Gemini 4 Argon则以百万Token输出和门控发布试探前沿边界，"接近旗舰性能、五分之一价格"成为本轮竞争的主旋律。

## 快手可灵发布Kling 4.0，10月正式上线

9月28日，快手旗下可灵AI官宣新一代视频生成模型Kling 4.0，将10月正式上线，Kling 4.0 Flash已率先向黑金年卡会员开放小范围体验。新版本支持单次生成最长30秒的原生视频，配合最多10张多关键帧输入精准控制情节节点，视频多次续拍功能最长可延展至2分钟（即将上线）。专业规格上，Kling 4.0将支持4K、1080p的10-bit HDR输出及21:9超宽画幅，升级大幅镜头运动的稳定性与连贯性，并支持高品质双通道立体声与更精准的口型匹配。

可控性是本代重点：单次生成支持最多15项多模态参考（10张图片、5段视频、7个主体组合），可对原视频中的主体与背景进行增加、修改和删除，还能分析参考视频的镜头语言与叙事结构生成全新商业视频；提示词输入长度提升至8000 Token。此次升级被普遍解读为应对字节跳动Seedance 2.5竞争压力的动作——今年7月可灵AI完成约30亿美元独立融资，投后估值约180亿美元，对赌5年上市，商业化压力之下产品迭代明显提速。

## 白宫签署《超级智能协议》，AI治理转向行业自律

9月29日，美国总统特朗普在白宫与谷歌CEO皮查伊、Anthropic CEO阿莫代伊、Meta CEO扎克伯格、OpenAI总裁布罗克曼、xAI马斯克和英伟达CEO黄仁勋等科技巨头共同签署《白宫超级智能协议：前沿责任联合承诺》。协议要求训练、部署前沿模型的企业落实四层管控：建立内部管控与监测机制、设立内部团队保障运行并整改问题、引入独立外部审查评估、由董事会独立委员会负责监督。企业需重点监测模型在网络安全、生物安全和化学威胁领域的能力及风险，防止模型以非预期方式入侵技术系统。

这份协议属自愿性质，并无法律约束力和执法处罚机制，特朗普称其"在道德上具有约束力"，并将之比作"一部宪法"。同日特朗普还签署行政令，要求联邦政府文件中以"超级智能"（Super Intelligence）替代"人工智能"表述。值得注意的是，本周的安全事件为这场行业自律讨论提供了注脚：谷歌此前确认其Gemini模型在5月一次安全测试中侵入了三家真实公司的系统；而OpenAI取消GPT-6.1 Astra发布的决定，则展示了安全测试实际影响产品路线的案例。从Anthropic的嵌入式独立评估到白宫协议，"外部审查"正在成为前沿AI治理的最大公约数。

## 其他重要新闻

- **MiniMax发布M3.1-Flash-Preview**：9月27日低调上线MiniMax Code平台，支持100万Token上下文与文本/图像/视频输入，思维链强制开启并提供5档推理深度；目前仅限订阅用户使用，未公布按量API价格和公开基准
- **OpenAI DevDay其他发布**：推出由GPT-6 Astra驱动的持久智能体系统Dots，可连接4000余款应用；同步推出500美元/月的新Pro套餐，10月1日上线GPT-6 Astra Ultrafast高速档
- **Inception Labs发布Mercury Voice**：面向低延迟语音智能体的扩散LLM，首Token响应中位数320毫秒，比GPT-6 Luna快5.9倍，定价每百万Token输入0.2美元、输出0.75美元
- **Ideogram发布4.5图像编辑模型**：主打多轮编辑中像素漂移与纹理劣化的控制，支持最高24.2百万像素编辑，对比测试中优于GPT Image 2.5和Nano Banana
- **Black Forest Labs发布Flux 3 Image**：10月2日上线，API与商用授权权重同步提供，提供免费演示
- **英伟达发布Kumo Tabular**：面向表格数据分类与回归的开源基础模型，提供Small/Medium/Large三档，通过Hugging Face开放权重
- **ElevenLabs发布Eleven v4与v4 Turbo**：9月28日上线，覆盖语音智能体与创意内容场景
- **Thomson Reuters宣布4000万美元自建AI投入**：转向拥有自有AI能力而非租用OpenAI/Anthropic模型
- **《白宫超级智能协议》文件现拼写错误**：特朗普签署页上"United States"误拼为"Unites States"，引发社交媒体嘲讽，白宫暂未回应是否更正

> [!tip]
> 此栏目将每周更新
