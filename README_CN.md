<p align="right">
  中文 | <a href="README.md">English</a>
</p>

<p align="center">
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/Logo%20Mark%20Cricle.png" alt="Dokie" width="100" />
</p>

<h1 align="center">Dokie AI PPT Skill</h1>

<p align="center">
  和你的 AI 助手对话，生成专业的 HTML 演示文稿。<br/>
  由 <a href="https://dokie.ai">dokie.ai</a> 出品
</p>

<p align="center">
  当前最强大的 AI 演示文稿 Skill。不只是静态幻灯片 — 而是完全交互式的 HTML 演示文稿，支持入场动画、页面转场、可点击元素、实时图表，甚至 3D 模型。基于 Web 技术构建（Tailwind CSS、Chart.js、GSAP、Font Awesome），远超传统 PPT 工具的能力边界。
</p>

<p align="center">
  <a href="#快速开始">快速开始</a> · <a href="#核心功能">核心功能</a> · <a href="#效果预览">效果预览</a> · <a href="#在-dokie-中深度编辑">深度编辑</a>
</p>

<p align="center">
  支持 Claude Code、Cursor、Codex 等 35+ AI 智能体 — 任何兼容 open skills 生态的智能体均可使用。
</p>

---

## 快速开始

**安装 Skill：**

```bash
npx skills add MYZY-AI/dokie-ai-ppt
```

**让你的 AI 助手开始创建演示文稿：**

```
"帮我做一个季度汇报 PPT"
"创建一个创业融资路演 deck"
"做一个产品发布会演示文稿，要有创意动画"
```

Skill 会引导你的 AI 助手一步步完成 — 收集需求、选择主题、生成大纲、制作幻灯片、预览效果。每一步都会等你确认，你始终掌控全局。

<details>
<summary>指定智能体安装</summary>

```bash
npx skills add MYZY-AI/dokie-ai-ppt -a claude-code
npx skills add MYZY-AI/dokie-ai-ppt -a cursor
```

</details>

<details>
<summary>前置依赖</summary>

```bash
npx dokie-cli themes    # 验证 Dokie CLI 是否可用
```

</details>

---

## 核心功能

### 25+ 主题

覆盖商务、医疗、科技、教育、创意等多种风格 — 选择内置主题或自定义颜色、字体、装饰元素，打造你的品牌风格。每个主题都包含完整的样式体系：字体排版、配色方案、背景和装饰元素。

<p align="center">
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/dokietheme.png" width="260" />
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/market.png" width="260" />
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/medi.png" width="260" />
</p>
<p align="center">
  <em>左：Dokie 品牌主题 &nbsp;·&nbsp; 中：市场分析主题 &nbsp;·&nbsp; 右：医疗专业主题</em>
</p>

<p align="center">
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/qinghua.png" width="260" />
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/trends.png" width="260" />
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/yellow.png" width="260" />
</p>
<p align="center">
  <em>左：青花瓷国风主题 &nbsp;·&nbsp; 中：趋势数据主题 &nbsp;·&nbsp; 右：暖色创意主题</em>
</p>

### 10+ 图表类型

柱状图、折线图、饼图、雷达图、气泡图、金字塔图、漏斗图、时间线、流程图、象限图 — 全部在 HTML 中实时渲染，基于 Chart.js 驱动。不是静态截图，而是真正的交互式图表。数据需要更新？改个数字刷新就好。

<p align="center">
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/005.png" width="260" />
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/006.png" width="260" />
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/007.png" width="260" />
</p>
<p align="center">
  <em>柱状图 · 折线图 · 环形图 &nbsp;|&nbsp; 雷达图 · 气泡图 &nbsp;|&nbsp; 漏斗图 · 金字塔图</em>
</p>
<p align="center">
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/008.png" width="260" />
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/009.png" width="260" />
</p>
<p align="center">
  <em>时间线 · 象限图 &nbsp;|&nbsp; 流程图 · 循环图</em>
</p>

### 动画与交互

这不是普通的"淡入淡出"演示工具。每一页幻灯片都是一个真实的网页，意味着你可以使用 Web 动画和交互的全部能力：

- **入场动画** — 元素飞入、渐现、缩放、旋转、模糊 — 每个都有精确的时序和缓动曲线
- **页面转场** — 幻灯片之间的流畅过渡，带来电影感的视觉流
- **交互元素** — 可点击的标签页、悬停效果、可展开区域 — 观众可以探索，而不只是观看
- **滚动触发效果** — 内容随滚动逐步展现，营造叙事节奏
- **视差与分层运动** — 平面幻灯片无法实现的纵深感和空间感
- **3D 模型与高级视觉** — 嵌入 3D 物体、粒子效果等 — 浏览器就是你的画布

提供 3 种动画强度可选：

- **Minimal（极简）** — 淡入与滑动。干净专业，适合企业汇报等内容主导的场景。
- **Balanced（均衡）** — 适度的运动加上交错时序。增加视觉节奏但不喧宾夺主，适合产品演示和团队会议。
- **Creative（创意）** — 完整的电影级体验。滚动触发、视差分层、动态转场。专为需要震撼效果的路演和发布会打造，堪比 Awwwards 级别的动效设计。

<p align="center">
  <a href="https://www.dokie.ai/presentation/share/azVPjJDBaPgM">
    <img src="https://github.com/user-attachments/assets/85a9a3a3-5054-48b4-826f-209e3456e0f9" width="680" />
  </a>
</p>
<p align="center">
  <em>Creative 动画风格 — 电影感入场动效与多层转场。<a href="https://www.dokie.ai/presentation/share/azVPjJDBaPgM">点击查看在线演示 →</a></em>
</p>

### 自动质量检查

生成完成后，Skill 会自动检查每一页幻灯片：
- **内容溢出** — 文字或元素超出幻灯片边界
- **图表渲染** — 确保所有数据可视化正确显示
- **主题一致性** — 验证字体、颜色、间距是否符合所选主题

问题在你发现之前就已修复，第一次预览就能拿到完成度很高的成品。

---

## 效果预览

生成的幻灯片可以即时预览。预览服务器提供两个链接 — 一个本地链接供你查看，一个公网链接可以直接分享给任何人：

```
✓ Server running:

    ➜  Local:   http://localhost:3456
    ➜  Public:  https://your-presentation.trycloudflare.com
```

公网链接可以快速分享给任何人预览，无需安装。如果需要长期有效的分享链接，可以将演示文稿上传到 [dokie.ai](https://dokie.ai)，获取稳定的分享地址。

<p align="center">
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/preview.jpg" width="680" />
</p>
<p align="center">
  <em>内置预览 — 浏览所有幻灯片、检查布局、通过公网链接分享给团队</em>
</p>

---

## 在 Dokie 中深度编辑

想要更精细的控制？生成的每一份演示文稿都可以免费在 [dokie.ai](https://dokie.ai) 中打开。在 Dokie 编辑器里，你可以：

- 通过拖拽编辑器精调布局、文字和视觉细节
- 在颗粒度级别调整样式、颜色和字体
- 导出为 **PDF**、**PPTX**、**图片** 等多种格式

从 AI 生成到像素级精修 — 一套完整的工作流。

<p align="center">
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/edit.png" width="330" />
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/editdaochu.png" width="330" />
</p>
<p align="center">
  <em>左：在 Dokie 编辑器中精细调整 &nbsp;·&nbsp; 右：导出为 PDF、PPTX 等格式</em>
</p>

---

<p align="center">
  <a href="https://dokie.ai">dokie.ai</a> · MIT License
</p>
