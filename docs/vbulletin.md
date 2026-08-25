---
title: "vBulletin"
post_status: publish
post_name: vbulletin
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [import-forums]
source:
  blog_id: 4
  post_id: 78
  guid: "http://import.local/2021/12/24/vbulletin/"
---

vBulletin
Codex Home → Getting Started → Importing Data → Import Forums → vBulletin
vBulletin v4.x Importer for bbPress
FAQ & Known Issues
Known Issues: Users must reset their password manually using /wp-login.php?action=lostpassword See #1969 for detailed password information.
Forums
Forum visibility such as moderator or admin only forums will be publicly visible after importing and you need to secure these manually.
‘Link Forums’ will be imported as a standard forum without any URL redirect link.
‘Locked Forums’ will be imported as like a normal open forum, again you can close/lock these via the forums panel in wp-admin and setting the forum attributes status to closed.
Topics & Replies
No file attachments are imported.
Users
vBulletin does not support user profile support for ‘First Name’ and ‘Last Name’ only ‘username’ and that will be the WordPress Username.
vBulletin Moderators, Groups, Ranks are not imported, any users you wish to make ‘moderators’ or ‘keymasters’ you will have to assign these roles manually via the main WordPress Admin User panel (/wp-admin/users.php).
User ‘Personal Messages (PM’s) are not supported or imported.
User ‘Avatars’ are also not supported ‘out of the box’ by either WordPress or bbPress, if the users email address is registered with a ‘Gravatar this will automatically be used by WordPress and bbPress, otherwise this is plugin territory.
vBulletin MSN, Skype custom profile fields are also not supported by WordPress or bbPress ‘out of the box’. (See Note #1 below)
References
http://www.vbulletin.com/forum/misc.php?do=bbcode
http://stackoverflow.com/questions/13920322/vbulletin-to-bbpress-conversion-how-can-i-redirect-the-old-urls-to-the-new-one
Notes
Note #1 – vBulletin custom user profile fields stored in wp\_usermeta.
The following custom profile fields are imported into wp\_usermeta and as you build your community with WordPress and bbPress, maybe BuddyPress also this should help down the road in converting these values to whatever plugins and profile extensions you decide to use.
ICQ – ‘\_bbp\_vbulletin\_user\_icq’
MSN Messenger – ‘\_bbp\_vbulletin\_user\_msnm’
Skype’\_bbp\_vbulletin\_user\_skype’
