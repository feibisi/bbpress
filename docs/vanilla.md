---
title: "Vanilla"
post_status: publish
post_name: vanilla
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [import-forums]
source:
  blog_id: 4
  post_id: 82
  guid: "http://import.local/2021/12/24/vanilla/"
---

Vanilla
Codex Home → Getting Started → Importing Data → Import Forums → Vanilla
Vanilla 2.0.18.1 Importer for bbPress
FAQ & Known Issues
Note: This is for the ‘stand alone’ Vannila Forums from vannilaforums.org, if you are trying to import from vanillaforums.com you will have to export your data and then perform a custom import.
Forums
Forum ‘Categories’ are imported as a ‘Forum’ – You must manually configure the forum types for ‘category’ forum type after the import and recounts have finished.
Forum visibility such as moderator or admin only forums will be publicly visible after importing and you need to secure these manually.
‘Locked Forums’ will be imported as like a normal open forum, again you can close/lock these via the forums panel in wp-admin and setting the forum attributes status to closed.
Topics & Replies
Announcement and Sticky topics ‘topic status’ are not set during import, manually ‘stick’ any topics after import and recounts are complete. (See trac ticket #2126)
You may find extra page breaks   
 and paragraph

elements in topics and replies and is less than ideal and is from the way the BBCodes are converted during the forum import conversion. You will find these primarily around ‘blockquotes’ and ‘lists’
If you are using bbPress ‘Show Lead Topic’ some of the formatting will be broken, it has been converted correctly and is an issue with the content-single-topic-lead.php template, see trac # (Ticket to follow).
 elements seem to be a hit and miss at the moment, they render sometimes and sometimes not depending on the import. (not very helpful I know, still digging around this issue)
![](//example.com/file.jpg) are not currently enabled to be embedded inline in bbPress by default with topics and replies, everything was converted correctly and we just need to throw some switches and push some buttons before the next release of bbPress to make it work, watch this space.
Not all smilies are converted, only the subset the WordPress has built in.
Users
User ‘Favorites’, ‘Subscribed Topics’ or ‘Personal Messages (PM’s) are not supported or imported.
User ‘Avatars’ are also not supported ‘out of the box’ by either WordPress or bbPress, if the users email address is registered with a ‘Gravatar this will automatically be used by WordPress and bbPress, otherwise this is plugin territory.
References
Notes
Customizing
Via bbpress.org if you are using the Vanilla2 ‘ReplyTo’ plugin you can add support for threaded replies to youur import via this customized version of the import script.
