---
title: "创建测试数据"
post_status: publish
post_name: creating-test-data
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 154
  guid: "http://import.local/2021/12/24/creating-test-data/"
---

在添加任何数据之前，最好先设置一个测试环境来试用 bbPress。因此，请阅读有关如何在此处进行设置的指南：[创建测试站点](/document/bbpress/creating-a-test-site/)
您可以手动创建论坛、话题和回复，以便快速查看您正在进入的内容，但如果您想生成大量数据进行测试，这可能会变得很烦人。
如果您需要为测试站点生成大量测试数据以使用 bbPress 进行开发，您可以尝试以下几种方法。这些方法通常最适合测试服务器或本地开发环境，不要在生产网站上使用这些方法。

### [bbPress WXR 样本数据](#bbpress-wxr-sample-data)

由 Core Developer Stephen Edgar 创建，您可以使用 WordPress 导入器工具导入此 XML 文件。该文件导入了大约 17 个论坛，其中 15 个是公开的，2 个是隐藏的和私有的。数据还包括多个话题和回复。
您可以从[此处](https://bbpress.trac.wordpress.org/ticket/2516)获取此 trac 票证中的文件。
如果您想直接下载文件，请单击[此处](https://bbpress.trac.wordpress.org/raw-attachment/ticket/2516/bbpress-unit-test-data.xml)。
要导入数据，您需要：

1. 转到工具 > 导入。
2. 一直到它说 WordPress 的地方，然后单击链接。
3. 如果您尚未安装 WordPress 导入程序插件，请单击立即安装。
4. 如果您安装并启用了 WordPress Importer 插件，请继续导入过程。
5. 单击“选择文件”按钮 ，现在选择您之前刚刚下载的文件。
6. 单击上传文件并导入。
7. 您现在可以将帖子分配给您选择的特定用户并检查 导入附件
8. 现在点击提交
9. 之后它应该导入文件中的所有帖子并告诉您它是在最底部完成的

### [EpicWebs bbPress 测试数据](#epicwebs-bbpress-test-data)

这是一个 WordPress 插件，由 Rob Mehew 在测试他正在开发的 WordPress 主题时需要添加和删除数据时创建。
这个插件导入了大约 3 个带有 Lorem Ipsum 文本的论坛，每个论坛最多有 16 个回复或话题。
使用此插件添加 bbPress 测试数据

1. 从[这里](http://www.epicwebs.co.uk/bbpress-tutorials/test-data-for-bbpress-plugin/)下载插件，或者直接从这个[链接](http://www.epicwebs.co.uk/wp-content/uploads/2014/01/epicwebs-bbpress-create-test-data.zip)下载
2. 转到 插件> 添加插件
3. 单击上传插件按钮
4. 单击“选择文件”按钮并找到并选择 bbPress 测试数据插件
5. 然后点击立即安装按钮
6. 现在点击启用链接
