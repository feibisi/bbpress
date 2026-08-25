---
title: "常见问题"
post_status: publish
post_name: faq
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 25
  guid: "http://import.local/2021/12/24/faq/"
---

### [如何](#how-to)

- [如何让用户注册到网站的论坛？](#userreg)
- [如何阻止用户进入WordPress后端？](#backend)
- [如何启用注册？](#enablereg)
- [如何安装 bbPress 主题？](#bbpthemes)
- [登录后如何重定向用户？](#redirect)
- [如何创建子主题？](#childthemes)
- [如何在 bbPress 中更改我的用户头像？](#useravatar)
- [如何从其他论坛软件导入？](#importforums)
- [如何找到帖子ID？](#findpostid)
- [如何设置我的论坛？](#setupbbp)
- [如何删除 bbPress 并删除其所有内容？](#deletebbp)
- [如何创造内容？](#createcontent)
- [如何翻译bbPress？](#translatebbp)
- [如何自定义bbPress？](#customizebbp)

如何让用户注册到网站的论坛？
bbpress 与 WordPress 集成，参与论坛的用户注册对您 WordPress 站点上的所有用户都是相同的。他们可以使用 WordPress 提供的默认注册页面进行注册，或者您可以使用提供的[注册表简码](/document/bbpress/shortcodes/#account) 作为前端表单。一旦用户注册到您的网站，他们将能够参与论坛。
如何阻止用户进入WordPress后端？
所有用户都可以转到 WordPress 后端，如果某些用户能够管理您网站的其他选项，他们将在仪表盘中看到新的菜单项，默认情况下，参与者/订阅者角色等低级角色只能编辑他们的个人资料。版主可以通过后台的区域管理话题和回复。有些人不喜欢除具有管理员权限的用户进入 WordPress 后端之外的任何人，如果您是其中之一，您可以使用此[代码片段](/document/bbpress/layout-and-functionality-examples-you-can-use/#25-restricting-user-access-to-the-wordpress-backend)控制谁可以进入 WordPress 后端，或者安装[WP Admin No Show 之](https://wordpress.org/plugins/wp-admin-no-show/)类的插件 。
如何启用注册？
默认情况下，WordPress 注册是禁用的，但是您可以通过登录您网站的 WordPress 后端来更改此设置，然后转到设置 > 常规，然后启用允许任何人注册。
如何安装 bbPress 主题？
阅读代码中的[安装主题](/document/bbpress/installing-themes/)。
登录后如何重定向用户？
要在登录到您的站点后重定向用户的自定义 url，您可以使用此自定义[代码片段](/document/bbpress/layout-and-functionality-examples-you-can-use/#27-custom-redirect-after-login)，或安装一个插件，该插件可以添加与[Peter 的登录重定向](https://wordpress.org/plugins/peters-login-redirect/)相同的功能。
如何创建子主题？
遵循法典指南 [子主题](https://codex.wordpress.org/Child_Themes)。
如何在 bbPress 中更改我的用户头像？
按照代码指南，[如何更改我的用户头像？](/document/bbpress/user-avatars/).
如何从其他论坛软件导入？
有关从其他论坛软件导入的任何信息，请阅读此 bbPress codex 部分[导入论坛](/document/bbpress/import-forums/)。
如何找到帖子ID？
要查找 bbPress 自定义文章类型的帖子 ID，让我们说简码，在话题或回复帖子附近，您将看到每个帖子的类似 #12的数字，即帖子 ID 号。安装像[Reveal IDs](https://wordpress.org/plugins/reveal-ids-for-wp-admin-25/)这样的插件， 您将在 WordPress 后端的各自区域中看到每个帖子和用户 ID。通过阅读[WordPress Codex Guide 中的这篇文章，](https://codex.wordpress.org/FAQ_Working_with_WordPress#How_do_I_determine_a_Post.2C_Page.2C_Category.2C_Tag.2C_or_User_ID.3F)还有其他方法可以在不需要插件的情况下找到帖子的帖子 ID 。
如何设置我的论坛？
设置论坛有两个主要程序，[配置论坛设置](/document/bbpress/forum-settings/)和[创建一些内容](/document/bbpress/creating-content/)。如果您需要设置 bbPress 的其他进程，请参阅bbPress codex 的[入门](/document/bbpress/)部分。
如何删除 bbPress 并删除其所有内容？
如果您需要删除 bbPress 及其所有内容，请按照指南[删除 bbPress](/document/bbpress/deleting-bbpress/) 中列出的说明进行操作。
如何创造内容？
要了解如何在 bbPress 中创建论坛、话题和回复，请阅读以下指南[创建内容](/document/bbpress/creating-content/)。
如何翻译bbPress？
要了解如何翻译您的 bbPress 论坛，请阅读[您的语言（本地化）](/document/bbpress/bbpress-in-your-language/)中的以下bbPress指南。
如何自定义bbPress？
要了解自定义和扩展 bbPress 的方法，请阅读代码指南[自定义](/document/bbpress/customizing/)。

### [故障排除](#troubleshooting)

- [我的论坛帖子返回 404 消息。我怎样才能解决这个问题？](#404)
- [bbPress.org 上的插件似乎都不起作用。这是怎么回事？](#plugins)
- [布局和 CSS 问题？](#CSS)
- [插件冲突](#plugin-conflicts)

我的论坛帖子返回 404 消息。我怎样才能解决这个问题？
这可能是您的重写规则的问题。要解决此问题，请尝试重置您的永久链接。在您的 WordPress 管理屏幕中，导航到设置 > 永久链接，选择不同的永久链接结构并保存。然后选择您喜欢的永久链接结构并再次保存。
bbPress.org 上的插件似乎都不起作用。这是怎么回事？
bbPress.org 上列出的插件用于 2.x 之前的安装，很快它们将被移动和存档。最新版本的 bbPress (2.x) 的所有插件都可以在 WordPress.org 上找到，带有[bbPress 标签](https://wordpress.org/plugins/tags/bbpress) ——看看吧！
布局和 CSS 问题？
如果您遇到布局或 CSS 问题，请使用[Firebug](http://en.wikipedia.org/wiki/Firebug_(Firefox_extension))或任何内置“开发人员工具”的主要浏览器[Google Chrome](https://developers.google.com/chrome-developer-tools/)、[Safari](https://developer.apple.com/technologies/safari/developer-tools.html)、[Firefox](https://developer.mozilla.org/en-US/docs/Tools/Page_Inspector)、[Internet Explorer](http://msdn.microsoft.com/en-us/library/ie/gg589507(v=vs.85).aspx)和[Opera](http://www.opera.com/dragonfly/document/)。
插件冲突
要尝试解决与其他插件的冲突，请禁用除 bbPress 之外的所有插件，以查看错误是否仍然存在。一次重新启用每个插件，如果再次出现问题，您现在应该能够知道是哪个其他插件导致了冲突。

### [管理](#management)

- [如何让用户成为版主？](#mod)
- [如何制作置顶话题？](#stick)
- [如何在页面中显示来自特定论坛的最近话题？](#recenttopics)

如何让用户成为版主？
访问用户 > 所有用户并选择您希望成为主持人的用户。从将角色更改为...下拉菜单中选择论坛版主，然后单击保存。
如何制作置顶话题？
坚持话题是坚持论坛顶部的话题。要创建粘性话题，请在创建话题时从话题类型下拉菜单中选择粘性。您可以通过将话题设为“超级粘性”，使其在您的所有论坛上粘贴。
如何在主页中显示来自特定论坛的最近话题？
您可以通过在页面中插入简码来显示最近的话题。[bbPress 简码列表可以在这里找到](/document/bbpress/shortcodes/)。
