# CFC Studio 共学 FullStack Compass 指引

---

# RisingGalaxy

> I'm a rather lazy person, but I'm willing to learn new things.

## Note

<!-- Content_START -->

### 02.04

> Learning time: About `5` hours

---

> **简单认识**
>
> React 是一个用于构建交互式用户界面的 JavaScript 库。
>
> Next.js 是一个 React 框架。

有点迷茫，看文档也有点不知从何开始，所以我就先跟着 Youtube 上的 [Full-Stack Social Media App Tutorial](https://www.youtube.com/watch?v=o080tU3sd0k) 做着走吧。

---

`src/app` 下创建了 `profile/[id]/page.tsx`，这样访问 `/profile/[anyId]` 时都能够访问到这个页面。

---

跟着视频做，已经把 Clerk 用户认证引入了，为了避免不必要的麻烦，学习期间我还是先以教程视频中的版本开发吧。等到学习完成后实际开发过程中再去修补一些版本变化产生的不同？就视频中的版本 `"@clerk/nextjs": "^5.1.4"` 与当前学习时的最新版本相比已经差了一个大版本，如 Clerk 官方给的教程文档中对于 `SignIn` 组件已经是将登录和注册合并到一起的，而老版本是分开来写的，时间有限就先不在这种细节上深究了，以教程视频版本为主吧，新内容了解即可，实际开发时可以多根据官方教程来学习。

### 02.05

> Learning time: About `2.5` hours

---

时间有限今天仅跟着视频完成了 `HomePage` 的一部分设计：

![HomePage 半成品](images/RisingGalaxy/0205-1-1-PostCardDesign.png)

说是设计实际上还是在跟着视频做，不过做的过程中还是了解到一些小知识，之后设计自己想做的产品的时候再温习温习吧 ~~(Lazy)~~

### 02.08

> Learning time: About `5` hours

---

今天也是在继续跟着视频做了一会儿，其中的有个 `flex-1` 使用到了好几次，就去了解了下，这是由 [Tailwindcss](https://tailwindcss.com/docs/flex) 提供的预定义的类名，等同于为该元素挂上了 `​flex: 1`​。

`​​flex​` 是 CSS 中一个常用的 [简写属性](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Shorthand_properties)，其实际上是 [`flex-grow`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex-grow)​、[`flex-shrink`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex-shrink)​​、[`flex-basis`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex-basis)​ 三个属性的简写，而 `​flex: 1`​ 则等同于 `​flex: 1 1 0%`​。

- `​flex-grow: 1`​：定义项目的放大比例，值为 1 表示如果存在剩余空间，项目将按比例放大。
- `​flex-shrink: 1`​：定义项目的缩小比例，值为 1 表示如果空间不足，项目将按比例缩小。
- `​flex-basis: 0%`​：定义在分配多余空间之前，项目占据的主轴空间，值为 0% 表示项目的初始大小为 0。

#### `flex: auto`​ 与 ​`flex: 1`​ 的区别

---

在 CSS Flex 布局中，`flex: 1` 和 `flex: auto` 都用于定义弹性项目如何在容器中分配空间，但它们的行为有所不同，主要区别在于 `flex-basis` 属性的取值：

- **​`flex: 1`​**：等同于 `flex: 1 1 0%`，其中 `flex-basis` 为 `0%`。这意味着元素的初始大小被设为 0，在分配剩余空间时，各元素按比例平分剩余空间，而不考虑其内容的固有大小。
- **​`flex: auto`​**：等同于 `flex: 1 1 auto`，其中 `flex-basis` 为 `auto`。这表示元素的初始大小基于其内容的固有尺寸，在分配剩余空间时，首先考虑元素的内容大小，然后再根据剩余空间进行伸缩。

**具体区别：**

- **空间分配方式**：

  - 使用 `flex: 1` 时，所有设置了该属性的元素会忽略自身内容的宽度，平分容器的剩余空间。
  - 使用 `flex: auto` 时，元素首先根据自身内容确定初始大小，然后在剩余空间中按比例分配。

**适用场景：**

- **​`flex: 1`​**：适用于需要所有元素等分剩余空间的场景，例如创建等宽的导航按钮或卡片布局。
- **​`flex: auto`​**：适用于希望元素根据自身内容动态调整大小的场景，例如导航栏中的菜单项，其宽度根据文字长度自动调整。

#### Flex

---

以下摘取自 [MDN Web Docs](https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex?utm_source=blog.rising-galaxy.top) 中对该属性的语法解释：

##### **语法**

---

```css
/* 关键字值 */
flex: auto;
flex: initial;
flex: none;

/* 单值，无单位数字：flex-grow
flex-basis 此时等于 0。 */
flex: 2;

/* 单值，宽度/高度：flex-basis */
flex: 10em;
flex: 30px;
flex: min-content;

/* 双值：flex-grow | flex-basis */
flex: 1 30px;

/* 双值：flex-grow | flex-shrink */
flex: 2 2;

/* 三值：flex-grow | flex-shrink | flex-basis */
flex: 2 2 10%;

/* 全局值 */
flex: inherit;
flex: initial;
flex: revert;
flex: revert-layer;
flex: unset;
```

可以使用一个、两个或三个值来指定 `flex` 属性。

- **单值语法**：值必须是以下之一：

  - 一个 [`flex-grow`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex-grow) 的有效值：此时简写会扩展为 `flex: <flex-grow> 1 0`。
  - 一个 [`flex-basis`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex-basis) 的有效值：此时简写会扩展为 `flex: 1 1 <flex-basis>`。
  - 关键字 `none` 或者全局关键字之一。

- **双值语法**：

  - 第一个值必须是一个 [`flex-grow`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex-grow) 的有效值。
  - 第二个值必须是以下之一：

    - 一个 [`flex-shrink`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex-shrink) 的有效值：此时简写会扩展为 `flex: <flex-grow> <flex-shrink> 0`。
    - 一个 [`flex-basis`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex-basis) 的有效值：此时简写会扩展为 `flex: <flex-grow> 1 <flex-basis>`。

- **三值语法**：值必须按照以下顺序指定：

  1. 一个 [`flex-grow`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex-grow) 的有效值。
  2. 一个 [`flex-shrink`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex-shrink) 的有效值。
  3. 一个 [`flex-basis`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex-basis) 的有效值。

##### **取值**

---

- [`initial`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex?utm_source=blog.rising-galaxy.top#initial)：元素会根据自身宽高设置尺寸。它会缩短自身以适应 flex 容器，但不会伸长并吸收 flex 容器中的额外自由空间来适应 flex 容器。相当于将属性设置为 `flex: 0 1 auto`。

- [`auto`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex?utm_source=blog.rising-galaxy.top#auto)：元素会根据自身的宽度与高度来确定尺寸，但是会伸长并吸收 flex 容器中额外的自由空间，也会缩短自身来适应 flex 容器。这相当于将属性设置为 `flex: 1 1 auto`。

- [`none`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex?utm_source=blog.rising-galaxy.top#none)：元素会根据自身宽高来设置尺寸。它是完全非弹性的：既不会缩短，也不会伸长来适应 flex 容器。相当于将属性设置为 `flex: 0 0 auto`。

- [`flex-grow`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex?utm_source=blog.rising-galaxy.top#flex-grow)：定义 flex 项目的 [`flex-grow`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex-grow)。负值无效。省略时默认值为 `1`。 (初始值为 `0`)

- [`flex-shrink`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex?utm_source=blog.rising-galaxy.top#flex-shrink)：定义 flex 元素的 [`flex-shrink`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex-shrink)。负值无效。省略时默认值为`1`。 (初始值为 `1`)

- [`flex-basis`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex?utm_source=blog.rising-galaxy.top#flex-basis)：定义 flex 元素的 [`flex-basis`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex-basis) 属性。若值为 `0`，则必须加上单位，以免被视作伸缩性。省略时默认值为 `0`。(初始值为 `auto`)

#### 主要参考

---

- _[Flex 布局教程：语法篇 - 阮一峰的网络日志](https://www.ruanyifeng.com/blog/2015/07/flex-grammar.html?utm_source=chatgpt.com)_
- [mdn web docs &gt; CSS &gt; flex](https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex?utm_source=blog.rising-galaxy.top#%E5%BD%A2%E5%BC%8F%E5%AE%9A%E4%B9%89)

<!-- Content_END -->
