# REST API: GET destination abuses (Marketing Suite)

Each emailing is tracked, which allows Copernica to provide you with 
emailing statistics. Abuses are one of these statistics. You can 
retrieve all abuses for a specific destination by sending an HTTP GET call to the following URL:

`https://api.copernica.com/v2/ms/destination/{$destinationID}/abuses?access_token=xxxx`

This method also support the use of the [fields parameter](./rest-fields-parameter) 
for the **timestamp** field.

## Returned fields

The method returns a JSON object with several abuses. For each abuse 
the following information is available:

* **ID**: The ID of the abuse.
* **mailing**: The ID of the mailing.
* **timestamp**: Timestamp of the abuse.
* **report**: The abuse report.
* **destination**: The ID of the destination that reported the abuse.
* **profile**: The ID of the profile that reported the abuse.
* **subprofile**: The ID of the subprofile that reported the abuse.

## PHP example

This script demonstrates how to use this API method:

```php
// dependencies
require_once('copernica_rest_api.php');

// change this into your access token
$api = new CopernicaRestAPI("your-access-token", 2);

// execute the call
print_r($api->get("ms/destination/{$destinationID}/abuses"));
```

This example requires the [REST API class](./rest-php).

## More information

* [Overview of all REST API calls](./rest-api)
* [Get all abuses](./rest-get-ms-abuses)
* [Get destination clicks](./rest-get-ms-destination-clicks)
* [Get destination deliveries](./rest-get-ms-destination-deliveries)
* [Get destination errors](./rest-get-ms-destination-errors)
* [Get destination impressions](./rest-get-ms-destination-impressions)
* [Get destination unsubscribes](./rest-get-ms-destination-unsubscribes)
