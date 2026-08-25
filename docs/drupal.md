---
title: "Drupal"
post_status: publish
post_name: drupal
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [import-forums]
source:
  blog_id: 4
  post_id: 87
  guid: "http://import.local/2021/12/24/drupal/"
---

Drupal
Codex Home → Getting Started → Importing Data → Import Forums → Drupal
Drupal v7.22 Importer for bbPress
Note: This current implementation is for the Drupal ‘Out of the Box’ forums, if you are looking to convert ‘Drupal Advanced Forums’ or ‘Artesian Forum’ for Drupal create a ticket on Trac and we will see how we go.
FAQ & Known Issues
Forums
Forum ‘Categories’ are imported as a ‘Forum’ – You must manually configure the forum types for ‘category’ forum type after the import and recounts have finished.
Topics & Replies
Sticky topics ‘topic status’ are not set during import, manually ‘stick’ any topics after import and recounts are complete. (See trac ticket #2126)
Users
User passwords are NOT converted when importing existing Drupal users, during the import you will see the following error which can be ignored though your users will have to reset their passwords manually with WordPress or request a password reset. Please see Trac Ticket #2375 for more details.
Notice: Undefined variable: user\_pass in /home/ntwb/public\_html/dev.ntwb.co/wp-includes/user.php on line 1297
Any custom Drupal roles are not converted, any users you wish to make ‘moderators’ or ‘keymasters’ you will have to assign these roles manually via the main WordPress Admin User panel (/wp-admin/users.php).
Users who have been disabled are now imported, if the user content was “unpublished” these are now imported to bbPress with status “pending” and need to be “approved”, if the user was disabled and the user content kept, the user topics and replies will be published with the user ID set to Anoyomous, this mimics Drupal’s existing behaviour for handing disabled and deleted users and content.
References
Original Importer and discussion by @vogelsang https://bbpress.org/forums/topic/importing-from-drupal/
Drupal v8 Importer for bbPress
Drupal v8 is now in ‘alpha’ and will be supported once the final v8 is released.
