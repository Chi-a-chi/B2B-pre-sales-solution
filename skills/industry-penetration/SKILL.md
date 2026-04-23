---
name: industry-penetration
description: Use this skill for systematic B2B industry analysis that identifies structural opportunities and unmet needs without assuming any particular capability provider's viewpoint. Trigger when the user (1) names a B2B industry and requests deep analysis, penetration, or opportunity mapping, (2) pastes user complaints, discussion threads, or demand signals from a specific industry and asks to identify real vs. fake pain points, (3) asks to evaluate whether structural frictions in an industry represent genuine opportunities, or (4) requests industry landscape mapping with opportunity prioritization. Do NOT use this skill for consumer-facing industry analysis, for analyses pre-scoped to a specific capability provider (e.g., "how should a financial institution enter industry X"), or for simple factual questions about an industry.
---

# 行业穿透与需求发现

## 核心立场

**产出的是客观机会图景,不是某个能力方的切入方案。** 机会清单独立于任何使用者能力输出,不因"某能力方接不住"就把节点从清单里剔除。能力方视角的二次筛选是下游项目的事,不在本 skill 范围内。

需求真伪判断优先于需求规模。警惕"讨论热度高但承担方强势"的过渡性摩擦——声音大不等于真痛点。

## 工作模式识别

接到请求时,先识别走哪条路径:

**演绎推导模式** — 用户指定行业名称、要求深度分析
- 执行三层回答结构(见 `rules/analysis-method.md` §一)
- 完成后强制走七层检查清单(见 `rules/checklist.md`)
- 产出深度分析档,归入 `archive/deep-dives/`

**素材驱动模式** — 用户贴入用户吐槽 / 讨论 / 需求信号
- 先过素材质量,剔除来源/时间/承担方身份不清晰的
- 按九流 + 合规五类映射,不按素材自然话题分类
- 区分情绪吐槽 vs 结构性痛点:多人不同角度提同一件事 = 结构性;单人反复强烈情绪 = 可能是个案
- 标注承担方议价地位:强势方吐槽和弱势方吐槽权重不同
- 产出两份清单:真痛点清单 + 伪痛点清单

**直答模式** — 事实性小问题 / 连续追问细节 / 规则调试
- 简短直接,不走三层结构

两种深度模式可以互喂:素材驱动跑出的行业可以转入演绎模式做深度分析。

## 核心方法(按需加载)

所有深度分析都必须调用这三个文件:

- `rules/analysis-method.md` — 三层回答结构、分析原则、九流框架、合规必选项、演绎法穷举规则、通用表格列
- `rules/checklist.md` — 深度分析完成后的七层检查清单(推导链 / 维度完整性 / 输出质量)
- `rules/handoff.md` — 对话收尾「转接新对话」机制

项目实例配置(用户身份、能力、触达约束、项目专属筛选条件与表格列)在 `instance-config.md`,每次启动先读一遍,避免混用其他项目的配置。

## 深度分析硬性要求

每份深度分析必须满足以下所有约束,不满足的不交付:

**摩擦节点标注**
- 每个节点标注承担方 + 承担方在行业中的议价地位(强势 / 中性 / 弱势)
- 每个节点标注可能的介入者类型(能力直接提供方 / 资源整合方 / 平台方 / 资本方 / 监管)
- 不预选特定介入者

**参与方结构**
- 如有层级,画清层级和各层议价地位:谁强势、谁沉默、谁在承接大部分风险

**摩擦节点排序**
- 必须排优先级,不能并列堆砌
- 排序依据写出来:痛感 / 结构性 vs 过渡性 / 承担方议价地位 / 当期催化强度
- **禁止使用"触达难度""能力匹配度"作为排序依据**——这是能力方视角,违反本 skill 核心立场

**数据可追溯**
- 所有引用数字登记在文件末尾的数据速查表,作为单一事实源

**成品紧凑**
- 填完 `_template.md` 后,删除所有 `[占位]`、`>` 引用式填写指引、方法论术语
- 章节名用具体名词
- 详细填写指引见 `archive/deep-dives/_HOWTO.md`

## 产出沉淀

完成新行业深度分析时:
1. 在 `archive/deep-dives/` 新建文件,按 `_template.md` 填
2. 更新 `archive/industry-map.md` 的「已深入分析」段落
3. 新行业全景穷举,按 `rules/analysis-method.md` §五的演绎法规则,不从已知行业联想

## 对话收尾

用户说「转接新对话」时,按 `rules/handoff.md` 的四段式输出转接文档(核心结论 / 悬置问题 / 上下文关键词 / 规则变更清单)。