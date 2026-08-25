---
title: "自定义导入"
post_status: publish
post_name: custom-import
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 75
  guid: "http://import.local/2021/12/24/custom-import/"
---

相关： [#2134](https://bbpress.trac.wordpress.org/ticket/2134)提高 Example.php 论坛导入程序的可读性（内联文档和代码格式）
您可以自定义包含在/bbpress/includes/admin/converters/Example.php 中的example.php以设置从任何 MySQL 数据库导入。
一个很好的参考是查看包含的转换器[bbPress1.php](https://bbpress.trac.wordpress.org/browser/trunk/src/includes/admin/converters/bbPress1.php)、[phpBB.php](https://bbpress.trac.wordpress.org/browser/trunk/src/includes/admin/converters/phpBB.php)和[SimplePress5.php](https://bbpress.trac.wordpress.org/browser/trunk/src/includes/admin/converters/SimplePress5.php)并比较数据库表和字段映射，因为这应该会给您一些很好的提示。
以下是逐步完成自定义包含的 Example.php 转换器的示例的工作，该示例取自支持论坛[请求，以帮助制作 Mingle 论坛转换器](https://bbpress.org/forums/topic/importing-mingle-forums-into-bbpress/)。[@robin-w 的](https://bbpress.org/forums/profile/robin-w/)另一篇关于使用自定义导入器将 Snitz 论坛从 Microsoft Access 转换为 MySQL 数据库的精彩帖子也可以[在这里阅读](https://bbpress.org/forums/topic/documented-import-from-snitz-access-database/)。

1. 您需要的第一步是找到要从中导入的当前 SQL 数据库的数据库架构，这可以在现有软件的文档中，或者您可以使用 phpMyAdmin 找到它，现在我将链接到[这是来自原始帖子的这里](https://bbpress.org/forums/topic/importing-mingle-forums-into-bbpress/#post-124525)
2. 我们还需要确定将在“导入论坛”用户界面中使用的数据库前缀

现有论坛是否共享相同的目标 WordPress 数据库，还是现有数据库与目标 WordPress 数据库完全分开？
在这个使用 Mingle 的例子中，它是一个 WordPress 插件，与 WordPress 共享相同的数据库，并将以下表格添加到现有的 WordPress 数据库中（在这种情况下，WordPress 设置为使用 wp\_ 作为数据库前缀）：
`wp_forum_forums
wp_forum_groups
wp_forum_posts
wp_forum_threads
wp_forum_usergroup2user
wp_forum_usergroups`

1. 在同一文件夹中复制 Example.php 并将其命名为 Mingle.php（这里的文件名区分大小写）
2. 打开您最喜欢的文本编辑器（记事本、Text Pad、Notepad++、Sublime Text 等）并开始编辑您新创建的 Mingle.php 文件

- - - 通过进行以下更改为转换器指定唯一名称：
      [第 4 行](https://bbpress.trac.wordpress.org/browser/trunk/src/includes/admin/converters/Example.php#L4)从：`* Implementation of Example converter.第 4 行到：
      * Implementation of Mingle Forums converter.`[第 06 行](https://bbpress.trac.wordpress.org/browser/trunk/src/includes/admin/converters/Example.php#L6)来自：
      `class Example_Converter extends BBP_Converter_Base`
      第 06 行至：（
      class Mingle extends BBP\_Converter\_Base
      确保上述内容与文件名的第一部分匹配，因为它区分大小写）

从论坛部分和第一个数据库表和字段映射“论坛 ID”在[Example.php 第 18 行开始](https://bbpress.trac.wordpress.org/browser/trunk/includes/admin/converters/Example.php#L18)

- - - `18 // Forum id. Stored in postmeta.
      19 $this->field_map[] = array(
      20 'from_tablename' => 'forum', 'from_fieldname' => 'forumid',
      21 'to_type' => 'forum', 'to_fieldname' => '_bbp_forum_id'
      22 );`看到我们有一个“from\_tablename”叫“论坛”和“from\_fieldname”叫“forumid”这些是只有两个值，您将需要在大多数情况下的变化。'to\_type' 'to\_type'和'to\_fieldname'值都是此数据存储在 bbPress 中的位置，我们不需要更改其中任何一个。
    - 如果我们将这些相同的值与[bbPress1.php](https://bbpress.trac.wordpress.org/browser/trunk/src/includes/admin/converters/bbPress1.php#L29)进行比较：`29 'from_tablename' => 'forums',
      30 'from_fieldname' => 'forum_id',`
    - 与[phpBB.php](https://bbpress.trac.wordpress.org/browser/trunk/src/includes/admin/converters/phpBB.php#L18)相比：18 'from\_tablename' => 'forums',
      19 'from\_fieldname' => 'forum\_id',
    - 与[SimplePress5.php](https://bbpress.trac.wordpress.org/browser/trunk/src/includes/admin/converters/SimplePress5.php#L20)相比：`20 'from_tablename' => 'sfforums',
      21 'from_fieldname' => 'forum_id',`
    - 如果我们查看 Mingle Forums 数据库架构：
      `wp_forum_forums
      id
      name
      parent_id
      description
      views
      sort`
    - 计算得出的猜测将使我们将以下内容用于我们的第一个数据库映射

`'from_tablename' => 'forum_forums',
'from_fieldname' => 'id',`
下一步在论坛部分，用于[Example.php Line#24 中](https://bbpress.trac.wordpress.org/browser/trunk/src/includes/admin/converters/Example.php#L24)的第二个数据库映射“论坛父 ID”

- - - `24 // Forum parent id. If no parent, than 0. Stored in postmeta.
      25 $this->field_map[] = array(
      26 'from_tablename' => 'forum', 'from_fieldname' => 'parentid',
      27 'to_type' => 'forum', 'to_fieldname' => '_bbp_parent_id'
      28 );`
    - 这次计算出的猜测将使我们将以下内容用于我们的第二个数据库映射

`'from_tablename' => 'forum_forums',
'from_fieldname' => 'parent_id',`

1. 现在我们对 Example.php 中的每个现有数据库映射重复此操作
2. 连接特定字段值的表...
3. 标签 – 如果源论坛不使用话题标签，您可以从转换器中删除此部分，如果它确实编辑了“来自”值。
4. 用户…
5. 迁移 BBCode、笑脸和自定义 HTML……
6. 下一步…
