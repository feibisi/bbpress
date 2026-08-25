---
title: "Step by step guide to setting up a bbPress forum – Part 1"
post_status: publish
post_name: step-by-step-guide-to-setting-up-a-bbpress-forum-part-1
lang: en
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 99
  guid: "http://import.local/2021/12/24/step-by-step-guide-to-setting-up-a-bbpress-forum-part-1/"
---

Step by step guide to setting up a bbPress forum – Part 1
Codex Home → Step by step guide to setting up a bbPress forum – Part 1
bbPress is a plugin for WordPress that adds forum capability to your site.
bbPress inherits your currently active theme’s styles where it can to try and match your themes style. This can work really well on some themes, but sometimes doesn’t work well on others, so some styling may be needed. Out of the box, it works well with most of the default WordPress themes , but like I said it might need minor CSS styling to fix some layout issues.
Setting up WordPress requires some or all of the following stages depending on how you want it to look.
The instructions here generate a forum working within a twentyten theme that looks like:
 
In summary you need to
Install the plugin
Set up some test forums or import a forum
Create a WordPress page for your forum display
Amend any other settings
Hidden vs. public forums – decide which or a mixture suits you
Decide on registration/user logins – automatic or manual?
Manually adding users to your forum – if you have chosen this route.
Make sure bbPress uses the page template we want
Add a custom sidebar or use existing sidebar with conditional logic
So let’s get started.
 
1. Installing the plugin
So we’ll assume you have a site with wordpress installed
Go to dashboard>plugins>add new
You will see bbPress part of the featured plugins then install and activate.
You can also type ‘bbpress’ into the search bar , and that should lead you to the latest version then install and activate from there.
 
2. Set up some test forums
Go into Dashboard>forums>add new
Add a forum and name it whatever you want, but you need at least one to get the forum page going (you can always delete it later).
Now go into the dashboard>topics and create a new topic.  Again you can trash this later, but you’ll want to see what one looks like.
Okay, so now we have bbPress with one forum and one topic, but we’ll need to show it somewhere,  so go to 3 below.
2. Alternative  –  Import a forum !
If you’re planning on migrating from a different forum and would like to use bbPress but keep all of your original forum data, then you will need to import your existing forum data into bbPress.
To import forums go to Dashboard > Tools > Forums and go to the tab “import forums”
If you need anymore help during this importing process there is a guide that will help you here.
https://codex.bbpress.org/document/
 
