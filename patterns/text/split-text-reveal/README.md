# 逐行/逐字拆分入场 Split Text Reveal

- **分类**: 文字动效
- **难度**: ★
- **见于**: [Lando Norris](../../../cases/lando-norris/analysis.md)(`high-line-reveal` 逐行 clip)、[Hashgraph Ventures](../../../cases/hashgraph-ventures/analysis.md)(`text-splitter`)、[Robin Payot](../../../cases/robin-payot/analysis.md)(`split-text__letter` 逐字)——三站实测撞车,行业通用语言
- **Demo**: [demo.html](https://saime428.github.io/web-fx-lab/patterns/text/split-text-reveal/demo.html)

## 设计意图

标题不是"出现",而是"到场"。逐行从遮罩里升起 = 庄重;逐字错落浮现 = 轻盈。它把静态排版变成时间上的排版,是获奖站几乎人手一份的开场白。

## 核心机制

把文字拆成 span,用索引换延迟;逐行版外层套一个 `overflow: hidden` 的遮罩:

```js
// 逐字:索引 → 延迟
[...word].forEach((ch, i) => {
  span.style.transitionDelay = `${i * 28}ms`;
});
```

```css
.line { overflow: hidden; }                    /* 遮罩 */
.line > .inner { transform: translateY(110%); }
.show .line > .inner { transform: none; transition: .8s cubic-bezier(.22,1,.36,1); }
```

## 实现要点

- **逐行拆分不要用 JS 量**:换行位置随视口变(SplitType 靠 resize 重拆),零依赖场景直接在 HTML 里手工分行,反而稳
- 逐字拆分后原文本对屏幕阅读器变成碎片:父元素给 `aria-label` 原文,span 层 `aria-hidden="true"`
- 触发用 IntersectionObserver(阈值 ~0.4),进视口才播,只播一次
- 逐字延迟 20~40ms/字,逐行 80~120ms/行;曲线用 ease-out 家族,入场要"减速抵达"
- 中文逐字比英文更好看(方块字等宽);英文按词拆比按字母拆更易读

## 代价与注意

- 性能: 只动 transform/opacity,几百字无压力;整页别超过 2-3 处,到处都是就没有"到场"了
- 可访问性: `prefers-reduced-motion` 直接显示终态;aria 处理见上
- 移动端: 正常;注意手工分行在窄屏是否溢出(demo 用 clamp 字号规避)

## 变体与延伸

- 遮罩内加轻微 rotate(3deg→0)更有"翻起"感(Lando 用法)
- 逐字 + [stagger-grid](../stagger-grid/) 的距离思路 = 从鼠标处扩散的文字波
- 库方案: SplitType(免费)/ GSAP SplitText,自动处理 resize 重拆
