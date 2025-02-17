# CFC Studio 共学 FullStack Compass 指引
---
# Hoshino

> I'm joker king.

## 笔记证明
<!-- Content_START -->

### 02.07

这次主要是想学一下TS、React以及Next.js。

今天看了点react基础，JSX相关的东西。

忙着旅游呢，忙里偷闲看了一点，具体学习内容后面再补笔记。

### 02.09

今天又在css上踩坑了，一个滚动组件的使用。滚动组件里面填充的列表被我套了一层盒子，导致滚动组件下只有一个元素无法触发滚动。

还有一个css的布局属性`display:block`会使一个元素自动占据一行， 导致本该渲染在同一行的元素呈`column`布局,使用`display:inline`布局可以解决这个问题。

### 02.15

JSX 是一个看起来很像 XML 的 JavaScript 语法扩展。

- JSX 执行更快，因为它在编译为 JavaScript 代码后进行了优化。
- 它是类型安全的，在编译过程中就能发现错误。
- 使用 JSX 编写模板更加简单快速。

React 认为渲染逻辑本质上与其他 UI 逻辑内在耦合，比如，在**UI**中需要绑定处理事件、在某些时刻状态发生变化时需要通知到**UI**，以及需要在**UI**中展示准备好的数据。但是React不强制要求使用JSX。

JSX是JS的语法糖，编译时JSX会通过Babel编译成JS。React源码中使用React.createElement()方法来创建JSX，该方法依次接收DOM节点（比如div、span）、属性集合（比如className、style）和children（子节点）三个参数，并返回一个JS对象，也就是虚拟DOM。

以下两段示例是等价的：

```jsx
const element = (
  <h1 className="greeting">
    Hello, world!
  </h1>
);
```

```jsx
const element = React.createElement(
  'h1',
  {className: 'greeting'},
  'Hello, world!'
);
```

要从组件返回多个元素，必须用一个`parent tag`包裹它们，可以使用`<div></div>`或者一个空标签`<></>`

JSX 要求标签明确关闭：像 `<img>` 这样的自闭合标签必须写成 `<img />`，像 `<li>oranges` 这样的包装标签必须写成 `<li>oranges</li>`。

可以使用[转换器](https://transform.tools/html-to-jsx)，将现有的`html`代码转换为`JSX`代码。

### 02.16

今天主要过了一遍React基础部分。了解基本用法，然后准备直接上手Nxet.js框架了。

- React 应用程序是由*组件*组成的。组件是 UI（用户界面）的一部分，具有自己的逻辑和外观。组件可以小到一个按钮，也可以大到整个页面。
- React 组件是返回 markup 的 JavaScript 函数。
- React 组件名称必须始终以大写字母开头，而 HTML 标签必须为小写。
- 在 React 中，使用 `className` 指定 CSS 类。然后，在单独的 CSS 文件中编写它的 CSS 规则。React 没有规定如何添加 CSS 文件。在最简单的情况下，直接向 HTML 添加 [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) 标签即可。

在React中要使用响应式的变量需要从 React 导入 [`useState`](https://react.dev/reference/react/useState) ，并在代码中使用它来定义变量：

```react
import { useState } from 'react';

function MyButton() {
  const [count, setCount] = useState(0);

  function handleClick() {
    setCount(count + 1);
  }

  return (
    <button onClick={handleClick}>
      Clicked {count} times
    </button>
  );
}
```

如果多次渲染同一个组件，每个组件都会得到它自己的状态。

以 `use` 开头的函数称为 *Hook。*`useState` 是 React 提供的内置 Hook。Hook 比其他函数更具限制性。只能在组件（或其他 Hook）*的顶部*调用 Hook。如果想在条件或循环中使用 `useState`，需要提取一个新组件并将其放在那里。

React的组件共享数据我感觉比Vue简单多了。在上面的代码中，数据是被定义在组件内的，所以每一个单独的组件的数据是隔离的。只要将数据定义在组件的上一级节点中，通过传参的方式就能实现组件的数据共享。

```react
export default function MyApp() {
  const [count, setCount] = useState(0);

  function handleClick() {
    setCount(count + 1);
  }

  return (
    <div>
      <h1>Counters that update together</h1>
      <MyButton count={count} onClick={handleClick} />
      <MyButton count={count} onClick={handleClick} />
    </div>
  );
}

function MyButton({ count, onClick }) {
  return (
    <button onClick={onClick}>
      Clicked {count} times
    </button>
  );
}
```

<!-- Content_END -->