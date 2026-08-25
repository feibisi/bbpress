---
title: "审核和黑名单"
post_status: publish
post_name: moderation-and-blacklisting
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 107
  guid: "http://import.local/2021/12/24/moderation-and-blacklisting/"
---

bPress 使用与 WordPress 用于评论的相同的审核和黑名单工具。如果您希望用户的话题和回复受到额外审核，和/或完全禁止发布，您可以使用评论审核和评论黑名单设置，位于：
管理后台 > 设置 > 讨论
当在您的评论审核设置中发现包含单词的话题或回复时，它将被置于待处理状态，而不是立即发布。
当发现某个话题或回复在您的评论黑名单设置中包含某个词时，它会被阻止发布，并且用户会收到一个相对通用的回复，例如：
> 目前无法创建您的话题。

响应保持通用的原因是，冒犯的用户不会被发现问题，然后他们可以尝试使用空格、符号或其他 Web voo-doo 来规避。
您目前无法修改这些响应的结果，尽管该bbp\_add\_error()功能的核心补丁可以在 bbPress 的未来版本中相对轻松地启用它。
