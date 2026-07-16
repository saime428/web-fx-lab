# Active Theory — 工作室官网

- **URL**: https://activetheory.net/
- **收录日期**: 2026-07-15
- **一句话印象**: 整个网站就是一个 WebGL 应用:无 JS 直接白屏,DOM 只是挂载点

## 整体气质从哪来

- 自研引擎(业内知名的内部 WebGL 工具链,Hydra 体系)驱动全站
- GPU 粒子/流体质感的过渡,是众多品牌大项目(Google、Pharrell 等)背后的团队
- "作品即简历":官网本身就是技术演示

## 效果清单

| # | 效果描述 | 分类 | 推测技术 | 值得抽成 pattern? |
|---|---|---|---|---|
| 1 | 全 canvas 渲染 UI(文字/布局都在 WebGL) | 3d-webgl | 自研引擎,SDF 文字 | ☐(超纲) |
| 2 | GPU 粒子过渡 | transitions | GPGPU/FBO 粒子 | ✅(简化版) |
| 3 | 页面间无缝 WebGL 转场 | transitions | 单 canvas 场景切换 | ☐ |

## 技术栈侦察

- 完全客户端渲染:fetch 只返回 "Please enable javascript"
- 自研工具链(非 Three.js 生态),需 DevTools 深挖
- 资料: 官网 work 列表 + 各项目的 Awwwards 页面

## 借鉴笔记

代表了炫酷网页的"上限路线":自研引擎、全 canvas。个人项目别学架构,学它的过渡语言——粒子化消散/重组可以用 Three.js 简化复现。

## 运行时实测(Chrome 注入探测,2026-07-15)

- **自研引擎实锤**: `window.Hydra` / `World` / `Global` 全局对象,非 Three.js 生态
- **多线程渲染**: 加载 8 份 `hydra-thread.js`——Web Worker 线程池分担计算
- 单 canvas WebGL2,整页仅 **54 个 DOM 节点**,UI 基本都在 GL 里画
- shader 预编译分发(`compiled.vs`),配 `uil.json` 运行时配置
- 品牌字体 NBArchitektStd(woff2)
