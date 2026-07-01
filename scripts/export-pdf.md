# PDF 导出说明

该 Skill 的报告建议先生成 Markdown，再根据使用场景导出为 PDF。PDF 字体优先使用 PingFang SC / 苹方体；如果运行环境没有该字体，请使用 `styles/pdf-style.css` 中的 fallback 字体栈。

## 方案 A：Markdown -> HTML -> PDF

推荐流程：

1. 使用 `prompt-template.md` 或 `report-template.md` 生成完整 Markdown 诊断报告。
2. 使用 Markdown 渲染器将报告转为 HTML。
3. 在 HTML 中引入 `styles/pdf-style.css`。
4. 使用浏览器打印、Playwright 或 Puppeteer 导出 PDF。

注意事项：

- PDF 字体优先使用 PingFang SC。
- 如果系统没有苹方体，使用 CSS fallback：PingFang TC、Hiragino Sans GB、Microsoft YaHei、Noto Sans CJK SC、Arial、sans-serif。
- 页面建议使用 A4。
- 标题层级保持一致。
- 每个大章节建议分页。
- 表格需要避免过宽，必要时拆表或缩短列名。
- 不要在同一页底部留下孤立标题。

## 方案 B：文档工具导出 PDF

推荐流程：

1. 将 Markdown 复制到 Notion、飞书文档、Typora 或 Obsidian。
2. 设置字体为苹方体 / PingFang SC。
3. 页面设置为 A4。
4. 检查标题、表格、分页和重点结论样式。
5. 导出 PDF。

适用场景：

- 需要人工微调版式。
- 需要与团队协作评论。
- 需要插入图表、截图或品牌视觉资产。

## Puppeteer / Playwright 导出思路伪代码

以下是导出思路，不强制创建真实 JS 文件：

```js
import { chromium } from "playwright";
import { marked } from "marked";
import fs from "node:fs/promises";

const markdown = await fs.readFile("report.md", "utf8");
const css = await fs.readFile("brand-diagnosis-skill/styles/pdf-style.css", "utf8");
const body = marked(markdown);

const html = `
<!doctype html>
<html lang="zh-CN">
<head>
  <meta charset="utf-8" />
  <style>${css}</style>
</head>
<body>${body}</body>
</html>
`;

await fs.writeFile("report.html", html);

const browser = await chromium.launch();
const page = await browser.newPage();
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

- 报告是否包含 0-9 的完整章节。
- 每个章节是否先给结论。
- 关键判断是否区分事实、分析、洞察、启示。
- 所有假设、待验证判断和缺失数据是否明确标注。
- 表格是否清晰，不因列数过多影响阅读。
- 字体是否优先使用 PingFang SC / 苹方体。
- 页面是否为 A4，章节分页是否自然。
