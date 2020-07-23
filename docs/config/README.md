---
sidebar: auto
tags:
 - configuration
 - properties
 - attributes
---

# Admin Config
The following configuration properties can be set through the admin interface to control the behaviour of the site.

## addressLineRows

Number of address row lines to show in the checkout

- Type: `Integer (1 - 4)`
- Default: `4`

## allowOOSAddToOrder

Allow out of stock items to be added to the basket

- Type: `Boolean`
- Default: `false`

## askForZip

Ask for zip/post code in the stripe checkout widget

- Type: `Boolean`
- Default: `false`

## badgerApplicationFeePercentage

- Type: `Double`
- Default: `2.4`

## badgerApplicationFeeFixed

- Type: `Integer`
- Default: `20`

## billPayFromAddress

- Type: `String`
- Default: `do-not-reply@bdgr.co.uk`

## billPayFromName
- Type: `String`

- Default: `Bill Notifications`

## billPaySubject

- Type: `String`
- Default: `You have a new bill:`

## billPayBCC

- Type: `String`
- Default: `admin@kedos.co.uk`

## creditCardStatementDescription

- Type: `String`
- Default: `siteContext.getSiteName() + " purchase"`

## contactUsEmailAddress
- Type: `String`
- Default: `admin@kedos.co.uk`

## contactUsCCEmailAddress
- Type: `String`
- Default: `""`

# countryCodeList
Country list displayed in checkout for the customer to choose from
- Type: `Comma-separated List`
- Default: `GB,US`

## defaultCountryCode
Default value chosen in checkout
- Type: `String`
- Default: `GB`

## displayLastOrderForMins
Determines how long the last order will be displayed for in the order confirmation page - after this it will not show the last order. This will not be required once the
- Type: `Integer`
- Default: `15`

## fixedServiceFee
Sets an integer value for fixed service fees - the amount that is charged to the customer for a transaction
- Type: `Integer`
- Default: `20`

# inventoryServiceName
selects inventory service

- Type: `String (catalogueInventoryService / mongoInventoryService)`
- Default: `mongoInventoryService`

## inStockByDefault

Determines whether a product will be in-stock if no inventory is set, or whether it defaults to out-of-stock until an explicit inventory has been set.
- Type: `String` 
- Default: `true`

## landingPageRedirectURL
When the landing page redirect is set, anything sent to / will be rewritten internally to this URL.
- Type: `String`
- Default: `/collection/home`

## mergeLineItems
If more than 1 product with the same sku is added to the basket, if this is true, the line items will be merged with a quantity of 2, rather than two separate line items.
- Type: `Boolean` 
- Default: `true`

## noShippingTriggerStates
- Type: `String`
- Default: `personalDetailsSet,addressDetailsSet`

## numberOfDaysToKeepInactiveUsers
Number of days that inactive users and orders will be kept
- Type: `Integer`
- Default: `45`

## openGraphProtocol
- Type: `String`
- Default: `http:`

## orderAndUserCleanUpBatchSize
Number of users to fetch from mongo in a batch for the clean up job
- Type: `String`
- Default: `10`

## orderDispatchSubjectPattern
Pattern used to generate the subject line for the order dispatch emails
- Type: `String`
- Default: `Order #{0} has been dipatched!`

## orderDispatchTemplate
Name of the template to be used for order dispatch emails.
- Type: `String`
- Default: `orderDispatched`

## orderFulfilmentEmailToAddress
The address used for order fulfilment emails
- Type: `String`
- Default: `order-notification@bdgr.co.uk`

## orderNotificationFromAddress
The address used for order notifications

- Type: `String (email)`
- Default: `order-notification@bdgr.co.uk`

## orderNotificationFromName
The name used for order notifications
- Type: `String (email)`
- Default: `siteContext.getSiteName()`

## orderNotificationBCCAddress
The address used for order notifications
- Type: `email address`
- Default: `null`

## paymentGatewayPctServiceFee
The percentage fee that the payment gateway charges for transactions
- Type: `Number`
- Default: `2.4`

## percentageServiceFee
The total fee that should be added to customer's orders when using the "customer pays fee" option.
- String: `Number`
- Default: `3.5`

# redirectionRules
A set of redirection rules that will be applied to all incoming requests.
- Type: `Colon separated list`
- Default: `null`

Each entry follows the following pattern:

`/sitemap.xml->/p/sitemap.xml->302`

Where each parameter is separated by a `->`, with the three params being:

- Original URL
- New URL
- Redirection Method - `301` (Permanent), `302` (Temporary)

NOTE: The redirection method is optional.



## securePagesColonSepVals

A list of URLs that if matched will be redirected to HTTPS (if they're not already over HTTPS).

- Type: `String - colon separated list`
- Default: `""`

## secureServerPort

The port that HTTPS requests should be sent to

- Type: `Integer`
- Default: `443`

## shippingRequiredTriggerStates

- Type: `String`
- Default: `personalDetailsSet,addressDetailsSet,deliveryMethodSet`

## siteCurrencyCode
Currency code that the site uses.

- Type: `String`
- Default: `gbp`

## sslRedirectEnabled
Determines whether the current URL should be checked against the "securePagesColonSepVals" property to see if a redirect should occur.

- Type: `Boolean`
- Default: `false`


## taxCalculationMode

Determines which method is used to calculate the tax.
- Type: `String`
- Default: `ORDER`

  - `ORDER` - Tax is calculated at the order level
  - `LINE_ITEM` - Tax is calculated at the Line Item level and summed
  - `ITEM` - Tax is calculated at the Item level, summed for the line item, and summed for the order

## trendingProductsEnabled
Determines whether the trending items should be calculated for a site.

- Type: `Boolean`
- Default: `false` 

## useFTPForImages
If true the images are saved using FTP. If false, they are uploaded from an S3 bucket.

- Type: `Boolean`
- Default: `true`

## useRedirectForLandingPage

Determines whether a redirect or an internal rewrite should be used when someone hits /.
- Type: `Boolean`
- Default: `true`

## useSearch
enables the search box on the template.
- Type: `Boolean`
- Default: `true`

## useSharedCheckout

Determines

- Type: `Boolean`
- Default: `false`

## validSortByValues

A list of values that will be accepted for sorting. Anything not on this white-list is rejected.

- Type: `Colon separated list.`
- Default: `price:attributes.collectionOrdering:rating:productName`

## favIconOverride

Override HTML for the favicon - this can be used to replace the HTML generated for the favicon with a separately generated fragment - good for when you want to override multiple screen sizes with different files. Suggestion: use [RealFaviconGenerator](https://realfavicongenerator.net)

- Type: `String: Valid HTML`
- Default: `null`

## favIconPath

Path to the replacement favicon - overrides the default badger icon

- Type: `String - absolute url to the image, should not contain protocol - i.e. //test.com/image.ico`
- Default: `null`

## appleTouchIconPath
Path to the apple touch 180px icon - used when creating a homepage shortcut on an iOS device
- Type: `String - absolute url to the image, should not contain protocol - i.e. //test.com/image.ico`
- Default: `null`