# 🩺 医学文献智能双语阅读器 (Medical Literature Intelligent Bilingual Reader)

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white)
![PDF.js](https://img.shields.io/badge/PDF.js-3.11-8C827A?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)

一款专为医学生、临床医生及生物医药研究人员设计的**轻量级、纯前端、免 API Key** 的医学文献智能双语点读系统。

解决传统阅读医学 PDF 时**图表排版错乱、专业医学术语发音困难、长难词构词难记、频繁切屏查词**等痛点，提供沉浸式的视听结合与构词记忆自学环境。

---

## ✨ 核心特性 (Features)

* **📄 100% 原生 PDF 排版保留（本地离线解析）**  
  内置 Mozilla `PDF.js` 渲染引擎，直接在前端画布（Canvas）绘制原版文献。零失真保留所有解剖图、数据统计表、化学分子式与复杂排版。文件仅在本地内存解析，**绝不外传，保障文献数据与隐私安全**。
* **🆓 全程免 Key，开箱即用 (Zero Configuration)**  
  无需注册第三方账户或填写高昂的 API Key：
  * **全文翻译**：通过安全映射机制，免费调用谷歌翻译公用稳定接口，实现整句/段落级精准临床术语汉化。
  * **自然发音**：调用现代浏览器底层神经语音合成（Web Speech API），完美复现 Microsoft Natural/Samantha 等高保真学术英语发音。
* **🔍 三通道核心词汇解析 (Three-Channel Analysis)**  
  鼠标单击任意单词，即刻触多维解析：
  * **【词根拆解】**：内置超过 120 项拉丁语/希腊语高频临床前缀、词根与病理后缀数据库，将长难词可视化拆解为 `前缀 ➔ 词根 ➔ 后缀`（例如：`hyper-(高) ➔ chole-(胆) ➔ sterol-(固醇) ➔ emia-(血症)`）。
  * **【中文释义】**：同步抓取谷歌翻译精准医学术语汉化结果。
  * **【英文原版】**：异步对接 Dictionary API，拉取国际音标（IPA）与权威英英简明释义。
* **🔊 慢速发音与自学闭环 (0.75x Slow-speed TTS & Anki Export)**  
  针对长难医学名词，默认开启 **0.75 倍速慢速连读**，帮助大脑建立清晰的“音形义”神经绑定。点击一键加入生词本，支持导出标准 CSV 格式表格（自动分列：`单词 | 音标 | 词根拆解 | 中文释义 | 英文释义`），无缝导入 **Anki** 或 **Excel** 制作翻转记忆卡片。
* **🎛️ 全方位自由拖拽分栏 (Fully Resizable Layout)**  
  * **横向调整**：左右面板宽度支持 20% ~ 80% 自由拉伸，左侧看大图，右侧看精细分析。
  * **纵向调整**：右侧「段落对照区」、「词汇解析卡片」与「发音生词本」三块区域高度均可上下拉动，根据工作流动态定制视野。

---

## 🚀 快速开始 (Quick Start)

本项目为**零依赖的单个静态 HTML 文件**，无需 Node.js 环境，无需安装任何依赖或启动本地服务器。

### 方式一：直接使用在线网页（推荐）
点击访问 GitHub Pages 部署的在线演示链接：  
👉 **[在线阅读器地址 https://<你的用户名>.github.io/medical-bilingual-reader/](https://<你的用户名>.github.io/medical-bilingual-reader/)**

### 方式二：电脑本地离线运行
1. 点击项目主页绿色的 `Code` 按钮，选择 `Download ZIP` 下载全部文件。
2. 解压文件夹，进入后用任何现代浏览器（强烈推荐 **Microsoft Edge** 或 **Google Chrome** 以获取最好的神经网络语音能力）双击打开 `index.html` 即可。

---

## 📖 日常使用工作流 (Workflow)

```text
[导入PDF文献] ──► [左侧保持原版图表阅读] ──► [遇到长难词单击点读]
                                                    │
    ┌───────────────────────────────────────────────┘
    ▼
[中间弹出：慢速发音 + 拉丁/希腊词根剖析 + 中英双语解释]
    │
    ├─► 遇到长难句：点击右侧 "🌐 显示/隐藏中文翻译" 或 "🔊 朗读整句"
    │
    └─► 核心词汇：点击 "+ 加入生词记忆本" ──► 学习结束一键导出 Anki/CSV
```

1. 载入文件：点击左上角蓝色的 📁 上传医学 PDF 按钮，选择本地文献。

2. 段落精读：视线移至右侧【当前页平行双语】区，这里已按句切分好文本，点击对应段落下方的“显示中文翻译”获取段落大意。

3. 词根攻克：在左侧画布或右侧文本中单击如 atherosclerosis（动脉粥样硬化），中间面板会立马语音展示音标，并展示词根路径 athero-(粉瘤) ➔ scler-(硬) ➔ osis-(病态)。

4. 视听同步：点击右上角调整语速为 0.75x (慢速记忆) 或 1.0x (正常语速)，对难词反复听读模拟。

5. 卡片复习：每天文献阅读完后，点击右下角生词本的 导出复习 (Excel/Anki)，将积累的专业词汇同步至你的记忆软件中。

🛠️ 技术栈 (Tech Stack)
UI 与排版：HTML5, CSS3, Tailwind CSS (经 CDN 动态引入)

PDF 解析引擎：PDF.js v3.11

发音合成：HTML5 Web Speech Synthesis API

接口服务：Google Translate Public Endpoint, Dictionary API v2

数据持久化：Browser LocalStorage API

🤝 贡献与建议 (Contributing)
欢迎对本开源工具提出改进建议或提交 Pull Request！
如果你觉得这个小工具对你的临床学习和论文阅读有所帮助，欢迎点亮右上角的 ⭐️ Star 支持！