3. Creating a forum page
Now we have some forums, we need to have somewhere to display them.
There are two ways to do this. Most themes support method 1, and this can (can not will) produce tighter theme integration on style . However Method 2 allows you to have some introductory words. Your choice…!
Method 1
This requires a couple of checks first
a. In Dashboard>settings>forums look for what is set in the forum root under the forum root slug heading. The default is ‘forums’ but you can set this to anything
b. In Dashboard>settings>permalinks check that the common settings check is set to ‘postname’ If it isn’t and you don’t want to change it, then use method 2.
Now just create a wordpress page that has the heading that was found in a. above eg if the root slug is ‘forums’ create a page with the title ‘forums’, and save.
Once the permalink has been created, you can rename the page to whatever you wish eg ‘mysite forums’ (as the permalink will stay the same, and it is this permalink that bbpress looks for)
Save this page, add it to a menu if you are using custom menus, or decide its order if you have automatic menus. Then publish it to your site.
Job done!
Method 2
If either your theme doesn’t work with method 1, you don’t want permalinks with postname, or you want to use some introductory text (eg “welcome to our forums…”, then method 2 is for you.
In dashboard>pages
go to add new page
Call this ‘Forums’ or whatever you want your menu item to be.
Then in the content section, you may want to have some introductory words “welcome to the forum” etc. then add the following bbpress shortcode
[bbp-forum-index]
Save this page, add it to a menu if you are using custom menus, or decide its order if you have automatic menus. Then publish it to your site.
You will now have a forum page, and a forum to display.
 
4. Amending any other settings
There are several parameters which you can set to get bbPress working as you want it.
These are accessed via Dashboard>Settings>forums
See  https://codex.bbpress.org/document/configuring-bbpress/forum-settings/  for further details.
 
5. Forum Visibility and access
You can use a combination of forum visibility and registration to set up who can :
see your forums
post in your forums
Forum visibility:
Public – Anyone can see these forums
Private – Only logged in registered users with a forum role  can see these forums
Hidden: Only Moderators/keymasters can see these forums
Visibility is set for each forum, go into Dashboard>forums> and when you add/edit a forum, you will see visibility options on the right hand side in the forum attributes.
Users then have a forum role which can be
spectator
particiapant
moderator
keymaster
blocked
 
Forum access
You can set whether users need to be registered and control the registration process.
These two controls give you various degrees of control
Public viewing, public posting
By default forums are available to be publically viewed.  If you set anonymous posting to be on (see 4. Above) then anyone can also post.  This is the most public version of the forum.  It can lead to lots of spam being posted, and does hand control of what’s said in your forums to the internet community, with you effectively being able to only delete afterwards.
Public viewing, registered user posting
Here anyone can view the forums, but only registered users can join in and post.  Registration can be automatic or manual – see 6. below
private viewing, registered user posting
Here you have a private forum. Only registered users can view and post.  Here it would be very unusual to allow automatic registration, and this will be typically a manual process.  To set a forum as private go into dashboard>forums and select edit for the forum you wish to be hidden.  Under the forum attributes on the right hand side, set visibility to private.
 
6. Automatic vs manual registration
If you do not permit anonymous posting, then your users will need to register with your site. It is up to you to decide which method is preferable.
Automatic registration is easier and it does allow people to quickly sign up, but by the same token gives you less control over who is contributing to your forums, and can lead to spam postings.
Manual signup involves you in more administration, but does give you complete control over who has write access.
Neither is better overall, but one will be better for you !
To allow automatic registration, go to Dashboard > Settings > General settings and under membership, tick “anyone can register”.  Then in Dashboard > settings > forums tick the auto role, and ensure this is only at participant level.
To set manual registration, go to Dashboard > Settings > General settings and under membership, and ensure  “anyone can register” is not ticked.  Then in Dashboard>settings>forums tick the auto role, and ensure this is only at participant level.
In both cases, you will then need a screen for users to register – we’ll come back to where to put this screen later, but for the moment go into dashboard>pages>add new page and create a page.  You can call this page anything you like but “register” or “registration” would be logical when users view or access its URL.
If you are doing automatic registration, then put whatever preamble you’d like (“to register for our forums” etc.) , and then add the following shortcode  [bbp-register].  Save the page.
If you opt for manual registration, then you’ll either need to get your users to email you, or set up a contact form for them to use.
To get you going quickly, maybe just set the page to have you preamble followed by an email link such as
[email us your details here](mailto:admin@mysite.com?subject=Register&body=Name:%0AEmail address:%0A) 
Remember to write this in the “text” tab of the content, so that the html is understood.
There are lots of contact form plugins, which you can use later to get a registration form going on this screen.  By all means set this up now, but a placeholder email will get you enough to see how it works.
So now we have a page where our users can register.
 
7. Manually adding forum users to your site and editing them.
If you have opted for manual registration (and it’s what  I do), then when you receive either a contact form or email as set up in 6 above, you’ll need to add each user.
Go into Dashboard>users>add user
Enter their details as required.  You can use the “send email” to automatically send them their details from within your site, or you can email external to the site afterwards using your favourite software.  I use an email template within outlook as I can then send “joining instructions”  and “forum rules” as part of the signup.
You’ll not see any bbPress forum related user options/settings at this stage.
If you want to set/amend access level – say to make a user a moderator, then you’ll need to create the user first, and then go back into edit, and now you’ll see an option at the bottom of the amend screen to allow you to change access levels.
Manually adding users also allow you to take away the “toolbar” , which I feel always draws away from the look and feel of the site.  We’ll give profile access later in this setup, so it’s not needed.
WHERE HAVE WE GOT TO?
So we now have a forum (or two) on a page which is accessible from the menu.  We’ve decided if any/all forums will be hidden, and who and when people can contribute.  We’ve set up a registration process (albeit the manual one might be a bit basic).
However we’ve not given anyone a place to logon, or indeed register, or anywhere where they can see the latest posts.
You can do this by adding these into a sidebar, or if you are using a full-width page, but adding them to a menu.
But first you need to see if you need to change what page template bbPress is using for your site.
 
8. Make sure bbPress uses the page template we want
So you may want bbpress to display differently than the template it chooses for instance you might want your forum on a full width page and find that it uses a sidebar template, or visa versa.
If you have some knowledge of editing files then follow this guide to help create a bbpress.php file to use for all your bbPress pages.
https://codex.bbpress.org/theme-compatibility/getting-started-in-modifying-the-main-bbpress-template/
Otherwise a more basic explanation follows :
By default bbPress will use a page template in your theme root folder.
It will look for the existence of several files in the following order, using the first one it finds.
plugin-bbpress.php
bbpress.php
forums.php
forum.php
generic.php
page.php
single.php
index.php
Typically most (but not all) themes have a page.php, so if you do nothing else, chances are that that’s the one it will use.
To get bbpress to use a different template from the one your theme is using just copy that template and rename it bbpress.php within your theme root. This is explained a bit more below.
So you may want bbpress to display differently than the template it chooses for instance you might want your forum on a full width page and find that it uses a sidebar template, or visa versa.
You can even find that bbPress appears differently when displaying the forum index than it does with topics, which is probably not what you want. Nowadays theme developers will quite often use “if…” code within the page template to change the display of types of pages. Since topics share the same characteristics as posts, but the index page is more like an “about” page, the theme can believe that it should show then in different ways.
If bbPress is using the page layouts you want, then that’s fine, and you can ignore the rest of this section.
If not, then the following will let you set bbPress up in the way you want.
You theme will have page templates in the root of the directory, that is :
wp-content/themes/%mytheme%/ where %mytheme% is your theme’s name.
You’ll need to find the name of the page template that you want to use. Look in your theme’s directory – normally they are named very obviously – eg pagefullwidth or pagesidebar. If it’s not obvious, you can see what the template is called by editing a page that has the correct layout, and looking at the name of the template on the right hand side of the edit screen in a panel under the publish/update panel. If you then open the various page.php files, you see that they are named in the first few lines, so you can easily match the name.
So once you know which page template file you need, copy this and rename the copy to bbpress.php
Place this file in the root of your theme ie wp-content/themes/%mytheme%/bbpress.php where %mytheme% is your theme’s name.
bbpress will the use this file for all it’s pages.
If you want to customise the layout for your forums, you can then do this within this file.
 
9. Creating a forum specific sidebar
For most sites, the forum is part of a larger experience, and it is really useful to have a separate sidebar for the forum page that has forum specific widgets on it.
If your forum is all that is on your site, then the default sidebar may be all you need. But If you want to add a sidebar just for your bbPress pages then please follow this tutorial.
Creating a bbpress specific sidebar
 
10. Adding forum menu items
If you don’t use sidebars or footers to display your login and register items, (or even if you do) you’ll probably want to add some menu items.
You can do this quite easily here is how.
First you go to Appearance > Menus.
If you haven’t created a menu for your site , then create one.
You then select the menu you want to edit.
Now you go to the Custom Links section to your left and enter the url of the form you want to lead them to.
So the url of the login form of your site would be
http://yoursite.com/wp-login.php
Where “http://yoursite.com” is your sites url.
And the Link Text would be “Login”.
If you want to put a link to the registration form it would be
http://yoursite.com/wp-login.php?action=register
And the lost password form would be
http://yoursite.com/wp-login.php?action=lostpassword
You can of course use front-end login forms and link to them,
You can also use this plugin to control when to show these menu links to users when they or logged out or haven’t created an account to your site.
https://wordpress.org/plugins/menu-items-visibility-control/
 
AND THAT’S IT !
Now you have a fully functional forum !!!!
Users can register, login, see what forums are available, and contribute.
It may look a little rough at points, this will be clashes between bbPress and your theme, and we’ll start to deal with these in part 2
