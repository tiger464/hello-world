# hello-world
The first repository

Hi Humans!

Jwang here, I like I like Node.js and Coffeescript (that's what I'm made of!).
I've had tacos on the moon and find them far superior to Earth tacos.
test

## 小工具箱（网页版）

`index.html` 是一个零依赖的单文件工具箱，直接用浏览器打开即可（双击文件，或执行 `start index.html`），不需要服务器、不需要联网。

| 工具 | 说明 |
| --- | --- |
| JSON 格式化 | 美化 / 压缩 / 校验，错误定位到行列 |
| Base64 | 文本与 Base64 互转，UTF-8 与 URL 安全字符集 |
| 时间戳 | 秒 / 毫秒自动识别，时间戳与日期互转 |
| 文本统计 | 字符、中文、单词、行数、字节数、阅读时长 |
| 颜色转换 | HEX / RGB / HSL / CMYK 互换，同色系配色 |
| 密码生成 | 本地生成高强度随机密码，可选字符集 |
| URL 编解码 | encodeURIComponent 编解码 + URL 结构解析 |
| UUID 生成 | 批量生成 v4 UUID |
| 阅读器 | 打开本地 TXT / EPUB / MOBI / AZW3 文本，竖向纸页排版、阅读区约占窗口高度 91%，可调字体 / 字号 / 行距 / 段距 / 背景色，支持单页或双页对开、全屏阅读、翻页与阅读进度（PDF 用浏览器内置查看器打开） |

支持明暗主题、手机 / 桌面响应式布局，快捷键 `1`–`9` 切换工具；所有计算都在浏览器本地完成，不会上传任何数据。

### 拿到别的电脑上用

只有一个 `index.html`，**复制这一个文件**就够（README、Java 文件都不需要），双击用浏览器打开即可，不用装环境、不用起服务器、不用联网。

- 页面里的样式和脚本全部内联，没有任何外部链接、CDN、字体或网络请求；用 `file://` 打开即可（开发验证也都是在 `file://` 下做的）。
- 已验证：Chrome / Edge（Chromium，Windows 全流程实测）；**WebKit（Safari 内核，即 MacBook 上的 Safari）** 实测通过——EPUB 解析、分页、双页对开、目录浮层、全屏与退出、其它小工具均正常，页面零报错。
- 浏览器版本建议 Safari 15+ / Chrome 100+ / Edge 100+ / Firefox 100+。更老的 Safari 没有 `DecompressionStream`，代码里有纯 JS inflate 兜底，EPUB 照样能解压；`clamp()` / `min()` 需要 Safari 13.1+。
- 小差异：PDF 交给浏览器内置查看器（Safari 会直接内嵌显示，被拦时面板里有「新窗口」按钮）；`file://` 下浏览器可能限制剪贴板 API，复制会退回旧式 `execCommand`；宋体 / 楷体在 macOS 上会落到系统自带的宋体-简 / 楷体-简。
- 手机 / 平板：Android 版 Chrome 可以直接打开本地 html；iOS 的 Safari 不能直接打开本地 `file://` 页面，需要放到静态托管（如 GitHub Pages）再访问。

### 阅读器说明

- **TXT**：自动识别 UTF-8（含 BOM）、UTF-16、GB18030（GBK），能识别「第一回 / 第 3 章 / 序章」等标题并生成目录。
- **EPUB**：内置 ZIP + deflate 解压与 OPF/spine/NCX 解析，按 spine 顺序抽取正文，只呈现文字（不渲染插图）。
- **MOBI / AZW3**：内置 PalmDOC 与 HUFF-CDIC 解压，DRM 加密文件会被明确提示。AZW3（KF8）按文件原始顺序解析，个别文件可能章节顺序异常。
- **PDF**：交给浏览器内置 PDF 查看器，可阅读但无法套用字体 / 字号 / 背景等排版设置。
- 阅读区按书本比例排成**竖向纸页**（页高 > 页宽，可在「排版设置 → 页面比例」里切换修长 3:2 / 标准书页 / 宽版），默认单页阅读；点「双页」可把屏幕切分成左右两页**对开**阅读，中间带书脊阴影，页码显示为 `5–6 / 2088 页`。
- 阅读区自动撑满窗口可用高度（1440×900 下约 **91%**，纸页 490×680），底部翻页条始终留在窗口内；页头与工具栏都收成**一条竖向图标工具条**（50px 宽，配色低调），可在「排版设置 → 控制栏位置」里放左或右。目录与排版设置以浮层出现，不占用正文宽度；点「全屏」让阅读器铺满整个浏览器窗口：此时侧边工具条会整体隐藏，只在右上角留一个纯图标按钮退出（也可按 `Esc`）。
- 翻页按钮「‹ 上一页 / 下一页 ›」并排放在阅读区右下角，误触后不用长距离移动鼠标；进度条显示「第 x / y 页 · 百分比」，点击可跳转；`←` `→`、空格、`PageUp` / `PageDown`、鼠标滚轮、触屏左右滑动也都能翻页。排版设置会记在 `localStorage` 里。
