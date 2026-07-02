# HTML 报告与 PDF 导出说明

该 Skill 默认生成 HTML 品牌诊断报告。PDF 不是第一生成形态，而是由 HTML 报告继续导出。

## 默认流程：HTML-first

推荐流程：

1. 使用 `prompt-template.md` 生成完整 HTML 报告。
2. HTML 结构参考 `report-html-template.html`。
3. 视觉样式引用 `styles/html-report.css`。
4. 在浏览器中打开 HTML 检查版式。
5. 如需 PDF，使用浏览器打印、Playwright 或 Puppeteer 导出。

## 视觉系统

必须遵守：

- 核心视觉：暗色背景 + 玻璃拟态卡片 + 紫/蓝/粉霓虹渐变 + 白色文字
- 整体风格：Dark mode SaaS dashboard
- 视觉语言：Glassmorphism 轻玻璃拟态 + Neon gradient 紫 / 蓝 / 粉
- 背景：`#0B0F1A` / `#0E1117`
- 主渐变：`#6C5CE7 -> #00D2FF -> #FF4ECD`
- 卡片：`rgba(255,255,255,0.06)`
- 边框：`rgba(255,255,255,0.08)`
- 中文字体：`PingFang SC`
- 英文字体：`Inter / Helvetica Neue`
- 标题：Inter 系无衬线 + 极粗标题字重

## 方案 A：浏览器打印为 PDF

推荐流程：

1. 打开生成的 HTML 文件。
2. 检查一页核心结论、诊断依据页、表格、Mermaid 图示和路线图。
3. 使用浏览器打印。
4. 页面选择 A4。
5. 勾选打印背景图形或背景颜色，确保暗色背景、霓虹渐变、玻璃卡片和 glow 被保留。
6. 导出 PDF。

## 方案 B：Playwright / Puppeteer 导出 PDF

伪代码：

```js
import { chromium } from "playwright";
import fs from "node:fs/promises";

const html = await fs.readFile("brand-diagnosis-report.html", "utf8");
const browser = await chromium.launch();
const page = await browser.newPage({
  viewport: { width: 1440, height: 1200 }
});

await page.setContent(html, { waitUntil: "networkidle" });
await page.pdf({
  path: "brand-diagnosis-report.pdf",
  format: "A4",
  printBackground: true,
  preferCSSPageSize: true
});

await browser.close();
```

## 导出前检查清单

- HTML 是否能直接在浏览器打开。
- 是否使用暗色背景、白色/半透明白色文字、紫/蓝/粉霓虹渐变。
- 中文字体是否优先使用 PingFang SC。
- 英文字体是否使用 Inter / Helvetica Neue。
- 标题是否足够粗，并有提案级层级。
- 表格是否为暗色半透明底、细玻璃边框和渐变表头。
- Mermaid 图示是否保留为代码块或已渲染。
- 一页核心结论是否有明显视觉重点。
- 诊断依据页是否清晰。
- 12 个月路线图是否适合横向阅读。
