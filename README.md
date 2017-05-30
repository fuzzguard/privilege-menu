# privilege-menu
Privilege Menu WordPress Plugin


== Description ==

This plugin allows you to display menu items based on if a user is logged in, logged out or based on the role you have given the user.

This plugin allows fine-grained permissions to be added to each individual menu item to display or not display the item based on the
 users logged in/logged out status or the role assigned to the user.  This solves the problem of having to modify theme functions.php files to add in menu restrictions.  The changes in functions.php is often overwritten by a theme update.  This plugin removes that worry, as you can update the theme, independent of the plugin.
= Please Note =
This plugin uses a modified version of the Nav Menu Walker class.  This means any other plugins that utilize their own custom Nav Menu Walker class, can and will conflict with this plugin.  WordPress developers have support for proper custom hooks in this area of the Admin Menu slated for v4.8 release.  Please see FAQ item "I cannot see the options for Privilege Menu under menu items in the Admin Panel?" for more information.

== Installation ==

1. Upload the `plugin` folder to the `/wp-content/plugins/` directory
1. Activate the plugin through the 'Plugins' menu in WordPress
1. Go to Appearance > Menus
1. Edit the menu items accordingly.  First select whether you'd like to display the item to all logged in users, all logged out users or Both (Default).
1. Save the changes to the menu.  You should now see excluded menu items based on a users logged in/logged out state.

== Frequently Asked Questions ==

= Can I localize this plugin for my own language? =

Yes you can.  Included now in this plugin is a folder call "lang".  Within this folder is a file called "privilege-menu.pot".  This file can be used to create the localized translations for your own language using poedit.

If you contact me after you have done this through my website at: https://www.fuzzguard.com.au/contact/ I can include this translation file in the next plugin release.  You will be credited for your work of course.

= I cannot see the options for Privilege Menu under menu items in the Admin Panel? =

This usually occurs due to a plugin conflict.  The Admin Menu Walker can only have one custom walker so any other plugin that uses a custom Admin Menu Walker will cause conflicts with Privilege Menu plugin.

WordPress does not yet have sufficient hooks in this area of the admin panel.  Due to this plugins are forced to load a modified custom Admin Menu Walker.  The custom Admin Menu Walker is limited to one so only one Admin Panel menu modification plugin can be active at one time.

Although this feature has been requested since 3.6 it still hasn't been added to the WordPress Core.
There's a possibility that support for "Nav Menu UI" Hooks will be added in WordPress 4.8 as it has now been picked up by the developers and they are actively working on implementing this:
http://core.trac.wordpress.org/ticket/18584

== Screenshots ==

1. How to add an menu item as only viewable to logged IN users.
2. How to add an menu item as only viewable to logged OUT users.
3. This is the menu a logged IN user would see.  These users don't see "Login" due to the fact that it is denied to logged IN users in the Admin Panel Nav Menus section.
4. This is the menu a logged OUT user would see.  These users don't see "Logout", "My Account" or "Control Panel" due to the fact that they are denied to logged OUT users in the Admin Panel Nav Menus section.
5. This is a view of a menu item you could select only to be viewable for administrators.

== Changelog ==

= 1.8.2 =
* Moved '_priv_menu_role' option string into 'public $privMenuOption' to allow access from uninstall.php
* Changed all references to '_priv_menu_role' string to access $this->privMenuOption (For Conformity)
* Fixed styling for text in widget admin panel
* Fixed styling for text in widget admin panel in responsive mode.

= 1.8.1 =
* Tested with version 4.7 of WordPress

= 1.8 =
* Updated customWalker.php to match new navWalker code added to WordPress core
* Tested with version 4.6 of WordPress
* Upgraded TGM Plugin Activation class file version to 2.6.1

= 1.7.4 =
* Upgraded TGM Plugin Activation class file version to 2.6.0

= 1.7.3 =
* Added in backwards compatibility with old User Roles versions

= 1.7.2 =
* Removed erroneous recommended plugins.  Should only recommend relevant plugins to "Privilege Menu", such as "Privilege Widget"

= 1.7.1 =
* Upgraded TGM Plugin Activation class file version to 2.5.2

= 1.7 =
* Tested with version 4.5 of WordPress
* Added TGM Plugin Activation code to recommend FuzzGuards other useful plugins

= 1.6.1 =
* Added uninstall file to remove all options from DB if plugin is removed.

= 1.6 =
* Added in ability to select menu display via User Role.
* Removed 'Admin Users" option - Replaced by "Logged In", "Administrators" checkbox
* Selecting logged in users now allows you to choose the Users Role

= 1.5 =
* Added Serbian Translation - Translated by: Ogi Djuraskovic (firstsiteguide.com)

= 1.4 =
* Added "lang" folder for localization files
* Added French, German, Spanish and Chinese translations
* Added .pot file for localization by others.  Located in "lang" folder

= 1.3 =
* Added WordPress admin class protection coding to customWalker.php
* Changed "Display Mode" to "User Restriction"
* Added in bottom border to "User Restriction" area in each menu item to make the menu area easier to read

= 1.2 =
* Removed superfluous "2" from end of plugin name

= 1.1 =
* Changed "Both" to "All Users" in customWalker.php
* Added in ability to show menu only to administrators

= 1.0 =
* Gold release
