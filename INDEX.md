# Pattern 选型索引(机器友好)

> 给 AI/自动化用的单文件决策索引。人类请看 [README.md](README.md)。
> 每行:效果 | 难度 | 一句话机制 | 适用场景。选中后读该 pattern 的 README(规格)+ demo.html(参考实现)。

## 全部 pattern

| Pattern | 难度 | 一句话机制 | 适用场景 |
|---|---|---|---|
| [scroll/scroll-reveal](patterns/scroll/scroll-reveal/) | ★ | IntersectionObserver 进视口加 class | 任何内容页入场,最保守的默认选择 |
| [scroll/horizontal-gallery](patterns/scroll/horizontal-gallery/) | ★★ | sticky 容器把纵向滚动映射为横向位移 | 作品集、时间线、产品线陈列 |
| [scroll/scroll-driven-shader](patterns/scroll/scroll-driven-shader/) | ★★★ | 滚动进度 → shader uniform | 3D 叙事站、WebGL 背景联动 |
| [scroll/parallax-cards](patterns/scroll/parallax-cards/) | ★ | 偏移 = 离视口中心距离 × (speed−1) | 漂浮卡片群、贴纸、装饰元素 |
| [scroll/css-scroll-scrub](patterns/scroll/css-scroll-scrub/) | ★ | CSS animation-timeline: scroll()/view(),零 JS | 进度条、可倒放的入场,渐进增强场景 |
| [hover/image-swap](patterns/hover/image-swap/) | ★ | 双图预载 + opacity 切换 | 画廊/头像 hover,成本最低的惊喜 |
| [text/svg-line-draw](patterns/text/svg-line-draw/) | ★★ | stroke-dashoffset 从满到零 | logo 入场、签名、路径叙事 |
| [text/stagger-grid](patterns/text/stagger-grid/) | ★ | delay = 到波心距离 × 单位延迟 | 网格/列表的编排入场,波纹注意力 |
| [text/split-text-reveal](patterns/text/split-text-reveal/) | ★ | 拆 span + 索引延迟 + 行遮罩 | 大标题入场,获奖站标配,三站实测撞车 |
| [text/scroll-marquee](patterns/text/scroll-marquee/) | ★ | rAF 推进 + lerp 滚动速度反馈 | 品牌字幕带、章节分隔、logo 墙 |
| [text/count-up](patterns/text/count-up/) | ★ | IntersectionObserver + rAF easeOut + Intl | 数据统计区,B 端性价比之王 |
| [transitions/theme-shift](patterns/transitions/theme-shift/) | ★ | 滚动触发 data 属性换 CSS 变量 | 长页分章换肤,低成本高感知 |
| [transitions/view-transitions](patterns/transitions/view-transitions/) | ★★ | startViewTransition + 同名共享元素 | 列表↔详情、SPA 路由转场 |
| [transitions/menu-stagger-reveal](patterns/transitions/menu-stagger-reveal/) | ★ | clip-path 遮罩 + 菜单项索引延迟 | 任何站的导航,泛用性最高 |
| [transitions/image-displacement](patterns/transitions/image-displacement/) | ★★★ | 噪声图推 UV 采样坐标再 mix | 图片画廊的高级切换,液态质感 |
| [layout/section-narrative](patterns/layout/section-narrative/) | ★ | 全屏分节 + 编号 + 进退导航 | 宣言页、发布页、故事型官网 |
| [layout/sticky-stack](patterns/layout/sticky-stack/) | ★ | 每卡 sticky top:0,后者压前者 | 功能列表、服务介绍、案例翻牌 |
| [layout/comment-heading](patterns/layout/comment-heading/) | ★ | CSS counter + ::before 注释前缀 | 开发者/极客气质的章节标题 |
| [loading/entry-preloader](patterns/loading/entry-preloader/) | ★★ | 资源预载 + 进度 + Enter 门 | 重资产站开场,兼做声音手势解锁 |
| [loading/ambient-sound-toggle](patterns/loading/ambient-sound-toggle/) | ★★ | 手势解锁 AudioContext + 全局开关 | 体验型站的氛围音 |
| [3d-webgl/canvas-ambient-bg](patterns/3d-webgl/canvas-ambient-bg/) | ★★ | 渐变圆斑 + lighter 叠加 + 正弦漂移 | 任何站的氛围背景层,高级感地板价 |

## 气质套餐(场景 → 组合)

| 场景 | 推荐组合 | 口径 |
|---|---|---|
| B 端 / 机构 / 金融 | comment-heading + count-up + css-scroll-scrub + theme-shift + canvas-ambient-bg | 克制;动效为信息服务,Hashgraph 是参照 |
| 作品集 / 个人站 | entry-preloader + split-text-reveal + menu-stagger-reveal + image-displacement + scroll-marquee | 仪式感;开场和菜单是两大记忆点 |
| 产品发布 / 营销长页 | section-narrative + theme-shift + sticky-stack + parallax-cards + count-up | 滚动叙事;Shopify Editions 是参照 |
| 电商 / 图片画廊 | image-swap + image-displacement + horizontal-gallery + parallax-cards | 图片即内容,动效只加在图上 |
| 3D / 体验型 | scroll-driven-shader + entry-preloader + ambient-sound-toggle + canvas-ambient-bg | 重开场重氛围;Robin/Igloo 是参照 |

## 使用铁律(从库规范继承,不可省)

1. 动画只碰 transform / opacity(clip-path、filter 谨慎)
2. `prefers-reduced-motion` 必须降级到静态终态
3. hover 效果给触屏(点击)和键盘(`:focus-visible`)等价物
4. 声音必须用户手势解锁
5. 强注意力效果(波纹/marquee/displacement)一页一次,别当壁纸
6. 抄机制不抄样式:demo 的配色排版是占位,进项目要跟项目的设计体系走

## 灵感源(cases)

拆解了 10 个获奖站,按气质找参照:[cases/](cases/) — Bruno Simon(游戏化)、Igloo(shader 叙事)、Lando Norris(品牌动效密度)、Hashgraph(克制的机构感)、Shopify Editions(发布页叙事)、Active Theory(上限参考)等,各篇末尾有"运行时实测"。
