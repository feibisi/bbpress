---
title: "Step by step guide to setting up a bbPress forum – part 3"
post_status: publish
post_name: step-by-step-guide-to-setting-up-a-bbpress-forum-part-3
lang: en
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 101
  guid: "http://import.local/2021/12/24/step-by-step-guide-to-setting-up-a-bbpress-forum-part-3/"
---

Step by step guide to setting up a bbPress forum – part 3
Codex Home → Step by step guide to setting up a bbPress forum – part 3
Part 2 of the guide dealt with styling changes.
This part will deal with changing what appears and where it appears – changing some of the functionality of bbPress.
Now you can alter functionaility in many ways. These include
1. with plugins
2. with functions
3. by changing bbPress files
4. adding filters
5. adding hooks
1. Plugins
If you’re not familiar with coding, then plugins can offer a great way to add functionality without needing to do coding. There are lots around, if you’re after something it’s always worth trying a google search with “bbpress plugin” and whatever you are after.
Some I have used include :
bbP signature – lets users add a ‘signature’ to their posts – used a lot in forums
bbP topic views – displays how many times a topic has been viewed
and ones that might well be useful, but I haven’t used :
bbpress-notify – notifies admins, moderators etc. (fully configurable to role) when new post and replies are made
The rest of this part will assume that you have a child theme, if you’re not familiar with what this is and why you need it, please visit part 2 of this guide where it is all explained.
So lets assume you have a child theme.
2. Functions
A short guide on how to create a child theme and functions file can be found here
Functions files and child themes explained
3. Changing bbPress files
This part of the guide is primarily going to deal with the bbPress templates that the default bbPress plugin uses to display your forum.
NOTE: This part deals with changing templates that belong to the bbPress Plugin, and these changed templates should then reside within a bbpress folder in your theme.  HOWEVER if you create a bbpress.php file from a theme template or php file (that is a file that sites in your theme such as page.php) , then this resides in your theme’s root.  So if the source is the plugin, then bbpress folder;  if the source is your theme, then your theme folder !
Changing these files gives you a powerful way to improve how your forum works for your users, and in some cases making it easier for you to administer.
In part 2 we explained how changing files in the bbPress plugin was not a good idea, and these files are frequently overwritten on an upgrade. So to change files, you’ll need to copy them you your child theme.
Bbpress will normally use the default files found at
wp-content/plugins/bbpress/templates/default/bbpress
However if you create a directory in your child theme at
/wp-content/themes/%your-theme%/bbpress/
(where %your-theme% is your child theme’s name)
then any files stored there will be used instead.
This means that if you want to alter how a topic displays, then copying the relevant file (in this case loop-single-reply) to this folder will mean that bbPress uses this file instead, so you can now alter it to work how you want.
There are two sources that you might want to use for files – one is at
wp-content/plugins/bbpress/templates/default/bbpress
For instance in this bbPress folder you’ll find
loop-single-reply – this file displays a topic and all its replies letting you change the heading and the format within a post – for instance removing the avatar or adding extra words below it.
If you want to alter lower level files, then the other source is
wp-content/plugins/bbpress/templates/default/extras
Here you can alter for instance whether a single topic has a footer.
To alter any of these lower level files they need to be copied to the root of your child theme that is to
/wp-content/themes/%your-theme%/
(where %your-theme% is yout themes name).
So bbPress offers a simple way to change the layout and information displayed.
As an example, the default forum display looks like
which displays the forum counts for the sub-topics.
If you wanted to take these out to look like
Then you would need to change
loop-single-forum.php by changing how the code displays
so you would change line 44  from
 
 
to read
 
false,
‘show\_reply\_count’    => false,
‘separator’ => ”,
));  ?>
 
So copy the file loop-single-forum.php from wp-content/plugins/bbpress/templates/default/bbpress to /wp-content/themes/%your-theme%/bbpress/
and add the above function. Then save, and hey presto, the counts have gone !
For some starters on what you might want to change have a look at Layout and Functionality – Examples you can use
Part 4 deals with adding actions and
Part 5 deals with adding filters
