# 章节式滚动叙事 Section Narrative

- **分类**: 布局手法 / 滚动动效
- **难度**: ★
- **见于**: [Hashgraph Ventures](../../../cases/hashgraph-ventures/analysis.md)(//01 Manifesto)、机构/品牌宣言站
- **Demo**: [demo.html](demo.html)

## 设计意图

把长页组织成"编号的章"(//01、//02…),配一个常驻进度导航。读者随时知道"我在故事的哪里、还剩多少"——秩序感本身就是高级感,尤其适合 VC/律所/品牌宣言这类要"稳"的客户。

## 核心机制

侧边固定导航 + IntersectionObserver 高亮当前章:

```js
const io = new IntersectionObserver(es => es.forEach(e => {
  if (e.isIntersecting)
    nav.querySelector(`[href="#${e.target.id}"]`).classList.add('active');
}), { rootMargin: '-50% 0px -50% 0px' });
```

## 实现要点

- 编号排版(//01 风格)用等宽字体或加宽字距,做出"文件编号"的克制感
- 导航点击用 `scrollIntoView({ behavior:'smooth' })`,免费的平滑滚动
- 可选 `scroll-snap-type: y proximity`(不要 mandatory,会绑架滚轮)
- 章内元素配 scroll-reveal 入场,两个 pattern 天然组合

## 代价与注意

- 可访问性: 导航要是真 `<a href="#id">`,键盘/读屏可用;当前章加 `aria-current`
- 章节数 3~6 最佳,超过 8 个编号就失去"章"的重量感
- 移动端侧导航改为顶部细进度条或隐藏

## 变体与延伸

- 导航项带小标题,hover 展开(Hashgraph 的 Read more 结构)
- 编号联动主题突变(见 theme-shift pattern),一章一色
