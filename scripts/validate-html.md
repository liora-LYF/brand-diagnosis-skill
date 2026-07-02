# HTML 报告验证指南

生成 HTML 品牌诊断报告后，按以下清单逐项检查，确保报告可直接交付。

## 1. 结构完整性检查

- [ ] 包含 `<!doctype html>` 和 `<html lang="zh-CN">`
- [ ] `<head>` 中包含 `<meta charset="utf-8">` 和 viewport
- [ ] `<title>` 包含品牌名称（如 `XX品牌诊断报告`）
- [ ] 0-9 全部章节都有对应的 `<section class="page-section">`
- [ ] 每个 `<section>` 有正确的 `section-kicker`（如 `00 / EXECUTIVE SUMMARY`）
- [ ] 首屏包含 Hero Section、Metrics Cards、Feature Grid、Workflow Section、Output Preview、CTA Section
- [ ] Chapter 5 标题中的 `{{品牌名称}}` 已替换为实际品牌名称
- [ ] Chapter 5 包含 `5.8 增长卡点地图`
- [ ] 所有 `{{占位符}}` 已被替换，无残留模板变量
- [ ] 报告以 `</html>` 正确闭合

## 2. 样式与视觉检查

- [ ] 所有 `<table>` 有正确的 `<thead>` / `<tbody>` 结构
- [ ] `<th>` 元素使用暗色半透明底和紫/蓝/粉渐变表头（通过 `html-report.css` 的 `th` 样式）
- [ ] Mermaid 图表包裹在 `<pre><code class="language-mermaid">` 中，或已渲染为 SVG
- [ ] `.evidence-strip` 组件包含"依据类型""可信度""是否需补充验证"三个 `<span>`
- [ ] `.pyramid` 组件包含 4 层 `<div>`（表面问题、直接原因、深层根因、战略命题）
- [ ] `.highlight-panel` 用于核心诊断结论，有明显视觉重点
- [ ] `.migration` 组件包含 3 列（当前心智、过渡心智、目标心智）
- [ ] `.bottleneck-map` 组件包含增长阶段、当前卡点、卡点类型、产生原因、增长影响和优先级
- [ ] `.tag` 样式用于标注依据类型标签
- [ ] 使用 Dark mode SaaS dashboard、Glassmorphism、Neon gradient、Card-based layout

## 3. 数据与内容检查

- [ ] 0.2 诊断依据页的每一行与 0.1 核心诊断结论对应
- [ ] 每个核心结论后有依据类型标签（公开数据/竞品观察/用户调研/业务数据/专家判断/待验证假设）
- [ ] 信息不足处已标注"待验证假设"，并说明验证方式
- [ ] 无编造的具体数据（如"市场份额 35.7%""用户增长 120%"等精确数字）
- [ ] 第 6.6 反方论证表格中至少有 4 行，其中至少 1 行"质疑是否成立"为"成立"或"部分成立"
- [ ] 第 6.7 修正判断中至少有 1 条实质性修正（不是"原判断维持不变"）
- [ ] 第 5.8 增长卡点地图没有重复 5.5 断点诊断，而是说明增长卡在哪里、为什么卡、影响什么增长指标
- [ ] 第 9.2 去重检查表对每个高频观点有明确判断（"是"或"否"）
- [ ] 没有写死任何具体品牌的固定分析内容
- [ ] 没有简历相关内容

## 4. 浏览器打开检查

在浏览器中打开 `report.html`，逐项检查：

1. **整体视觉效果**：暗色背景、白色/半透明白色文字、紫/蓝/粉霓虹渐变、玻璃拟态卡片明确可见
2. **字体显示**：中文使用 PingFang SC，英文使用 Inter / Helvetica Neue，标题极粗字重
3. **Mermaid 图表**：所有 Mermaid 代码块是否正确渲染（如未引入 mermaid.js，可添加 CDN：`<script src="https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.min.js"></script>`）
4. **表格溢出**：检查宽表（如竞品转化链路对比表、12 个月路线图）是否在小屏幕上溢出
5. **响应式**：在手机宽度（375px）下，网格布局是否正确折叠为单列
6. **分页预览**：使用浏览器打印预览（Cmd+P），检查：
   - 一页核心结论是否单独成页
   - 各章节分页位置是否合理
   - 暗色背景、霓虹渐变、玻璃卡片和 glow 是否正确保留（勾选"打印背景图形"）
   - 表格是否在页面内完整显示

## 5. 常见问题修复

| 问题 | 可能原因 | 修复方法 |
|---|---|---|
| Mermaid 不渲染 | 未引入 Mermaid JS | 在 `</body>` 前添加 Mermaid CDN 并调用 `mermaid.initialize()` |
| 表格溢出页面 | 列数过多或列名过长 | 缩短列名，或将宽表拆分为多个窄表，或使用 `font-size: 13px` |
| 中文显示为宋体 | CSS font-family 未生效 | 检查 `<link>` 路径是否正确，确认 CSS 中 `--font-cn` 变量值 |
| 打印时渐变或暗色背景丢失 | 浏览器未启用背景打印 | 勾选"打印背景图形"/"背景颜色"。CSS 中已有 `print-color-adjust: exact` |
| 金字塔倒置 | 4 层 div 宽度顺序错误 | 检查 `.pyramid div:nth-child(1-4)` 的 width 值：55% → 70% → 85% → 100% |
| 迁移箭头不显示 | `::after` 伪元素被覆盖 | 检查 `.migration div::after` 的 z-index 或 position 值 |
| 分页位置不当 | section 未正确分页 | 在需要分页的 section 上添加 `page-break-after: always` |

## 6. PDF 导出前最终检查

- [ ] 所有上述检查项通过
- [ ] 选择 A4 纸张大小
- [ ] 勾选"打印背景图形"
- [ ] 页边距设为 14mm
- [ ] 预览至少前 5 页和后 3 页，确认无明显格式问题
- [ ] 导出 PDF，再次打开检查暗色背景、霓虹渐变、表格边框和字体是否正确

## 7. 自动化验证脚本（可选）

如需命令行快速检查，可在报告目录运行：

```bash
# 检查占位符是否全部替换
grep -n '{{' report.html && echo "发现未替换占位符" || echo "占位符检查通过"

# 检查章节完整性
for i in $(seq 0 9); do
  grep -q "section-kicker.*0${i}" report.html || echo "缺少 Chapter ${i} section-kicker"
done

# 统计依据类型标签数量
echo "依据类型标签出现次数："
grep -c 'tag' report.html
```
