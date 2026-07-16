# Robin Payot — 个人作品集

- **URL**: https://robinpayot.com/
- **收录日期**: 2026-07-15
- **一句话印象**: 把作品集做成一场 3D 巡游,"Scroll to explore" 式沉浸叙事

## 整体气质从哪来

- 整站是一个连续的 WebGL 3D 场景,滚动即"推进镜头",没有传统分页感
- 配合音效设计(sound design),视听同步强化沉浸
- 明确"desktop first":移动端直接提示旋转/降级,不迁就

## 效果清单

| # | 效果描述 | 分类 | 推测技术 | 值得抽成 pattern? |
|---|---|---|---|---|
| 1 | 滚动驱动 3D 场景推进 | scroll / 3d-webgl | Three.js + 滚动进度映射相机 | ✅ |
| 2 | Wind Waker 风格水面 shader | 3d-webgl | GLSL 自定义 shader | ☐ |
| 3 | 进入动画 "Enter" 序章(带声音授权) | loading | 用户手势后启动 AudioContext | ✅ |
| 4 | 项目画廊 3D 过渡 | transitions | WebGL 纹理过渡 | ☐ |

## 技术栈侦察

- 渲染: WebGL / Three.js(meta keywords 直接写了 threejs)
- 作者花 8 个月业余时间完成,Awwwards + FWA 双 SOTD
- 资料: [Codrops Developer Spotlight](https://tympanus.net/codrops/2025/06/12/developer-spotlight-robin-payot/)、[three.js forum showcase](https://discourse.threejs.org/t/portfolio-robin-payot/42559)

## 借鉴笔记

"滚动=镜头推进"是 3D 作品集最通用的叙事骨架;声音需要用户手势触发,所以"Enter"按钮既是仪式感也是技术需要。
