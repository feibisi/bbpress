---
title: "Invision"
post_status: publish
post_name: invision
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [import-forums]
source:
  blog_id: 4
  post_id: 80
  guid: "http://import.local/2021/12/24/invision/"
---

Invision
Codex Home → Getting Started → Importing Data → Import Forums → Invision
Invision IPB v3.1x, v3.2x, v3.3x & v3.4x Importer for bbPress
FAQ & Known Issues
Forums
Forum visibility such as moderator or admin only forums will be publicly visible after importing and you need to secure these manually.
‘Link Forums’ will be imported as a standard forum without any URL redirect link.
‘Locked Forums’ will be imported as like a normal open forum, again you can close/lock these via the forums panel in wp-admin and setting the forum attributes status to closed.
Topics & Replies
Announcement and Sticky topics ‘topic status’ are not set during import, manually ‘stick’ any topics after import and recounts are complete. (See trac ticket #2126)
Custom BBCodes are not supported eg. [youtube] – You will have to manually change these yourself either before importing in Invision/IPB or after importing into bbPress using phpMyAdmin.
BBCodes not converted: [post=’123′]abc[/post] & [topic=’456′]def[/topic]
Smilies are rendered as images if contained in ‘code’ tags eg. `:)`
Smilies NOT converted::huh:, :wacko:, ^\_^, :wub:, -\_-, <\_ < & :ph34r:
No file attachments are imported.
All ‘Ordered Lists’

will be displayed as numerical lists.
You may find extra page breaks   
 and paragraph

elements in topics and replies and is less than ideal and is from the way the BBCodes are converted during the forum import conversion. You will find these primarily around ‘blockquotes’ and ‘lists’
If you are using bbPress ‘Show Lead Topic’ some of the formatting will be broken, it has been converted correctly and is an issue with the content-single-topic-lead.php template, see trac # (Ticket to follow).
 elements seem to be a hit and miss at the moment, they render sometimes and sometimes not depending on the import. (not very helpful I know, still digging around this issue)
![](//example.com/file.jpg) are not currently enabled to be embedded inline in bbPress by default with topics and replies, everything was converted correctly and we just need to throw some switches and push some buttons before the next release of bbPress to make it work, watch this space.
Users
Invision does not support user profile support for ‘First Name’ and ‘Last Name’ only ‘name’ and ‘display\_name’ and ‘name’ will be the WordPress Username.
Existing passwords are converted during the import so users can login to WordPress/bbPress as soon as the import and recounts have finished.
Invision/IPB Moderators, Groups, Ranks are not imported, any users you wish to make ‘moderators’ or ‘keymasters’ you will have to assign these roles manually via the main WordPress Admin User panel (/wp-admin/users.php).
User ‘Favourites’, ‘Subscribed Topics’ or ‘Personal Messages (PM’s) are not supported or imported.
References
Notes
