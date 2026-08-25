---
title: "搜索重定向到首页"
post_status: publish
post_name: search-redirects-to-front-page
lang: zh
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 175
  guid: "http://import.local/2021/12/24/search-redirects-to-front-page/"
---

此问题包括从论坛索引页面上方的搜索表单、话题索引页面或 bbPress 论坛搜索小工具在 bbPress 论坛搜索中进行的任何搜索，以某种方式重定向到您网站的首页。

### [原因](#causes)

这可能是用户 在“单一论坛 Slug”部分的“设置”>“论坛”中编辑论坛搜索 slug 引起的用户问题。一些用户将论坛搜索变成了一些包含两个单词之间的空格的东西，比如“论坛搜索”。最后，在使用这个 slug 时会输出一个%20 之类的 url  来代替空格，并且几乎肯定会每次都重定向到主页。
在某些情况下，在“设置”>“论坛”中禁用论坛 root slug可能会出现相同的问题。

### [解决方案](#solutions)

将“设置”>“论坛”中的论坛搜索自定义 slug 编辑为不带空格的内容，只需将空格替换为例如破折号，例如 (forum-search)。
如果您在论坛中禁用了论坛 root slug，请使其不再出现问题，或者将论坛搜索 slug 更改为默认 slug“搜索”以外的其他内容。
如果问题仍然存在，请确保您已完成此处所述的插件和话题问题解决方案： [故障排除](/document/troubleshooting/)
