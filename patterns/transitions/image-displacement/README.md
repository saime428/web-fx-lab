# Displacement 图片过渡 Image Displacement

- **分类**: 页面切换 / 悬停交互
- **难度**: ★★★
- **见于**: [Robin Payot](../../../cases/robin-payot/analysis.md)(项目画廊 3D 过渡);Codrops 时代经典,获奖站图片画廊的默认语言
- **Demo**: [demo.html](https://saime428.github.io/web-fx-lab/patterns/transitions/image-displacement/demo.html)

## 设计意图

两张图不是淡入淡出,而是像被液体推着变形过去——过渡本身成了材质。这是"网页感"和"体验感"分界线上最著名的一个效果:机制小(一张噪声图),感知大。

## 核心机制

一张灰度噪声图当"位移地图":过渡进度越深,像素被噪声推得越远,两张图的采样坐标反向错开再 mix:

```glsl
float d = texture2D(uDisp, vUv).r;                 // 噪声亮度 = 推力
vec2 uvA = vUv + vec2(d * I * p, 0.0);             // 出场的图:越走越歪
vec2 uvB = vUv - vec2(d * I * (1.0 - p), 0.0);     // 进场的图:越来越正
gl_FragColor = mix(texture2D(uTexA, uvA), texture2D(uTexB, uvB), p);
```

进度 p 用 rAF lerp 逼近目标(hover 进,离开退),缓动感来自 lerp 本身。

## 实现要点

- **噪声图决定气质**:软圆斑=液态,竖条纹=百叶窗,径向=波纹——换贴图不换代码
- 位移只加在一个轴上(demo 是 x)比全向更"有方向感";强度 I 取 0.2~0.5
- demo 的三张纹理全部 canvas 程序化生成,零外部资源;真实项目里图片纹理注意 CORS 和 2 的幂尺寸(或用 CLAMP_TO_EDGE)
- 进度收敛后停掉 rAF(demo 写法),别让 GPU 空转
- 裸 WebGL ~100 行就够,不需要 Three.js;要批量管理多个画廊项再上库(curtains.js 专做这个)

## 代价与注意

- 性能: 单 quad 单 pass,任何 GPU 无感;每个画廊项一个 canvas 时注意上下文数量上限(浏览器 8~16 个),多项共享一个 canvas 分区渲染
- 可访问性: hover 触发要给键盘等价物(focus 同样触发);`prefers-reduced-motion` 直接跳终态(等价于普通图片切换)
- 移动端: 无 hover,改点击切换;demo 已做

## 变体与延伸

- 进度用滚动驱动 = [scroll-driven-shader](../../scroll/scroll-driven-shader/) 的图片版
- RGB 三通道分别偏移(色散)是加强版,再加一点就是故障风(glitch)
- 参考:Codrops《WebGl Image Transitions》系列、hover 距离场变体
