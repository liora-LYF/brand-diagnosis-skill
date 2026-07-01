---
name: brand-diagnosis-skill
description: Generate consulting-style brand diagnosis reports for brand marketing leaders, senior brand managers, brand strategy consultants, growth marketing leaders, content marketing leaders, IP commercialization owners, new business brand owners, and annual brand planning owners. Use when the user asks for brand diagnosis, brand audit, brand full-case diagnosis layer, industry/competitor/user/brand self-analysis, core problem extraction, opportunity judgment, strategic implications, PDF-ready brand diagnosis reports, or a reusable Chinese consulting report structure for a company, product, service, IP, or business line.
---

# 品牌诊断 Skill

## 使用目标

使用该 Skill 生成咨询公司风格的中文品牌诊断报告，完成品牌全案中的「品牌诊断层」。输出必须以问题导向、结论先行、事实支撑、分析推导、战略启示为主，而不是简单信息整理。

该 Skill 适合用于：

- 品牌全案前期诊断
- 年度品牌规划前
- 品牌升级或重新定位前
- 新业务品牌启动前
- Campaign、内容矩阵、渠道策略、用户增长策略制定前
- IP 商业化规划前
- 品牌增长乏力、认知模糊、竞品压力较大、转化效率低时

## 使用流程

1. 先读取 `skill.md`，按其中的输入字段、核心处理逻辑、咨询式表达原则和 0-9 章报告结构执行。
2. 用户只给品牌名称或少量信息时，先基于公开信息和合理假设输出，并明确标注“基于公开信息判断”“假设”“待验证”；不要编造具体数据。
3. 如果用户要求完整报告，必须输出 0-9 章完整结构，不要只给执行摘要或策略短评。
4. 如果用户要求可复用提示词，读取并使用 `prompt-template.md`。
5. 如果用户要求报告模板或要生成可填充文档，读取并使用 `report-template.md`。
6. 如果用户要求校验输出结构，读取并对齐 `output-schema.md`。
7. 如果用户要求 PDF 导出，读取 `scripts/export-pdf.md`，并使用 `styles/pdf-style.css` 的 A4 与 PingFang SC 字体样式要求。
8. 如果用户需要示例，参考 `examples/huaxiaozhu-brand-diagnosis-example.md` 的输入与片段结构。

## 必须遵守的输出原则

- 所有面向用户的正文使用中文。
- 每个章节先给结论，再给分析。
- 围绕品牌当前问题展开，不泛泛做行业、竞品或用户资料整理。
- 关键判断尽量按“事实 - 分析 - 洞察 - 启示”展开。
- 核心问题必须 MECE，区分表面问题、直接原因、深层根因和业务影响。
- 机会点必须有优先级，区分短期、中期、长期。
- 最后必须连接后续品牌战略层、品牌策略层、创意层和执行层。
- 缺少数据时必须说明“基于现有信息判断”或“待验证”，不得虚构调研结论、下载量、DAU、市场份额、收入等具体数据。
- 不加入“简历成果表达”相关内容，不输出“可写进简历的成果表达”。

## 完整报告结构

完整品牌诊断报告必须包含以下章节：

0. 执行摘要
1. 诊断目标与核心假设
2. 行业环境分析
3. 竞争格局分析
4. 用户洞察分析
5. 品牌现状诊断
6. 核心问题提炼
7. 机会点判断
8. 战略启示与下一步建议
9. 附录

每个章节的二级、三级标题和表格要求以 `skill.md` 和 `report-template.md` 为准。

## PDF 导出要求

当用户要求 PDF 或 PDF-ready 报告时：

- 先生成 Markdown 报告。
- 可通过 Markdown -> HTML -> PDF 工作流导出。
- HTML/PDF 样式使用 `styles/pdf-style.css`。
- 字体优先级必须为：PingFang SC、PingFang TC、Hiragino Sans GB、Microsoft YaHei、Noto Sans CJK SC、Arial、sans-serif。
- 页面使用 A4，标题层级清晰，表格避免过宽，每个大章节建议分页。
