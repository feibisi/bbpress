---
title: "简码"
post_status: publish
post_name: shortcodes
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 28
  guid: "http://import.local/2021/12/24/shortcodes/"
---

由于版本2.0 bbPress 支持所谓的Shortcodes。引入它们是为了创建宏，用于在 WordPress 页面上的论坛内容布局中使用。要使用任何简码，只需将所需的简码插入任何 WordPress 页面即可。
要获取$forum\_id、$topic\_id、$reply\_id 和 $tag\_id所需的数字 ID，您需要访问您的 /wp-admin/ 部分并通过编辑帖子或将鼠标悬停在适用的论坛/话题/回复/标记文章类型，您将看到该帖子的数字 ID，例如。/wp-admin/post.php?post=47

### [论坛](#forums)

[bbp-forum-index] – 这将显示您的整个论坛索引。
[bbp-forum-form] – 显示“新论坛”表单。
[bbp-single-forum id=$forum\_id] – 显示单个论坛话题。例如。[bbp-single-forum id=32]

### [话题](#topics)

[bbp-topic-index] – 使用分页显示所有论坛中最近的 15 个话题。
[bbp-topic-form] – 显示“新话题”表单，您可以从下拉菜单中选择与该话题相关联的论坛。
[bbp-topic-form forum\_id=$forum\_id] – 显示特定论坛 ID 的“新话题表单”。
[bbp-single-topic id=$topic\_id] – 显示单个话题。例如。[bbp-single-topic id=4096]

### [回复](#replies)

[bbp-reply-form] – 显示“新回复”表单。
[bbp-single-reply id=$reply\_id] – 显示单个回复，例如。[bbp-单回复 id=32768]

### [话题标签](#topic-tags)

[bbp-topic-tags] – 显示所有话题标签的标签云。
[bbp-single-tag id=$tag\_id] – 显示与特定标签关联的所有话题的列表。例如。[bbp-single-tag id=64]

### [查看次数](#views)

[bbp-single-view] – 单一视图 – 显示与特定视图关联的话题。当前包含 bbPress 的“视图”是“流行的”[bbp-single-view id='popular'] 和“无回复”[bbp-single-view id='no-replies']

### [搜索](#search)

[bbp-search] – 显示搜索输入表单。
[bbp-search-form] – 显示搜索表单模板。

### [帐户](#account)

[bbp-login] – 显示登录屏幕。
[bbp-register] – 显示注册屏幕。
[bbp-lost-pass] – 显示丢失的密码屏幕。

### [统计数据](#statistics)

[bbp-stats] – 显示论坛统计信息。
\*\* 尚未实施，计划在未来发布。
