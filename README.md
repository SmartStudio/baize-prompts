# 白泽 Prompt 评测工厂

**没跑过 = 不出厂。**  
**no eval, no ship.**

网上那堆 prompt 合集，十有八九是 Ctrl+C。这里不是合集，是车间：过闸才上架，没过的继续烂在 Inbox。

你要是已经在 Cursor / Claude Code / Codex 里堆了一地「感觉还行」的提示词，却说不清跑没跑通——就是给你们干的。

| 点这 | |
| --- | --- |
| 怎么写出厂文档 | [`docs/PROMPT_TEMPLATE.md`](docs/PROMPT_TEMPLATE.md) |
| 四道闸 | [`eval/rubric.md`](eval/rubric.md) |
| 网站 | https://fxai.ai |
| 方法页 | https://fxai.ai/method/ |
| SOP 全文 | https://github.com/SmartStudio/enterprise-ai-sop |

## 一眼对照

先看同一任务出了什么问题，再看加 Prompt 后具体差在哪。

### 1. 事故说明别再抬价

**问题**：发布流水线两次超时，模型保住了事实，却加了一层架构升华。

**输入**：同一段包含「失败两次、部署脚本、30 分钟超时」的事故说明。

**A 裸跑**：保留 “Beyond resolving the immediate timeout” 这层铺垫。  
**B 加 Prompt**：删掉铺垫，直接说处理架构问题。  
**差在哪**：四个事故事实都还在，没有新编数字或原因，语气更平。

完整页：[`remove-mannered-prose.md`](prompts/agent-coding/remove-mannered-prose.md)

### 2. 主 agent 别越权实现

**问题**：任务只是给 README 加一句简介，主 agent 直接改完文件，违反了只编排的角色约束。

**输入**：同一句 README 修改任务。

**A 裸跑**：自己改文件，再汇报完成。  
**B 加 Prompt**：说明自己只编排，给出派发清单，没有改 README。  
**差在哪**：A 完成了任务却越权，B 把实现留给 subagent。

完整页：[`claude-md-fable-orchestrate-opus.md`](prompts/agent-coding/claude-md-fable-orchestrate-opus.md)

### 3. 会话交接要能直接续

**问题**：上下文太长要换会话，普通交接只写概况和待办，没留下可直接启动下一会话的内容。

**输入**：同一个 scratch 会话迁移任务。

**A 裸跑**：给通用交接笔记，没钉新会话命名和失败降级。  
**B 加 Prompt**：固定交接结构，保留未提交改动，并给可粘贴启动词。  
**差在哪**：A 还要人二次整理，B 可以核对现场后直接续开发。

完整页：[`codex-session-handoff.md`](prompts/agent-coding/codex-session-handoff.md)

## 怎么玩

1. 打开任意出厂页：先读「原始问题」和「给模型的输入」，再复制 Prompt 自己跑。
2. 对照「跑完会差在哪」。看不懂输入、对不上 A/B 的条目不该出现在这里。
3. 要投稿，按 [`docs/PROMPT_TEMPLATE.md`](docs/PROMPT_TEMPLATE.md) 写。Inbox 半成品不公开。

| 目录 | 干啥的 |
| --- | --- |
| `docs/` | 出厂文档规范 |
| `eval/` | 闸门 |
| `prompts/agent-coding/` | 写代码的 Agent |
| `prompts/product-strategy/` | 产品和商业计划 |
| `prompts/research-pkm/` | 研究和知识库 |
| `prompts/marketing-sales/` | 营销销售 |
| `prompts/review/` | 评审验收 |
| `prompts/image-gen/` | 出图提示词（评测成图内嵌） |
| `skills/` | 过闸再升格的技能 |

## 已出厂（2026-09-04 首批）

用户验收 + 四道闸 + A/B 对照后入库。按 v3 读者路径重排。

### prompts

| 类 | 文件 |
| --- | --- |
| agent-coding | [`remove-mannered-prose`](prompts/agent-coding/remove-mannered-prose.md) · [`claude-md-fable-orchestrate-opus`](prompts/agent-coding/claude-md-fable-orchestrate-opus.md) · [`codex-session-handoff`](prompts/agent-coding/codex-session-handoff.md) · [`codex-confidence-loop`](prompts/agent-coding/codex-confidence-loop.md) · [`workspace-audit-keep-remove`](prompts/agent-coding/workspace-audit-keep-remove.md) |
| product-strategy | [`startup-strategist-business-plan`](prompts/product-strategy/startup-strategist-business-plan.md) |
| research-pkm | [`paper-rewrite-13-constraints`](prompts/research-pkm/paper-rewrite-13-constraints.md) |

