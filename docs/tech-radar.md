# 技术雷达

拆解网站时常遇到的技术,按"先学哪个"排序。

## 必会(大多数炫酷效果的地基)

| 技术 | 用途 | 备注 |
|---|---|---|
| CSS transform / transition / @keyframes | 一切动画的基础 | 只动 transform 和 opacity,不触发重排 |
| IntersectionObserver | 滚动渐显、懒加载触发 | 零依赖滚动动效首选 |
| requestAnimationFrame + lerp | 平滑跟随、惯性 | `x += (target - x) * 0.1` 是无数拖尾效果的核心 |
| View Transitions API | 页面/状态切换 | 原生共享元素过渡,渐进增强使用 |
| CSS scroll-driven animations | `animation-timeline: scroll()` | 新特性,可替代部分 ScrollTrigger 场景 |

## 高频库

| 库 | 场景 | 何时用 |
|---|---|---|
| GSAP (+ ScrollTrigger) | 复杂时间线、滚动驱动 | 效果编排超过 3 个关键帧时 |
| Lenis | 平滑滚动 | 几乎所有"高级感"网站都在用 |
| Three.js / OGL | WebGL 3D | 有 3D 或 shader 需求 |
| SplitType | 文字拆分 | 逐字动画前置步骤 |
| Lottie | 设计师产出的矢量动画 | AE 动画落地 |
| Swup / Barba.js | MPA 页面过渡 | 非 SPA 项目的转场 |

## 侦察工具(怎么看别人用了什么)

- DevTools → Network → JS 文件名里搜 `gsap`、`three`、`lenis`
- Console 输入 `window.gsap`、`window.THREE` 试探全局变量
- Elements 里看 canvas 元素 → 有 WebGL context 基本就是 Three.js/OGL/shader
- [Wappalyzer](https://www.wappalyzer.com/) 浏览器插件识别框架

## 灵感来源

- [Awwwards](https://www.awwwards.com/) / [Godly](https://godly.website/) / [Minimal Gallery](https://minimal.gallery/)
- [Codrops](https://tympanus.net/codrops/) — 大量效果教程 + 源码
- [CodePen](https://codepen.io/) — 搜效果关键词直接看实现
