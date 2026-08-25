---
title: "WordPress 版本兼容性"
post_status: publish
post_name: wordpress-version-compatibility
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 174
  guid: "http://import.local/2021/12/24/wordpress-version-compatibility/"
---

bbPress 在最新可用版本的 WordPress 上运行时效果最佳——我们针对最新和最好的版本进行了优化。出于这个原因，bbPress 团队强烈建议所有 WordPress 安装保持最新。但是，我们努力保持对许多旧版 WordPress 版本的支持——通常是四个或五个主要版本。
在每个开发周期开始时，我们都会重新评估 bbPress 所需的最低 WP 版本。我们的粗略指导方针如下：

- 如果 WordPress 版本在一年多以前就过时了，那么它就是一个被删除的候选者。有关WP 发布日期的列表，请参阅<https://wordpress.org/news/category/releases/>。
- 如果 WordPress 版本的使用率低于所有 WP 安装的 5%，则它是一个强有力的删除候选者。有关 WordPress 版本使用情况的信息，请参阅<https://wordpress.org/about/stats/>。

当我们说 bbPress “支持”给定版本的 WordPress 时，我们是什么意思？大致：

- bbPress 应该在 WP 版本上无错误地运行（即，没有致命错误或 PHP 通知）。
- 如果新版本的 bbPress 包含需要最新版本 WordPress 的功能，则应在较早的 WP 版本上正常禁用该功能。
- WP 版本将包含在我们的[自动化测试版本中](https://travis-ci.org/bbpress/bbpress/)。

通过扩展：当我们“放弃支持”某个版本的 WordPress 时，这意味着我们停止将其包含在我们的构建中，停止回答与该特定 WP 版本相关的支持问题，并停止function\_exists()在构建时针对该版本进行检查（等）新的 bbPress 功能。放弃支持并不意味着我们会积极尝试破解旧版本的 WP ????
