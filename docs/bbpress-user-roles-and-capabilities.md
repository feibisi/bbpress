---
title: "bbPress 用户角色和能力"
post_status: publish
post_name: bbpress-user-roles-and-capabilities
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 60
  guid: "http://import.local/2021/12/24/bbpress-user-roles-and-capabilities/"
---

### [概述](#overview)

bbPress 内置用户角色，使网站所有者能够定制用户对其网站的访问权限。此页面详细介绍了每个角色具有的 bbPress 功能。
您可以像管理 WordPress 用户角色一样管理 bbPress 用户角色。( /wp-admin/users.php)
可以在[此处](https://bbpress.org/forums/topic/roles-and-capabilities-in-bbpress-2-2/)阅读 bbPress 2.2 引入的角色和功能的详细信息。
（bbPress 用户角色可以在 中找到/includes/core/capabilities.php）
有关 WordPress 角色和功能的更多一般信息，请参阅[WordPress Codex 中](https://codex.wordpress.org/Roles_and_Capabilities)的指南。
对于 bbPress 用户角色的高级编辑，请通过 bbPress的[高级用户功能编辑查看](https://github.com/johnjamesjacoby/bbp-capabilities)[@JJJ](https://bbpress.org/forums/profile/johnjamesjacoby/)的插件。

### [角色概要](#summary-of-roles)

默认的 bbPress 角色是：

- [Keymaster](#keymaster) – 可以创建、编辑和删除其他用户的论坛、话题和回复。可以管理标签，并使用审核工具管理论坛。可以访问全球论坛设置、工具和导入程序。
- [版主](#moderator)- 可以创建和编辑论坛。可以创建、编辑和删除其他用户的话题和回复。可以管理标签，并使用审核工具管理论坛。
- [参与者](#participant)- 可以创建和编辑自己的话题和回复。
- [旁观者](#spectator)– 只能阅读话题和回复。
- [已阻止](#blocked)- 所有功能都被明确阻止。

### [角色详细分解](#detailed-breakdown-of-roles)

### [论坛管理员](#keymaster)

论坛功能

- keep\_gate\*\* 请参阅下面的注释
- 发布论坛
- 编辑论坛
- edit\_others\_forums
- 删除论坛
- delete\_others\_forums
- read\_private\_forums
- read\_hidden\_​​forums

话题能力

- 发布话题
- 编辑话题
- edit\_others\_topics
- 删除话题
- delete\_others\_topics
- read\_private\_topics

回复能力

- 发布回复
- 编辑回复
- edit\_others\_replys
- 删除回复
- delete\_others\_replys
- read\_private\_replys

话题标签功能

- manage\_topic\_tags
- edit\_topic\_tags
- delete\_topic\_tags
- assign\_topic\_tags

杂项

- 旁观
- 参加
- 缓和
- 压制
- 查看垃圾箱

### [版主](#moderator)

论坛功能

- 发布论坛
- 编辑论坛
- read\_private\_forums
- read\_hidden\_​​forums

话题能力

- 发布话题
- 编辑话题
- edit\_others\_topics
- 删除话题
- delete\_others\_topics
- read\_private\_topics

回复能力

- 发布回复
- 编辑回复
- edit\_others\_replys
- 删除回复
- delete\_others\_replys
- read\_private\_replys

话题标签功能

- manage\_topic\_tags
- edit\_topic\_tags
- delete\_topic\_tags
- assign\_topic\_tags

杂项

- 旁观
- 参加
- 缓和
- 压制
- 查看垃圾箱

### [参与者](#participant)

论坛功能

- read\_private\_forums

话题能力

- 发布话题
- 编辑话题

回复能力

- 发布回复
- 编辑回复

话题标签功能

- assign\_topic\_tags

杂项

- 旁观
- 参加

### [观众](#spectator)

杂项

- 旁观

注意：
\*\* 该keep\_gate功能可用于允许向任何用户授予特定的“在论坛中做所有事情”的功能，而无需实际直接授予他们 Keymaster 角色。
