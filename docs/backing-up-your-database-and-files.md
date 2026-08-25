---
title: "备份您的数据库和文件"
post_status: publish
post_name: backing-up-your-database-and-files
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 135
  guid: "http://import.local/2021/12/24/backing-up-your-database-and-files/"
---

定期备份您的数据库和站点文件对于能够从服务器崩溃、站点被黑客入侵或人为错误等悲惨事件中恢复至关重要。您需要从站点备份两个重要区域，即数据库数据和 WordPress 文件。创建站点备份的方法有很多种，您可以使用插件来创建站点备份以允许您自动备份，也可以手动创建备份，我们将在本指南中讨论这两种方式。
建议您保留站点的多个备份，以防其中一个备份损坏或丢失。还要确保定期安排备份，并存储在不同的介质上，如 CD、拇指驱动器、电子邮件和云存储（如 Dropbox 等）。
有关备份站点的更多信息，您还可以按照 WordPress 指南 [WordPress 备份进行操作](https://codex.wordpress.org/WordPress_Backups)。

### [备份您网站的文件](#backing-up-your-site%e2%80%99s-files)

使用 FTP 手动备份文件
您可以使用 FileZilla 等 FTP/SFTP 客户端，将所有站点文件下载到计算机上的文件夹中。例如，您可以只下载您创建/上次修改的文件，如自定义 bbPress 模板或添加到 bbPress 样式表的自定义样式。无需复制 WordPress 核心文件，因为您可以从 wordpress.org 全新下载的 WordPress zip 文件中替换它们。要备份的最重要的文件之一是 wp-config.php 文件，因为该文件包含有关数据库配置的信息以及有关如何设置站点的其他选项。其他重要文件位于 wp-content 文件夹中，其中包含所有已安装的主题、插件和所有上传媒体。
在某些情况下，您不必下载站点的所有文件，除非您安装了新插件或修改了主题。默认情况下，WordPress 按一年中的几个月对您的媒体文件进行存档，如果您上个月备份了您的网站，则无需下载旧的媒体媒体文件。
有关如何备份文件的更多信息，您还可以按照此 WordPress 指南 [备份您的 WordPress 文件](https://codex.wordpress.org/Backing_Up_Your_WordPress_Files)。
备份站点文件和数据库的自动化解决方案
有大量非常好的免费插件可以在[这里](https://wordpress.org/plugins/tags/backup)备份 WordPress 插件存储库中的数据库和文件。但如果您正在寻找自动化的高级服务，请考虑使用Automattic 的[VaultPress](https://vaultpress.com/)。

### [备份您的 WordPress 数据库](#backing-up-your-wordpress-database)

数据库是您站点的重要组成部分，因为它在一堆表中包含您的所有站点数据，通常在默认 WordPress 安装中以 wp\_ 为前缀。当您的用户创建话题、回复，甚至只是有关用户的信息时，所有这些都存储在 WordPress 数据库表中。
使用 phpMyAdmin 手动备份数据库
以下是手动备份数据库的分步指南。有关使用 phpMyAdmin 手动备份数据库的更多详细信息，请联系您的托管服务提供商或阅读以下 WordPress 指南 [备份您的数据库](https://codex.wordpress.org/Backing_Up_Your_Database)。
备份数据库的自动化解决方案
这些只是仅备份数据库的插件

- [WP-DBManager](https://wordpress.org/plugins/wp-dbmanager/) – 这提供了一个功能齐全的前端界面来管理您的数据库，您可以通过这个插件优化、修复、备份、恢复、删除表和运行选定的查询。这很方便，但请在安装前阅读插件主页上的免责声明。

另请注意，WordPress 的许多顶级安全插件也有备份/恢复数据库的选项。

### [恢复您的网站](#restoring-your-site)

您需要学习如何备份您自己的站点文件并知道如何恢复它们，以便如果有一天您需要恢复您已经准备好的站点备份。因此，请尝试进行测试备份并正确恢复，以便您熟悉备份软件的工作原理。
请注意，仅将恢复作为最后的手段，如果问题只是来自一个简单、易于修复的问题，则只需修复该问题。在站点恢复期间，您将丢失自上次备份以来的所有新数据。
例如，如果您在周一进行了备份，而您的站点在周三由于编辑模板文件时的轻微 PHP 问题而出现错误，则不要恢复周一的备份，否则您将丢失周二和周三的所有数据，只是一个未成年人可以轻松解决的问题。
使用 FTP 手动恢复您的文件
只要您刚刚从您的站点下载 wp-content 文件夹和 wp-config.php 文件进行备份，那么恢复就像将文件复制回您的 WordPress 站点一样简单。然后，上传 wp-content 文件夹中的其余文件，例如插件和主题，以及您的媒体文件。
使用 phpMyAdmin 手动恢复数据库
按照 WordPress Codex 指南使用 phpMyAdmin [恢复数据库，从备份恢复数据库](https://codex.wordpress.org/Restoring_Your_Database_From_Backup)。

### [备份数据的其他方法](#other-ways-to-backup-data)

WordPress 后端导出工具
WordPress 提供了一种通过将 bbPress 帖子导出到 XML 文件来导出数据的方法。您可以在 WordPress 后端的工具 > 导出中找到它。这只是备份站点的快速方法，不能替代完整备份过程。它只备份网站上的内容而没有数据库信息，最好将其视为恢复一些可能已丢失且无法从帖子修订表中恢复的帖子的快速方法。
主机提供的备份软件
大多数 WordPress 托管服务提供商都提供有限的备份服务来备份您的站点。请务必联系您的托管服务提供商以了解他们提供的备份服务。
请记住，备份您的网站是您的责任，不要仅仅依赖您的托管服务提供商进行备份。

### [其他资源](#additional-resources)

- [WordPress 备份](https://codex.wordpress.org/WordPress_Backups)
- [备份您的数据库](https://codex.wordpress.org/Backing_Up_Your_Database)
- [备份您的 WordPress 文件](https://codex.wordpress.org/Backing_Up_Your_WordPress_Files)
- [从备份中恢复数据库](https://codex.wordpress.org/Restoring_Your_Database_From_Backup)
- [FTP客户端](https://codex.wordpress.org/FTP_Clients)
