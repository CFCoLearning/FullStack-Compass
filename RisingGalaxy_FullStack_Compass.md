# CFC Studio 共学 FullStack Compass 指引

---

# RisingGalaxy

> I'm a rather lazy person, but I'm willing to learn new things.

## Note

<!-- Content_START -->

### 02.04

> Learning time: About 5h

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

<!-- Content_END -->