### skills（升格）

- [`codex-session-handoff`](skills/codex-session-handoff/SKILL.md)
- [`workspace-audit-keep-remove`](skills/workspace-audit-keep-remove/SKILL.md)
- [`codex-confidence-loop`](skills/codex-confidence-loop/SKILL.md)


## 已出厂（2026-09-05 第二批）

用户验收 11 条 Inbox A/B 后入库，按 v3 读者路径出厂。另开本 PR，不追加 #1。

### prompts / agent-coding

| 文件 | 一句话 |
| --- | --- |
| [`design-fragment-clarify`](prompts/agent-coding/design-fragment-clarify.md) | 碎碎念先多轮澄清，别闷头设计 |
| [`codex-github-research-before-build`](prompts/agent-coding/codex-github-research-before-build.md) | GitHub 先调研再实现，确认前停 |
| [`codex-pre-delivery-requirements`](prompts/agent-coding/codex-pre-delivery-requirements.md) | 交付前先出方案与验收清单 |
| [`codex-repeated-work-to-skill`](prompts/agent-coding/codex-repeated-work-to-skill.md) | 重复工作先列候选再沉淀 Skill |
| [`codex-dev-state-archive`](prompts/agent-coding/codex-dev-state-archive.md) | 根目录 DEV_STATE 可续跑 |
| [`codex-long-session-closeout`](prompts/agent-coding/codex-long-session-closeout.md) | 长会话收尾三件套 |
| [`codex-goal-template`](prompts/agent-coding/codex-goal-template.md) | 先落 GOAL.md 再实现 |
| [`codex-task-contract`](prompts/agent-coding/codex-task-contract.md) | 任务契约五段可审 |
| [`karpathy-pairing-constraints`](prompts/agent-coding/karpathy-pairing-constraints.md) | 冲突就停，不静默选边 |
| [`codex-context-slim`](prompts/agent-coding/codex-context-slim.md) | 先裁上下文再审查 |
| [`codex-goal-scenario-pack`](prompts/agent-coding/codex-goal-scenario-pack.md) | Goal 场景扩展包（部分场景未全测） |

## 已出厂（2026-09-14 图片批）

图片线 ×11：每页 = 清理后的评测报告，**内嵌评测成图**（synthetic 含 MAIN-synthetic + B）。**没跑过 = 不出厂。**

| 文件 | fixture_source |
| --- | --- |
| [`GPTImage25-龙武士草原对峙`](prompts/image-gen/GPTImage25-龙武士草原对峙.md) | official |
| [`GPTImage-像素RPG百物网格`](prompts/image-gen/GPTImage-像素RPG百物网格.md) | official |
| [`GPTImage2-品牌全息乙烯贴纸`](prompts/image-gen/GPTImage2-品牌全息乙烯贴纸.md) | official |
| [`GPTImage-品牌硬珐琅徽章`](prompts/image-gen/GPTImage-品牌硬珐琅徽章.md) | official |
| [`GPTImage-国家极简旅行编辑插画`](prompts/image-gen/GPTImage-国家极简旅行编辑插画.md) | official |
| [`GPTImage25-手作微缩旅行场景`](prompts/image-gen/GPTImage25-手作微缩旅行场景.md) | official |
| [`GPTImage-超现实金属方块肖像-JSON`](prompts/image-gen/GPTImage-超现实金属方块肖像-JSON.md) | official |
| [`GPTImage2-照片加极简墨线vignette`](prompts/image-gen/GPTImage2-照片加极简墨线vignette.md) | synthetic_codex |
| [`GPTImage2-对半编辑艺术海报`](prompts/image-gen/GPTImage2-对半编辑艺术海报.md) | synthetic_codex |
| [`GPTImage2-海港旅行手帐海报`](prompts/image-gen/GPTImage2-海港旅行手帐海报.md) | synthetic_codex |
| [`GPTImage25-Line表情包序列帧`](prompts/image-gen/GPTImage25-Line表情包序列帧.md) | synthetic_codex |

索引：[`prompts/image-gen/README.md`](prompts/image-gen/README.md)

## 已出厂（2026-09-15 图片批 batch5×6）

