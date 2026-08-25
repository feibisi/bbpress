---
title: "论坛设置"
post_status: publish
post_name: forum-settings
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 31
  guid: "http://import.local/2021/12/24/forum-settings/"
---

### [论坛用户设置](#forum-user-settings)

该区域定义了 bbPress 论坛的权限和限制。
禁止编辑帖子
将此设置为时间（以分钟为单位）以限制后期编辑。一旦达到时间限制，论坛帖子将不再可供论坛参与者编辑。管理员和 bbPress 版主可以随时覆盖此设置。
限制发布
时间 将此设置为在 bbPress 论坛中发布新回复之间的最短时间（以秒为单位）。这有助于阻止垃圾邮件或其他干扰论坛正常流程的尝试。
匿名发布
任何站点访问者都可以发布新话题或回复，而无需登录您的站点。他们仍然需要输入姓名和电子邮件才能发布，但不需要创建用户名或密码，也不会显示在 WordPress 用户列表中。
自动角色
选择bbPress论坛成员默认分配的角色，角色有Keymaster、Moderator、Participant（默认）、Spectator和Blocked。有关这些角色分配的权限的完整详细信息，请参阅[用户角色和功能](/document/bbpress-user-roles-and-capabilities/ "用户角色和能力")。

### [论坛特色](#forum-features)

修订版
的WordPress存储每个草稿保存时间或岗位后的新版本被编辑和重新发布。在此处为 bbPress 话题和回复启用或禁用此功能。要了解有关修订的更多信息，请查看有关[修订管理](https://codex.wordpress.org/Revision_Management "修订管理")的 WordPress 法典文章。
收藏夹
论坛参与者可以“收藏”任何话题。这些话题稍后可从参与者的论坛资料中查看。此外，还提供自定义 RSS 提要，使参与者能够及时了解对他们来说很重要的话题。
订阅
论坛参与者可以选择订阅论坛或话题。当在订阅的论坛中创建新话题或向订阅的话题发布新回复时，他们将收到通知。订阅的论坛和话题将出现在他们的论坛用户资料中。
话题标签
这将在站点范围内禁用话题标签，并且不再显示与每个话题或话题标签输入表单相关联的话题标签。
搜索
这将启用论坛范围的搜索，允许用户在您的论坛中搜索论坛、话题和回复。
帖子格式化
这会将工具栏和按钮添加到 textarea 以帮助进行 HTML 格式设置，默认值为“b”（粗体）、“i”（斜体/强调）、“link”（URL 超链接）、“del”（删除线） )、'img'（通过 URL 链接图像）、'ul'（无序列表）、'ol'（有序列表）、'li'（列表项）、'code'（用于预格式化文本的 HTML/PHP/SQL 代码) & 'close tags'（关闭任何未关闭的标签）。
自动嵌入链接
使论坛参与者能够通过简单地将链接粘贴到他们的话题或回复中来嵌入来自 YouTube、Twitter 和其他人的链接。这是使用 WordPress oEmbed API 完成的。更多信息和支持站点的完整列表可以在[嵌入 Codex 页面](https://codex.wordpress.org/Embeds "WordPress 嵌入")上找到。
回复线程
这将允许您的用户回复特定回复，在“线程”视图中为讨论提供上下文。这也将删除话题分页，因此话题和所有回复只会是一个页面。
允许全局访问
在 WordPress 多站点安装中，bbPress 在单个站点上被启用。允许全局访问将允许网络中的所有用户在此特定站点的论坛上发布话题和回复。

### [每页话题和回复](#topics-replies-per-page)

话题– 每页显示多少话题。
回复- 每页显示多少回复。

### [每个 RSS 页面的话题和回复](#topics-replies-per-rss-page)

话题– 每个 RSS 页面显示多少个话题
回复– 每个 RSS 页面显示多少个回复

### [论坛根别名](#forum-root-slug)

论坛根(Root) – 用于在论坛
上添加自定义 root slug前缀 Forum Prefix – 用于在 Archive Slugs 中使用 Forums base slug 启用论坛前缀
论坛 root 应显示– 设置您的论坛以显示您的论坛索引或最新话题列表.

### [单论坛别名](#single-forum-slugs)

Forum – 用于论坛 root slugs 的前缀
Topic – 用于话题 root slugs 的前缀
Topic Tag – 用于单个话题标签 root slugs 的前缀
Topic View – 用于话题视图根 slugs 的前缀
Reply – 用于回复 root slugs 的前缀
Search – 用于前缀搜索根段

### [论坛用户别名](#forum-user-slugs)

用户基础– 用于添加用户 root slug 的前缀
Topics Started – 用于添加用户创建的话题 slugs
Replies Created – 用于添加用户创建的回复 slugs
最喜欢的话题– 用于添加用户最喜欢的话题 slugs
Topic Subscriptions – 用于添加用户订阅 slugs 的前缀
