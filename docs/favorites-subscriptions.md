---
title: "收藏夹和订阅"
post_status: publish
post_name: favorites-subscriptions
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 176
  guid: "http://import.local/2021/12/24/favorites-subscriptions/"
---

bbPress 2.6 改变了收藏夹和订阅在数据库中的存储方式。此页面解释了原因，以及如果升级没有自动为您触发，您可能需要采取哪些步骤。
如果升级在完成之前失败，那没关系。您可以随时安全地重新运行升级，Tools > Forums 而不会破坏或复制数据。

### [警告](#caveat)

对于用户少于 10,000 的小型论坛，bbPress 将尝试自动迁移您的收藏夹和订阅。如果您的论坛有超过 10,000 名用户，bbPress 知道它可能需要比可用资源更多的资源，并且会跳过升级。

### [解释](#explanation)

bbPress 2.6 之前的所有版本都存储了收藏夹和订阅，wp\_usermeta每个站点上的每个用户都有 1 个值。在具有许多用户的多站点安装中，这会导致低效的数据库查询和许多从未以全局方式使用的全局可用行。
bbPress 2.6 采用将每个个人收藏和订阅存储在wp\_postmeta数据库表中的方法。这允许进行一些不同的改进

- 两种方式都可以更轻松地查询 - 每个用户和站点的订阅数，以及每个话题的订阅数
- 更少的行wp\_usermeta导致 WordPress 和 bbPress 中的单方面性能改进
- 收集用户电子邮件地址以发送订阅现在是一个非常简单且快速的数据库查询

### [手动升级](#manually-upgrade)

如果您是少数幸运的人之一，因为您拥有 10,000 多个用户，因此需要手动升级您的论坛，那么您需要查看 3 个 bbPress 功能bbpress/includes/admin/tools.php：

- bbp\_admin\_upgrade\_user\_forum\_subscriptions()
- bbp\_admin\_upgrade\_user\_topic\_subscriptions()
- bbp\_admin\_upgrade\_user\_favorites()

这 3 个函数执行以下操作：

- 查询wp\_usermeta 通过meta\_key 为所有用户谁已经收藏或订阅
- 循环遍历每一行，并将其拆分为帖子 ID
- 循环遍历每个帖子 ID，并将用户 ID 添加到它的元数据中，并使用适当的 meta\_key
- 如果添加的项数与原来匹配，usermeta则删除2.6之前的

您可能想要执行以下操作：

- 增加可用于 PHP 和 Web 服务器软件（Apache、Nginx 等）的内存量
- 增加运行这些脚本的服务器的物理内存
- 增加超时长度以允许这些脚本按原样运行几分钟
- 修改原始查询以限制用户 ID 结果循环。（通常一次 1000 个用户是一个不错的数字。）
- 注释掉 对测试的调用add\_post\_meta() 和delete\_metadata\_by\_mid()试运行

对于添加的上下文，这些是 bbPress 团队用来升级 BuddyPress.org、bbPress.org、WordCamp.org 和 WordPress.org 的相同脚本和技术。它们工作正常，而且工作得很好，但我们理解移动数据是可怕的，并希望您对幕后发生的事情做好准备并感到舒适。
