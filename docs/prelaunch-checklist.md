---
title: "启动前检查清单"
post_status: publish
post_name: prelaunch-checklist
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 134
  guid: "http://import.local/2021/12/24/prelaunch-checklist/"
---

向全世界发布 bbPress 是一件大事，需要很多手动步骤才能确保所有人都能安全舒适地进行更新和升级。以下是核心团队在每个新版本中执行的步骤。

1. 在 codex 上编写发布版本页面（即 https://codex.bbpress.org/releases/version-2-5-5/）
2. 将新版本页面添加到 codex Releases 页面 (https://codex.bbpress.org/releases/)
3. bbpress.php 中的冲突版本（插件标题）
4. src/bbpress.php 中的冲突版本（插件标题 + $this->version (setup\_globals())）
5. 在 src/bbpress.php ($this->version (setup\_globals())) 中修改数据库版本
6. 开发主干/src readme.txt 中的冲突版本
7. 在开发主干/src readme.txt 中插入稳定标签
8. 在 readme.txt 中为该版本添加新的升级通知
9. 向 dev svn 存储库提交碰撞
10. 如果这是一个主要的 xy 版本，从主干创建 dev 分支
11. 导出 dev 分支部署分支
12. 从 dev 分支创建部署标签
13. 更新 wp.org 主干中的 readme.txt，包括 stable 标签。该版本现已上线。

现在您已经标记了一个新的 bbPress 版本，是时候向全世界宣传它了！

1. 在 bbpress.org 上写一篇博文
2. 在 bbpress.org 的下载页面中更新版本号。
3. 在 bbpdevel.wordpress.com 上写一篇博文
4. bbpress.org/forums 中的论坛公告

快完成了！

1. 在 bbpress.php (2.1-alpha) 中将开发主干提升到 alpha
2. 在 bbpress.php (2.0.1-alpha) 中凹凸新创建的 dev 分支
3. 同步部署主干和开发主干
4. 更新 https://codex.bbpress.org/releases/

GlotPress 翻译字符串

- bbPress 的翻译由 GlotPress 处理
- 开发字符串在这里 https://translate.wordpress.org/projects/wp-plugins/bbpress
- bbpress.pot 的来源 https://bbpress-i18n.svn.wordpress.org/pot/trunk/bbpress.pot
- 通过运行grunt release和推送到 https://plugins.svn.wordpress.org/browser/bbpress/trunk/ 的定期更新将使#Polyglots 翻译人员感到高兴
- 当新版本临近时，这也允许相对容易的“字符串冻结”
- 注意：以上两行不影响 bbPress，而bbpress.pot保留在bbpress-i18n.svnrepo 中。