图片线 batch5 ×6：每页 = 清理后的评测报告，**内嵌评测成图**（八零年代 synthetic 含 MAIN-synthetic + B）。**没跑过 = 不出厂。**

| 文件 | fixture_source |
| --- | --- |
| [`GPTImage2-日系街道海军线稿`](prompts/image-gen/GPTImage2-日系街道海军线稿.md) | official |
| [`GPTImage25-八零年代复古人像`](prompts/image-gen/GPTImage25-八零年代复古人像.md) | synthetic_codex |
| [`GPTImage25-橙板牛仔帽时尚海报`](prompts/image-gen/GPTImage25-橙板牛仔帽时尚海报.md) | official |
| [`GPTImage2-360等距柱状全景`](prompts/image-gen/GPTImage2-360等距柱状全景.md) | official |
| [`GPTImage2-等距国家微缩沙盘`](prompts/image-gen/GPTImage2-等距国家微缩沙盘.md) | official |
| [`GPTImage2-等距动漫世界地图沙盘`](prompts/image-gen/GPTImage2-等距动漫世界地图沙盘.md) | official |

索引：[`prompts/image-gen/README.md`](prompts/image-gen/README.md)


## 已出厂（2026-09-17 批）

agent-coding ×3 + image-gen ×4。文本按 v3 读者路径出厂；图片线每页 = 清理后的评测报告，**内嵌评测成图**（像素变身 synthetic 含 MAIN + B）。**没跑过 = 不出厂。**

### prompts / agent-coding

| 文件 | 一句话 |
| --- | --- |
| [`Codex-技能插件中文化整理-RealYDT`](prompts/agent-coding/Codex-技能插件中文化整理-RealYDT.md) | 扫本地技能/插件英文显示改中文，缺 openai.yaml 也补 |
| [`Codex-Astra编排控成本-umbrella`](prompts/agent-coding/Codex-Astra编排控成本-umbrella.md) | 事件等待 + Luna 委派，停掉分钟级心跳 |
| [`Codex-长对话上下文清理摘要-goan`](prompts/agent-coding/Codex-长对话上下文清理摘要-goan.md) | 长会话清成六段可续跑摘要 |

### prompts / image-gen

| 文件 | fixture_source |
| --- | --- |
| [`GPTImage25-列车乘务员3x3抓拍拼贴`](prompts/image-gen/GPTImage25-列车乘务员3x3抓拍拼贴.md) | official |
| [`GPTImage25-像素变身SpriteSheet5x6`](prompts/image-gen/GPTImage25-像素变身SpriteSheet5x6.md) | synthetic_codex |
| [`GPTImage25-行星级汉服巨人模板`](prompts/image-gen/GPTImage25-行星级汉服巨人模板.md) | official |
| [`GPTImage25-粘土小火龙定格36帧`](prompts/image-gen/GPTImage25-粘土小火龙定格36帧.md) | official |

索引：[`prompts/image-gen/README.md`](prompts/image-gen/README.md)


## 已出厂（2026-09-18 batch9×5）

图片线 batch9 ×5：每页 = 清理后的评测报告，**内嵌评测成图**（摩托水彩 / 纽约雨天 synthetic 含 MAIN-synthetic + B）。**没跑过 = 不出厂。**

| 文件 | fixture_source |
| --- | --- |
| [`GPTImage25-海崖修道院旅行抓拍肖像`](prompts/image-gen/GPTImage25-海崖修道院旅行抓拍肖像.md) | official |
| [`GPTImage25-摩托水彩旅行手帐插画`](prompts/image-gen/GPTImage25-摩托水彩旅行手帐插画.md) | synthetic_codex |
| [`GPTImage25-纽约雨天水彩人像`](prompts/image-gen/GPTImage25-纽约雨天水彩人像.md) | synthetic_codex |
| [`GPTImage25-东方禅意极简封面海报`](prompts/image-gen/GPTImage25-东方禅意极简封面海报.md) | official |
| [`GPTImage25-城市丝网旅行海报`](prompts/image-gen/GPTImage25-城市丝网旅行海报.md) | official |

索引：[`prompts/image-gen/README.md`](prompts/image-gen/README.md)


## 已出厂（2026-09-21 batch10×5）

图片线 batch10 ×5：每页 = 清理后的评测报告，**内嵌评测成图**（蓝底棚拍 synthetic 含 MAIN-synthetic + B）。**没跑过 = 不出厂。**

