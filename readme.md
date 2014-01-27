=== JSON API Auth ===

Tags: json api, api, authenticate user, wordpress user authentication

Contributors: parorrey

Stable tag: 1.0

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

= 1.0 =
* Added the user avatar info for generate_auth_cookie() and get_currentuserinfo().

* Updated the FAQs

= 0.1 =
* Initial release.


== Upgrade Notice ==

= 0.1 =
* Initial release.

==Frequently Asked Questions==

*Thanks to 'mattberg' who developed the auth controller. I have authored it as a WordPress plugin so that it could easily be searched and installed. mattberg made Auth controller available here https://github.com/mattberg/wp-json-api-auth

* There are three methods available: validate_auth_cookie(), generate_auth_cookie(), get_currentuserinfo()

* nonce can be created by calling http://your-domain/api/get_nonce/?controller=auth&method=generate_auth_cookie

* You can then use 'nonce' value to generate cookie. http://your-domain/api/auth/generate_auth_cookie/?nonce=f4320f4a67&username=Catherine&password=password-here

* Use cookie like this with your other controller calls: http://your-domain/api/contoller-name/method-name/?cookie=Catherine|1392018917|3ad7b9f1c5c2cccb569c8a82119ca4fd