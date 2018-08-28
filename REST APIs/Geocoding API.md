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

Parameters | Type | Default | Description | Example
-----------|------|---------|-------------|--------
admin_1 |String | N/A |UTF-8/URL encoded string. Can be spelled out or abbreviated. |New York or NY 
API_KEY*| String| N/A| N/A | N/A 
building| Boolean| False| User can specify wether they want building polygon rendered | N/A 
entrance_type| String| pedestrian_primary| Type of entrance that user is geocoding for | pedestrian-primary, pedestrian-secondary, all, loading, service, parking, OR all- followed by any of the above, OR all-pedestrian.
locality| String| N/A| Name of the local area| New York
lat| Double| N/A| Latitude| 39.466847 
lon| Double| N/A| Longitude| -76.8211403 
postal_code| String| N/A| Postal Code| 12345 
street_address*| String| N/A| The address to be geocoded| 4 Pennsylvania, NewYork, NY


### Responses

### Status Codes

Different HTTP Status Code signify different things in Mapfit Geocode API:


**200** - The request was processed, and an answer found according to the geocoder logic as detailed above.  The result is either some kind of entrance to a place, an interpolated point, general location, etc. 

**400** - There was an issue interpreting the request.  I.e. a street_address was missing, or was not a recognizable address, or the request body was not valid application/json.  There will be an error_type and a message to help the user better understand the cause.  The error_type will be client when HTTP status is 400.

**500** - There was an issue processing the request.  The issue may be transient (like an IO-related exception) which may necessitate trying the request again later.  The issue may also be semi-permanent, indicating a bug in the geocoder.  There will be a error_type of server and an associated message to help the client better understand the nature of the failure.


### Response Parameters
Parameters | Type | Explanation
-----------|------|------------
locality | String| String representing local area
postal_code| String| Postal code of queried Street address 
admin_1| String| String also representing are of queried street address 
country| String| Country of the queried string 
neighborhood| String| General area for inputed Query 
response_type| Integer| Number code signifying type of response received
building| Object| Object containing Building information if a building was found during geocoding.
type| String| String nested in the building object that signifies shape of building
coordinates| Array| Array of coordinates nested within the building object that can be used to render the building.
street_address| String| Address that was queried 
entrances| Array| An array of objects each object representing an entrance found on a geocoded address.
lon| Double| Latitude nested in an object in the array of entrances
lat| Double| Longitude nested in an object in the array of entrances
entrance_type| String| Specific type of entrance of an object found in the array of entrance objects
error_type| String| If an error is present this specifies what type of error 
message| String| Message for the response that comes in.


### Response Types
Every response has a response_type. The response type gives more information to the user on what information was received.

Response Type | Meaning | Example Response
--------------|---------|-----------------
0 |Error| `[{ "response_type": 0, "error-type": "client", "message": "Must specify a value for 'street_address'" }]` 
1| Success| `[{ "street_address": "3210 Grace St NW", "country": "USA", "admin_1": "DC", "locality": "Washington", "response_type": 1, "neighborhood": "", "entrances": [{ "lon": -77.063513, "entrance_type": "pedestria . n-primary", "lat": 38.903922 }], "postal_code": "20007" }]` 
2| Interpolated address. This means the exact address was not found but the information given was enough for an educated guess.| `[{ "street_address": "3211 Grace St NW", "country": "USA", "admin_1": "DC", "locality": "Washington", "response_type": 2, "neighborhood": "", "entrances": [{ "lon": -76.961165, "lat": 38.872153 }], "postal_code": "20007" }]` 
3| Zero results were found from the input query| `[{ "response_type": 3, "message": "Zero results" }]` 
5| Region. We found a geographic region by the name provided in the street_address field. This can either be a locality, an admin_1, or a country. The response street_address will contain a label suitable for display of the region on a map. For example, a result for a search with street_address 'Washington DC’ is street_address 'Washington, District Of Columbia, United States'.| `[{ "country": "USA", "street_address": "Washington, District Of Columbia, United States", "admin_1": "DC", "viewport": { "southwest": { "lon": -77.06137000000001, "lat": 38.88011 }, "northeast": { "lon": -77.01137, "lat": 38.91011 } }, "locality": "Washington", "response_type": 5, "location": { "lon": -77.03637, "lat": 38.89511 }, "neighborhood": "" }]` 
6| Road. We found a road the provided the street_address as its name|` [{ "street_address": "Sacred Heart Ln", "country": "USA", "admin_1": "MD", "locality": "Reisterstown", "response_type": 6, "location": { "lon": -76.82191, "lat": 39.46971 }, "neighborhood": "", "postal_code": "21136" }]`
13| Fallback. We relied on a less-precise geocoding approach to find the input. The result is either a building centroid, best-guess, geographic region or other data type about which we make very few guarantees.| `[{ "postal_code": "", "country": "GTM", "street_address": "14 Avenida 62, Guatemala, Guatemala", "locality": "Guatemala", "response_type": 13, "location": { "lon": -90.5514631, "lat": 14.612469 }, "admin_1": "", "neighborhood": "Zona 11" }]`

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