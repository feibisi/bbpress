---
title: "升级论坛"
post_status: publish
post_name: upgrade-forums
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 177
  guid: "http://import.local/2021/12/24/upgrade-forums/"
---

随着 bbPress 的改进，偶尔需要升级数据库，但有些论坛太大而无法自动升级。使用以下工具手动运行升级例程。
“升级论坛”工具位于：
WordPress 仪表盘 > 工具 > 论坛 > 升级论坛
(/wp-admin/tools.php?page=bbp-upgrade)
这些工具会产生大量的数据库开销，因此一次只能运行 1 个修复作业。

- 升级用户话题参与度
- 升级用户话题收藏夹
- 升级用户话题订阅
- 升级用户论坛订阅
- 从用户元中删除收藏夹
- 从用户元中删除话题订阅
- 从用户元中删除论坛订阅
- 升级 BuddyPress Group 论坛关系
