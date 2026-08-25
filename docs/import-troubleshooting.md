---
title: "导入疑难解答"
post_status: publish
post_name: import-troubleshooting
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 131
  guid: "http://import.local/2021/12/24/import-troubleshooting/"
---

### [特定论坛导入](#specific-forum-imports)

确保您还检查每个论坛导入器法典页面以了解与每个论坛相关的特定问题，列表可在[此处](/document/custom-import/)找到。

### [导入被“卡住”](#the-import-gets-%e2%80%98stuck%e2%80%99)

导入话题或回复时，导入可能会“卡住”并且导入将不再继续导入。
> 这些类型的错误通常是由于该帖子中的某些编码问题造成的。有时这是从在某个时候完成的编码转换为 UTF8。不管它是什么，如果不对查询设置时间限制并将差异一分为二，直到我们可以缩小违规条目的范围并跳过它，这几乎是不可能检测到的。因为查询自然会花费很长时间，并且会导致丢失数据，所以我对这种方法不满意。

解决方法是查找并删除有问题的话题或回复，这既耗时又棘手，但这是现阶段的唯一方法。
这是我如何调试它并找到有问题的话题/回复：

- 导入挂起后，单击stop，记下它的位置，例如 Converting 11,299 – 11,300
- start再次单击，导入将从停止的地方继续
- 如果它再次挂起，请注意它再次达到的位置
- 完成后制作源数据库的新副本
- 现在删除数据库中所有不在导入过程中失败的行范围内的行
- 使用此数据库执行全新导入，并将“行数限制”设置设置为“1”
- 导入应该挂在有问题的话题/回复上
- 再次，记下它的话题/回复
- 点击停止，再次点击开始继续
- 一旦您有您的违规者名单并且导入完成，从数据库中删除这些行并再次测试以确保它完成而不会挂起
- 现在回到您的完整数据库（可能是原始数据库的副本）从数据库中删除这些相同的行并再次运行导入

### [调整 MySQL](#tweaking-mysql)

当您有非常大的论坛要导入时，可能需要很长时间。
[@ezyridah](https://buddypress.org/members/ezyridah/)执行了 100 万多条消息的 MyBB 导入，接近 4 万个话题和 400 多个成员，耗时约 48 小时，他添加了一些自定义 PHP 和 MySQL 调整，有助于加快速度，您可以看到他使用了哪些设置[在这里](https://bbpress.org/forums/topic/conversion-mybb-to-bbpress/#post-151257)，请注意，这是非常先进的，不适合胆小的人。

### [西里尔字母用户名](#cyrillic-usernames)

如果您需要在导入之前导入用户 'Cyrillic' 安装并启用[@SergeyBiryukov](https://profiles.wordpress.org/SergeyBiryukov/)的 [Allow Cyrillic Usernames](https://wordpress.org/plugins/allow-cyrillic-usernames/)。
