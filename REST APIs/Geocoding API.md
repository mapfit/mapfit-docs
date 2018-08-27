# Geocoding API
## Getting started

Familiar with [Postman](https://www.getpostman.com/)? Download and run our postman collection below to get started with API examples in seconds.

[![Run in Postman](https://files.readme.io/3178ec7-POSTMANPIC.png)](https://s3.us-east-2.amazonaws.com/mapfit-test-assets/180521_Mapfit_REST_API.postman_collection.json)

### GET

The Mapfit Geocode API is accessible through GET requests. The GET requests have a root URL and params passed in as a query string.  Params are signified by ampersand symbols and street address is a string with white space between words written as plus signs.

### Example Get Request
[https://api.mapfit.com/v2/geocode?street_address=119+w+24th+st+new+york+ny&building=true&api_key={API_KEY}](https://api.mapfit.com/v2/geocode?street_address=119+w+24th+st+new+york+ny&building=true&api_key={API_KEY})

### POST

The Mapfit Geocoding API is also accessible through POST requests with up to 50 POST objects possible at the same time. 
[block:api-header]
{
  "title": "Post Options (***) required"
}
[/block]

[block:parameters]
{
  "data": {
    "h-0": "Parameters",
    "h-1": "Type",
    "h-2": "Default",
    "h-3": "Description",
    "h-4": "Example",
    "0-0": "admin_1",
    "0-1": "String",
    "0-2": "N/A",
    "0-3": "UTF-8/URL encoded string. Can be spelled out or abbreviated.",
    "0-4": "New York or NY",
    "1-0": "API_KEY***",
    "1-1": "String",
    "1-2": "N/A",
    "1-3": "N/A",
    "1-4": "N/A",
    "2-0": "building",
    "2-1": "Boolean",
    "2-2": "False",
    "2-3": "User can specify wether they want building polygon rendered",
    "2-4": "N/A",
    "3-0": "entrance_type",
    "3-1": "String",
    "3-2": "pedestrian_primary",
    "3-3": "Type of entrance that user is geocoding for",
    "3-4": "pedestrian-primary, pedestrian-secondary, all, loading, service, parking, OR all- followed by any of the above, OR all-pedestrian.",
    "4-0": "locality",
    "4-1": "String",
    "4-2": "N/A",
    "4-3": "Name of the local area",
    "4-4": "New York",
    "5-0": "lat",
    "5-1": "Double",
    "5-2": "N/A",
    "5-3": "Latitude",
    "5-4": "39.466847",
    "6-0": "lon",
    "6-1": "Double",
    "6-2": "N/A",
    "6-3": "Longitude",
    "6-4": "-76.8211403",
    "7-0": "postal_code",
    "7-1": "String",
    "7-2": "N/A",
    "7-3": "Postal Code",
    "7-4": "12345",
    "8-0": "street_address***",
    "8-1": "String",
    "8-2": "N/A",
    "8-3": "The address to be geocoded",
    "8-4": "4 Pennsylvania, NewYork, NY"
  },
  "cols": 5,
  "rows": 9
}
[/block]

### Responses

### Status Codes

Different HTTP Status Code signify different things in Mapfit Geocode API:


**200** - The request was processed, and an answer found according to the geocoder logic as detailed above.  The result is either some kind of entrance to a place, an interpolated point, general location, etc. 

**400** - There was an issue interpreting the request.  I.e. a street_address was missing, or was not a recognizable address, or the request body was not valid application/json.  There will be an error_type and a message to help the user better understand the cause.  The error_type will be client when HTTP status is 400.

**500** - There was an issue processing the request.  The issue may be transient (like an IO-related exception) which may necessitate trying the request again later.  The issue may also be semi-permanent, indicating a bug in the geocoder.  There will be a error_type of server and an associated message to help the client better understand the nature of the failure.


### Response Parameters

[block:parameters]
{
  "data": {
    "h-0": "Parameters",
    "h-1": "Type",
    "h-2": "Explanation",
    "0-0": "locality",
    "1-0": "postal_code",
    "2-0": "admin_1",
    "3-0": "country",
    "0-1": "String",
    "1-1": "String",
    "2-1": "String",
    "3-1": "String",
    "4-0": "neighborhood",
    "5-0": "response_type",
    "6-0": "building",
    "4-1": "String",
    "5-1": "Integer",
    "6-1": "Object",
    "7-0": "type",
    "8-0": "coordinates",
    "9-0": "street_address",
    "7-1": "String",
    "8-1": "Array",
    "9-1": "String",
    "0-2": "String representing local area",
    "1-2": "Postal code of queried Street address",
    "2-2": "String also representing are of queried street address",
    "3-2": "Country of the queried string",
    "4-2": "General area for inputed Query",
    "5-2": "Number code signifying type of response received",
    "6-2": "Object containing Building information if a building was found during geocoding.",
    "7-2": "String nested in the building object that signifies shape of building",
    "8-2": "Array of coordinates nested within the building object that can be used to render the building.",
    "9-2": "Address that was queried",
    "10-0": "entrances",
    "11-0": "lon",
    "12-0": "lat",
    "13-0": "entrance_type",
    "14-0": "error_type",
    "13-1": "String",
    "14-1": "String",
    "15-0": "message",
    "15-1": "String",
    "13-2": "Specific type of entrance of an object found in the array of entrance objects",
    "14-2": "If an error is present this specifies what type of error",
    "15-2": "Message for the response that comes in.",
    "10-1": "Array",
    "11-1": "Double",
    "12-1": "Double",
    "10-2": "An array of objects each object representing an entrance found on a geocoded address.",
    "11-2": "Latitude nested in an object in the array of entrances",
    "12-2": "Longitude nested in an object in the array of entrances"
  },
  "cols": 3,
  "rows": 16
}
[/block]

### Response Types
Every response has a response_type. The response type gives more information to the user on what information was received.

[block:parameters]
{
  "data": {
    "h-0": "Response Type",
    "h-1": "Meaning",
    "h-2": "Example Response",
    "0-0": "0",
    "0-1": "Error",
    "0-2": "[{\n \"response_type\": 0,\n \"error-type\": \"client\",\n \"message\": \"Must specify   a \n  value for 'street_address'\"\n}]",
    "1-0": "1",
    "1-1": "Success",
    "1-2": "[{\n    \"street_address\": \"3210 \n     Grace St NW\",\n    \"country\": \"USA\",\n    \"admin_1\": \"DC\",\n    \"locality\": \"Washington\",\n    \"response_type\": 1,\n    \"neighborhood\": \"\",\n    \"entrances\": [{\n      \"lon\": -77.063513,\n      \"entrance_type\": \"pedestria .      n-primary\",\n      \"lat\": 38.903922\n    }],\n    \"postal_code\": \"20007\"\n  }]",
    "2-0": "2",
    "2-1": "Interpolated address. This means the exact address was not found but the information given was enough for an educated guess.",
    "2-2": "[{\n    \"street_address\": \"3211 Grace St NW\",\n    \"country\": \"USA\",\n    \"admin_1\": \"DC\",\n    \"locality\": \"Washington\",\n    \"response_type\": 2,\n    \"neighborhood\": \"\",\n    \"entrances\": [{\n      \"lon\": -76.961165,\n      \"lat\": 38.872153\n    }],\n    \"postal_code\": \"20007\"\n  }]",
    "3-0": "3",
    "3-1": "Zero results were found from the input query",
    "3-2": "[{\n    \"response_type\": 3,\n    \"message\": \"Zero    results\"\n }]",
    "4-0": "5",
    "4-1": "Region.  We found a geographic region by the name provided in the street_address field.  This can either be a locality, an admin_1, or a country.  The response street_address will contain a label suitable for display of the region on a map.  For example, a result for a search with street_address 'Washington DC’ is street_address 'Washington, District Of Columbia, United States'.",
    "4-2": "[{\n  \"country\": \"USA\",\n  \"street_address\": \"Washington, District Of Columbia, United States\",\n  \"admin_1\": \"DC\",\n  \"viewport\": {\n    \"southwest\": {\n      \"lon\": -77.06137000000001,\n      \"lat\": 38.88011\n    },\n    \"northeast\": {\n      \"lon\": -77.01137,\n      \"lat\": 38.91011\n    }\n  },\n  \"locality\": \"Washington\",\n  \"response_type\": 5,\n  \"location\": {\n    \"lon\": -77.03637,\n    \"lat\": 38.89511\n  },\n  \"neighborhood\": \"\"\n}]",
    "5-0": "6",
    "5-1": "Road. We found a road the provided the street_address as its name",
    "5-2": "[{\n  \"street_address\": \"Sacred Heart Ln\",\n  \"country\": \"USA\",\n  \"admin_1\": \"MD\",\n  \"locality\": \"Reisterstown\",\n  \"response_type\": 6,\n  \"location\": {\n    \"lon\": -76.82191,\n    \"lat\": 39.46971\n  },\n  \"neighborhood\": \"\",\n  \"postal_code\": \"21136\"\n}]",
    "6-1": "Fallback.  We relied on a less-precise geocoding approach to find the input.  The result is either a building centroid, best-guess, geographic region or other data type about which we make very few guarantees.",
    "6-2": "[{\n    \"postal_code\": \"\",\n    \"country\": \"GTM\",\n    \"street_address\": \"14 Avenida 62, Guatemala, Guatemala\",\n    \"locality\": \"Guatemala\",\n      \"response_type\": 13,\n    \"location\": {\n         \"lon\": -90.5514631,\n         \"lat\": 14.612469\n    },\n    \"admin_1\": \"\",\n    \"neighborhood\": \"Zona 11\"\n}]",
    "6-0": "13"
  },
  "cols": 3,
  "rows": 7
}
[/block]

### Example Response


```json

 [{
  		"locality": "New York",
  		"postal_code": "10011",
  		"admin_1": "NY",
  		"country" : "USA",
  		"neighborhood": "",
  		"response_type": 1,
  		"building": {
    		"type": "Polygon",
    		"coordinates": [[[-73.992953, 40.744257], [-73.993265, 40.744389],[-73.993448, 40.744138],[-73.993136, 40.744006], [-73.992953, 40.744257]]]
  			},
  		"street_address": "119 W 24th St",
  		"entrances": [{
    		"lon": -73.99324,
    		"lat": 40.74405,
    		"entrance_type": "pedestrian-primary"
  		}]
	}]

```