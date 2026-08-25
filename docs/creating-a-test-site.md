---
title: "创建测试站点"
post_status: publish
post_name: creating-a-test-site
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 115
  guid: "http://import.local/2021/12/24/creating-a-test-site/"
---

创建测试站点非常有益，因为您可以了解 bbPress 和 WordPress 的工作原理，并同时测试它们。

- 对于开发人员来说，创建一个测试站点可以帮助他们为 bbPress 开发插件或主题。
- 对于常见的 WordPress 站点调整器，它可以在将更改传输到实时站点之前在其测试站点上测试简单的样式或功能更改。
- 更重要的是，创建一个测试站点将允许您测试插件/主题升级的问题，以便更新不会使您的实时站点容易受到黑客的攻击或破坏您的站点。

这个简单的过程应该可以帮助您自信地升级，并且可以更大胆地使用您的站点，首先测试测试站点中的所有内容，只有在您对一切正常工作感到满意后才提交到实时站点。
如果您不相信您需要一个测试站点，那么请阅读我的推理：[为什么要有一个测试站点？](/document/why-have-a-test-site/)
创建测试站点有两种流行的选择：

1. 在您的计算机上安装本地服务器环境客户端
2. 使用现有域的子域。

### [本地安装](#local-installation)

在您的计算机上创建测试站点是购买新域的一种很好且免费的替代方法。如果您想走这条路，您需要安装一个支持您的操作系统的应用程序，并允许您运行主机服务器通常安装的软件来在您的计算机上运行测试站点。
每个应用程序通过它支持的操作系统识别自己，并安装软件，包括  A pache 、M ySQL 和P HP（XAMPP 还包括P erl）。以下是流行的本地服务器环境客户端列表，以及 WordPress 手册中的指南链接，可帮助您安装每个应用程序。
最流行的本地服务器包是：

