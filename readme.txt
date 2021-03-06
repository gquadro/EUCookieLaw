=== Plugin Name ===
Contributors: diego-la-monica
Donate link: https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=me%40diegolamonica%2einfo&lc=IT&item_name=EU%20Cookie%20Law&no_note=0&currency_code=EUR&bn=PP%2dDonationsBF%3abtn_donateCC_LG%2egif%3aNonHostedGuest
Tags: Cookie, Law Compliance
Requires at least: 4.0
Tested up to: 4.2.2
Stable tag: 2.1.2
License: LGPLv3
License URI: http://www.gnu.org/licenses/lgpl-3.0-standalone.html

A Wordpress solution to the European Cookie Law Issue

== Description ==

EUROPA websites must follow the Commission's guidelines on [privacy and data protection](http://ec.europa.eu/ipg/basics/legal/data_protection/index_en.htm) and inform
users that cookies are not being used to gather information unnecessarily.
   
The [ePrivacy directive](http://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=CELEX:32002L0058:EN:HTML) – more specifically Article 5(3) – requires prior informed consent for storage for access to information stored on a user's terminal equipment.
In other words, you must ask users if they agree to most cookies and similar technologies (e.g. web beacons, Flash cookies, etc.) before the site starts to use them.

For consent to be valid, it must be informed, specific, freely given and must constitute a real indication of the individual's wishes.

In this context this plugin lives.
It simply alters the default `document.cookie` behavior to disallow cookies to be written on the client side,
until the user accept the agreement. The same does for the server side where since the user does not have accepted the agreement,
then it would not store any cookie.

   **Note that this plugin blocks any URL you define which generates third-party cookies.**

To get detailed informations about the plugin go to https://github.com/diegolamonica/EUCookieLaw

== Installation ==

For manual installation using WordPress plugin installer:
* download the zip file
* upload via the WordPress plugin installer page
* Activate the plugin

For manual installation via FTP
* extract files in a local directory
* upload through FTP the whole directory contents under `/wp-content/plugins/eucookielaw`.
* Goto plugin administration panel
* Activate the plugin

== Screenshots ==

1. The configuration page

== Changelog ==

= 2.1.2 =

* **IMPROVEMENT**: If not defined the `EUCOOKIELAW_BANNER_DISAGREE_BUTTON` the disagree button will not be shown on the page.
* **IMPROVEMENT**: Removed the session/local storage in favor of technical session cookie for storing the user rejection
* **IMPROVEMENT**: Improved the way to detect if the cookie is approved or rejected
* **IMPROVEMENT**: Uniformed the way to write the technical cookie `__eucookielaw`
* **IMPROVEMENT**: Improved the way how the banner is removed
* **IMPROVEMENT**: Updated missing pieces in documentation.
* **IMPROVEMENT**: Optimized behavior when asked reload of contents after consent.
* **BUGFIX**: Resolved an [anicient related firefox issue](https://bugzilla.mozilla.org/show_bug.cgi?id=356558)
* updated the minor version number
* updated documentation

= 2.1.0 =

* **BUGFIX**: when PHP does not have gzdecode the method is implemented on needs.
* **BUGFIX**: Internet Explorer and some mobile Browser does not recognize the `instance` variable as `EUCookieLaw` object causing a bad banner behavior.
* **BUGFIX**: \[WP\] NextGenGallery has some weird behavior sometimes (skipped to load the locker if it is a NGG URL.
* **IMPROVEMENT**: \[WP\] The plugin now tries to write into `wp-config.php` only if there is another cache plugin enabled on the site.
* **IMPROVEMENT**: EUCookieLaw related PHP Warnings threated as required
* updated documentation
* updated the version number

= 2.0.2 =

* **CRITICAL**:
Most of WordPress sites uses a FTP settings for writing files. Used native `file_get_contents` and `file_put_contents`
to write data into some files for a better user experience.

* **BUGFIX**: Changed stable version number in readme

= 2.0 =

* **NEW:** [\WP\] Full compliant with any cache plugin (actually successfully tested with **WP Super Cache**, **W3 Total Cache**, **Zen Cache**)
* **NEW:** The banner is now visible either with and without javascript enabled.
* **NEW:** User consent whenever he clicks on an element of the page (Issue [#12](https://github.com/diegolamonica/EUCookieLaw/issues/12))
* **NEW:** You can list the allowed cookies before consent (aka *Technical Cookies*). This solves the issue [#15](https://github.com/diegolamonica/EUCookieLaw/issues/15)
* **NEW:** Now Google Analytics is able to write cookies via JavaScript (if configured) (Issue [#15](https://github.com/diegolamonica/EUCookieLaw/issues/15))
* **NEW:** \[WP\] You can enable/disable the banner on frontend (Issue [#20](https://github.com/diegolamonica/EUCookieLaw/issues/20))
* **NEW:** \[WP\] You can enable/disable the banner on the login page (Issue [#21](https://github.com/diegolamonica/EUCookieLaw/issues/21))
* **NEW:** You can set the "reload on scroll" (Issue [#26](https://github.com/diegolamonica/EUCookieLaw/issues/26))
* **NEW:** \[WP\] Added the WPML XML Configuration File for a better WPML compatibility.
* **IMPROVEMENT:** \[WP\] Lack of documentation on certain admin fields (Issue [#27](https://github.com/diegolamonica/EUCookieLaw/issues/27))
* **IMPROVEMENT:** Most of PHP Code was completely refactored from the ground to improve performance and readability.
* **BUGFIX:** \[WP\] NextGenGallery conflict resolved (Issue [#31](https://github.com/diegolamonica/EUCookieLaw/issues/31))
* **BUGFIX:** \[WP\] QuickAdsense conflict resolved (Issue [#36](https://github.com/diegolamonica/EUCookieLaw/issues/36) and  [#32](https://github.com/diegolamonica/EUCookieLaw/issues/32) )
* **BUGFIX:** \[WP\] Revolution Slider conflict resolved (Issue [#37](https://github.com/diegolamonica/EUCookieLaw/issues/37))
* **BUGFIX:** Page URL changes after reload (Issue [#38](https://github.com/diegolamonica/EUCookieLaw/issues/38))
* **BUGFIX:** Scroll on tablet does not work  (Issue [#40](https://github.com/diegolamonica/EUCookieLaw/issues/40))
* **BUGFIX:** Invalid Calling Object in Internet Explorer 9 and Safari was resolved  (Issue [#41](https://github.com/diegolamonica/EUCookieLaw/issues/41))
* updated translation files
* updated documentation
* updated the version number

= 1.5 =

This update introduces several improvements, features and bugfixes. For a detailed information about the new release see
the [documentation page](https://github.com/diegolamonica/EUCookieLaw/) and the [Milestone 1.5](https://github.com/diegolamonica/EUCookieLaw/issues?q=milestone%3A1.5+is%3Aclosed)

* **NEW:** Now the plugin is able to detect if the user agent and does not block contents if it is search engine
* **NEW:** All the external contents are loaded after the user consent without page reloading ( Issues [#4](https://github.com/diegolamonica/EUCookieLaw/issues/4) and [#10](https://github.com/diegolamonica/EUCookieLaw/issues/10))
* **NEW:** The script allows to define the consent duration in days (Issue [#7](https://github.com/diegolamonica/EUCookieLaw/issues/7), [#17](https://github.com/diegolamonica/EUCookieLaw/issues/17) and [#23](https://github.com/diegolamonica/EUCookieLaw/issues/23))
* **NEW:** Now is possible to check almost in every HTML element ( Implicitly resolved issue [#6](https://github.com/diegolamonica/EUCookieLaw/issues/6))
* **NEW:** The script remembers the user rejection.
* **NEW:** New JavaScript public method `reconsider` to revoke the consent (and the rejection) showing the banner again (Issue [#7](https://github.com/diegolamonica/EUCookieLaw/issues/7))
* **NEW:** \[WP\] Added shortcode for reconsider button (see documentation for further details) (Issue [#7](https://github.com/diegolamonica/EUCookieLaw/issues/7))
* **NEW:** \[WP\] Added shortcode for wrapping contents (see documentation for further details)
* **NEW:** Now the consent on scroll is fired at least after 100px scroll (up or down)
* **IMPROVEMENT:** \[WP\] Made compliant with **WP Super Cache**, **W3 Total Cache**, **Zen Cache** (Issue [#23](https://github.com/diegolamonica/EUCookieLaw/issues/23))
* **IMPROVEMENT:** Javascript has been refactored to improve performance and maintenability
* **IMPROVEMENT:** \[WP\] Admin interface improved
* **IMPROVEMENT:** Some CSS improvements (Issue (Issue [#8](https://github.com/diegolamonica/EUCookieLaw/issues/8))
* **BUGFIX:** Consent on scroll doesn't work propery
* **BUGFIX:** \[WP\] Custom content path not recognized correctly ( Issue [#9](https://github.com/diegolamonica/EUCookieLaw/issues/9))
* **BUGFIX:** Typos where `script` was written as `srcript` on server script (Issue [#16](https://github.com/diegolamonica/EUCookieLaw/issues/16))
* **BUGFIX:** Only first occourrence of the same/similar URL is blocked (Issue [#19](https://github.com/diegolamonica/EUCookieLaw/issues/19))
* **BUGFIX:** Corrected some IE8 weird behavior
* updated translation files
* updated documentation
* updated the version number


= 1.4.1 =
* **BUGFIX:** fixed the javascript that has wrong characters in the script
* Fixed errors in documentation

= 1.4 =
* **NEW:** when you specify a domain starting with a dot (eg. `.google.com`) all the subdomains are valid (eg. `www.google.com` and `sub.domain.google.com`)
* **NEW:** Improved the banner loading (loaded before the DOM Event `load`)
* **NEW:** Optional implicit user agree on page scrolling ([Issue #4](https://github.com/diegolamonica/EUCookieLaw/issues/4)).
* **NEW:** Debugging options
* **NEW:** You can fix the banner on top or bottom of the page.
* **NEW:** The custom CSS (from `EUCookieLawCustom`) will be loaded in conjunction with the default CSS.
* **BUGFIX:** removed the `<![CDATA[ ... ]]>` envelop on script replacement due to some browser incompatibility.
* **BUGFIX:** Custom translations was never read
* updated translation files
* updated documentation
* updated the version number

= 1.3.1 =
* **BUGFIX:** the default text for disagree button when not given was `Disagree` instead it should be empty.
* **BUGFIX:** whatever is the name of the plugin directory the directory for the customizations (translations and CSS) must be `/wp-content/plugins/EUCookieLawCustom/`.
* updated documentation
* updated the version number

= 1.3 =
* Updated the eucookielaw-header.php,
  * **NEW:** now the disallowed domains trims the spaces on each domain. It means that is allowed to write `domain1.com ; domain2.com` and they will be correctly interpreted as `domain1.com` and `domain2.com`
* **NEW:** If not defined the disagee label text then the button is not shown. Useful for informative non-restrictive cookie policy.
* **BUGFIX:** the cookie `__eucookielaw` setted by javascript is defined at root domain level.
* updated documentation
* updated the version number

= 1.2 =
* Updated the eucookielaw-header.php,
  * **NEW:** now the search of url is performed in `<script>...</script>` tags too.
  * **BUGFIX:** some translations strings were broken.
* updated translation files
* updated documentation
* updated the version number

= 1.1 =
This update introduces several improvements, features and bugfixes. For a detailed information about the new release see:
[Issue #1](https://github.com/diegolamonica/EUCookieLaw/issues/1)

* updated the eucookielaw-header.php,
  * **NEW:** now it blocks script tags with `data-eucookielaw="block"` attribute
  * **NEW:** now is possible to define a blacklist of domains to block before the user consent the agreement
  * **NEW:** the blacklist is related to a set of tags (by default the plugin will scan `iframe`, `link` and `script` tags
* **NEW::** managed title tag, blocked domains and tags to scan
* **NEW:** if the plugin WP Super Cache is installed then the plugin will clear the cache until the user has not approved the agreeement to ensure to show always the right contents
* **NEW::** if there is a CSS file named `eucookielaw.css` in the custom directory `wp-content/plugins/EUCookieLawCustom/` the it will be appliead in place of the default one.
* **BUGFIX:** unescaped post data before saving the admin settings
* updated the version number
* updated translation strings
* updated documentation

= 1.0 =
* First release

== FAQ ==

* **How can I customize the banner style?**
  Please visit the [official documentation page on GitHub](https://github.com/diegolamonica/EUCookieLaw)
