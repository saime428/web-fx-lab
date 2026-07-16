# Igloo Inc.(Pudgy Penguins 母公司)

- **URL**: https://www.igloo.inc/
- **收录日期**: 2026-07-15
- **一句话印象**: 滚动雕刻冰晶:程序化生成 + shader 驱动 UI 的教科书

## 整体气质从哪来

- 全站一块"冰":晶体生长算法 + 体积数据渲染,材质即品牌
- UI 元素也走 shader(shader-driven UI),2D/3D 边界消失
- 滚动是唯一交互,但每一屏都有新的物质形态

## 效果清单

| # | 效果描述 | 分类 | 推测技术 | 值得抽成 pattern? |
|---|---|---|---|---|
| 1 | 滚动驱动 3D 场景变换(冰晶生长) | scroll/3d-webgl | 滚动进度 → shader uniform | ✅ |
| 2 | 程序化晶体生成 | 3d-webgl | 晶体生长算法 + 体积数据 | ☐(太专) |
| 3 | shader 驱动的 UI 过渡 | transitions | 全屏 quad shader | ✅ |
| 4 | 冰面折射/次表面散射质感 | 3d-webgl | 自定义 GLSL,raymarching | ☐ |

## 技术栈侦察

- 技术: Three.js + three-mesh-bvh + **Svelte** + GSAP + Vite + vanilla JS
- 制作方: **Abeto**(和 Messenger 同一工作室)× Bureaux
- 资料: [Awwwards Case Study](https://www.awwwards.com/igloo-inc-case-study.html)(官方拆解,必读)、[three.js forum](https://discourse.threejs.org/t/landing-site-igloo-inc/67249)、[WebGPU.com 分析](https://www.webgpu.com/showcase/igloo-inc-procedural-crystals/)

## 借鉴笔记

Awwwards 官方 case study 详细讲了晶体算法和 shader UI,是本库最值得精读的一手资料。"滚动进度直接喂给 shader uniform" 是 3D 叙事站的核心管线。