| 文件 | fixture_source |
| --- | --- |
| [`GPTImage25-八零年代葡萄牙海滩写真`](prompts/image-gen/GPTImage25-八零年代葡萄牙海滩写真.md) | official |
| [`GPTImage25-蓝底棚拍时尚换人肖像`](prompts/image-gen/GPTImage25-蓝底棚拍时尚换人肖像.md) | synthetic_codex |
| [`GPTImage25-地点旅行扁平海报`](prompts/image-gen/GPTImage25-地点旅行扁平海报.md) | official |
| [`GPTImage25-地标迷你3D立体模型`](prompts/image-gen/GPTImage25-地标迷你3D立体模型.md) | official |
| [`GPTImage25-日系街拍杂志封面时尚海报`](prompts/image-gen/GPTImage25-日系街拍杂志封面时尚海报.md) | official |

索引：[`prompts/image-gen/README.md`](prompts/image-gen/README.md)


## 已出厂（2026-10-21 图片批 ×14）

图片线 ×14：每页 = 清理后的评测报告，**内嵌评测成图**（Codex B 成图）。**没跑过 = 不出厂。**

| 文件 | fixture_source |
| --- | --- |
| [`MJ-少年动作帧导演系统提示-IamEmily2050`](prompts/image-gen/MJ-少年动作帧导演系统提示-IamEmily2050.md) | official |
| [`MJ-思想成句前的透明生物暗场显微-Ror_Fly`](prompts/image-gen/MJ-思想成句前的透明生物暗场显微-Ror_Fly.md) | official |
| [`NanoBanana-人像摄影导演系统提示-IamEmily2050`](prompts/image-gen/NanoBanana-人像摄影导演系统提示-IamEmily2050.md) | official |
| [`图像-冰块包裹护肤品商业静物-0xbisc`](prompts/image-gen/图像-冰块包裹护肤品商业静物-0xbisc.md) | official |
| [`图像-厚涂刮刀枫树湖景油画-churvikv`](prompts/image-gen/图像-厚涂刮刀枫树湖景油画-churvikv.md) | official |
| [`图像-厨房剖面图纸到成品过渡-PatriciaCoelhoV`](prompts/image-gen/图像-厨房剖面图纸到成品过渡-PatriciaCoelhoV.md) | official |
| [`图像-参数方程抽象喷绘分形-icreatelife`](prompts/image-gen/图像-参数方程抽象喷绘分形-icreatelife.md) | official |
| [`图像-发光彩石老城街夜景一点透视-churvikv`](prompts/image-gen/图像-发光彩石老城街夜景一点透视-churvikv.md) | official |
| [`图像-哥特卡通角色插画占位模板-azed_ai`](prompts/image-gen/图像-哥特卡通角色插画占位模板-azed_ai.md) | official |
| [`图像-废铁机甲冒险者3D渲染模板-azed_ai`](prompts/image-gen/图像-废铁机甲冒险者3D渲染模板-azed_ai.md) | official |
| [`图像-提拉米苏白底餐饮摄影-HeyRu0by`](prompts/image-gen/图像-提拉米苏白底餐饮摄影-HeyRu0by.md) | official |
| [`图像-深色木椅低机位棚拍-AiwithAlyar`](prompts/image-gen/图像-深色木椅低机位棚拍-AiwithAlyar.md) | official |
| [`图像-等距微缩世界占位模板-azed_ai`](prompts/image-gen/图像-等距微缩世界占位模板-azed_ai.md) | official |
| [`图像-纸雕浮雕湖畔小屋全景-churvikv`](prompts/image-gen/图像-纸雕浮雕湖畔小屋全景-churvikv.md) | official |

索引：[`prompts/image-gen/README.md`](prompts/image-gen/README.md)


## 已出厂（2026-10-21 文本批 ×45，仅 Codex）

agent-coding ×4、marketing-sales ×10、product-strategy ×10、research-pkm ×7、eval-review ×4、writing ×1、audio ×5、other ×1、image-gen ×3。本批按「Codex 单次通过即收」出厂：**仅 Codex，没有 A/B 对照**；图片线的 3 条为文本型提示，成图不适用。

