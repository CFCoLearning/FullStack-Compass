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

- 要从组件返回多个元素，必须用一个`parent tag`包裹它们，可以使用`<div></div>`或者一个空标签`<></>`

- JSX 要求标签明确关闭：像 `<img>` 这样的自闭合标签必须写成 `<img />`，像 `<li>oranges` 这样的包装标签必须写成 `<li>oranges</li>`
- 使用驼峰式命名

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

### 02.22

React使用声明式编程，只需要声明页面需要展示的内容，React会负责操作DOM来完成页面的渲染。

在React中，组件就是函数，要使React正常运行，需要注意以下几点：

- React 组件应该大写，以区别于纯 HTML 和 JavaScript
- 使用 React 组件的方式与使用常规 HTML 标签的方式相同，带有尖括号 `<>`

```jsx
function Header() {
  return <h1>Develop. Preview. Ship.</h1>;
}
 
const root = ReactDOM.createRoot(app);
root.render(<Header />);
```

与作为第一个函数参数传递给组件的`props`不同，`state`是初始化并存储在组件中。你可以将`state` 的信息作为`props`传递给子组件，但更新`state`的逻辑应该保留在最初创建`state`的组件中。

#### 如何启动一个next.js项目？

首先使用npm安装依赖包

```shell
npm install react@latest react-dom@latest next@latest
```

Next.js 使用文件系统路由。这意味着，可以使用文件夹和文件，而不是使用代码来定义应用程序的路由。

创建`app`文件夹，然后在该文件夹下创建`page.js`

```jsx
import { useState } from 'react';
 
function Header({ title }) {
  return <h1>{title ? title : 'Default title'}</h1>;
}
 
//将 export default 添加到 <HomePage> 组件，以帮助Next.js区分要呈现为页面主组件的组件。
export default function HomePage() {
  const names = ['Ada Lovelace', 'Grace Hopper', 'Margaret Hamilton'];
 
  const [likes, setLikes] = useState(0);
 
  function handleClick() {
    setLikes(likes + 1);
  }
 
  return (
    <div>
      <Header title="Develop. Preview. Ship." />
      <ul>
        {names.map((name) => (
          <li key={name}>{name}</li>
        ))}
      </ul>
 
      <button onClick={handleClick}>Like ({likes})</button>
    </div>
  );
}
```

在项目根目录创建`package.json`并添加以下json配置：

```json
{
  "scripts": {
    "dev": "next dev"
  },
  "dependencies": {
    "next": "^14.0.3",
    "react": "^18.3.1",
    "react-dom": "^18.3.1"
  }
}
```

运行`npm run dev` 来启动项目，启动后页面报错：

![image-20250222202900283](https://minio.drivefly.cn:443/image-hoshino/blog/2025/02/22/image-20250222202900283.png)

这是因为 Next.js 使用了 React Server Components，这是一项允许 React 在服务器上渲染的新功能。服务器组件不支持 `useState`，因此需要改用 Client 组件。

项目启动后在`app`文件夹下自动创建了一个`layout.js`。这是应用程序的主要布局。可以使用它来添加在所有页面之间共享的 UI 元素（例如导航、页脚等）。

#### 服务端渲染与客户端渲染

在幕后，组件被拆分为两个模块图。**服务器模块图（或树）**包含在服务器上渲染的所有服务器组件，**客户端模块图（或树）**包含所有客户端组件。

服务器组件渲染后，一种称为 **React 服务器组件有效负载 （RSC）** 的特殊数据格式被发送到客户端。RSC 有效负载包含：

1. Server Components 的渲染结果。
2. 客户端组件应呈现位置的占位符以及对其 JavaScript 文件的引用。

![image-20250222205729252](https://minio.drivefly.cn:443/image-hoshino/blog/2025/02/22/image-20250222205729252.png)

React默认在服务端进行渲染，但`useState`这样的Hook函数只能在客户端用，因此上面的写法会报错，导致页面无法渲染。

需要将`button`抽离为单个组件并声明在客户端进行渲染。

```jsx
'use client'; // 在客户端渲染

import { useState } from 'react';
 
export default function LikeButton() {
  const [likes, setLikes] = useState(0);
 
  function handleClick() {
    setLikes(likes + 1);
  }
 
  return <button onClick={handleClick}>Like ({likes})</button>;
}
```

然后在主页面中导入这个组件即可正常渲染。

```jsx
import LikeButton from './like-button';

function Header({ title }) {
  return <h1>{title ? title : 'Default title'}</h1>;
}
 
export default function HomePage() {
  const names = ['Ada Lovelace', 'Grace Hopper', 'Margaret Hamilton'];
 
  return (
    <div>
      <Header title="Develop. Preview. Ship." />
      <ul>
        {names.map((name) => (
          <li key={name}>{name}</li>
        ))}
      </ul>
 
      <LikeButton />
    </div>
  );
}
```

### 02.23

今天主要看了Next.js的路由怎么配置。

Next.js 采用了基于文件系统的路由机制，其中浏览器中的 URL 路径是由代码库中的文件夹及文件位置决定的。遵循约定对于正确实用路由功能至关重要。通过创建嵌套的文件夹结构，Next.js 自动路由到指定文件。这简化了创建嵌套路由的过程，并增强了应用程序的组织和结构。

`[]`包裹的文件夹表示动态路由。Next.js会自动渲染路由对应文件夹下的`page.txs`页面。

![img](https://minio.drivefly.cn:443/image-hoshino/blog/2025/02/23/4a3e4caa59ae450e9539ad9e696b7d88~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

动态路由可以利用每个页面中提供的 `params` 对象来获取动态路由的值。

```tsx
export default function ProductDetail({
  params,
}: {
  params: { productId: string };
}) {
  return <h1>Details about product {params.productId}</h1>;
}
```

对于嵌套的动态路由，也可以在路由对应的`page.txs`中通过`params`来获取所有的路由参数。

```tsx
export default function ProductDetail({
  params,
}: {
  params: { productId: string; reviewId: string };
}) {
  return (
    <h1>
      Review {params.reviewId} for product {params.productId}
    </h1>
  );
}
```

Next.js 提供了 catch-all segments（捕获所有路由段）功能，允许灵活地使用路由。假设我们想创建一个文档站点，其中包含多个功能和概念，每个概念都有自己独特的路由。我们可以使用 catch-all segments 路由来代替为每个路由创建单独文件。

路由组允许在不影响 URL 结构的情况下对路由和文件进行逻辑分组（logical grouping）。可以通过将文件夹放入圆括号中来创建：`(folderName)`。例如，`(auth)/register`、`(auth)/login` 和 `(auth)/forgot-password` 可以通过 `/register`、`/login` 和 `/forgot-password` 访问。使用 `auth` 路由组可以更有效地组织路由。

Next.js 中还提供了私有文件夹功能，只需在文件夹名称前加下划线`_`，就让它成为一个私有实现细节，不能通过路由访问。

<!-- Content_END -->