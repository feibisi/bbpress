---
title: "故障排除"
post_status: publish
post_name: troubleshooting
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 146
  guid: "http://import.local/2021/12/24/troubleshooting/"
---

bbPress 可以很好地与许多主题和插件配合使用，但无法测试它们的所有组合，许多常见问题都是由插件和主题冲突引起的。
某些问题的最常见解决方案是完成这些基本的故障排除步骤。
请注意，如果您使用的是付费主题或插件，请联系作者寻求解决方案，因为他们可能知道如何修复它。

### [常见问题](#common-issues)

这些是您需要检查的常见问题。

- [空白页](/document/blank-pages/)
- [导航链接返回 404s 错误](/document/navigation-links-return-404s-errors/)
- [bbp\_setup\_current\_user 被错误调用](/document/bbp_setup_current_user/)
- [搜索重定向到首页](/document/search-redirects-to-front-page/)

### [插件](#plugins)

有时插件可能与 bbPress 冲突并导致您的网站出现问题。按照这个简单的过程查找插件问题。

1. 转到插件 > 已安装的插件
2. 现在批量选择除bbPress之外的所有插件，在下拉列表中选择Deactivate并点击Apply，然后看看这是否能解决您的问题。

如果这解决了您的问题，请通过一次单击一个插件的启用来重新启用您的插件，以查看是哪个导致您的问题发生。
如果您发现问题是由您当前安装的插件生成的，请联系导致问题的特定插件的插件作者。看看他们是否知道任何修复程序，或者他们是否在 bbPress 中发现了错误，以便 bbPress 可以在不久的将来应用补丁。您还可以安装导致问题的插件的替代品，或者只是将其删除，仅此而已。
如果您无法停用插件。因为您无法到达屏幕来停用它们，那么您可以使用 FTP.或 phpMyAdmin 停用您的插件。这是帮助您执行此操作的 WordPress 代码指南，[如何使用 FTP 和 phpMyAdmin 停用插件](https://codex.wordpress.org/FAQ_Troubleshooting#How_to_deactivate_all_plugins_when_not_able_to_access_the_administrative_menus.3F)

### [主题](#themes)

如果插件没有查明问题，作为测试切换到 WordPress 默认主题，例如[2012](https://wordpress.org/themes/twentytwelve/)，看看这是否能解决您的问题。我们推荐二十二的原因是因为它与 bbPress 插件完美配合。

1. 转到外观>主题
2. 如果您已经安装了二十二，点击主题截图照片附近的启用按钮。如果您还没有安装二十二，现在就安装。单击站点主题部分顶部的添加新按钮。现在在主题搜索搜索栏中搜索二十二。搜索后，如果拼写正确，它应该是第一个选项。从那里，单击“安装”按钮 ，然后在安装后单击“启用”以使“二十二”成为您当前的活动主题，然后看看这是否能解决您的问题。

如果您发现问题是由您当前安装的主题产生的，请联系导致问题的特定主题的主题作者。看看他们是否知道任何修复程序，或者他们是否在 bbPress 中发现了错误，以便 bbPress 可以在不久的将来应用补丁。您也可以为您的网站安装和使用完全不同的主题。
如果这不能解决您的问题，并且您也已完成插件冲突的故障排除步骤，请尝试以下附加解决方案。

### [其他解决方案](#additional-solutions)

以下不会造成任何伤害，因此值得一试并可以解决一些问题。

- 转到Settings > Permalinks，选择默认的永久链接然后保存。现在选择您喜欢的永久链接结构。这会刷新重写规则并可以解决一些可能的 404 错误。
- 转到“工具”>“论坛”>“修复论坛”并一次运行一项修复工作。大多数修复工作只会重新计算帖子关系、帖子计数，并删除将位于用户个人资料中的用户订阅和收藏夹中的任何垃圾帖子。运行这些可以时不时地运行。

请注意，运行将 现有用户重新映射到默认论坛角色 可能会删除任何具有管理员分配的论坛用户角色（例如，主持人、被阻止、旁观者、不是站点管理员的键盘管理员）并且本身不是管理员的用户，回到在Settings > Forums > Auto Role中设置的默认论坛角色。任何站点管理员都将被自动授予 Keymaster 论坛角色。
如果您确实运行了此修复作业并丢失了管理员为您的用户分配的论坛角色，要修复它，您只需通过编辑每个用户个人资料或从站点前端或后端的 bbPress 论坛个人资料手动重新分配它们。

- 刷新您可能拥有的任何缓存，并确保您的缓存插件配置正确。
- 检查服务器中的任何错误日志。
- 作为最后的手段，重新安装 bbPress 的新副本。

### [高级故障排除](#advanced-troubleshooting)

如果您在编码方面有经验，并且了解当这些选项弹出其信息时要查找什么，那么这些推荐选项可用于诊断您站点上的问题。
使用 WP\_DEBUG
通过进入 wp-config 文件并将 WP\_DEBUG 值设置为 true，您可以启用 WP\_DEBUG 以获取有关站点上任何问题的非常有用的调试信息。请确保这仅适用于非生产环境，因为您的用户也可以看到调试信息。

```
define( 'WP_DEBUG', true );
```

执行此操作后，转到出现问题的位置，您应该查看是否存在导致问题的任何详细信息。完成后，确保通过将值设置为 false 来禁用此 WP\_DEBUG。
诊断 JavaScript 错误
如果您遇到某些交互功能的问题，这可能是由于某些 JavaScript 错误造成的。这个 WordPress 代码指南将有助于向您展示如何诊断不同浏览器中的 JavaScript 问题。[使用浏览器诊断 JS 错误](https://codex.wordpress.org/Using_Your_Browser_to_Diagnose_JavaScript_Errors)

### [其他资源](#additional-resources)

- [常见的 WordPress 错误](https://codex.wordpress.org/Common_WordPress_Errors)
- [常见故障排除问题](https://codex.wordpress.org/FAQ_Troubleshooting)
- [在 WordPress 中调试](https://codex.wordpress.org/Debugging_in_WordPress)
- [我做出改变，什么也没发生](https://codex.wordpress.org/I_Make_Changes_and_Nothing_Happens)

如果您需要任何其他帮助，请在[支持论坛中](https://bbpress.org/forums/)创建话题。
如果您已经解决了自己的问题，请在支持论坛中告诉我们，以便您可以帮助可能遇到相同问题的其他用户。
