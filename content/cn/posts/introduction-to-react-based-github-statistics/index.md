---
title: "Github Statistics 一个基于 React 的 GitHub 数据统计工具 "
date: 2019-12-25
description: "不论 Star、Fork 和 Commit，issue 、pr 也应该是一个开源项目社区关注的数据。在本文我们将了解到市面上有哪些 GitHub 数据统计工具"
---

# Github Statistics 一个基于 React 的 GitHub 数据统计工具 

![GitHub](https://user-images.githubusercontent.com/56643819/71428867-87327100-26fe-11ea-8769-11be8fd257f8.png)

V 站曾经有个热帖说为何我的开源项目只有 Fork 没有 Star，楼下有个热评说开源项目关注的不应该是 Commit 数据吗？先不论 Star、Fork 和 Commit，issue 、pr 也应是一个开源项目社区关注的数据。

下面我们来看看市面上有哪些 GitHub 数据统计工具

## GitHub Star 数据统计工具

### Chrome 插件—— Star History
顾名思义你可以通过 [Star History ](https://chrome.google.com/webstore/detail/star-history/iijibbcdddbhokfepbblglfgdglnccfn)这个项目看到一个项目的趋势增长，安装上此插件之后你可以直接在某个开源项目主页，如下图所示，一键操作看 star 增长趋势无烦恼。

![q](https://user-images.githubusercontent.com/56643819/71428782-fd82a380-26fd-11ea-8ef7-7963baf670c6.gif)

当然它也有在线版：[https://star-history.t9t.io/](https://star-history.t9t.io/) 可以戳这个链接体验。


### 在线版 —— StarTrack-js

[StarTrack ](https://seladb.github.io/StarTrack-js/)和 Star History 类似也是一个 Star 统计工具，操作稍繁琐，需要填入该项目所有者的用户名及项目名，下图以 VEsoft-inc 的 Nebula 项目为例：

![image](https://user-images.githubusercontent.com/56643819/71428786-02475780-26fe-11ea-89bd-438dc7873a9d.png)

除了简单的 Star 趋势图，StarTrack 还为你统计了这个项目的 Star 总数、开源时间及每日获得 Star 数等维度数据。

![image](https://user-images.githubusercontent.com/56643819/71428787-04111b00-26fe-11ea-8f37-3fa83da2066e.png)

## GitHub 数据统计工具—— Github Statistics

不只是 Fork 数和 Commit 数，统计 issue 数的工具在 Google 搜索也是查无此项（如果你有知道此类工具欢迎在评论文留言 👏），[GitHub Statistics](https://github.com/vesoft-inc/github-statistics) 是据我所知唯一的可以统计某个开源项目的指标数，包括 GitHub Star、Fork、Commit、issue 和 pr 等数据的工具，当然 GitHub Statistics 也支持你查看项目的 Release 信息，在线体验：[https://vesoft-inc.github.io/github-statistics/](https://vesoft-inc.github.io/github-statistics/)。

Github Statistics 项目采用 React 框架，在图表显示上使用了 highChart，对二者有兴趣的话可以查看源码~~

除了常规的 GitHub 数据统计之外，你可以用 GitHub Statistics 进行多项目 GitHub 数据比较，以 React、Vue、Angular 为例，以下为三个项目的 GitHub 数据分析图为例子。

### 多项目 GitHub 数据比较

在 GitHub Statistics 输入某个项目名，并选中点击 `update` 即可查看该项目的相关数据，如果你需要比较多个项目的数据，记得勾选多个项目。

![image](https://user-images.githubusercontent.com/56643819/71428789-07a4a200-26fe-11ea-8987-1caa68580a08.png)

### 项目信息总览

Repository 可以查看到 GitHub 项目的 `创建时间` （可以理解为立项时间，并非开源时间）、 `项目年龄` （立项到现在的时间）、 `编程语言` 、 `最后一次更新时间` 、 `Watch` 数，数据显示 React 和 Vue 的关注者是一个量级的。

![image](https://user-images.githubusercontent.com/56643819/71428793-0a9f9280-26fe-11ea-915a-00c1e720da37.png)

### Star 趋势图
Star 可以看到这个项目的 `Star 数增长趋势` 、 `日增星` 和 `单日最高星量` 。可以从总 Star 数看出，Vue 和 React  不分伯仲，Vue 异军突起，在 2017 年 6 月 17 日，Vue 项目的 star 超过了 Angular，在 2018 年 6 月 12 日弯道超车甩掉了 React。

![image](https://user-images.githubusercontent.com/56643819/71428796-0f644680-26fe-11ea-945b-9a675d133126.png)

除了总 star，GitHub Statistics 也可以看到**每日增长**，看看被淹没的 Angular 曾经也是 2k 起跑线的项目…再看看 Vue 和 React 在 2018 年 6 月 15 日获得 star，这一天的 star 可吊打 90% 的开源项目了（🍋 Nebula 敬上），小八卦了下这是那天的 Hacker News 热帖《Has Vue passed React yet? 》：[https://news.ycombinator.com/item?id=17316267](https://news.ycombinator.com/item?id=17316267)

![image](https://user-images.githubusercontent.com/56643819/71428801-14c19100-26fe-11ea-9f4c-0c0dacd42112.png)

### Fork 趋势图
和 Star 趋势图类似，总趋势图可以看到这三个项目的 Fork 总数、每日平均数，看每日平均 Vue、React、Angular 相差不大，但是总量上来说，Angular 还是领先两位后起之秀的。

![image](https://user-images.githubusercontent.com/56643819/71428804-19864500-26fe-11ea-8af7-91164cde329e.png)

从每日 Fork 增量图来看，Angular 的 Fork 数比 Vue 和 React 多全靠先发优势，React 和 Vue 诞生之后，Angular 的增长大不如前，而 React 的 Fork 和 Vue 的 Fork 比较，二者是不相上下。

![image](https://user-images.githubusercontent.com/56643819/71428806-1c813580-26fe-11ea-8253-b9a176220f27.png)

### Commit 趋势图

![image](https://user-images.githubusercontent.com/56643819/71428809-1ee38f80-26fe-11ea-9a40-5a8a7e244e5f.png)

虽然 star 上 Vue 和 React 是一个量级，但是在 Commit 或者说项目活跃度上，React 领跑这三个项目，🤔 当中的缘由就不揣测了。

和总的趋势图类似，每日新增 Commit 趋势也是 React 一枝独秀。

![image](https://user-images.githubusercontent.com/56643819/71428811-2145e980-26fe-11ea-8513-4cf5dbbde22e.png)

## 总结 GitHub Statistics
GitHub Statistics 是一个查看 GitHub 相关指标的工具，如果你在为技术选型苦恼，而你看中的技术栈刚好是开源项目，不妨用它试一试，可以看到开源项目的开发进度、社区活跃度，再也不用担心遇到“闭源”的开源项目了。GitHub Statistics GitHub 地址：[https://github.com/vesoft-inc/github-statistics](https://github.com/vesoft-inc/github-statistics)，在线访问：[https://vesoft-inc.github.io/github-statistics/](https://vesoft-inc.github.io/github-statistics/)





