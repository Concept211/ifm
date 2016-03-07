# IFM - improved file manager
This is a simple filemanager. It is a single file solution which uses HTML5, CSS3, JavaScript and PHP. It works like a client-server system where HTML5/CSS3/JavaScript is the client part and the PHP API acts as the server, which reduces the traffic significant.
The IFM comes with a embedded Version of [jQuery](http://jquery.com) and [ACE Editor](http://ace.c9.io).

## requirements
Client
  * HTML5 and CSS3 compatible browser
  * activated JavaScript

Server
  * >= PHP 5.5 (only if using auth; if not PHP 5.4 works either)
  * optional: cURL extention (for remote upload)

## issues
If you are running the IFM on windows systems (e.g. XAMPP) it is necessary that you configure ifm to hide file owner and group. Otherwise the IFM uses PHP functions that are not available in windows environments and will not work.

## installation
Just copy this ifm.php to your webspace - thats all :)

## configuration
The configuration array is located at the top of the script, so you can customize it as you like. The directives in the array are commented and named laconically. If you have questions anyway [write me an email](mailto:marco@misterunknown.de).
### authentication
Meanwhile I added a super simple authentication feature using the configuration keys `auth` and `auth_source`. You can configure it like this:
```php
    "auth" => 1,
    "auth_source" => 'inline;<username>:<password_hash>',
```
In the example above the user and password are declared inline. You can also use a file (which should lie out of the $DocumentRoot of the webserver):
```php
	"auth_source" => 'file;/path/to/file',
```
The file should contain ONLY ONE LINE:
```
<username>:<password_hash>
```
The password hash has to be a hash generated by PHPs `password_hash()` function. The default credentials are "admin:admin".


## security information
The IFM was developed with the assumption that the highest level of operation is the scripts base location. So it is neither possible to nagivate nor to use any API function in a level above the script root.

It is highly recommended to restrict access to the script e.g. using the apache basic authentication.

## references
I used some nice free icons in my script which I want to mention here:
  * file icons: [Free file icons by Teambox](https://github.com/teambox/Free-file-icons)
  * other icons: [Mono icons from tutorial9.net](http://www.tutorial9.net/downloads/108-mono-icons-huge-set-of-minimal-icons/)

## developers
written by Marco Dickert [(website)](http://misterunknown.de) marco@misterunknown.de