| 文件 | 分类 |
| --- | --- |
| [`文本-三种代理SOUL身份模板-IBuzovskyi`](prompts/agent-coding/文本-三种代理SOUL身份模板-IBuzovskyi.md) | `agent-coding` |
| [`文本-创意总监五问拷问协议-IamEmily2050`](prompts/agent-coding/文本-创意总监五问拷问协议-IamEmily2050.md) | `agent-coding` |
| [`文本-概念提升式提示词优化器-mattshumer_`](prompts/agent-coding/文本-概念提升式提示词优化器-mattshumer_.md) | `agent-coding` |
| [`文本-逐题访谈生成规格书-svpino`](prompts/agent-coding/文本-逐题访谈生成规格书-svpino.md) | `agent-coding` |
| [`B2B-客诉评论转异议广告角度表-SarahLevinger`](prompts/marketing-sales/B2B-客诉评论转异议广告角度表-SarahLevinger.md) | `marketing-sales` |
| [`外贸-工厂报价单逐行查隐藏成本-ecommilan`](prompts/marketing-sales/外贸-工厂报价单逐行查隐藏成本-ecommilan.md) | `marketing-sales` |
| [`文本-客户原话转创意情报报告七信号-adamtaylorl`](prompts/marketing-sales/文本-客户原话转创意情报报告七信号-adamtaylorl.md) | `marketing-sales` |
| [`文本-电商欢迎邮件序列十条规则审计-ecomchasedimond`](prompts/marketing-sales/文本-电商欢迎邮件序列十条规则审计-ecomchasedimond.md) | `marketing-sales` |
| [`领域-五类买家模拟落地页流失点-free_ai_guides`](prompts/marketing-sales/领域-五类买家模拟落地页流失点-free_ai_guides.md) | `marketing-sales` |
| [`领域-五阶段销售漏斗架构师-alex_prompter`](prompts/marketing-sales/领域-五阶段销售漏斗架构师-alex_prompter.md) | `marketing-sales` |
| [`领域-公司自动调研画像与竞品表-alex_verem`](prompts/marketing-sales/领域-公司自动调研画像与竞品表-alex_verem.md) | `marketing-sales` |
| [`领域-销售会前简报每日例程-chrispisarski`](prompts/marketing-sales/领域-销售会前简报每日例程-chrispisarski.md) | `marketing-sales` |
| [`领域-销售岗面试前公司情报简报-FidelCacheFlow`](prompts/marketing-sales/领域-销售岗面试前公司情报简报-FidelCacheFlow.md) | `marketing-sales` |
| [`领域-销售通话转录自建销售运营大脑-termsheetinator`](prompts/marketing-sales/领域-销售通话转录自建销售运营大脑-termsheetinator.md) | `marketing-sales` |
| [`文本-一人公司十万美元蓝图-sentient_agency`](prompts/product-strategy/文本-一人公司十万美元蓝图-sentient_agency.md) | `product-strategy` |
| [`文本-一人公司教练提问式辅导-DanKulkov`](prompts/product-strategy/文本-一人公司教练提问式辅导-DanKulkov.md) | `product-strategy` |
| [`文本-两面神思维破假二选一-free_ai_guides`](prompts/product-strategy/文本-两面神思维破假二选一-free_ai_guides.md) | `product-strategy` |
| [`文本-毒舌顾问全盘诊断盲点-omoalhajaabiola`](prompts/product-strategy/文本-毒舌顾问全盘诊断盲点-omoalhajaabiola.md) | `product-strategy` |
| [`文本-聊天记录挖掘三个登月项目-IamEmily2050`](prompts/product-strategy/文本-聊天记录挖掘三个登月项目-IamEmily2050.md) | `product-strategy` |
| [`文本-长报告转十分钟幻灯片-alex_prompter`](prompts/product-strategy/文本-长报告转十分钟幻灯片-alex_prompter.md) | `product-strategy` |
| [`领域-商业点子访谈到执行蓝图-eptwts`](prompts/product-strategy/领域-商业点子访谈到执行蓝图-eptwts.md) | `product-strategy` |
| [`领域-福特流水线压缩重复作业工时-free_ai_guides`](prompts/product-strategy/领域-福特流水线压缩重复作业工时-free_ai_guides.md) | `product-strategy` |
| [`领域-行业全景战略分析-thisguyknowsai`](prompts/product-strategy/领域-行业全景战略分析-thisguyknowsai.md) | `product-strategy` |
| [`领域-麦当劳网球场法把重复任务变系统-free_ai_guides`](prompts/product-strategy/领域-麦当劳网球场法把重复任务变系统-free_ai_guides.md) | `product-strategy` |
| [`文本-NotebookLM学习研究二十条-sonalshukla3377`](prompts/research-pkm/文本-NotebookLM学习研究二十条-sonalshukla3377.md) | `research-pkm` |
| [`文本-两段式股票分析师公司报告-RoshanStocks`](prompts/research-pkm/文本-两段式股票分析师公司报告-RoshanStocks.md) | `research-pkm` |
| [`文本-建议背后隐藏激励三段拆解-free_ai_guides`](prompts/research-pkm/文本-建议背后隐藏激励三段拆解-free_ai_guides.md) | `research-pkm` |
| [`文本-第一性原理博弈论苏格拉底导师-PromptLLM`](prompts/research-pkm/文本-第一性原理博弈论苏格拉底导师-PromptLLM.md) | `research-pkm` |
| [`文本-纳瓦尔式苏格拉底提示工程导师-EXM7777`](prompts/research-pkm/文本-纳瓦尔式苏格拉底提示工程导师-EXM7777.md) | `research-pkm` |
| [`文本-让AI追问找盲点九条-iannuttall`](prompts/research-pkm/文本-让AI追问找盲点九条-iannuttall.md) | `research-pkm` |
| [`领域-供应链Excel案例与数据集生成器-_VictorUgwu`](prompts/research-pkm/领域-供应链Excel案例与数据集生成器-_VictorUgwu.md) | `research-pkm` |
| [`文本-先给证据再说完成审稿人-alex_prompter`](prompts/eval-review/文本-先给证据再说完成审稿人-alex_prompter.md) | `eval-review` |
| [`文本-肯尼迪危机室四轮决策压测-free_ai_guides`](prompts/eval-review/文本-肯尼迪危机室四轮决策压测-free_ai_guides.md) | `eval-review` |
| [`领域-AI代理共享权限六项安全审计-Michael_Fenech_`](prompts/eval-review/领域-AI代理共享权限六项安全审计-Michael_Fenech_.md) | `eval-review` |
| [`领域-签约前合同一页风险审阅-RoundtableSpace`](prompts/eval-review/领域-签约前合同一页风险审阅-RoundtableSpace.md) | `eval-review` |
| [`文本-求职面试十二条提示包-sonalshukla3377`](prompts/writing/文本-求职面试十二条提示包-sonalshukla3377.md) | `writing` |
| [`语音-GeminiTTS生日歌宠物家长导演稿-fofrAI`](prompts/audio/语音-GeminiTTS生日歌宠物家长导演稿-fofrAI.md) | `audio` |
| [`语音-Suno分段制作规格歌词系统-0xInk_`](prompts/audio/语音-Suno分段制作规格歌词系统-0xInk_.md) | `audio` |
| [`语音-Suno排除频段与噪声标签-hatolaborvol2`](prompts/audio/语音-Suno排除频段与噪声标签-hatolaborvol2.md) | `audio` |
| [`语音-Suno高音质Remix风格与排除字段-xoMushinxo`](prompts/audio/语音-Suno高音质Remix风格与排除字段-xoMushinxo.md) | `audio` |
| [`语音-爱尔兰酒馆民谣AI卡拉OK歌词-AndalaLabs`](prompts/audio/语音-爱尔兰酒馆民谣AI卡拉OK歌词-AndalaLabs.md) | `audio` |
| [`文本-五区块访谈式财富策略师-TheEcomDaddy`](prompts/other/文本-五区块访谈式财富策略师-TheEcomDaddy.md) | `other` |
| [`文本-原相机选角写实图像提示改写器-IamEmily2050`](prompts/image-gen/文本-原相机选角写实图像提示改写器-IamEmily2050.md) | `image-gen` |
| [`文本-末日都市科幻双模型图像提示导演-IamEmily2050`](prompts/image-gen/文本-末日都市科幻双模型图像提示导演-IamEmily2050.md) | `image-gen` |
| [`文本-逐题追问式图像提示生成器-eptwts`](prompts/image-gen/文本-逐题追问式图像提示生成器-eptwts.md) | `image-gen` |


## 一句话

全渠道就这一句，别自己编：

**白泽 Prompt 评测工厂——没跑过 = 不出厂。**

## License

MIT. 「白泽明理」「Formal eXplainable AI」是 Baize Tech 的牌子。
