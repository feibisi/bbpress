---
title: "多站点"
post_status: publish
post_name: multisite
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 144
  guid: "http://import.local/2021/12/24/multisite/"
---

WordPress 多站点是一种能够创建由单个 WordPress 安装提供支持的站点网络的方法。以这种方式运行多个站点的设置非常简单，而 bbPress 在这种类型的环境中开箱即用。
要了解如何设置站点网络，请按照有关如何设置站点网络的 WordPress 法典文章进行操作：  [如何创建网络](https://codex.wordpress.org/Create_A_Network)
在以下任何一种情况下，bbPress 完全按照您的要求工作。bbPress 本机仅在其启用的站点上运行。如果它在网络范围内、在子站点上或作为必须使用的插件被启用，它将在网络中的所有站点上闲置，为这些站点的关键大师准备创建论坛并制作适合该需求的体验地点。

### [全网启用](#network-wide-activation)

1. 转到仪表盘 > 网络管理员。
2. 转到插件 > 添加插件。
3. 您将看到特色插件的 bbPress 部分，您可以从那里安装，或者您可以在搜索栏中键入“bbPress”并按 Enter 键来搜索插件。
4. 单击立即安装。
5. 打网络启用在插件列表中的bbPress的插件。

bbPress 也可以配置为[必须使用的插件，](https://codex.wordpress.org/Must_Use_Plugins)以便在网络范围内工作。

### [仅多站点域根](#multisite%c2%a0domain-root-only)

1. 转到仪表盘 > 网络管理。
2. 转到插件 > 添加插件。
3. 您将看到特色插件的 bbPress 部分，您可以从那里安装，或者您可以在搜索栏中键入“bbPress”并按 Enter 键来搜索插件。
4. 单击立即安装。
5. 安装 bbPress 插件后不要点击网络启用。
6. 将鼠标悬停在WordPress 工具栏顶部的“我的站点”链接上，然后选择您网络的域根站点。
7. 转到插件 > 已安装的插件。
8. 现在启用bbPress 插件。

### [仅网络的子站点](#sub-sites-of-the-network-only)

1. 转到仪表盘 > 网络管理。
2. 转到插件 > 添加插件。
3. 您将看到特色插件的 bbPress 部分，您可以从那里安装，或者您可以在搜索栏中键入“bbPress”并按 Enter 键来搜索插件。
4. 单击立即安装。
5. 安装 bbPress 插件后不要点击网络启用。
6. 将鼠标悬停在WordPress 工具栏顶部的“我的站点”链接上，然后选择您希望 bbPress 所在的网络站点。
7. 转到插件 > 已安装的插件。
8. 现在启用bbPress 插件。

### [多网络安装](#multiple-network-installation)

bbPress 还适用于多个 WordPress 网络。您可以将多站点安装变成许多多站点网络，所有这些网络都围绕一个中央用户群。您需要安装WP Multi Network等插件 才能配置此类设置。
