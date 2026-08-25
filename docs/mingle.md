---
title: "Mingle"
post_status: publish
post_name: mingle
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [import-forums]
source:
  blog_id: 4
  post_id: 79
  guid: "http://import.local/2021/12/24/mingle/"
---

Mingle
Codex Home → Getting Started → Importing Data → Import Forums → Mingle
Mingle Forums WordPress Plugin v1.0.33.3 Importer for bbPress
FAQ & Known Issues
Forums
Forum ‘Categories’ are not imported from wp\_forums\_groups you will need to manually create these ‘parent forums’ and assign the forums to these after the import and recounts have finished.
Topics & Replies
Sticky topics ‘topic status’ are not set during import, manually ‘stick’ any topics after import and recounts are complete. (See trac ticket #2126)
Custom BBCodes are not supported eg. [youtube] – You will have to manually change these yourself after importing into bbPress using phpMyAdmin.
Smilies are rendered as images if contained in ‘code’ tags eg. `:)`
You may find extra page breaks   
 and paragraph

elements in topics and replies and is less than ideal and is from the way the BBCodes are converted during the forum import conversion. You will find these primarily around ‘blockquotes’ and ‘lists’
If you are using bbPress ‘Show Lead Topic’ some of the formatting will be broken, it has been converted correctly and is an issue with the content-single-topic-lead.php template, see trac # (Ticket to follow).
 elements seem to be a hit and miss at the moment, they render sometimes and sometimes not depending on the import. (not very helpful I know, still digging around this issue)
![](//example.com/file.jpg) are not currently enabled to be embedded inline in bbPress by default with topics and replies, everything was converted correctly and we just need to throw some switches and push some buttons before the next release of bbPress to make it work, watch this space.
Users
If you are going to use the same WordPress install for your import you do not need to import the users as they are already in the WordPress wp\_users table. If you are setting up a fresh install of WordPress simple check the ‘convert users’ option before you start your import.
Any custom Mingle Moderators or Groups are not converted, any users you wish to make ‘moderators’ or ‘keymasters’ you will have to assign these roles manually via the main WordPress Admin User panel (/wp-admin/users.php).
User ‘Favourites’, ‘Subscribed Topics’ or ‘Personal Messages (PM’s) are not supported or imported.
References
Importing Mingle Forums into bbPress?
Notes
