---
title: "Step by step guide to setting up a bbPress forum – part 4"
post_status: publish
post_name: step-by-step-guide-to-setting-up-a-bbpress-forum-part-4
lang: en
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 104
  guid: "http://import.local/2021/12/24/step-by-step-guide-to-setting-up-a-bbpress-forum-part-4/"
---

Step by step guide to setting up a bbPress forum – part 4
Codex Home → Step by step guide to setting up a bbPress forum – part 4
Using Actions
Actions and Filters add a powerful way that you can alter how bbPress (and of course WordPress) work.
For the newcomer to WordPress, they are also probably one of the hardest to find information on. This tutorial tries to demystify some of this area, and help newcomers code those changes that will make their site work how they wish.
This section deals with actions.
1. Actions
These are things you can get wordpress to do at a particular point in the code.  So if you want to add something to an area, then an action is probably what you want.  WordPress and bbPress are full of actions points throughout the code.
So lets look at what one looks like, so that you can recognise it
They start with do\_action and then each one has a unique action name.
This example above occurs in the bbPress code before the author avatar on a topic or reply
So if you wanted bbPress to say the words “Posted by” before the author details are shown in a topic or reply, you’d create some code that would “hook” to this action, and that’s what the code will do.
2. Finding the code
So where is the code that we need to look at?
This is of course the first issue with bbPress (as with any other part of WordPress – finding out what file needs to be altered.
All the critical template files (the most likely you’ll want to alter) are held in the folder
Wp-content/plugins/bbpress/tempaltes/default/bbpress
Whilst many of the names give a good clue to what they do, you’ll probably need to delve into a few before you find the one you want.
I plan to make a list of these templates and what they do if/when I work it out!
For the meantime, just look through, and you should find.
3. Where to add actions
In this tutorial, we’ll look the code you need to create, but obviously that code needs to go somewhere.  So where do we put it?
We add actions either to the functions file, or create them as a plugin.
Both methods have uses.
If you like using plugins, then they’re a good way to add changes, and work well if you have a number of sites, as the plugin is easily uploaded to each.  But they do require a bit more knowledge to code.  But google the subject and you’ll find lots of help on creating one.  Then just put the code into it, and upload to your site. If you want others to use your clever code, then a plugin is a definite.
The alternate is to use a functions file.  As you are now at the “advanced” stage of using WordPress, you should either be developing your own themes, or using a Childtheme to store the specifics.
If you still just have a main theme from someone else (eg a wordpress default theme, a free theme or a premium theme), then you should create a childtheme.  This simply uses the main theme, and the you can add your tweaks to the childtheme.  Then if the maintheme is updated, you tweaks in the childtheme are not overwritten.  For help on creating a childtheme  google “child theme wordpress video” and you’ll find lots of demonstrations.
If someone has built a site for you, it may already be a in a child theme, and again the video’s will let you see whether this is the case.
Within our childtheme, we’ll put a functions.php file, and the actions we set up will go in there.
4. Example of code we can alter
So to start to understand what we need to do, lets have a look at one of bbPress’s templates and see where these are used.
The file we’ll look at is called “loop-single-reply.php” and the dafault is held at
wp-content/plugins/bbpress/templates/default/bbpress/loop-single-reply.php
Loop single reply is the template that  is used by bbpress to display a topic and the replies associated with it – eg this page
If we start to look at this file we’ll find at around line 39 the following
'  
', 'show\_role' => false ) ); ?>This part of the code displays the author details.
Line 1 – So the first things we see is an action an action for ‘bbp\_theme\_before\_reply\_author\_details’
Line 2 – This is followed by the bbp\_reply\_author link code which displays the author avatar, name, and role.
Line 3 – tests if the viewer is keymaster
Line 4 – if the viewer is keymaster, you can add some admin things to do here.
Line 5 – if the viewer is keymaster,displays the IP address of the author
Line 6 – is another action we can hook to after it has displayed this
Line 7 – ends the “if admin..” statement
5. Adding a simple action
So as stated above, if we hook to ‘bbp\_theme\_before\_reply\_author\_details’, we can add text or data at this point
So lets add “posted by” to the start of the author display area.
To do this we’ll simply hook to this action.
In effect we create a bit of code with
a name
what we want to hook it to, and
what we want it to do
The name must be unique, as other plugins, themes or indeed you could have actions that should be carried out at this point.
So this is what I coded :
//this function hooks to BBpress loop-single-reply.php and adds "posted by" before the author details
function robin\_w\_posted\_by ()
 {
echo 'Posted by' ;
 }
add\_action ('bbp\_theme\_before\_reply\_author\_details', 'robin\_w\_posted\_by') ;
So let’s pick this apart
Line 1 – starting ‘//’ is a comment line. You may know today what this function does, but in a few months time, you may not, so comments are good to remind you !
Line 2 – This sets up a function and calls it  ‘robin\_w\_posted\_by’.  Functions within your website must be unique, so adding your name at the start will make it highly unlikely that any WordPress, bbPress or any plugins you have will already have this name.
Line 3 – The actual function code is then contained in the {  } so this opens the function code area.
Line 4 – the function code – in this case it is a simple ‘echo’ command
Line 5 – closes the code area
So that creates the function, but now you must hook it to the do\_action command in the bbPress code, that is tell WordPress where to implement it.
Line 6 – The final ‘add\_action’ command tells WordPress to add an action to ‘bbp\_theme\_before\_reply\_author\_details’ called ‘robin\_w\_posted\_by’ – the function we’ve just created.  And that’s it!
so
becomes
6. Adding an Action – further example
This example adds a post count to the author area, using the do\_action( ‘bbp\_theme\_after\_reply\_author\_details’ ) action hook
//this function hooks to BBpress loop-single-reply.php and adds the post count to the reply display
function robin\_w\_display\_count ()
{
$post\_count = bbp\_get\_user\_post\_count( bbp\_get\_reply\_author\_id( $reply\_id )) ;
echo "
Total posts : " ;
echo $post\_count ;
echo "" ;
}
add\_action ('bbp\_theme\_after\_reply\_author\_details', 'robin\_w\_display\_count') ;
Very similar to the first example, but here we set a variable called $post\_count to the count and then use this to display the count.
The result:
