---
title: "修复论坛"
post_status: publish
post_name: repair-forums
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 62
  guid: "http://import.local/2021/12/24/repair-forums/"
---

bbPress 跟踪论坛、话题、回复、话题标签和用户之间的关系。有时这些关系会变得不同步，最常见的是在导入或迁移之后。
“修复论坛”工具位于您的 WordPress 仪表盘 ->“工具”->“论坛”->“修复论坛”（/wp-admin/tools.php?page=bbp-repair）
这些工具会产生大量的数据库开销，因此一次只能运行 1 个修复作业。

- 重新计算每个帖子的父话题
- 重新计算每个帖子的父论坛
- 重新计算私人和隐藏论坛
- 重新计算每个话题和论坛的最后活动
- 重新计算每个话题的粘性关系
- 修复 BuddyPress 组论坛关系
- 统计每个论坛的话题
- 统计每个论坛的回复
- 计算每个话题的回复
- 计算每个话题中的声音
- 计算每个话题中的垃圾邮件和垃圾回复
- 计算每个用户的话题
- 统计每个用户的回复
- 从用户收藏夹中删除垃圾话题
- 从用户订阅中删除垃圾话题
- 从用户订阅中删除垃圾论坛
- 将现有用户重新映射到默认论坛角色
