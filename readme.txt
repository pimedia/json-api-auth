
=== JSON API Auth ===

Donate link: http://www.parorrey.com
Tags: json api, api, authenticate user, WordPress user authentication
Contributors: parorrey
Stable tag: 2.5.0
Requires at least: 3.0.1
Tested up to: 5.5.3
Requires PHP: 5.3
License: GPLv2 or later

License URI: http://www.gnu.org/licenses/gpl-2.0.html

Extends the JSON API Plugin for RESTful user authentication

== Description ==

JSON API Auth extends the JSON API Plugin to allow RESTful user authentication.

JSON API Plugin, that is required, was closed on August 7, 2019 from WordPress repository. You can download <a href="https://github.com/PI-Media/json-api">JSON API Plugin</a> from https://github.com/PI-Media/json-api until it is republished and available on WordPress.

Features include:

* Generate Auth Cookie for user authentication

* Validate Auth Cookie

* Get Current User Info

For documentation: See 'Other Notes' tab above for usage examples. 

Credits: http://www.parorrey.com/solutions/json-api-auth/

== Installation ==

First you have to install the JSON API for WordPress Plugin (http://wordpress.org/extend/plugins/json-api/installation/). or You can download <a href="https://github.com/PI-Media/json-api">JSON API Plugin</a> from https://github.com/PI-Media/json-api

To install JSON API Auth just follow these steps:

* upload the folder "json-api-auth" to your WordPress plugin folder (/wp-content/plugins)

* activate the plugin through the 'Plugins' menu in WordPress or by using the link provided by the plugin installer

* activate the controller through the JSON API menu found in the WordPress admin center (Settings -> JSON API)

== Screenshots ==

1. Call to generate_auth_cookie endpoint using Postman
2. Call to get_currentuserinfo endpoint using Postman
3. Call to validate_auth_cookie endpoint using Postman

== Changelog ==

= 2.5.0 =
* Updated for wordpress version 5.5.3

= 2.4.0 =

* Fixed bug in the generate_auth_cookie endpoint.

= 2.3.0 =

* Updated for JSON API Plugin diretory check error and updated action links.

= 2.2.0 =

* Updated for GitHub and settings action links.

= 2.1.0 =

* Updated for WordPress version & added JSON API plugin GitHub link due its closing down on WordPress repository.

= 2.0.0 =

* Updated for wordpress version


 == Frequently Asked Questions ==

Thanks to 'mattberg' who wrote the auth controller (https://github.com/mattberg/wp-json-api-auth) initially. I have added few methods and authored it as a WordPress plugin so that it could easily be searched and installed vis WordPress. 

* There are following methods available: validate_auth_cookie, generate_auth_cookie, clear_auth_cookie, get_currentuserinfo

* nonce can be created by calling http://localhost/api/get_nonce/?controller=auth&method=generate_auth_cookie

* You can then use 'nonce' value to generate cookie. http://localhost/api/auth/generate_auth_cookie/?nonce=f4320f4a67&username=Catherine&password=password-here

* Use cookie like this with your other controller calls: http://localhost/api/contoller-name/method-name/?cookie=Catherine|1392018917|3ad7b9f1c5c2cccb569c8a82119ca4fd

For instance, you have a new controller 'events' and want to allow users to post new 'event' using 'add_event' method.
This is how you will call the end point with cookie and post the event with user info:

http://localhost/api/events/add_event/?cookie=Catherine|1392018917|3ad7b9f1c5c2cccb569c8a82119ca4fd

If you want sample code how it can be done, check 'JSON API User' plugin https://wordpress.org/plugins/json-api-user/. This Auth plugin is part of JSON API User plugin.
 
= Method: validate_auth_cookie =

It needs 'cookie' var.

http://localhost/api/auth/validate_auth_cookie/?cookie=Catherine|1392018917|3ad7b9f1c5c2cccb569c8a82119ca4fd


= Method: generate_auth_cookie =

It needs `username`, `password` vars. `seconds` is optional.

Then generate cookie: http://localhost/api/auth/generate_auth_cookie/?username=john&password=PASSWORD-HERE

Optional 'seconds' var. It provided, generated cookie will be valid for that many seconds, otherwise default is for 14 days.

generate cookie for 1 minute: http://localhost/api/auth/generate_auth_cookie/?username=john&password=PASSWORD-HERE&seconds=60

60 means 1 minute.


= Method: get_currentuserinfo =

It needs 'cookie' var.

http://localhost/api/auth/get_currentuserinfo/?cookie=Catherine|1392018917|3ad7b9f1c5c2cccb569c8a82119ca4fd