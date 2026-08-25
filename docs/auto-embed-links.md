---
title: "自动嵌入链接"
post_status: publish
post_name: auto-embed-links
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 151
  guid: "http://import.local/2021/12/24/auto-embed-links/"
---

自动嵌入链接允许用户自动将任何 Youtube 视频、Twitter 推文、Imgur 图像、Vine 视频和 Instagram 照片直接嵌入话题和回复中。这是由 WordPress 内部的 oEMBED 功能提供支持的。有关 oEMBED 在 bbPress 和 WordPress 中支持的完整列表，请访问[此处](https://codex.wordpress.org/Embeds)。
要启用在 bbPress 话题和回复上使用 oEMBED 的能力：

1. 转到WordPress 后端中的设置 > 论坛
2. 然后在论坛功能部分确保启用“将媒体（YouTube、Twitter、Flickr 等）直接嵌入话题和回复中”

### [如何嵌入](#how-to-embed)

您所要做的就是放置您尝试嵌入的对象的完整 url。例如，在回复中，您可以将其放入回复内容框中。
Check out this cool video:
[YouTube 链接网址]
那是一个很酷的视频。
然后在您看到 YouTube 链接 URL 的地方，当您提交帖子时，您会看到完整的 youtube 视频。

### [如何调整嵌入对象的宽度](#how-to-adjust-the-width-of-the-embedded-object)

嵌入对象的宽度调整为当前活动主题的宽度。要调整对象的宽度，您需要将其添加到子主题的functions.php 文件中

```
if ( ! isset( $content_width ) ) $content_width = 600;
```

您可以将 600 更改为更适合您的主题的内容。

### [如何添加对更多网站的支持](#how-to-add-support-for-more-websites)

请转到这篇 WordPress 法典文章： [我如何添加或更改对网站的支持](https://codex.wordpress.org/Embeds#How_Can_I_Add_or_Change_Support_For_Websites.3F)
