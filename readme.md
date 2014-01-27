=== JSON API Auth ===

Tags: json api, api, authenticate user, wordpress user authentication

Contributors: parorrey

Stable tag: 0.1

Requires at least: 3.0.1

Tested up to: 3.8

License: GPLv2 or later

License URI: http://www.gnu.org/licenses/gpl-2.0.html

Extends the JSON API for user authentication


==Description==


JSON API Auth is a plugin that extends the JSON API Plugin with a new Controller to allow user authentication.


==Installation==

First you have to install the JSON API for WordPress Plugin (http://wordpress.org/extend/plugins/json-api/installation/).

To install JSON API Auth just follow these steps:

* upload the folder "json-api-auth" to your WordPress plugin folder (/wp-content/plugins)

* activate the plugin through the 'Plugins' menu in WordPress or by using the link provided by the plugin installer

* activate the controller through the JSON API menu found in the WordPress admin center (Settings -> JSON API)

== Screenshots ==


==Changelog==

= 0.1 =
* Initial release.


== Upgrade Notice ==

= 0.1 =
* Initial release.

==Frequently Asked Questions==

*All Thanks to 'mattberg' who developed the auth controller. I have authored it as a WordPress plugin so that it could easily be searched and installed. mattberg made Auth controller available here https://github.com/mattberg/wp-json-api-auth

* There are three methods available: validate_auth_cookie(), generate_auth_cookie(), get_currentuserinfo()

* nonce can be created by calling http://your-domain/api/get_nonce/?controller=auth&method=generate_auth_cookie

* You can then use 'nonce' value to generate cookie.