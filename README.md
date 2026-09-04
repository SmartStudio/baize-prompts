# 白泽 Prompt 评测工厂

**没跑过 = 不出厂。**  
**no eval, no ship.**

网上那堆 prompt 合集，十有八九是 Ctrl+C。这里不是合集，是车间：过闸才上架，没过的继续烂在 Inbox。

你要是已经在 Cursor / Claude Code / Codex 里堆了一地「感觉还行」的提示词，却说不清跑没跑通——就是给你们干的。

| 点这 | |
| --- | --- |
| 四道闸 | [`eval/rubric.md`](eval/rubric.md) |
| 网站 | https://fxai.ai |
| 方法页 | https://fxai.ai/method/ |
| SOP 全文 | https://github.com/SmartStudio/enterprise-ai-sop |

## 怎么玩

1. 先看闸。过不了的，这个仓里不会有。
2. 过了的在 `prompts/<类>/<名字>.md`；更稳的升到 `skills/<名字>/SKILL.md`。
3. 复制走就行。别指望 star 一下 magically 装好。

| 目录 | 干啥的 |
| --- | --- |
| `eval/` | 闸。工厂规矩。 |
| `prompts/agent-coding/` | 写代码的 Agent：交接、编排、审计 |
| `prompts/product-strategy/` | 产品和商业计划 |
| `prompts/research-pkm/` | 研究和知识库 |
| `prompts/marketing-sales/` | 营销销售 |
| `prompts/review/` | 评审验收 |
| `skills/` | 过闸再升格的技能，一夹一个 `SKILL.md` |

每条出厂最少四段：**干啥 / 别啥时候用 / 人必须点头啥 / 原文**。再贴一笔：在哪跑的、哪天、四闸过没过。客户名、密钥、糊墙图视频词——别扔进来。

现在车间是空的。第一条过闸的，验收完再上。

## 一句话

全渠道就这一句，别自己编：

**白泽 Prompt 评测工厂——没跑过 = 不出厂。**

## License

MIT. 「白泽明理」「Formal eXplainable AI」是 Baize Tech 的牌子。
