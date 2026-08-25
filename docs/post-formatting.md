---
title: "帖子格式化"
post_status: publish
post_name: post-formatting
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 166
  guid: "http://import.local/2021/12/24/post-formatting/"
---

使用名为 Quicktags 工具栏的简单 HTML 编辑器可以实现 bbPress 帖子的格式，该工具栏显示在话题或回复表单上方，可快速轻松地进行 HTML 格式设置。此工具栏将简单的 HTML 标签插入话题或回复表单，以更好地格式化用户帖子。
要启用使用 HTML 和 Quicktags 工具栏格式化帖子的功能：

1. 转到WordPress 后端中的设置 > 论坛
2. 然后在论坛功能部分确保启用“将工具栏和按钮添加到文本区域以帮助进行 HTML 格式设置”

![快速标签工具栏](/_images/quicktags-toolbar.webp)
与 WordPress 评论类似，没有 Keymaster bbPress 角色或 Admin WordPress 角色的论坛用户只能使用特定的 HTML 标签集。这是出于安全原因而设置的，因此用户将无法发布潜在的恶意 JavaScript。
使用WordPress 中的[Quicktags API](https://codex.wordpress.org/Quicktags_API)，可以轻松扩展 Quicktags 工具栏以添加任何其他自定义按钮。每当您为 Quicktags 工具栏创建自定义按钮时，您都可以将任何 JavaScript 代码放入 editor.js 文件中，前提是您将该文件复制到 bbPress 插件的主题兼容性文件中名为 js 的文件夹中的子主题中，以便JavaScript 可能会在您的 bbPress 论坛中的 Quicktags 工具栏中正确排队。
