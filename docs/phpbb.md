---
title: "phpBB"
post_status: publish
post_name: phpbb
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [import-forums]
source:
  blog_id: 4
  post_id: 77
  guid: "http://import.local/2021/12/24/phpbb/"
---

phpBB
Codex Home → Getting Started → Importing Data → Import Forums → phpBB
phpBB v3.x Importer for bbPress
FAQ & Known Issues
Forums
Forum visibility such as moderator or admin only forums will be publicly visible after importing and you need to secure these manually.
‘Link Forums’ will be imported as a standard forum without any URL redirect link.
Topics & Replies
‘Announcement’ and ‘Global’ stickies are imported as bbPress ‘Super Stickies’, standard forum ‘stickies’ are imported as bbPress ‘Stickies’.
Custom phpBB BBCodes are not supported eg. [youtube] – You will have to manually change these yourself either before importing in phpBB or after importing into bbPress using phpMyAdmin.
Smilies are rendered as images if contained in ‘code’ tags eg. `:)`
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
phpBB does not support user profile support for ‘First Name’ and ‘Last Name’ only ‘member\_name’ and that will be the WordPress Username.
Existing passwords are converted during the import so users can login to WordPress/bbPress as soon as the import and recounts have finished.
phpBB Moderators, Groups, Ranks are not imported, any users you wish to make ‘moderators’ or ‘keymasters’ you will have to assign these roles manually via the main WordPress Admin User panel (/wp-admin/users.php).
User ‘Personal Messages (PM’s) are not supported or imported.
User ‘Avatars’ are also not supported ‘out of the box’ by either WordPress or bbPress, if the users email address is registered with a ‘Gravatar this will automatically be used by WordPress and bbPress, otherwise this is plugin territory. (See Note #1 below)
phpBB Signatures, Location, Occupation and Interests custom profile fields are also not supported by WordPress or bbPress ‘out of the box’. (See Note #2 below)
References
https://www.phpbb.com/community/faq.php?mode=bbcode
Notes
Note #1 – phpBB User Avatars
The phpBB avatar filename used in phpBB user avatars is imported and stored in the wp\_usermeta table as ‘\_bbp\_phpbb\_old\_user\_avatar\_filename’. phpBB stores user avatars in /phpbbv3/images/avatars/upload/ and with some tom foolery I am quite sure these can be imported into WP’s media library and with the right plugin enabled quite easily.
Note #2 – phpBB custom user profile fields stored in wp\_usermeta.
The following custom profile fields are imported into wp\_usermeta and as you build your community with WordPress and bbPress, maybe BuddyPress also this should help down the road in converting these values to whatever plugins and profile extensions you decide to use.
ICQ – ‘\_bbp\_phpbb\_old\_user\_icq’
MSN Messenger – ‘\_bbp\_phpbb\_old\_user\_msnm’
Occupation – ‘\_bbp\_phpbb\_old\_user\_occ’
User Insterests – ‘\_bbp\_phpbb\_old\_user\_interest
Location ‘\_bbp\_phpbb\_old\_user\_location’
Signature ‘\_bbp\_phpbb\_old\_user\_signature’ (All BBCode is also converted here into HTML)
