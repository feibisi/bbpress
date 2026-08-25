---
title: "回复线程"
post_status: publish
post_name: reply-threading
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 163
  guid: "http://import.local/2021/12/24/reply-threading/"
---

回复线程将启用对话题的嵌套回复布局，因此如果用户正在回复另一个用户的回复，它将显示嵌套而不是默认的平面论坛视图。
要在整个 bbPress 论坛中启用回复线程：

1. 转到WordPress 后端中的设置 > 论坛
2. 然后在论坛功能部分确保启用“启用线程（嵌套）回复”

有一些设置可以为线程回复设置，类似于线程 WordPress 评论，例如设置用户可以线程特定回复的可能级别。
![回复标题级别](/_images/reply-theading-levels.webp)
要让用户发送另一个回复，用户只需单击用户尝试回复的回复帖子上的回复管理链接。这当然不适用于话题管理链接，当您单击它时，它只会跳到回复表单并创建一个新回复，您不能在该话题下发帖，只能回复其他回复。
![回复线程回复管理链接](/_images/reply-threading-reply-admin-link.webp)
一旦用户点击了回复管理链接，它应该将他们定向到回复表单，然后您可以添加一些内容并提交您的回复以在您回复的回复下进行线程化，或者单击提交附近的取消链接按钮取消回复。
如果您添加了一些内容并点击提交按钮发布您的回复。它应该显示与此类似的内容。
![回复线程显示](/_images/reply-threading-display.webp)
请注意，启用回复线程后您可能会遇到一些问题，或者看起来像是问题的事情。

1. 布局自我关闭中的某些标记似乎存在问题，这可能会导致某些响应式样式不输出的问题，并且可能因此导致绝对定位的头像。（[#2757](https://bbpress.trac.wordpress.org/ticket/2757)）
2. 虽然不是真正的问题，但对于遇到它的用户来说似乎是回复帖子没有分页。我们正在研究一种干净的方式来为线程回复引入分页。（[#2785](https://bbpress.trac.wordpress.org/ticket/2785)）
