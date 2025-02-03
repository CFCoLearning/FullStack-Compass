# CFC Studio 共学 FullStack Compass 指引

---

# [Drive_FLY]

> Great success starts with a ordinary beginnings.

## 笔记证明

<!-- Content_START -->

### 02.03

概要：对 CSS 的内容进行了基础面的补充，同时开始观看[Full-Stack Social Media App Tutorial](https://www.youtube.com/watch?v=o080tU3sd0k)了解 React && Next.JS。参与本次共学的目的主要也是围绕这两个方面进行的：更全面地对 CSS 的常用属性有一个了解、额外掌握 Tailwind CSS、了解并使用 React 与 Next.JS 框架，至于产品设计的部分，时间有限，暂时不考虑做过多涉及。

### display

每一个元素根据标签的不同都有默认的`display`值，最为常见的有这些：

- `block`块级元素：开启新的一行、撑满整个容器

  div、p、form、header、footer、section

- `inline`行内元素：在段落中包裹一段内容，不影响段落排版

  span、a

- `inline-block`：

- `none`用于显示或隐藏元素

  > 和`visibility:hidden`不同的是`display`不会占据空间，而前者会。

默认的`display`是可以被重写的，例如可以重写`li`为`inline`用于制作水平菜单。

### width

width 可以限定元素的宽度，避免长段文字占据整个屏幕，用户需要不断将眼睛焦点从左到右移动，配合 margin 的`auto`可以将元素居中展示。

```css
#main {
  width: 600px;
  margin: 0 auto;
}
```

但美中不足的是在浏览器本身宽度小于 width 时会展示滚动条。这时可以将`width`替换为`max-width`，实现在有空间时尽可能变宽，空间不足时则主动收缩。

### 盒模型

![盒模型示意图](https://developer.mozilla.org/zh-CN/docs/Learn_web_development/Core/Styling_basics/Box_model/box-model.png)

元素的 border 与 padding 会撑开 box，也就是说实际上元素的实际宽度或高度是 width/height+padding+border。

通过设置`box-sizing: border-box`，可以启用代替盒模型，盒子实际宽高即设置宽高，不会再向外扩展。

### 边距

padding 和 margin 接收 1~4 个参数，分别对应不同情况：

> padding 创建元素内部的额外空间，margin 创建元素外部的额外空间。

```css
/* 应用于所有边 */
padding: 1em;

/* 上边下边 | 左边右边 */
padding: 5% 10%;

/* 上边 | 左边右边 | 下边 */
padding: 1em 2em 2em;

/* 上边 | 右边 | 下边 | 左边 */
padding: 5px 1em 0 2em;
```

### position

position 的默认值是`static`。设置为`static`的元素不会被`positioned`，即特殊地定位，设置为其他值（relative、fixed、absolute）则反之。

**relative（相对的）**

relative 单独使用与 static 一致，没有额外的效果。当配合 top、right、bottom、left 使用时，可以将元素从原有位置向设置的方向偏移，需要注意的是偏移后空出的部分仍然会被占用，不会被其他元素使用。

**fixed（固定的）**

用于固定在页面的指定位置，需要配合 top、right、bottom、left 使用。如停留在右下角可将 right 与 bottom 设置为 0。元素的右侧及下方与页面的边距即为 0。fixed 元素不占用页面空间。

**absolute（绝对的）**

与 fixed 类似，但定位的对象不是页面整体而是最近的`positioned`祖先（设置为非`static`的元素），若无祖先则相对页面。

### Reference

https://zh.learnlayout.com/
https://learn.shayhowe.com/html-css/

<!-- Content_END -->
