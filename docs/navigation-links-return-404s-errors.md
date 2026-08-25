---
title: "导航链接返回 404s 错误"
post_status: publish
post_name: navigation-links-return-404s-errors
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 152
  guid: "http://import.local/2021/12/24/navigation-links-return-404s-errors/"
---

这是安装 bbPress 后的常见错误。问题涉及您的 WordPress 安装或服务器配置。

### [原因](#causes)

原因可能是以下任何一种

- 未安装 Apache mod\_rewrite 模块
- 您的 WordPress [.htaccess](http://httpd.apache.org/docs/2.2/howto/htaccess.html)文件丢失或无法被 Web 服务器写入。

### [解决方案](#solutions)

该问题很容易解决，请通过这些步骤尝试解决您的问题。

1. 首先确保您的服务器上安装了 mod\_rewrite 模块。
2. 现在转到“设置”>“永久链接”并将您的永久链接选项设置为默认值以外的选项。

如果问题仍然存在，请确保您已经解决了此处所述的常见问题：[故障排除](/document/bbpress/troubleshooting/)
如果在所有这些之后问题仍然存在，请联系您的网络托管服务商支持以获得有关您的问题的其他支持。
