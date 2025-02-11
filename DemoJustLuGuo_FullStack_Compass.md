# CFC Studio 共学 FullStack Compass 指引
---
# [DemoJustLuGuo]


## 笔记证明

<!-- Content_START -->

### 02.03

#### 学习时长：1.5小时

今天是学习前端开发的第一天，因为基础不太行加上比较迷茫，遂从实验室成员处得到了学习建议。这里采用的是b站UP主黑马程序员的前端开发教程，视频链接为https://www.bilibili.com/video/BV1kM4y127Li 前面教的是HTML5的语法使用，看着并没有什么吃力的地方，甚至觉得有些轮椅，今天没什么好写的就先到这里。

后面的打算是准备实战做网页开发，不过也不一定，总之后面的事后面再决定！今天就水一点内容做占位吧。

### 02.04

#### 学习时长：1小时

今天主要还是在熟悉HTML的使用，预计明天开始学习CSS，跟着视频学着并根据萌娘百科上的内容抄了一篇介绍，暂时没有遇到什么难点，今天就这样吧，摸了。


### 02.10

#### 学习时长：1.5小时

这几天家里修新房子在搞手续什么的比较忙，CSS这方面的内容断断续续看了一些，但是感觉没什么好写的，学习笔记就断了很久也没提交新东西，今天卡着斩杀线先push上来一些内容吧。

CSS是一种样式表语言，通常跟HTML一起使用。CSS用来描述HTML中的内容该以什么样的方式呈现，主要是用来美化网页的。

CSS的引入非常灵活，直接在HTML文件里通过`style`标签写css代码即可，或者用`link`标签引入单独的css文件也可以。在开发中一般是使用第二种方式，我因为还不熟悉所以就直接用第一种了。

目前学了几个选择器和画盒子，还有文字属性之类的，感觉选择器挺好用的，跟函数引用差不多的原理。很省事，实操了一下发现直接在HTML内引入CSS的话显得代码太乱了，还是外部引入的方式比较好用，已老实。

没东西可水了就贴点我写出来的💩(只贴了我用CSS美化的部分，另外欢迎收听我的心头好乐队ずっと真夜中でいいのに捏)
```HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>永远是深夜有多好。</title>
    <style>
        #background {
            background-color: thistle;
            width: auto;
            height: auto;
        }
    </style>
</head>
<body>
<h1 style="color: violet;">百科介绍：ずっと真夜中でいいのに。</h1>
<p style="font-size: large;width: auto;height: auto; background-color: aqua;" >永远是深夜有多好。（日语：ずっと真夜中でいいのに。，罗马字：Zutto Mayonaka de
Iinoni.，粉丝简称真夜中）[1]又称ZUTOMAYO（日语：ずとまよ），是日本音乐组合。其主唱、作词作曲均由ACA-Ne（ACAね）完成或合作完成。</p>
<p style="width: auto;height: auto; background-color: aqua;">关于名称的由来，ACA-ne在2021年1月30日播出的NHK节目“SONGS”中提到；“当我专注于某件事时，通常会发现已经变成了半夜或早晨。所以我想“永远是深夜有多好。””这个名字正是来源于此。 </p>
<div id="background"><ul>
    <li>别名 永远是深夜有多好。
    Zutto Mayonaka de iinoni.
    永远都是深夜就好了。</li>
    <li>音乐类型 摇滚乐
    J-POP
    独立摇滚
    另类摇滚
    节奏蓝调
    电子音乐</li>
    <li>
        出道地点 日本
    </li>
    <li>
        活跃年代 2018年–
    </li>
    <li>
        唱片公司 EMI Records Japan
    </li>
    <li>
        网站 <a href="zutomayo.net">zutomayo.net</a>
    </li>
    <li id="red">
        现任成员
        ACA-Ne（ACAね）
    </li>
</ul>
</div>
```



<!-- Content_END -->
