## Amazon Pay and Login with Amazon for Magento

[View the Complete User Guide](https://github.com/amzn/amazon-payments-magento-plugin/wiki)
or [Learn More about Amazon Pay](https://pay.amazon.com/sp/magento)


### Pre-Requisites
* Magento CE 1.7+ or EE 1.11+.
    * Magento 1.5 is supported with a patch see [here](https://github.com/amzn/amazon-payments-magento-plugin/wiki/Community-and-FAQ#q-i-am-on-magento-ce-15-or-magento-ee-110-can-i-use-amazon-payments) for more information
    * Magento 1.6 is supported with a fix explained in [issue #264](https://github.com/amzn/amazon-payments-magento-plugin/issues/264)
* SSL is installed on your site and active on Checkout and Login pages
* Compilation is turned off in your Magento system

**NOTE:** If you are based in the UK or EU, please check out our [Amazon Pay and Login with Amazon for Europe](https://www.magentocommerce.com/magento-connect/amazon-pay-and-login-with-amazon-for-europe.html) extension.

### Installation
> **NOTE** Before you begin, make a backup of your Magento site.

* Using Magento Connect (Recommended):
    * https://marketplace.magento.com/amzn-login-and-pay-for-magento.html
* Using Manual Installation:
    * Click the Download Zip button and save to your local machine
    * Transfer the zip file to your Magento webserver
    * Unpack the archive in the root directory of your Magento instance (this consists of copying the app, lib, and skin folders within the downloaded plugin zip into the root Magento directory)
    * Flush your Magento caches
        * In the admin page for your Magento instance, navigate to System->Cache Management
        * Click the 'Flush Magento Cache'
        * More information on Magento Cache Management [here](http://www.magentocommerce.com/knowledge-base/entry/cache-storage-management)
    * Log out of the admin page and then log back in to ensure activation of the module

### Uninstall/Disable  
#### Uninstalling via Magento Connect Manager
* Log into your magento administration panel
* Click on Magento Connect -> Magento Connect Manager
* Click the dropdown menu besides the extension you want to uninstall and choose "Uninstall".  Then click "Commit Changes"

**Note:** If 'uninstall' is not provided for Amazon Pay extension, please manually remove the Amazon Pay folder from your server.

#### Disabling manually 
   * From the command line edit the files: 
      * `<magento_root>/app/etc/modules/Amazon_Login.xml` (in versions <= 1.3.1)
      * `<magento_root>/app/etc/modules/Amazon_Payments.xml`
   * In each file, change the line
      `<active>true</active>`
      to
      `<active>false</active>`
   * This will completely disable the extension and prevent any resources being loaded by Magento.


### Configure Magento
* The plugin is configured under **System**->**Configuration**->**Payment Methods**->**Amazon Payments**.
* If you haven't already registered, use the link in the module to create an Amazon Payments account.
   * The new and improved registration system will automaticaly exchange your Amazon Pay account keys, provided you have SSL enabled for your admin. 
   * If you don't have SSL enabled, copy and paste the encrypted keys string and the end of the registration flow into the configuration and it will automatically set up your keys as well.

## Release Notes
### v.1.7.0 Release
## Enhancements
- Alexa Delivery Notifications support
- README.md file changes

### v1.6.0 Release
## Enhancements
- Amazon Pay is now SCA/PSD2 compliant
- Support for new merchant on-boarding platform for Amazon Pay merchants

## Issues Resolved
- Fix for the Magento [Security Patch SUPEE-11555](https://devdocs.magento.com/guides/m1x/ce19-ee114/ce1.9_release-notes.html?_ga=2.59452335.340946191.1561493917-546575631.1561493917#ce19-1942) release, for Amazon Pay

### v1.5.0 Release
## Enhancements
- Amazon Pay is now available as a payment option in the checkout step
- Improved error handling while disabling Amazon Pay extension
- Improved declined authorization handling when facing the AmazonRejected decline
- Improved the way merchants can limit shipping to certain states
- Added a callout for incompatbility of Amazon Pay with the Suhosin extension

## Issues Resolved
- Put email templates in correct folders
- Add in async decline hard template for en_GB which seemed to be missing
- Improves modman
- Added support for Magento 1.8
- Fixed an issue in OnePageCheckout that prevented the shipping info from showing
- Fixed an issue with the redirect after account verification when an existing Magento account with the same email already exists
- Trim config values during retrieval to prevent leading/trailing whitespaces creating issues
- Remove duplicate discount code appearing during checkout
- Fixed the notice that appears when enabling Amazon Pay on Website/Store view by loading value from parent scope if field set as inherited
- Rename config path for Amazon Pay as per Magento standard for payment options
- Fixed an issue where shopping cart rules were incorrectly implemented
- Fixed an issue where Amazon Pay ignored the default custoemr address
- Fixed the redirect on verify account to implement HTTPS
- Fixed an edge-case when a store is undefined at the time of order placements
- Fixed an issue where a customer could place an order from a non-allowed country
- Fixed an issue with responsive CSS styles which caused widgets to overlap.
- Improves the way the Amazon Pay button is rendered on the final step of checkout
- Fixed the getAmazonName method, to help in resolving #328

### v1.4.5 Release
## Enhancements
- #337 Replaced deprecated mcrypt_cbc with openssl_decrypt
- #356 Adding standard Magento files to repository

## Issues Resolved
- #322 Fixes issue with FireCheckout where order total is doubled
- #336 Fixes compatibility issues with PHP 5.6
- #354 Fixes syntax error
- #358 Fixes issue with discount codes in Standalone checkout

### v1.4.4 release
## Enhancements
 *  #294 Feature: Ability to add Coupon/Discount Code Field on Amazon Standalone Checkout
 *   #61 Enable tokenized payments
 *   #292 Change Widgets.js loading to async

## Pull Requests Merged
 * Fix outdated paths in modman file #307
 * Update Modman #270 

## Issues Resolved
 *   #281 ShipStation Phone Number Issue
 *   #274 Problem using onestepcheckout
 *   #287 Customer verify redirect to empty cart
 *   #291 Fix check for enabled amazon login
 *   #295 Amazon Payments Diagnostics tool throwing exception
 *   #284 JQuery Conflict Render Unusable
 *   #261 Script Loading Issue
 *   #286 Logout Error
 *   #293 JS failing to Serialize form during SaveOrder function call
 *   #280 Double Redirect on Cart Page
 *   #271 Add secure URL from config files
 *   #264 Fix broken admin in Magento 1.6
 *   #272 Add Disable Login with Amazon functionality
 *   #255 Disable shipping widget during decline flow
 *   #263 Limit shipping to supported countries


### v1.4.2 Bug Fix  
 * #260 Backend not loading after installation of new module

### v1.4.1 Widget Optimization and Bug Fixes
#### Pull Requests Merged  
 * #189 Making credential validation region aware. Addressing #185  
 * #191 EU  
 * #250 Fixed getFormParams() to work with DB prefixes  
 * #251 Update modman file for simplepath  
 * #254 removed buyer multi-language parameter and eu regions form the config  
 * #259 1.4.1 Release

#### Issues Resolved  
 * #159 Billing address not used  
 * #160 Placement of Login Button on Account Page  
 * #179 Localize admin links to amazon.com  
 * #190 Add hard decline email template for EU  
 * #199 Amazon buyer clicking cancel on consent form is sent to blank page  
 * #204 Add Support For SoftDescriptor  
 * #210 Add Email Store Name to all views  
 * #212 Add notification for delay for Pay with Amazon button on product page  
 * #214 Add shipping method validation  
 * #215 Center Button in Minicart  
 * #216 Wrong redirect URLs being shown  
 * #217 Add EU support to diagnostics  
 * #219 Default Scope cannot be empty / Validation only on default scope  
 * #216 Fix popup redirect URLs (mod_rewrite and store id detection)  
 * #220 cURL using IPv6  
 * #223 Magento EE feature "Gift wrapping" not supported  
 * #223 Fix Enterprise-only gift wrapping block  
 * #230 Amazon Payments ignoring the shipment rules and restrictions (using productMatrix Shipping Extension)  
 * #232 PHP 5.6 : iconv_set_encoding  
 * #233 Login: Email Confirmation Required Bug  
 * #236 1st checkout step button does not obey the login experience config bug Fix now  
 * #241 Inadvertently calling indexAction on redirect during error condition  
 * #243 Store view level does not allow to configure credentials  
 * #244 Widget Optimization on Standalone checkout  
 * #248 IWD with amazon payments  
 * #253 Use default store id  
 * #238 Issue changing Client ID & Client Secret in multistore magento 1.9.1.1 

### v1.4.0 Automated key exchange, new streamlined registration, condensed UI
#### Enhancements:
   * Enabled automated key exchange between Amazon and Magento for merchants
   * New simplified and streamlined registration process to help merchants start making transactions sooner
   * Redesigned UX to group and collapse settings
   * Removed duplication of keys in the Login with Amazon settings
   * Now using randomized internal reference IDs (e.g. for re-authorizations)

#### Pull Requests Merged:
   * #146 Update Shopping Cart Button Placement
   * #121 Override mage address validation and force Amazon address for shipping calculation
   * #143 Updates to Api.php
   * #164 Fixed call to a method on a non-object
   * #163 Fixed Content-Type header duplicate
   * #150 Added OneStepCheckout.com support
   * #188 Update modman paths
   * #192 Center the Amazon Badge just like Paypal is
   * #184 Fix where users were getting a Mixed Content warning on cart page

#### Bug Fixes:
   * #139 Fix capture error when auth is greater than 7 days old
   * #132 Add 'None' (new) payment action
   * #151 Obey account sharing scope config
   * #152 Fix multi-site refund, cancel, async, etc.
   * #170 Billing address fixes
   * #156 Restrict/disable Amazon widgets during standalone checkout order placement
   * #162 Disable Place Order if no payment method set
   * #158 Improve async testing and declines
   * #157 Restrict address widget and shipping method if payment declined
   * #156 Disable iframe and divs for IE 10
   * #158 Add email template for async declines
   * #176 Don't redirect to secure cart if Amazon payment method is disabled
   * #175 Don't inject JS when payment method disabled
   * #158 Add wallet widget on order detail page for async declines
   * #180 Always display login button on Checkout page
   * #157 Disable shipping widget and method on declines
   * #158 Use 'Login with Amazon' button instead of 'Pay'
   * #131 Add Sync auth in front of Async auth
   * #157 remove exception message
   * #174 Add Pay with Amazon button in mini cart
   * #181 Close Amazon Order when order state changed to COMPLETE (e.g. when order is shipped)
   * #182 Add Login button to register/account creation page
   * #193 Change payment decline email to transactional email for cron compatibility
   * #161 Add jQuery.noConflict() to fix JS errors and conflicts with prototype
   * #197 Fix amazon account logout
   * #198 Fix JS error when shipping method is hidden (e.g. virtual products)
   * #140 Auth Decline Errors could be more user friendly
   * #190 Add hard decline email for async
   * #206 Remove Widgets.js if cart is empty or 'Display on Product Page' is set to No

### v1.3.0 Automated key check, async improvements, diagnostics
#### Enhancements:
   * Automated Amazon key checking on save from admin page
   * Fixed an issue in Asyncrhonous mode where orders wouldnt be updated if any previous orders had mutiple payment methods attached
   * Added diagnostics tool to help support

#### Other Feature Additions:
   * Added modman, composer.json support (see https://github.com/magento-hackathon/magento-composer-installer)
   * Async cron job is more durable, will not exit on errors
   * Better manual syncing on async orders when admin presses Sync With Amazon button
   * Async capture bug
   * Better messaging to buyer when existing customer account is found

#### Pull Requests Merged:
   * #134 Add modman, composer.json
   * #125 Update Amazon Login Account Merging Text
   * #120 Diagnostics
   * #119 Check for user_id in amazon profile data.
   * #117 Fixed Amazon Login after Amazon account e-mail change

#### Bug Fixes:
   * #122 Sandbox orders should be identifiable to a merchant
   * #116 Display Plugin Version in Config
   * #110 Disable Login with Amazon from customer account page if disabled product in cart
   * #107 Onepage checkout. Moving to Amazon logged in user persists checkout preview items
   * #106 Add key checking on save from payment configuration
   * #104 Order Review Block Issues on Some Sites
   * #103 Add Site Badge
   * #102 Add Badge to OnePage Payment Label


### v1.2 Release - Asynchronous Authorization
   * In the admin configuration, you enable Asynchronous mode by setting the 'Asynchronous Mode' to 'Yes' Now when buyers checkout, the call is asynchronous and the state returned from any Authorize call is 'Pending'
   * The system uses Magento's built-in cron job functionality to poll Amazon systems for the status of any Open orders. See http://www.magentocommerce.com/wiki/1_-_installation_and_configuration/how_to_setup_a_cron_job for more information.
   * NOTE Orders will never update to their correct status if you do not have cron enabled as specified in the Magento documentation.
   * The polling interval is 5 minutes and when the cron job executes, it will get the new status, update the order in Magento appropriately to your configured 'New Order Status' and, if Authorize and Capture is configured, create the Invoice in Magento.

#### When should you use async vs sync?

   * You should use async when you have large average order values, on the order of > $500-$1000
   * You might also consider using async to speed up checkout since the authorizations come back immediately with a 'Pending' status.
   * Only merchants who have an existing workflow for reaching out to customer's whose payment method was declined should use the asynchronous model.

#### Features:

   * Developer client restrictions
      ** #78 Implement Developer Client Restrictions
   * Sort order variable
      ** #75 Fire/Onestep/IWD : Add sort order variable that determines where Amazon Payments shows up in list
   * Works with iwd onepage checkout/firecheckout
      ** #77 Fire/Onestep/IWD : Amazon address pullled into form when buyer bails out of Amazon flow
      ** #74 Fire/Onestep/IWD : Launch amazon checkout (login) on radio button select

#### Bug Fixes

   * #88 Standalone Checkout with Modal: Content blocked when account verification required
   * #85 PaymentPlanNotSet exception when invalid payment method.
   * #83 CE v1.5 missing core public method lookupTransaction
   * #82 Orders break when plugin disabled.
   * #81 Display as Payment Option setting is not respected in Onestepcheckout
   * #80 Use CSS !Important for Place Order Button

### v1.1.2
#### Features

   * Integration with Firecheckout extension
   * Integration with IWD OnePage checkout extension
   * Capture shipping address in customer address book in Magento
   * Allow configuration for secure cart (on/off). Allows for AJAX "Add to Cart" extensions to function and/or merchants to function without a secure cart

#### Bug Fixes

   * Fix #62 - add Amazon address to customer shipping address book when order is placed, checking for duplicates 5ef24c4
   * Fix #40 - allow 115% or $75 over-refunds, whichever is smaller 51573d9
   * Add configuration for secure cart on/off #71 b720bf6
   * Fix iundefined isSecureCart #71 b4943d5
   * Fix redirect if secure URL config is not HTTPS #71 f95734f
   * #24 more fixes for undefined index notices on certain themes 7dd2e20
   * Add Amazon pay button under Payment Info (enabled in config, off by default) for thrid-party checkouts 96fbb35
   * #72 add payment option pay button 4721339
   * Fix order state to be processing for auth & capture 27bfec4
   * Fix customer address update for virtual (no shipping address) orders cea65e4
   * Fix order status e5a8015

### v1.1.1 

   * Fix product shortcut button - JS SyntaxError: missing ) after argumen… … 0157078
   * Fix #60 remove port numbers from URL in help text 7cdde2c
   * Fix #57 hide amazon payments method if no amazon session a8e2fde
   * Adding package file such that tgz downloads are installable in Magent… … f33fb83
   * Add payments button block reference to onepage f8fe834
   * Fix#24 - overrode Progress block to prevent 'undefined index: widget' error 3e6e9b4
   * Fix #66 fix terms and conditions on stand alone checkout 8ead600
   * Update README.md 582ed69
   * Shortened authorizationReferenceId e735839
   * Fix #67 add spinner and opacity to review on submit 1e762cf
   * Fix #69 - remove undefined blackslash 872d6dd
   * Fix #70 - skip payment processing on -bash orders 73d7a20
   * Add benchmark for Amazon API calls and optimized order error checking

### v1.1.0

   * Updated payments admin screen to make it easier to configure.
   * Fixed JQuery conflict on product detail button shortcut.
   * Fixed compilation issue. (Issue #52)
   * Added button styling options. (Issue #47)

### v1.0.1

   * Fixed NOTICE and LICENSE
