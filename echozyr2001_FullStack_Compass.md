# CFC Studio 共学 FullStack Compass 指引
---
# [your name]

## 笔记证明

<!-- Content_START -->

### 02.03

> 学习时间： 60 min

发起这期共学，我主要是想学一点产品设计相关的内容。之前了解过 `figma` 者应该是比较主流的设计工具，但是在搜集资料时发现了 `framer`，这应该是比较新的工具。

我一向是喜欢尝鲜的，于是准备先学习 `framer` 的内容，先从官方的教程开始。

---

设置字体为 `Material Symbols Rounded`，可以将 `gesture` 转换为 ![gesture](./images/echozyr2001/gesture.png)

将 `color` 设置为 `assets`，方便下次使用。

通过点击右上角的加号，可以同时预览多端视图，不需要切换。

![tab1](./images/echozyr2001/tab1.png)

![tab2](./images/echozyr2001/tab2.png)

修改主视图内容可以影响其他视图，同时也可以单独修改其他视图，以满足多端适配。

将多个组件合并为一个 `stack`，可以通过某种特殊的规则操作它，暂时还没搞明白。

一个小时做了这么个鬼东西。

![home](./images/echozyr2001/home.png)

### 02.04

> 学习时间：60(10) min

调整组件 `position` 属性为 `fixed`，可以避免对 `layout` 内 `stack` 的影响。

添加 `frmaer` 并设置 `width` 属性为 `fill`，可以实现 `spacer` 的效果。

![spacer](./images/echozyr2001/spacer.png)

淡入动画需要设置 `Effects` 的 `Appear` 效果。

动画在过程中被截断了，需要将 `Text` 部分的 `Overflow` 设置为 `Visible`。

注意修改之后 `publish` 需要点击 `Update` 才会生效。

最后，成品如下：https://global-lot-758021.framer.app/

### 02.05

> 学习时间：20 min

今天有点忙，只花了一点时间将新手教程浏览完了。

一个好用的插件：`Phosphor` 可以用来查询好看的 `icon`。

一个 `Portfolio` 模版：https://www.framer.com/marketplace/templates/cohesion/

通过 `Chrome` 插件，可以将一个网页直接复制成 `Framer` 项目，cv 工程师狂喜：https://www.framer.com/academy/lessons/html-to-framer 计划明天尝试用来玩玩。

### 02.07

> 学习时间：20 min

尝试之前提到的页面提取插件。

安装插件 `HTML to Framer`，同时注意修改其设置，将“允许访问文件网址”选项打卡才能正常使用。

确实好用，一瞬间就将别人的页面 copy 过来了：https://traditional-surprise-092015.framer.app/

![copy](./images/echozyr2001/copy.png)

最近在忙工作上的事，今天抽空暂时就做到这。

### 02.13

> 学习时间：60 min

使用里一段时间 `framer` 发现它确实有很多实用的特效和动画效果，但是和 `figma` 想比，它有一个很大的缺点：不能导出成代码。

`framer` 只能通过 publish 的方式发布设计的页面，这很方便，但是依赖 `framer` 官方，且缺少可定制性。

接下来还是回到 `figma` 的使用上吧。

---

字体最好设置在 `16px` 到 `18px` 之间

选择一个 `layer` 使用快捷键 `Shift + a` 可以将 `layer` 转换为 `frame`

将 `frame` 的布局设置为 `Hug` 可以自动适应页面布局

快捷键 `opt + cmd + k` 可以将 `frame` 转换为一个组件

---

创建可交互式组件

命名规则 `button/default/unsaved`

> 为什么要使用斜线分隔的命名系统？
>
> 使用斜杠 ( / ) 构造组件名称可让您快速设置组件的属性值。第一个斜杠之前的任何文本都将成为组件名称，并且每个额外的斜杠级别都会创建一个新属性，该属性将应用于组件集中的所有变体。例如，我们的按钮名称为 button/default/unsaved。
>
> 添加一个变体后，组件集将看起来像：
>
> Component set name: button
>
> Property 1: default
>
> Property 2: unsaved
>
> 要完成配置，我们需要更新属性名称并为组件集中的每个变体添加属性值。

![interactive](./images/echozyr2001/interactive.png)

![layer](./images/echozyr2001/layer.png)

![animation](./images/echozyr2001/animation.png)

<!-- Content_END -->
