# Lando Norris 官网

- **URL**: https://landonorris.com/
- **收录日期**: 2026-07-15
- **一句话印象**: F1 的速度感翻译成网页语言:荧光绿 × 深色 × 横向冲刺式滚动

## 整体气质从哪来

- 品牌色(McLaren 荧光绿)+ 深底,大面积超大字排版
- 摄影素材统一调色,图片即内容
- 滚动方向变化(纵向→横向画廊→纵向)制造"赛道"节奏

## 效果清单

| # | 效果描述 | 分类 | 推测技术 | 值得抽成 pattern? |
|---|---|---|---|---|
| 1 | 横向滚动照片画廊(带年份标注) | scroll/layout | GSAP ScrollTrigger pin + 水平位移 | ✅ |
| 2 | 头盔画廊 hover 双图切换(base/hover 图对) | hover | 双 webp 预载 + opacity 切换 | ✅ |
| 3 | "tap to lock" 滚动劫持交互 | scroll | 自定义滚动状态机 | ☐ |
| 4 | Rive 矢量动画(合作伙伴/页脚) | loading/text | Rive runtime | ✅ |
| 5 | 菜单展开多图错位入场 | transitions | GSAP stagger | ☐ |

## 技术栈侦察

- 平台: **Webflow**(cdn.prod.website-files.com 实锤)+ 自定义代码
- 动画: GSAP + Rive + WebGL 点缀
- 制作方: [OFF+BRAND](https://www.itsoffbrand.com/our-work/lando-norris),Awwwards SOTD/SOTM + FWA
- 资料: [Awwwards 页面](https://www.awwwards.com/sites/lando-norris)

## 借鉴笔记

证明 Webflow + 自定义 GSAP/Rive 也能拿 SOTM——"炫酷"不一定要从零手写工程。头盔 hover 双图切换是成本极低但效果极好的手法。
