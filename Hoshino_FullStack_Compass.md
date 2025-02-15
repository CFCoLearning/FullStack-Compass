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

<!-- Content_END -->