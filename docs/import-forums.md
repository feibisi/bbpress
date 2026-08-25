---
title: "导入论坛"
post_status: publish
post_name: import-forums
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 63
  guid: "http://import.local/2021/12/24/document/"
---

### [支持平台](#supported-platforms)

- [Advanced Electron Forum v1.x](/document/aef)（bbPress 2.5 的 beta 测试见[#2384](https://bbpress.trac.wordpress.org/ticket/2384)）
- [bbPress v1.1/v1.2](/document/bbpress)（这也包括 BuddyPress 组论坛）
- [Drupal v7.x](/document/drupal)（bbPress 2.5 的 beta 测试见[#2375](https://bbpress.trac.wordpress.org/ticket/2375)）
- [FluxBB v1.5.x](/document/fluxbb)（bbPress 2.5 的 beta 测试见[#2383](https://bbpress.trac.wordpress.org/ticket/2383)）
- [Invision](/document/invision)
- [Mingle](/document/mingle)
- [MyBB v1.6.x](/document/mybb)（bbPress 2.5 的 beta 测试见[#2378](https://bbpress.trac.wordpress.org/ticket/2375)）
- [Phorum v5.2.19](/document/phorum)（bbPress 2.5 的 beta 测试见[#2382](https://bbpress.trac.wordpress.org/ticket/2382)）
- [phpBB v.3.x](/document/phpbb)
- [PunBB v1.4.x](/document/punbb)（bbPress 2.5 的 beta 测试见[#2379](https://bbpress.trac.wordpress.org/ticket/2379)）
- [Simple Press v5](/document/simplepress)
- [Simple Machines Forum v2.0.x](/document/smf)（bbPress 2.5 的 beta 测试见[#2380](https://bbpress.trac.wordpress.org/ticket/2380)）
- [Vanilla v2.x](/document/vanilla)
- [vBulletin v4.x](/document/vbulletin)

您还可以使用包含在/bbpress/includes/admin/converters/Example.php 中的Example.php来创建您自己的[自定义导入器](/document/custom-import/)，以设置从任何 SQL 数据库的导入。

### [到达那里](#getting-there)

1. 登录到您的 WordPress 管理仪表盘
2. 选择“工具”选项卡，从导航菜单中选择“论坛”
3. 选择屏幕顶部的“导入论坛”选项卡。

### [配置导入器](#configuring-the-importer)

数据库设置

- 选择您要从中导入的源平台，bbPress、phpBB 等
- 数据库服务器：除非您的托管服务提供商要求您使用 IP 地址，否则请保留为“本地主机”。
- 数据库端口：如果不确定，请使用默认值 3306
- 数据库名称：包含旧论坛数据的数据库名称
- 数据库用户：数据库连接的用户
- 数据库密码：访问数据库的密码
- 表前缀：（如果从 BuddyPress 论坛转换，请使用“wp\_bb\_”或您的自定义前缀）

可选设置

- 行数限制
- 延迟时间
- 转换用户
- 重来
- 清除以前的导入

### [导入数据](#importing-the-data)

- 点击“开始”

### [完成导入](#finalizing-the-import)

- 导入您的论坛/话题/回复后，您需要通过[“修复论坛”](/document/repair-forums/ "维修论坛")工具更新论坛、话题、回复和话题标签与用户之间的关系，并单独运行这些工具中的每一个，因为在运行这些工具时会产生大量的数据库开销.

### [故障排除](#troubleshooting)

- 有关每个进口商的特定常见问题解答和已知问题，请访问该进口商法典页面。
- 如果在导入话题或回复时导入“卡住”，请参阅[导入疑难解答](/document/import-troubleshooting)

### [重定向旧 URL](#redirecting-your-old-urls)

- 在此阶段，我们没有任何关于将旧 URL 重定向到新 bbPress URL 的文档。您可以保留现有的 phpBB 论坛，并使用[此处](http://abiliocaetano.com/seo-migrate-phpbb-to-bbpress/)的方法将旧 URL 重定向到 bbPress 。Stack Overflow 上有一些很好的例子：[vBulletin](http://stackoverflow.com/q/13920322/1911294) , ..., ...
