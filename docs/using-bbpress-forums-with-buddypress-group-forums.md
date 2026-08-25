---
title: "使用 bbPress 论坛和 BuddyPress 群组论坛"
post_status: publish
post_name: using-bbpress-forums-with-buddypress-group-forums
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 73
  guid: "http://import.local/2021/12/24/using-bbpress-forums-with-buddypress-group-forums/"
---

使用 bbPress 站点范围的论坛和 BuddyPress Group 论坛是可能的并且非常强大。为了确保轻松设置，需要注意以下几点：

1. 安装并启用 bbPress 后，请转到“页面/所有页面”下的管理仪表盘，并使用“论坛”的 slug 查找任何页面。
2. 如果存在这样的页面 slug，就像您第一次安装 BuddyPress 时通常的情况一样，建议您删除此页面，以便为 bbPress 腾出“论坛”slug 的使用。
3. 请确保您还清空了此“论坛”页面的垃圾箱以释放 slug。
4. 然后，您可以使用不同的名称为 BuddyPress Group 论坛创建一个新的页面 slug。例如：“群组论坛”。
5. 创建新页面（例如：“群组论坛”）后，进入 Settings/BuddyPress/Pages 并选择此新页面作为 BuddyPress 群组论坛的占位符
6. 最后，转到设置/永久链接并单击“保存”以确保更新您的永久链接结构
