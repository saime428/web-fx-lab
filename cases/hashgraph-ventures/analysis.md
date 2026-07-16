# Hashgraph Ventures

- **URL**: https://hashgraphvc.com/
- **收录日期**: 2026-07-15
- **一句话印象**: VC 官网做成宣言式滚动叙事,音效开关暗示这是场"体验"而非官网

## 整体气质从哪来

- 章节编号排版(//01 Manifesto、//02 Investors)建立秩序感
- 首屏 "Scroll down to discover" + 每章 "Back to homepage / Read more" 的探索结构
- 全局声音开关(SOUND ON/OFF)——氛围音是身份的一部分

## 效果清单

| # | 效果描述 | 分类 | 推测技术 | 值得抽成 pattern? |
|---|---|---|---|---|
| 1 | 章节式滚动叙事(编号+进退导航) | scroll/layout | 滚动状态机或全屏分节 | ✅ |
| 2 | 全局氛围音 + 开关 | loading | Web Audio API,手势后播放 | ✅ |
| 3 | 大标题断行强调排版(词组拆行) | text/layout | 排版 + 入场动画 | ☐ |
| 4 | 背景生成式视觉(推测 WebGL) | 3d-webgl | 待 DevTools 验证 | ☐ |

## 技术栈侦察

- CMS: Sanity(cdn.sanity.io 实锤)
- 制作方: [rbxgc](https://rbxgc.co/)(页脚署名)
- 文案本身就是设计:"This team wasn't assembled. It was forged."

## 借鉴笔记

金融/机构类客户的"炫酷"要克制:编号章节+宣言文案+氛围音,不需要重 3D 也有高级感。适合 B 端项目参考。
