# REST API: GET miniview subprofiles

Subprofiles are to a collection what regular profiles are to a database. 
To request the subprofiles that represent a certain profile from a 
miniview you can send an HTTP GET request to the following URL:

`https://api.copernica.com/v2/miniview/$id/subprofile?access_token=xxxx`

The `$id` should be replaced with the numerical identifier of the miniview 
you're requesting the subprofiles of.

## Returned fields

This method returns an array of subprofiles of a miniview. These 
subprofiles are JSON objects with the following properties:

- **id**: unique numerical identifier of the subprofile
- **secret**: secret code associated with the subprofile
- **fields**: fields belonging to the subprofile
- **profile**: ID of the profile the subprofile belongs to
- **collection**: ID of the collection the subprofile belongs to
- **created**: timestamp of when the profile was created in YYYY-MM-DD hh:mm:ss format
- **modified**: timestamp of when the profile was last modified in YYYY-MM-DD hh:mm:ss format

## PHP Example

The following PHP script demonstrates how to use the API method.

```php
// dependencies
require_once('copernica_rest_api.php');
  
// change this into your access token
$api = new CopernicaRestAPI("your-access-token", 2);

// do the call, and print result
print_r($api->get("miniview/{$miniviewID}/subprofiles"));
```

The example above requires the [CopernicaRestApi class](rest-php).

## More information

* [List of all API calls](rest-api)
* [GET miniview](rest-get-miniview)
