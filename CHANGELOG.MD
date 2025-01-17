# Changelog

## 2.5.2
* Add john-lang-86/lj-maintenance-mode#15 shortcodes for dynamic page content. (Thanks to [@john-lang-86](https://github.com/john-lang-86/))
  1. Add [ljmm_is_maintenance_mode_enabled] Show this content only when maintenance mode is enabled [/ljmm_is_maintenance_mode_enabled] shortcode.
  2. Add [ljmm_is_maintenance_mode_disabled] Show this content only when maintenance mode is disabled [/ljmm_is_maintenance_mode_disabled] shortcode.
  3. Add [ljmm_is_user_logged_in] Show this content only when the user is logged in to the website [/ljmm_is_user_logged_in] shortcode.
  4. Add [ljmm_is_user_logged_out] Show this content only when the user is logged out of the website, they are a public user [/ljmm_is_user_logged_out] shortcode.
* Add john-lang-86/lj-maintenance-mode#6 to expand the supported languages. (Thanks to [@john-lang-86](https://github.com/john-lang-86/))
  1. Updated source code to be primarily human native language, removing the technology aspects (like %s) from the translatable phrases. This technique significantly improved the online translation success; while intentionally leaving 1 %s in the translation string list as a 'canary in the coal mine' test to see how well the translator handled it.
  2. Using 'PoEdit Pro' application and the DeepL/Google online ML translators. Keeping languages that had a > 98% online translation success, as anything less would be a disappointing user expectation and experience.
  3. As-at 28 Mar 2022, 145 locales (language_region combinations) have been translated. The full [journey from RTFM to commit](https://github.com/john-lang-86/lj-maintenance-mode/issues/6) has been documented.
      * Focus on [WordPress installation statistics](https://wordpress.org/about/stats/), in descending ranked order; then
      * Focus on [WordPress up-to-date translations](https://make.wordpress.org/polyglots/teams/), which indicates an active community.
      * Focus on [Stripe Payment Processor](https://support.stripe.com/questions/supported-languages-for-stripe-checkout-and-payment-links) supported languages.
* Resolves review [feedback about Twenty Twenty-Two theme compatability](https://wordpress.org/support/topic/love-this-plugin-so-much-i-donated/) as part of ['Alternative to get_header hook/action'](https://github.com/john-lang-86/lj-maintenance-mode/issues/11) solution. (Thanks to [@john-lang-86](https://github.com/john-lang-86/))
* Update screenshot-4.png for the new settings page options in 2.5.2, and add screenshot-10.png
* Update `README.md` and `readme.txt` files.

## 2.5.1.1
* Fix john-lang-86/lj-maintenance-mode#1 to improve trailing slash comparisons. (Thanks to [@john-lang-86](https://github.com/john-lang-86/))
* Fix john-lang-86/lj-maintenance-mode#13 to allow a strict comparison for the site home page. (Thanks to [@john-lang-86](https://github.com/john-lang-86/))
* Improved helpful messages to advanced setting options. (Thanks to [@john-lang-86](https://github.com/john-lang-86/))

## 2.5.1
* Added Autoptimize message. (Thanks to [@john-lang-86](https://github.com/john-lang-86/))
* Added "maintenance.min.login.css" feature. When detected in theme directory, this CSS file will be loaded in the standard login page to show users that maintenance mode is active. (Thanks to [@john-lang-86](https://github.com/john-lang-86/))
  1. Added filter "ljmm_css_login_filename".
  2. Added filter "ljmm_css_login_url".
* Resolve lukasjuhas/lj-maintenance-mode#37 by adding 6 "Allowed" setting lists; match one on a list and maintenance mode lets the request proceed. (Thanks to [@john-lang-86](https://github.com/john-lang-86/))
  1. Added "Allowed IPs (Contains)" setting, where $_SERVER[REMOTE_ADDR] matching requests will by-pass maintenance mode page.
  2. Added "Allowed URIs (Strict)" setting, where $_SERVER[REQUEST_URI] matching requests will by-pass maintenance mode page.
  3. Added "Allowed URIs (Contains)" setting, where $_SERVER[REQUEST_URI] matching requests will by-pass maintenance mode page.
  4. Added "Allowed Query Strings (Contains)" setting, where $_SERVER[QUERY_STRING] matching requests will by-pass maintenance mode page.
  5. Added "Allowed Referers (Contains)" setting, where $_SERVER[HTTP_REFERER] matching requests will by-pass maintenance mode page.
  6. Added "Allowed User Agents (Contains)" setting, where $_SERVER[HTTP_USER_AGENT] matching requests will by-pass maintenance mode page.
* Resolve lukasjuhas/lj-maintenance-mode#43 by switching from 'get_header' to 'wp_loaded' hook/action. (Thanks to [@john-lang-86](https://github.com/john-lang-86/))
  1. Always allow '/wp-login.php' URI access requests.
  2. Always allow 'action=enter_recovery_mode&rm_token=' query string access requests.
* Fix lukasjuhas/lj-maintenance-mode#44 by always allowing access when "current_user_can('administrator')" check passes. (Thanks to [@john-lang-86](https://github.com/john-lang-86/))
* Resolve lukasjuhas/lj-maintenance-mode#47 by adding 2 DIVs to maintenance mode page (wrapper and content); for more flexible CSS options. (Thanks to [@john-lang-86](https://github.com/john-lang-86/))
* Add helpful messages to advanced setting options. (Thanks to [@john-lang-86](https://github.com/john-lang-86/))
* Add screenshot-4-2-5-1.png of settings page for 2.5.1.

## 2.5
* Added WP Rocket message. (Thanks to [@john-lang-86](https://github.com/john-lang-86/))
* Added "maintenance.min.frontend.css" feature. When detected in theme directory, this CSS file will be loaded in the frontend to show logged in users that maintenance mode is active. (Thanks to [@john-lang-86](https://github.com/john-lang-86/))
  1. Added filter "ljmm_css_frontend_filename".
  2. Added filter "ljmm_css_frontend_url".
* Commit contains unit tested (functional) core for 'an exception allow list for non-logged in access to resources' for REMOTE_ADDR, REQUEST_URI (Strict Match), REQUEST_URI (Contains/Sloppy Match) and HTTP_REFERER; but still needs a settings page implementation. (Thanks to [@john-lang-86](https://github.com/john-lang-86/))
* Acknowledgment: Language translations for new strings in the settings page in 2.5 are missing.

## 2.4.4
* Bumped up "Tested up to"

## 2.4.3
* Added support for older PHP versions as per pre-2.4

## 2.4.2
* Add workaround capability management to support user role and capabilities plugins by using `delete_plugins` capability for super admins and `ljmm_control` for rest of the users

## 2.4.1
* Merge capabilities handling, tidy up and potentially fix capabilities issues some of the users have experienced

## 2.4
* More customisable than ever!
* Added support for stylesheet, widgets, code snippet injection and Analytify/Google Analytics tracking code (Thanks to Eric Mueller at [@switchplus](https://github.com/switchplus))
* Custom capability (Thanks to [@gabrielbijleveld](https://github.com/gabrielbijleveld))
* Code refactor and improvements
* Overall tidy up of the code
* Update broken support link
* Added shortcode support (Plugins like Contact Form 7 will work from now on)
* New icons and banners

## 2.3.2
* Added SiteOrigin Page Builder compatibility (Thanks to [@relgit](https://github.com/relgit))

## 2.3.1
* Hot Fix issue where user got locked out of admin area in maintenance mode.

## 2.3
* Small refactor, extract some of the parts to it's own method to make everything a bit cleaner
* Added 'ljmm_content' filter
* Move mode up to the "main" setting area instead of advanced settings
* From now on, `init` hook instead of `get_header` is used for maintenance mode
* Dedicated method to check if maintenance mode is enabled to make things cleaner
* Improve current_user_can checks. From codex: current_user_can( $capability ) will always return true if user is Super Admin, unless specifically denied - see [inline source code](https://developer.wordpress.org/reference/classes/wp_user/has_cap/)
* Update readme
* Preview mode will now perform capabilities check. (Thanks to [@esemlabel](https://wordpress.org/support/users/esemlabel/))
* Added Comet Cache support. (Thanks to [@doume](https://wordpress.org/support/users/doume/))
* Update translation files
* Updated French translation (Thanks to [@doume](https://wordpress.org/support/users/doume/))

## 2.2.5
* Add French translation (Thanks to [@doume](https://wordpress.org/support/users/doume/))

## 2.2.4
* Added missing translation strings (Thanks to [@doume](https://wordpress.org/support/users/doume/) for reporting this issue)
* Updated advanced settings toggle (Thanks to [@doume](https://wordpress.org/support/users/doume/) for reporting this issue)

## 2.2.3
* Updated POT file.(Thanks to [@doume](https://wordpress.org/support/users/doume/) for reporting this issue)
* Corrected typo for w3 total cache warning message. (Thanks to [@doume](https://wordpress.org/support/users/doume/) for reporting this issue)

## 2.2.2
* Fixed typo in variable ($cache_plugin_enabled). (Thanks to [@doume](https://wordpress.org/support/users/doume/) for reporting this issue)

## 2.2.1
* Added Dutch translation (Thanks to [@edwarddekker](https://github.com/edwarddekker))

## 2.2
* From now on, you can change status code being used while using maintenance mode between 503 (maintenance mode) or 200 (for "coming soon" page)
* Correct support url
* General code tidy up

## 2.1
* added WPML compatibility
* added TML (Theme My Login) compatibility
* Fixed issue where plugin capabilities were not being removed on uninstall
* Shorten admin bar indicator text, added icon
* Add support link to the plugins page
* Minor code tidy up

## 2.0.4
* Added Lithuanian translation (Thanks to [@gedeminas](https://github.com/gedeminas))

## 2.0.3
* Added Spanish Translations. (Thanks to [@bcien](https://github.com/bcien))
* Fixed issue where on non English sites admin bar indicator was broken.

## 2.0.2
* Fix db prefixing while getting roles. thanks @gablau
* Further checks improvements regarding problems caused by latest update for some users
* Add missing function wrapper for translations

## 2.0.1
* Improved checks regarding problems caused by latest update for some users

## 2.0
* Advanced settings
* Role Control
* You can now change title of the site while Maintenance Mode is enabled (in advanced settings)
* General tidy up of code
* Fix issue where Jetpack share was appearing in maintenance mode
* Settings page tidy up and corrections to formatting.

## 1.4.3
* Added German (DE) translations. (Thanks to Hoellenwesen)

## 1.4.2
* Update Pot file
* Small adjustments

## 1.4.1
* Bug fixes

## 1.4
* Bug fixes (Thanks to [@gablau](https://github.com/gablau))
* Security fixes - saving content more safely (Thanks to [@gablau](https://github.com/gablau))
* Languages: Add Italian (100%) (Thanks to [@gablau](https://github.com/gablau))
* Add compatibility while installed along wp-maintenance-mode [@gablau](https://github.com/gablau))
* Code: Avoid duplicating same code and use it as method instead.
* Code: Tidy up default messages and group them together within method to avoid repeating yourself and also searching all across code in order to change the messages in the future.

## 1.3.3
* Improvement: If MM is enabled, added message describing how to check if the maintenance mode is enabled as this was causing lot of confusion and unnecessary support tickets.
* Improvement: Move preview and support buttons to a more convenient place, also highlight the preview button.
* Languages: Add Canadian (100%), Hungarian(83%) languages.

## 1.3.2
* Fixed: Issue where non admin users could see admin bar indicator.

## 1.3.1
* Google is being notified right way from now on.
* Typo corrections
* General code tidy up

## 1.3
* Improvement: Translations adjustments and corrections. Plugin is now fully translatable.
* Improvement: Small code refactor and tidy up.
* Improvement: Correct various typo issues.

## 1.2.1
* Bug fixes
* Deprecated clear cache functionality as it caused errors to some users. From now on, plugin shows simple reminder to flush cache after enabling or disabling Maintenance Mode.


## 1.2
* Improvement: Improved Multisite Support
* Improvement: Show default maintenance message in the settings
* Improvement: Uninstalling will now clean up database
* Improvement: Added support link to the settings page
* Improvement: Translatable strings
* Improvement: Changed default site title while MM is active
* Improvement: Added preview button
* Improvement: Added support button
* Improvement: Added support for WP Super Cache
* Improvement: Added support for W3 Total Cache
* Bug Fixes

## 1.1.1
* Bug Fixes

## 1.1
* Added Indicator to Admin menu bar
* Added Settings button on plugins page
* Added Default maintenance mode message.
* Bug Fixes

## 1.0
* First release
