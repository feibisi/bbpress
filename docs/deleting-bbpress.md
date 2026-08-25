---
title: "删除 bbPress"
post_status: publish
post_name: deleting-bbpress
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 137
  guid: "http://import.local/2021/12/24/deleting-bbpress/"
---

### [删除 bbPress 数据](#remove-bbpress-data)

默认情况下，如果插件被停用和删除，bbPress 不会删除任何数据，因此如果您当前安装的 bbPress 有问题，您可以安装插件的干净版本，并且仍然像以前一样拥有所有数据。
如果您决定不运行 bbPress 并且您已经选择要删除 bbPress 创建的所有先前数据，则可以运行重置论坛工具来删除所有 bbPress 数据。

1. 登录您的 WordPress 后端。
2. 转至工具 > 论坛 > 重置论坛。
3. 选中“您确定要执行此操作吗？”复选框。
4. 可选：您可能还想检查删除导入的用户？因为一旦 bbPress 被重置，删除这些用户所需的元数据也将被删除。
5. 单击重置 bbPress。

请注意，如果您看到“删除转换表...失败”，如果您没有从其他论坛系统导入，看到此信息是正常的，因为在导入过程中会添加一个额外的数据库表。
使用重置论坛工具将从您的 WordPress 数据库中删除所有 bbPress 数据，包括自定义文章类型、话题标签分类法和 bbPress 用户元数据。
但是，在旧版本的 bbPress 中存在一个错误，即 bbPress 不会完全删除用户角色。（参见[#2580](https://bbpress.trac.wordpress.org/ticket/2580)）
因此，如果您使用的是旧版本的 bbPress，请在您的子主题 functions.php 文件中添加此功能。

```
$wp_roles = new WP_Roles();
$wp_roles->remove_role("bbp_keymaster");
$wp_roles->remove_role("bbp_moderator");
$wp_roles->remove_role("bbp_participant");
$wp_roles->remove_role("bbp_spectator");
$wp_roles->remove_role("bbp_blocked");
```

刷新您的网站，现在所有与 bbPress 相关的用户角色都已从数据库中删除。之后，您可以从子主题的functions.php文件中删除代码。
现在删除所有 bbPress 数据后，您可以继续卸载 bbPress。

### [卸载 bbPress](#uninstall-bbpress)

如果您因为核心文件被修改而需要安装新版本的 bbPress，您遇到了想要尝试修复的严重问题，或者您只是不想再使用 bbPress，您可以按照以下步骤操作从您的站点卸载 bbPress。

1. 登录您的 WordPress 后端。
2. 转到插件 > 已安装的插件。
3. 向下滚动，直到看到 bbPress，然后单击停用。
4. 页面重新加载后，向下滚动到 bbPress 插件，现在单击红色的删除链接。
5. 您现在将看到一个确认删除 bbPress 插件的屏幕，如果您确定要从安装中删除 bbPress，请点击OK。按钮。
6. bbPress 现在已从您的站点中卸载。
