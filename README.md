# web-fx-lab 🧪

> 炫酷网页效果沉淀库:把看到的好网站拆解成可复用的设计方法 + 可运行 Demo。

## 这个仓库怎么用

两个维度沉淀,互相交叉引用:

- **`cases/` 按网站**:每收藏一个好网站,写一篇拆解(它用了哪些效果、什么技术、为什么好看),并链接到对应 pattern。
- **`patterns/` 按效果**:核心资产。每个效果一个文件夹,包含原理文档 `README.md` + 零依赖可直接打开的 `demo.html`。

工作流:发现好网站 → 在 `cases/` 建拆解 → 把其中值得复用的效果抽成 `patterns/` 条目 → 双向链接。

## 效果分类

| 分类 | 目录 | 说明 |
|---|---|---|
| 页面切换 | [`patterns/transitions/`](patterns/transitions/) | 路由过渡、View Transitions、遮罩擦除 |
| 滚动动效 | [`patterns/scroll/`](patterns/scroll/) | 滚动驱动动画、视差、pin/scrub、平滑滚动 |
| 悬停交互 | [`patterns/hover/`](patterns/hover/) | 磁性按钮、图片扭曲、卡片翻转 |
| 文字动效 | [`patterns/text/`](patterns/text/) | 逐字入场、乱码解码、滚动文字带 |
| 3D / WebGL | [`patterns/3d-webgl/`](patterns/3d-webgl/) | Three.js 场景、shader 特效、粒子 |
| 鼠标跟随 | [`patterns/cursor/`](patterns/cursor/) | 自定义光标、拖尾、跟随元素 |
| 加载动画 | [`patterns/loading/`](patterns/loading/) | 进度序章、骨架屏、开场动画 |
| 布局手法 | [`patterns/layout/`](patterns/layout/) | 横向滚动、瀑布流、粘性分层 |

完整分类和判断标准见 [`docs/taxonomy.md`](docs/taxonomy.md)。

## Pattern 索引

| 效果 | 分类 | 难度 | Demo |
|---|---|---|---|
| [滚动渐显 Scroll Reveal](patterns/scroll/scroll-reveal/) | 滚动动效 | ★ | [demo](patterns/scroll/scroll-reveal/demo.html) |
| [横向滚动画廊 Horizontal Gallery](patterns/scroll/horizontal-gallery/) | 滚动动效 | ★★ | [demo](patterns/scroll/horizontal-gallery/demo.html) |
| [Hover 双图切换 Image Swap](patterns/hover/image-swap/) | 悬停交互 | ★ | [demo](patterns/hover/image-swap/demo.html) |
| [SVG 线条绘制 Line Draw](patterns/text/svg-line-draw/) | 文字动效 | ★★ | [demo](patterns/text/svg-line-draw/demo.html) |
| [滚动驱动 Shader](patterns/scroll/scroll-driven-shader/) | 滚动/WebGL | ★★★ | [demo](patterns/scroll/scroll-driven-shader/demo.html) |
| [章节主题突变 Theme Shift](patterns/transitions/theme-shift/) | 页面切换 | ★ | [demo](patterns/transitions/theme-shift/demo.html) |
| [章节式滚动叙事](patterns/layout/section-narrative/) | 布局手法 | ★ | [demo](patterns/layout/section-narrative/demo.html) |
| [氛围音开关](patterns/loading/ambient-sound-toggle/) | 体验层 | ★★ | [demo](patterns/loading/ambient-sound-toggle/demo.html) |
| [Stagger 网格波纹](patterns/text/stagger-grid/) | 编排 | ★ | [demo](patterns/text/stagger-grid/demo.html) |
| [加载序章 Entry Preloader](patterns/loading/entry-preloader/) | 加载动画 | ★★ | [demo](patterns/loading/entry-preloader/demo.html) |

## Case 索引

| 网站 | 亮点 | 开源 | 拆解 |
|---|---|---|---|
| [Bruno Simon 2019](https://2019.bruno-simon.com/) | 物理小车探索式导航 | ✅ [源码](https://github.com/brunosimon/folio-2019) | [拆解](cases/bruno-simon-2019/analysis.md) |
| [Igloo Inc.](https://www.igloo.inc/) | 滚动雕刻冰晶,shader 驱动 UI | 官方 case study | [拆解](cases/igloo-inc/analysis.md) |
| [Messenger](https://messenger.abeto.co/) | 5.7MB 多人小星球游戏 | — | [拆解](cases/messenger/analysis.md) |
| [Lando Norris](https://landonorris.com/) | Webflow+Rive+GSAP 拿 SOTM | — | [拆解](cases/lando-norris/analysis.md) |
| [Anime.js](https://animejs.com/) | 文档即演示,stagger 网格 | ✅ [源码](https://github.com/juliangarnier/anime) | [拆解](cases/animejs/analysis.md) |
| [Robin Payot](https://robinpayot.com/) | 滚动=3D