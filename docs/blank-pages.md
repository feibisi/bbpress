---
title: "空白页"
post_status: publish
post_name: blank-pages
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 153
  guid: "http://import.local/2021/12/24/blank-pages/"
---

此问题包括当您尝试访问该站点时出现空白屏幕加载。此问题的两个常见原因是由插件和主题引起的。
如果您可以访问管理面板，那么查明此问题的最佳方法是尝试一一停用除 bbPress 之外的所有插件。如果这不起作用，请尝试将您的主题更改为默认主题，如二十二。

### [原因](#causes)

原因可能是以下任何一种。

- 内存限制
- 主题
- 插件
- 自定义php代码函数
- 长篇帖子缓存

### [解决方案](#solutions)

按照主题/插件问题的常见故障排除步骤操作，并清除[故障排除中](/document/bbpress/troubleshooting/)列出的缓存。如果这不能解决您的问题，请尝试以下方法之一来增加内存限制以解决此问题。
使用 php.ini 增加内存限制
如果您可以访问 PHP.ini 文件，请更改 PHP.ini 中
的行 如果您的行显示 32M，请尝试 64M。
使用 wp-config.php 增加内存限制
打开位于 WordPress 目录根目录下的 wp-config.php 文件。现在将以下代码添加到文件中。

```
define('WP_MEMORY_LIMIT', '64M');
```

使用 htaccess 增加您的内存限制
您也可以将这段代码添加到您的 htaccess 代码中。

```
php_value memory_limit 64M
```

如果您无法通过上述方法解决问题，则意味着您的托管服务提供商阻止了内存限制的增加。立即联系您的网络托管服务商的支持人员。
