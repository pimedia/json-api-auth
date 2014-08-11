=== JSON API Auth ===

Donate link: http://www.parorrey.com

Tags: json api, api, authenticate user, wordpress user authentication

Contributors: parorrey

Stable tag: 1.3

Requires at least: 3.0.1

Tested up to: 3.9.1

License: GPLv2 or later

License URI: http://www.gnu.org/licenses/gpl-2.0.html

Extends the JSON API Plugin for RESTful user authentication

==Description==

JSON API Auth extends the JSON API Plugin to allow RESTful user authentication.



Features include:

* Generate Auth Cookie for user authentication

* Validate Auth Cookie

* Clear Auth Cookie

* Get Current User Info


For details: http://www.parorrey.com/solutions/json-api-auth/



==Installation==

First you have to install the JSON API for WordPress Plugin (http://wordpress.org/extend/plugins/json-api/installation/).

To install JSON API Auth just follow these steps:

* upload the folder "json-api-auth" to your WordPress plugin folder (/wp-content/plugins)

* activate the plugin through the 'Plugins' menu in WordPress or by using the link provided by the plugin installer

* activate the controller through the JSON API menu found in the WordPress admin center (Settings -> JSON API)


== Screenshots ==




==Changelog==

= 1.3 =

* Removed bug for generating cookie


= 1.2 =

* Updated plugin description, documentation and few urls

= 1.1 =

* Added clear_auth_cookie() for removing auth cookie.

* Added documentation for the available end points


= 1.0 =

* Added the user avatar info for generate_auth_cookie() and get_currentuserinfo()


* Updated the FAQs

= 0.1 =

* Initial release.



== Upgrade Notice ==

= 0.1 =

* Initial release.


==Documentation==

Thanks to 'mattberg' who wrote the auth controller (https://github.com/mattberg/wp-json-api-auth) initially. I have added few methods and authored it as a WordPress plugin so that it could easily be searched and installed vis WordPress. 


* There are following methods available: validate_auth_cookie, generate_auth_cookie, clear_auth_cookie, get_currentuserinfo

* nonce can be created by calling http://localhost/api/get_nonce/?controller=auth&method=generate_auth_cookie

* You can then use 'nonce' value to generate cookie. http://localhost/api/auth/generate_auth_cookie/?nonce=f4320f4a67&username=Catherine&password=password-here

* Use cookie like this with your other controller calls: http://localhost/api/contoller-name/method-name/?cookie=Catherine|1392018917|3ad7b9f1c5c2cccb569c8a82119ca4fd

For isntance, you have a new controller 'events' and want to allow users to post new 'event' using 'add_event' method.
This is how you will call the end point with cookie and post the event with user info:

http://localhost/api/events/add_event/?cookie=Catherine|1392018917|3ad7b9f1c5c2cccb569c8a82119ca4fd

If you want sample code how it can be done, check 'JSON API User' plugin https://wordpress.org/plugins/json-api-user/. This Auth plugin is part of JSON API User plugin.
 
= Method: validate_auth_cookie =

It needs 'cookie' var.

http://localhost/api/auth/validate_auth_cookie/?cookie=Catherine|1392018917|3ad7b9f1c5c2cccb569c8a82119ca4fd


= Method: generate_auth_cookie =

It needs 'nonce' var.

First get the nonce: http://localhost/api/get_nonce/?controller=auth&method=generate_auth_cookie

Then generate cookie: http://localhost/api/auth/generate_auth_cookie/?nonce=375034fjwfn39u8&user_id=john&password=PASSWORD-HERE


= Method: clear_auth_cookie =

It needs 'cookie' var.

http://localhost/api/auth/validate_auth_cookie/?cookie=Catherine|1392018917|3ad7b9f1c5c2cccb569c8a82119ca4fd

it will clear/expire any valid cookie that was earlier genereated using generate_auth_cookie end point


= Method: get_currentuserinfo =

It needs 'cookie' var.

http://localhost/api/auth/get_currentuserinfo/?cookie=Catherine|1392018917|3ad7b9f1c5c2cccb569c8a82119ca4fd