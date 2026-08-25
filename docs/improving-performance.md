---
title: "提高性能"
post_status: publish
post_name: improving-performance
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 150
  guid: "http://import.local/2021/12/24/improving-performance/"
---

性能是任何网站的关键，希望本指南能让您走上正确的轨道，以优化您的网站以在您的社区发展的同时执行。

### [主机托管](#hosting)

您拥有的服务器是快速网站最重要的一步，整体性能从您的主机服务器和硬件开始。
确保您拥有功能强大且功能强大的服务器，例如 Apache，或者使用 Nginx，因为它非常高效，但任何可以运行 PHP 或 MySQL 的服务器都应该没问题。
如果您的社区开始大幅增长，请将您的托管环境升级到虚拟专用服务器或更好的专用服务器，以便每天处理大量用户和帖子。虽然可以在共享托管环境中运行 bbPress，并且对于小型社区来说效果很好，但您的社区发展得越多，您的站点就越慢，共享托管就越不是一个可行的选择。
bbPress 和 WordPress 在丰富的托管环境中工作得最好。要为您的主机寻找推荐的解决方案，您可以查看此[特色 WordPress 主机列表](https://wordpress.org/hosting/)。

### [操作码缓存](#opcode-caching)

显着提高性能的一种极好方法是在您的服务器上安装 Opcode 缓存器。这可以通过缓存来自先前请求的 PHP 操作码来提高页面加载和每秒请求数。
要安装 Opcode 缓存器，您需要联系您的托管服务提供商并要求他们为您安装它，或者询问他们是否有帮助您在服务器上安装它的指南。
请注意，在大多数情况下，您将无法在共享主机上安装操作码缓存器，因为运行它需要大量内存。
以下是众所周知的 Opcode 缓存器列表：

- [OpCache](http://php.net/manual/en/book.opcache.php)
- [APC](http://pecl.php.net/package/APC)
- [XCache](http://xcache.lighttpd.net/)

### [对象缓存](#object-caching)

对象缓存是缓存复杂的 SQL 查询，因此它们不会在页面加载中多次执行。使用对象缓存器将使用 WordPress 缓存 API 缓存任何内容，这将阻止 WordPress 缓存到默认选项表，而是使用您安装的任何对象缓存后端。
然后，您需要选择要使用的持久缓存类型。您还可以使用其中一些操作码缓存器来进行对象缓存。
也可以在您站点上的内存对象缓存器中使用这些。

- [Memcached](http://memcached.org/)
- [Redis](http://redis.io/)

要使对象缓存与 WordPress 一起使用，您需要安装一个插件，该插件会将对象缓存插入文件添加到您的 WordPress 站点。有多个对象缓存后端插件会添加这个对象缓存插入文件，例如这个用于[APC](https://wordpress.org/plugins/apc/) 或这个用于[Memcached](https://wordpress.org/plugins/memcached/)  ，W3 Total Cache 也支持其中的大部分。
对于多服务器设置，您可能需要考虑使用 Memcached。
在共享服务器上，您可以使用磁盘来存储经常访问的数据，但这可能会导致问题并实际上降低站点的速度。

### [页面缓存](#page-caching)

页面缓存非常适合您的网站页面、博客文章和网站首页，但由于论坛高度动态且用户不断更新，页面缓存实际上取决于您如何设置 bbPress 论坛。
如果您只允许用户在登录时发帖，最好只为访客用户提供缓存。如果您在插件中找到设置缓存刷新的选项，请确保将其设置为较短的时间，例如大约一两个小时。同样在 bbPress 文章类型更新后，大多数 bbPress 兼容缓存插件将刷新缓存，一切都应该再次新鲜。
如果您允许用户在未注册到您的站点的情况下发帖，页面缓存可能不是非常实用的解决方案。因此，建议从页面缓存中排除 bbPress 论坛页面，以便您的论坛页面不会向访客用户显示过时的信息。如果您的论坛非常活跃，您也可以考虑这样做。
要禁止页面缓存中的论坛页面，请进入您最喜欢的缓存插件并将这些字符串添加到被拒绝的页面/字符串以缓存设置。
如果您为您的论坛保留了论坛 root slug，您可以将此论坛字符串用于大多数 bbPress 页面，以及主题存档的主题字符串。

```
/forums/
/topics/
```

如果您在论坛设置中禁用了论坛 root slug，则可以使用这些字符串集。

```
/forums/
/forum/
/topics/
/topic/
/reply/
```

如果您在论坛设置中设置了自定义 slug，您可以将我放置的字符串替换为您的自定义字符串。
为了获得更好的页面缓存性能，可以允许使用操作码缓存器 Redis。或 Memcached 将您的页面存储在内存中，但请记住，论坛往往有更多可缓存的页面，您可能需要密切关注网站上的 RAM 使用情况。

### [优化您的数据库](#optimize-your-database)

这是可选的。
当删除帖子、频繁编辑帖子、将帖子标记为垃圾邮件时，您的数据库将开始积累大量额外数据。即使每个部分单独可能是几个字节的数据，一段时间后这些数据将开始累加并可能影响您的服务器从数据库表中检索信息的时间。通过清理和删除您可能不需要的数据（例如占用数据库的垃圾邮件），优化数据库会略微提高性能并减小数据库大小。
虽然您可以使用 SQL 命令 OPTIMIZE TABLE 优化数据库表，或者通过选择每个表并从下拉菜单中选择优化表来运行优化 phpMyAdmin 中的数据库表的功​​能，但您只需使用一个方便的 WordPress 插件来优化您的数据库。安装[WP-DBManager](https://wordpress.org/plugins/wp-dbmanager/)和[WP-Sweep](https://wordpress.org/plugins/wp-sweep/)等插件或任何其他替代品，将允许您优化大部分数据库。
使用这些插件之一优化数据库时，您可能会看到删除此类数据的选项。我只是要告诉您在我看来可能很重要的选项，为什么您可能不运行它，以及为什么运行一个选项可能有用。我还建议至少一两个月优化一次数据库。
在执行任何操作之前，建议您在运行任何选项之前执行[数据库备份](/document/backing-up-your-database-and-files/)，因为删除数据是永久性的。

- 删除修订——虽然这可能很有用，尤其是当您疯狂地编辑您的帖子时，bbPress 使用 WordPress 中的帖子修订系统来进行话题和回复编辑日志记录。如果您想在您的帖子中保留编辑日志，其他插件可能是自定义 CSS 插件的修订系统。如果您觉得可能会丢失一些重要的东西，请不要运行它。
- 删除已删除/已删除的帖子- 如果您认为您删除的任何类型的帖子（包括话题、回复和博客帖子）都应该被删除而不会出现任何错误，您可以运行此程序。
- 删除垃圾邮件- 此选项通常包括垃圾邮件评论。垃圾评论可以很好地扩大您的数据库，它们通常每月至少会被 WordPress 自动删除一次，但使用这些插件可以缩短时间。

由于您可能有大量垃圾邮件话题和回复，因此请确保如果要运行此功能，您最好删除所有回复和话题垃圾邮件。

1. 转到WordPress 后端中的回复 > 所有回复或话题 > 所有话题。
2. 单击垃圾邮件操作链接，您可以查看所选文章类型的所有垃圾邮件。
3. 现在点击清空垃圾邮件按钮删除所有文章类型的垃圾邮件。

- 优化表- 在 WP-Sweep 和 WP-DBManger 中，这应该类似于 phpMyAdmin 优化数据库表的方式。

### [核心代码改进](#core-code-improvements)

就像生活中的任何事情一样，总是有更多的改进空间。bbPress 2.6 版将启动一些性能改进，任何能够帮助测试并在[bbPress trac 中](https://bbpress.trac.wordpress.org/)为现有 trac 票证创建补丁的人，或者只是为 bbPress 贡献任何可能的代码改进建议的人都将不胜感激。

### [提高性能的其他方法](#additional-ways-to-improve-performance)

- 删除不必要的对象、功能和插件——只使用您需要的。
- 将数据卸载到外部源——使用 CDN 或附加服务器来保存静态内容，可以大大减少带宽、服务器负载并加快您的网站速度。
- 缩小或组合您的网站 CSS 和 JS – 缩小 JavaScript 和 CSS 可以减少文件的大小，而组合将最大限度地减少对多个文件的请求。
- 启用浏览器缓存
- 头部的 CSS 和页脚的 JS
- 优化图像– 如果您的用户使用 bbPress 插件在您的论坛中上传了大量 Gif 和 JPEG，您会注意到这些图像会减慢您的主题加载时间。启用某种图像优化将减小这些图像的大小并使带有图像的帖子加载速度更快。
- 使用延迟加载– 使用延迟加载插件（如[Lazy Load](https://wordpress.org/plugins/lazy-load/)或[Rocket Lazy Load）](https://wordpress.org/plugins/rocket-lazy-load/)将最小化请求并仅在用户可见时显示图像。
- 使用 Gzip 压缩

### [其他资源](#additional-resources)

- [您如何衡量绩效](https://codex.wordpress.org/WordPress_Optimization#How_Do_You_Measure_Performance.3F)
- [WordPress 优化](https://codex.wordpress.org/WordPress_Optimization)
- [WordPress 性能](https://codex.wordpress.org/WordPress_Optimization/WordPress_Performance)
- [WP 对象缓存](https://codex.wordpress.org/Class_Reference/WP_Object_Cache)
- [缓存](https://codex.wordpress.org/WordPress_Optimization/Caching)
- [WordPress 的高流量提示](https://codex.wordpress.org/High_Traffic_Tips_For_WordPress)
- [服务器优化](https://codex.wordpress.org/WordPress_Optimization/Server_Optimization)
