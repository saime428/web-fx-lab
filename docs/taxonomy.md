# 效果分类体系

拆解一个网站时,按下面 8 类归档。一个效果只归入"最核心的那一类",跨类时用链接引用。

## 1. 页面切换 `transitions/`

页面/路由之间的过渡。判断标准:效果发生在"从一个视图到另一个视图"的瞬间。

典型:遮罩擦除(wipe)、共享元素过渡(FLIP / View Transitions API)、幕布式上滑、碎片化转场。
常见技术:View Transitions API、Barba.js、GSAP timeline、SPA 路由钩子。

## 2. 滚动动效 `scroll/`

由滚动位置驱动的一切。判断标准:动画进度和 scrollY 绑定。

典型:视差(parallax)、pin 固定 + scrub 擦洗、滚动渐显、水平劫持滚动、进度指示。
常见技术:IntersectionObserver、CSS `animation-timeline: scroll()`、GSAP ScrollTrigger、Lenis/虚拟滚动。

## 3. 悬停交互 `hover/`

指针悬停触发。典型:磁性按钮(magnetic button)、图片 RGB 位移/液态扭曲、下划线动画、卡片 3D 倾斜(tilt)。
常见技术:CSS transition、transform 矩阵、WebGL displacement map。

## 4. 文字动效 `text/`

以文字为主体。典型:逐字/逐行入场(stagger)、乱码解码(scramble)、无限滚动字幕(marquee)、文字描边填充、可变字体动画。
常见技术:SplitType/SplitText、CSS `@keyframes` + stagger delay、variable fonts。

## 5. 3D / WebGL `3d-webgl/`

需要 canvas/WebGL/WebGPU 渲染。典型:粒子系统、shader 噪声背景、3D 模型交互、图片曲面画廊。
常见技术:Three.js、OGL、react-three-fiber、GLSL shader。

## 6. 鼠标跟随 `cursor/`

自定义指针体验。典型:替换光标、延迟拖尾、悬停时光标变形放大、跟随的媒体预览。
常见技术:`mousemove` + lerp 插值、`mix-blend-mode: difference`。

## 7. 加载动画 `loading/`

首屏进入前的体验。典型:百分比进度序章、logo 开场动画、图片逐层显影、骨架屏。

## 8. 布局手法 `layout/`

不是"动画"但决定气质的结构手法。典型:超大字排版(oversized type)、粘性分层(sticky stack)、不对称网格、全屏分屏。

---

## 难度标注

- ★ 纯 CSS 或少量 JS,半小时内可复现
- ★★ 需要动画库(GSAP 等)或较复杂状态管理
- ★★★ 需要 WebGL/shader 知识

## 每个 pattern 必须回答的三个问题

1. **设计意图**:这个效果为页面带来了什么(引导视线/建立节奏/制造惊喜)?
2. **核心机制**:用一句话说清技术原理。
3. **代价**:性能开销、可访问性影响、移动端表现。
