---
title: "bbPress 使用您的语言"
post_status: publish
post_name: bbpress-in-your-language
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 65
  guid: "http://import.local/2021/12/24/bbpress-in-your-language/"
---

与 WordPress 一样，bbPress 具有可用于任何语言的内置功能。下面的说明假定您已经配置[在您的语言的WordPress](https://codex.wordpress.org/WordPress_in_Your_Language)，并[在您的语言安装WordPress。](https://codex.wordpress.org/Installing_WordPress_in_Your_Language)
与 WordPress 一样，您无需动动手指即可应用 bbPress 翻译或翻译更新。大多数站点现在都能够在后台自动应用这些更新。如果您的站点能够在不输入 FTP 凭据的情况下进行一键更新，那么您的站点应该能够自动更新翻译。
您的语言没有了吗？
bbPress 翻译包仅在翻译 100% 翻译时更新，如果您在更新翻译后没有看到您的语言，请考虑为 bbPress[翻译项​​目](https://translate.wordpress.org/projects/wp-plugins/bbpress)做出贡献，开始查看[翻译 WordPress](https://codex.wordpress.org/Translating_WordPress "翻译 WordPress")并发布您的任何问题在WordPress的Polyglots博客。
手动覆盖翻译
1. 最新（稳定）版本的 bbPress 和 dev
转到<https://translate.wordpress.org/projects/wp-plugins/bbpress>并选择您的首选语言，例如简体中文（中国大陆）
选择“稳定（最新版本）”或“开发（主干）”。
选择“所有当前”为“.po”并单击“导出”并将此文件保存到您计算机上的文件夹中，这次再次选择“.mo”
2. 直到 2.6.x 版本
转到[https://translate.wordpress.org/projects/bbpress/](https://translate.wordpress.org/projects/bbpress)并从子项目中选择版本
选择您的首选语言，例如[简体中文（中国）](https://translate.wordpress.org/projects/bbpress/2.6.x/zh-cn/default)
选择“所有当前”为“.po”并单击“导出”并将此文件保存到您计算机上的文件夹中，这次再次选择“.mo”
如何使用语言文件
将文件中的每个文件重命名为bbpress-language\_COUNTRY.extension
例如。bbpress-plugin-zh-cn.po到bbpress-zh\_CN.po
和bbpress-plugin-zh-cn.mo到bbpress-zh\_CN.mo。
注意：确保按照上述示例在正确的位置使用-和\_。
使用 FTP 将.po和.mo文件上传到WordPress 安装的/wp-content/languages/bbpress/。如果/wp-content/languages/和/wp-content/languages/bbpress/文件夹不存在，请创建它们。