- [WAMP](https://make.wordpress.org/core/handbook/tutorials/installing-a-local-server/wampserver/) – 适用于 Windows
- [MAMP](https://make.wordpress.org/core/handbook/tutorials/installing-a-local-server/mamp/) – 适用于 Mac
- [XAMPP](https://make.wordpress.org/core/handbook/tutorials/installing-a-local-server/xampp/) – 适用于 Windows、Mac 和 Linux

创建测试站点并使用列出的软件应用程序之一在您的计算机上安装 WordPress 后，您可以安装 bbPress 并对其进行测试。您可以看到插件如何与 bbPress 一起工作，主题如何工作，您还可以为 bbPress 开发插件或主题。

### [现有域的子域](#subdomain-of-an-existing-domain)

子域将您的主域用作单独的站点。因此，如果您创建一个名为“test”的子域，那么您将使用“test.mysite.com”作为访问该站点的 URL。
大多数主机提供商允许您创建子域。如果您访问您的托管区域，您应该会找到创建子域的选项。如何执行此操作因主机提供商而异，因此如果您需要任何帮助，请联系主机提供商的支持以获取有关如何为当前设置创建子域的任何信息。
创建后，您可以创建测试站点并获得以下好处：

- 测试任何性能问题
- 包含外部源 API 的测试插件

### [克隆现有站点](#cloning-an-existing-site)

通过克隆或镜像您的实时站点，您可以先在测试站点上测试任何修改/升级，而不会影响您现有的实时站点。
所以您可以测试：

- 主题和插件的新升级
- 添加并测试任何新插件
- 更改已安装的 WordPress 主题
- 添加 css、更改功能、布局以及与现有 WordPress 站点有关的任何内容

因此，您将首先仅在测试区域提交，如果您对结果感到满意，则可以将这些更改转移到您的实时站点。而且，如果插件有新的升级，您可以先在您的测试站点上测试升级，如果升级导致问题，您将知道在问题解决之前不要在您的实时站点上升级。
复制数据
所以现在您有一个测试域，其中包含您网站上的所有文件和文件夹，但您需要复制数据。
尝试操作

1. 使用phpMyAdmin访问您的实时站点的数据库。
2. 接下来，在左侧，您将看到所有创建的数据库。
3. 查找并选择您的实时站点的数据库，您现在将看到来自该数据库的一系列表格。
4. 您将在顶部的菜单中看到一个导出选项。单击它后，您将看到一些选项。
5. 现在您可以进行快速导出，但我认为不建议这样做，我更喜欢您进行自定义导出，以允许您将数据压缩为 zip 格式并添加任何其他值以改进恢复。
6. 所以现在启用Custom。
7. 通常，您可以将数据库导出到单个包中，但是如果您有一个特别大的数据库，您可能无法一次性导出/导入。在导入过程中，您可能需要复制单个数据库表或对表进行分组。但是，您可以先尝试导出所有表以进行测试并确保一切正常。
8. 在“输出”部分中，选择您选择的 zip 格式来压缩您的数据库数据。这可能会显着增加大型数据库的上传时间。它还可以让您克服主机提供商可能设置的某些文件上传大小限制。
9. 在对象创建选项中，启用添加 DROP TABLE/VIEW /PROCEDURE/FUNCTION/EVENT 语句。在导入过程中，这将在恢复新表之前删除所有现有表，确保导入干净。
10. 现在单击Go，文件将下载到您的计算机上。

导入数据
已经以压缩文件格式下载了数据库数据，您现在可以将数据导入到新的或现有的数据库中。
如果您尚未创建新数据库。

1. 转到phpMyAdmin主页。
2. 单击顶部的数据库菜单项
3. 您现在将看到一个用于创建新数据库的区域以及一个用于命名数据​​库的文本输入。
4. 为测试站点的新数据库创建一个新名称。将下拉列表保留为 Collat​​ion 的默认设置，然后单击创建按钮。
5. 您刚刚创建了新数据库。

将数据导入新数据库。

1. 为您的测试站点选择您最近创建的数据库。
2. 单击顶部的导入菜单项
3. 现在单击“选择文件”按钮 ，然后从下载中选择实时站点的数据库数据。
4. 单击“前往”按钮。等待导入完成，然后您应该会看到一条成功消息。
5. 现在，您已将实时站点的数据库数据导入到测试站点数据库中。

更改站点引用
由于活动站点的数据已导入到测试数据库中，您将在 wp\_options 表中看到您的活动站点的 url。如果您不更改这些，您将被重定向到您的实时站点，因此更改它是关键。

1. 在 phpmyadmin 中选择您的测试站点数据库
2. 单击最顶部的 SQL 菜单项
3. 现在在空框中输入以下 SQL 代码

```
UPDATE wp_options SET option_value = REPLACE(option_value, 'LIVESITE_URL', 'TESTSITE_URL');
UPDATE wp_postmeta SET meta_value = REPLACE(meta_value, 'LIVESITE_URL', 'TESTSITE_URL');
UPDATE wp_posts SET guid = REPLACE(guid, 'LIVESITE_URL', 'TESTSITE_URL');
UPDATE wp_posts SET post_content = REPLACE(post_content, 'LIVESITE_URL', 'TESTSITE_URL');
```

TESTSITE\_URL 是您的测试站点的完整 URL 地址。
LIVESITE\_URL 是您的实时站点的完整 URL 地址。
如果您对测试站点的数据库使用不同的内容，则可以更改 wp\_ 前缀。
安装 WordPress
完成创建测试站点的数据库后，您需要安装 WordPress。这将允许您在安装期间输入新数据库信息。您可以[手动](https://codex.wordpress.org/Installing_WordPress)执行此操作，也可以使用主机提供的 WordPress 安装过程。
传输文件

1. 首先使用 FTP 或 SFTP 客户端下载您的实时站点的 wp-content 文件夹的副本。
2. 然后将您下载的文件夹内容上传到您的测试站点的 wp-content 文件夹。所有重要的文件，如主题、插件和媒体上传都将通过此传输。

其他步骤
设置测试站点后，您需要禁止用户访问和搜索机器人索引测试站点。

1. 在仪表盘 > 设置 > 阅读中更改搜索引擎可见性以阻止搜索引擎索引您的测试站点。并且保持禁用任何 SEO 插件/功能应该会有所帮助。
2. 由于这是一个测试站点，您不会允许任何人注册到您的站点。因此，安装[Restrict Site Access](https://wordpress.org/plugins/restricted-site-access/)将允许您将站点限制为您的 IP 地址，并且只允许您访问您的测试站点。
