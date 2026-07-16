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

## Case 索引

| 网站 | 亮点 | 拆解 |
|---|---|---|
| (示例) | 见模板用法 | [`cases/_example/`](cases/_example/analysis.md) |

## 模板

- 网站拆解:[`docs/templates/case-analysis.md`](docs/templates/case-analysis.md)
- 效果条目:[`docs/templates/pattern.md`](docs/templates/pattern.md)
- 常用技术雷达:[`docs/tech-radar.md`](docs/tech-radar.md)

## 收录标准

1. 效果必须能说清"为什么好看"(设计意图),不只是"看着炫"。
2. Demo 尽量零依赖、单文件、双击可打开;确需库时在文档中注明版本。
3. 每个 pattern 标注:核心技术、性能注意点、可访问性影响(如 `prefers-reduced-motion`)。

## License

MIT
