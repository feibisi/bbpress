---
title: "Step by step guide to setting up a bbPress forum – part 5"
post_status: publish
post_name: step-by-step-guide-to-setting-up-a-bbpress-forum-part-5
lang: en
taxonomy:
  category: [bbpress]
source:
  blog_id: 4
  post_id: 116
  guid: "http://import.local/2021/12/24/step-by-step-guide-to-setting-up-a-bbpress-forum-part-5/"
---

Step by step guide to setting up a bbPress forum – part 5
Codex Home → Step by step guide to setting up a bbPress forum – part 5
1. Using  Filters
Actions and Filters add a powerful way that you can alter how bbPress (and of course WordPress) work.
For the newcomer to WordPress, they are also probably one of the hardest areas to understand and to find information on. This tutorial tries to demystify some of this area, and help newcomers code those changes that will make their site work how they wish.
Part 4 dealt with ‘actions’, this section deals with ‘filters.’
It does repeat some of the initial text in Actions as it is applicable to both.
2. Introduction.
If you are familiar with functions and filters, you’ll probably not need to read much of this article, but I presume if you’re here, then like me you see snippets and ‘brief’ explanations that get you to the stage where you are pretty sure what you want can be done, but can’t quite work out the exact way or get it to work.
So at this stage, make a cup of coffee, shut the kids out of the room, and I’ll try and take you through what I have learnt so far about filters.
If you can improve either the explanation, correct any errors I have made, or help in any other way, just post a topic on “requests and feedback” on the support forums, and I’ll pick it up.
3.  Filters
If actions ADD stuff at a particular point (see part 4 ), Filters are a way to ALTER what is being displayed (typically which bits of data or the format/order) at a particular point, without needing to change the code in the file.
This can be very handy if
the data is displayed in multiple places (eg the way an author name is displayed) – you change it once for all occurances
the file you want to alter is in the core of the code, so you don’t want to change the original file
You start to write plugins for others to use – filters let you alter lots of coding without touching the actual php files
So in essence think of it that actions add and filters alter.  But what does  a filter actually filter?  Well it filters a function, so we need to understand functions before we move forward
4. An explanation of functions
A function is a bunch of code that when combined does something.  In WordPress, functions are used to both hide complexity,  save repeating endless lines of code all over the place, and improve manageability.
So in bbpress the lines of code that go to the database, and fetch the identity of the author of a post is all put into a function  called  bbp\_get\_reply\_author\_id.  Anytime we want to do this, we can just quote that function, and save ourselves using many lines.  And if the guys behind bbPress want to change how that works, they do it just once and all the instances that use this then use the new function.
So lets create a simple function (we’ll get to some real bbPress examples later!)
function hello () {
$text="Hello Robin" ;
echo $text ;
}
Line 1 creates the function
Line 2 sets a variable of $text to Hello Robin
Line 3 writes that text to the screen
Then whenever called within a wordpess php file eg
hello () ;
it will write the result.
We might put this function in our functions.php file, or put it within a plugin.
Now bbPress is a plugin, and in bbPress there are hundreds of functions in many locations.
So imagine that someone else has written the ‘hello’ function above and buried this function in in their plugin, and that this function is used in many places. However you don’t want it to say “Hello Robin” but “Hello Fred”. Now you could find the function within the plugin and alter the code in the file, but on any upgrade of the plugin, you’ll lose the changes. So it would be better if you could just alter that variable $text, and filters offer a way to do that.
5. Not all functions are filterable
The above function cannot be filtered as it has not been written to allow this – hopefully all the functions you will come across have been – so let’s re-write it to be filterable.
function hello () {
$text="Hello Robin" ;
$text=apply\_filters('hello',$text) ;
Echo $text ;
}
Line 3 has been added. In essence it says that if a filter exists, then substitute the value of $text in that filter to the function.
So now if we create a filter and add a function to it that changes $text, whatever value of $text is in that filter replaces the original value of $text in the function. So we can make “Hello Robin” become “Hello Fred” without altering any code.
So lets create a filter for this.  As with actions, we do this by creating a function.
So the original code above is buried in someone else plugin. Our new code will sit in our functions file or in a plugin, and alter the effect of that original code, changing $text=”Hello Robin” to $text=”Hello Fred”.
So the resultant code looks like
//function to change 'Hello Robin' to 'Hello Fred' in 'hello' function
function called\_anything () {
$text="Hello Fred" ;
return $text ;
}
add\_filter('hello','called\_anything') ;
So lets run through this.
5.1 Names
First let’s deal with naming
We are creating a function, and functions can be called anything.  However every function (and there are thousands of them in there already) MUST have a unique name across your website.  Given that you have the core wordpress and probably lots of plugins, it is important that you don’t create a duplicate name.  Calling it something like in my case ‘robin\_w\_hello’ would probably make it pretty unique.
Adding a comment line at the start of your function to remind you what this is doing is also important, as you’ll never remember what this bit does when you start to have lots of these in your files.
5.2 Bringing in variables
In line 1 we called our function using function called\_anything () .  The () is the area in which to put any variables we want to bring into our function.  So if I wanted to alter $text rather than replace it, I’d put it into the () so that it was brought in ie function called\_anything ($text). In this case I could then  use some string manipulation to say strip the hello from the front.  So if you want to manipulate data from the core function import them here.
5.3 Return the data
Line 3 includes a return command.  This ensures that the data is passed back to the main function.  If omitted, then any variables you were planning to change will be blank, and therefore not show.
5.4 Add\_filter &  Remove filter
In the last line we add a filter to ‘hello’  named ‘called\_anything’
In this case we are adding filter. There is another command called remove\_filter for removing a filter – useful if someone else’s plugin has a filter that makes a change you don’t want.
6. The apply\_filter can have a different name from the function !
Ok so if you are not going mad by now, you are applying a filter with a name to your function, not applying a filter to your function’s name. So that apply\_filter can have a different name from your function, and indeed you can have several filters in a function.
So whilst we had a line above in our function ‘hello’ saying
$text=apply\_filters('hello',$text) ;
the ‘hello’ bit of “apply\_filter(‘hello'” is the name of the filter, and could be anything (or rather anything unique to your site!)
So whilst no one would actually write a function this way, we could have
function hello () {
$text1="Hello Robin" ;
$text1=apply\_filters('hello\_change1',$text) ;
$text2="goodbye Robin" ;
$text1=apply\_filters('hello\_change2',$text) ;
Echo $text1.$text2;
}
Now I wouldn’t tell you this unless you needed to know it, so you will frequently find filters in wordpress and bbPress are not the same as their function name. Indeed we will see later on that they are quite often different, but have a logic to them, which once known means that you can work it out.
7. Creating a filter for an array
An array is a set of data held within a single data name
So for instance
$data = array(
“name” => “Robin”,
“age” => “21”,
);
The array $data now contains both my name and my age.
Most bbPress functions create arrays, as they use multiple data, so lets create a function that has an array, and outputs some data
function hello () {
$data = array(
'name' => 'Robin',
'age' => '21',
'text' => ' years old.',
);
$data=apply\_filters('hello',$data) ;
echo $data['name']." is ".$data['age'].$data['text'] ;
}
Calling hello() in a php file will cause the result
“Robin is 21 years old.”
Let’s say we want to change the wording to say “Robin is 21 years young.”
So we need to alter the $data[‘text’] to say ” years young.”
So we will write a function to do that, and the add a filter to implement it
The result looks like this
//this adds a filter to change $data['text'] to ' years young'
function called\_anything ($data) {
$data ['text'] = ' years young.' ;
return $data ;
}
add\_filter('hello','called\_anything') ;
Let’s run through that
If we just had ‘function called\_anything()’ then anything we change we will reset the entire array, so we need to ‘bring in’ the current values. ‘called\_anything ($data)’ brings across the array into our new function.
The second line changes the ‘text’ value, and the third line returns the new array back to the original function
So now the array looks like
‘name’ => ‘Robin’,
‘age’ => ’21’,
‘text’ => ‘ years young.’,
and the output will be “Robin is 21 years young” – job done !
So now we’re ready to look at some real bbPress examples.
8. Finding the code
So where is the code that we need to look at?
This is of course the first issue with bbPress (as with any other part of WordPress) – finding out what file needs to be altered.
For bbPress, all the critical template files (the most likely you’ll want to alter) are held in the folder
Wp-content/plugins/bbpress/tempaltes/default/bbpress
Whilst many of the names give a good clue to what they do, you’ll probably need to delve into a few before you find the one you want.
I plan to make a list of these templates and what they do if/when I work it out!
But let’s start from the point where you have got something displaying in WordPress that you want to alter. You have found the template file that covers this, and within that you have a function that is displaying the data that you want to alter or alter the display of.
So we’ll need to create a filter.
9. Where to add filters
In this tutorial, we’ll generate the code you need, but obviously that code needs to go somewhere. So where do we put it?
We add actions or filters either to the functions file, or create them as a plugin.
Both methods have their uses.
If you like using plugins, then they’re a good way to add changes, and work well if you have a number of sites, as the plugin is easily uploaded to each. But they do require a bit more knowledge to code. But google the subject and you’ll find lots of help on creating one. Then just put the code into it, and upload to your site.
The alternate is to use a functions file. As you are now at the “advanced” stage of using WordPress, you should either be developing your own themes, or using a Childtheme to store the specifics.
If you still just have a main theme from someone else (eg a wordpress default theme, a free theme or a premium theme), then you should create a childtheme. This simply uses the main theme, and the you can add your tweaks to the childtheme. Then if the main theme is updated, you tweaks in the childtheme are not overwritten. For help on creating a childtheme google “child theme wordpress video” and you’ll find lots of demonstrations. If someone has built a site for you, it may already be a in a child theme, and again the video’s will let you see whether this is the case.
Within our childtheme, we’ll put a functions.php file, and the actions and filters we set up will go in there.
10. Example of code we can alter
So to start to understand what we need to do, lets have a look at something we might want to change
In the forums display we have a count of topics and replies next to each forum viz :
Let’s say we want to remove these counts and make it look like
Now we could do this by altering the template that does this. In fact the codex has a page Layout and functionality – Examples you can use . Section 2 shows how to change this by altering a template called loop-single-forum. But if we alter that template, then we will need to store it in a different place so that it is not overwritten by later updates. This can be quite easily done, and there is no reason why you shouldn’t do this, but adding a filter is an equally valid alternative.
So where to start?
Well let’s start by summarising what we are going to do, then you can follow the steps.
a) look at the templates to find which one has the function we want to alter
b) look at the codex to see if that function is there
c) if it is then we can see the arguments,
d) if not, then we’ll need to look for the function definition
e) and then code the filter
Looks easy(ish), but it’s a bit like being a detective, you have to follow the clues.
a) Well we start by finding out that bbPress stores all the main “display” areas of the plugin in a template folder held at
wp-content/plugins/bbpress/templates/default/bbpress
I plan to have a list of which templates do what, but for the moment it’s really a case of intelligent guesswork and lots of opening files and examining. Typically anything with lists in it will be running a loop (going through a list), so loop-something is a good bet.
So since we are loking at a list of forums, we loom at the templates that have loop and forum. At some stage we open loop-single-forum and in there we see a progression from forum title, forum description, sub-forums, and then some topic, reply and freshness counts.
Click here to see the file – opens in a new window so you can switch between this and the code.
The sub-forum list part on line 30
bbp\_list\_forums();
looks like a likely candidate, so let’s look at that. We’ll do that next.
b) So lets look at the codex to see what is written about this function. Go to the documentation (this section) and select any article – you’re actually reading this one, so that’s fine. On the left hand side you’ll see a “related” area. You’ll need to scroll back up from this article to see it. Look down the list for the function – in this case ‘bbp\_list\_forums’, and it’s listed (not all are – yet!)
Open this up and you’ll see that it lists the arguments (again not all do yet, so see d) below if yours is not there.
Within this are “show topic count” and “show reply count”, and you’ll see that they are set to “True” – setting these to false should hide the detail.
You’ll also see a line saying “To filter this array use add\_filter(‘bbp\_before\_list\_forums\_parse\_args’, ‘your\_filter\_name)” – so that’s the filter we need. As we said earlier, the filter name may well be different to the function name. So bbp\_list\_forums uses ‘bbp\_before\_list\_forums\_parse\_args’ to alter the array. (In fact there is a further filter in this function which does have the function name, but we’ll ignore that for the moment!)
So we’ll create a function to change the topic and reply values to false so that they don’t display and add a filter to implement it.
The data is held in an array, so we need to use the code for that.
So lets start with the function
function hide\_forum\_counts ($args = array() ) {
$args['show\_topic\_count'] = false;
$args['show\_reply\_count'] = false;
return $args;
}
Then we’ll add the filter
add\_filter ('bbp\_before\_list\_forums\_parse\_args','hide\_forum\_counts') ;
This code will go in our functions file (or as a plugin).
d) But what if the codex doesn’t show the filter? How do we find what filter to use?
Ok, we can work this out. We’ll start as before with bbp\_list\_forums. We need to fund where that function is defined.
Now all the functions used in the templates wp-content/plugins/bbpress/templates are held in 5 template folders that are located as follows :
wp-content/plugins/bbpress/includes/forums/template.php
wp-content/plugins/bbpress/includes/topics/template.php
wp-content/plugins/bbpress/includes/replies/template.php
wp-content/plugins/bbpress/includes/users/template.php
wp-content/plugins/bbpress/includes/search/template.php
As we are listing forums, we could take a bet that it will be in wp-content/plugins/bbpress/includes/forums/template.php (which it is), but if you had no clue, then download the plugin to your PC, extract it to a directory, and use your PC’s serach function to find it. But do search for ‘bbp\_list\_forums’ not ‘bbp\_list\_forums()’ as bbPress functions will normally have arguments, so the () will contain stuff, and your search will produce a nil return!
So we find wp-content/plugins/bbpress/includes/forums/template.php
and open it up. Inside we see on line 744
function bbp\_list\_forums( $args = '' ) {
and way down on line 801
echo apply\_filters( 'bbp\_list\_forums', $r['before'] . $output . $r['after'], $r );
so we’d think that the filter we want to add is to “apply\_filters( ‘bbp\_list\_forums'”. But no, this filter is after all the function has happened. We simply want to change a couple of the input parameters.
At the beginning of the function we find :
// Parse arguments against default values
$r = bbp\_parse\_args( $args, array(
'before' => '

',
'after' => '
',
'link\_before' => '- ',
  'link\_after' => '
',
'count\_before' => ' (',
'count\_after' => ')',
'count\_sep' => ', ',
'separator' => ', ',
'forum\_id' => '',
'show\_topic\_count' => true,
'show\_reply\_count' => true,
), 'list\_forums' );
This is a common format throughout bbPress, and indeed is similar to a function used throughout wordpress.
It uses a function called ‘bbp\_parse\_args’ to create a filter against all the arguments.
The filter created is in the format “bbp\_before\_” followed by X followed by “\_parse\_args” The X is the third argument from the bbp-parse\_args function – if you look at the code aboave you’ll see that it is actually
bbp-parse\_args ($args, Array(...), 'list\_forums' )
so in the last line we see ‘list forums’ which is the X above . In practice this is the function without the bbp start bit.
so an array filter for bbp\_list\_forums is ‘bbp\_before\_list\_forums\_parse\_args’
and for say bbp\_get\_topic\_pagination would be
bbp\_before\_get\_topic\_pagination\_parse\_args
Ok, so that’s a long explanation, that will need you to read several times, and I’ll add some more examples as I progress.
As said above, any feedback or clarity needed, post a topic at
requests and feedback
