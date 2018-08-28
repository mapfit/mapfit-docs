---
title: "Geocoder"
excerpt: "mapfit.Geocoder"
---

# Geocoder
### mapfit.Geocoder  

A class for handling geocoding. Geocoding is used to get coordinates for a given address. The Mapfit geocoder is also capable of returning entrances and building polygons if the given address belongs to a building.
Constructor | Description
------------|------------
mapfit.Geocoder(apiKey:String, apiUrl:String); |Construct a new Geocoder instance with your api key and the Mapfit api url: https://api.mapfit.com/v2. ```let geo = new mapfit.Geocoder("[MY_API_KEY]", "https://api.mapfit.com/v2");```

**Geocode** 

Method | Descriptions
-------|-------------
geocode(address: String, includeBuilding: Boolean): Promise(resolve, reject) | Returns a list of addresses with entrance points. Optionally returns the associated building polygon (where available).

Result Object
Field | Description
------|------------
admin_1: String | The principal subdivision's 2-character ISO 3166-2 name. For example, in the US, admin_1 would be the associated with the state's 2-character code, like "NY" for "New York State", "DC" for "Washington, D.C.", or "VI" for US Virgin Islands. For areas in which there are prefectures, provinces, or other top-level administrative divisions, the relevant principal subdivision code is returned in accordance with ISO 3166-2.
building: [] | The building polygon associated with the address, as represented as an array of coordinates (in GeoJSON format). 
country: String | This is the 3-character ISO 3166-1 country code for the country in which the streetAddress is known to exist, according to one or more sources in our data set. For example, 'USA' for the United States of America, and 'DEU' for Germany (Deutschland). 
entrances: [] | When an address is found associated with an entrance to its designated structure, the geocoder returns an entrances array with the entrances that were found, in no particular order. Only one entrance will exist unless the requested entrance_type is ALL or ALL-PEDESTRIAN. Each entrance is an object that has the following: lat - The latitude (WGS84) lon - The longitude (WGS84) entrance_type (returns only if reponse_type=1) - The type of entrance at the associated lat, lon. See below table for possible entrance types.
locality: String | This is the "city", or relevant municipality or local administrative area's name in which the street_address was found. For the USA, this will often be synonymous with "city"; though it could be a borough (like Manhattan)) or neighborhood name. 
neighborhood: String | The neighborhood, or geographically localised community within a larger city, town, suburb or rural area. 
postal_code: String | The postal code associated with the response street_address according to at least one of our data sources. For the US, this is the 5-digit zipcode (without the plus4 addition).
response_type: String | Response types indicate - using an integer value that can be easily checked by the client - information about the kind of response the server sent. See below for ennumerated reponse types.
street_address: String | This is the address (at the street level) of the resolved input. Note: secondary designators (Unit, Apt. Bldg. etc.) are not included, as the highest level of accuracy is at the structure-entrance-level. The street_address may include country, and/or adminArea in the address when the response_type is 13.

Response Type | Description
--------------|------------
0 | Error. 
1 | Success (entrance found in our data set). 
2 | Interpolated. We were unable to find the specified address by number, but were able to find contextual information and give an educated guess as to where the input address would be if we had it. 
3 | Zero results. We did our best, but could not find an answer to the input query. 
5 | Region. We found a geographic region by the name provided in the street_address field. This can either be a locality, an admin_1, or a country. The response street_address will contain a label suitable for display of the region on a map. For example, a result for a search with street_address 'Washington DC' is street_address 'Washington, District Of Columbia, United States'. 
6 | Road. We found a road with the provided street_address as its name. 
13 | Fallback. We relied on a less-precise geocoding approach to find the input. The result is either a building centroid, best-guess, geographic region or other data type about which we ake very few guarantees.

Entrance Type | Description
--------------|------------
pedestrian-primary | The primary entrance to the building addressed by the street_address. It is pedestrian accessible, and is usually the entrance at which one wants to arrive. There could be more than one pedestrian-primary entrance to a building, in which case, either a single one is returned, when searching the default entrance_type, or when searching specifically for pedestrian-primary. 
pedestrian-secondary | This is an alternate entrance, which is also pedestrian accessible. This will be returned if it is closest to the request's lat,lon and there is no known primary entrance, when the requested entrance_type is all or all-pedestrian or pedestrian-secondary. 
parking | This is the entrance to a parking lot, and as such is not considered pedestrian accessible, but a potential destination for travel to the requested address if driving and needing to park. parking entrances are only returned when the requested entrance_type is all or parking.
service | This is a service entrance to the requested address. This is returned only when the requested entrance_type is all or service 
loading | This is a loading dock associated with the building addressed by street_address. This is returned only when the requested entrance_type is all or loading.

**Reverse Geocode** 
Method | Descriptions
-------|-------------
reverseGeocode(latlng: String | Array | LatLng, building: Boolean, radius: Double, limit: Int): Promise(resolve, reject) | This API accepts a lat, lon and returns a response containing the closest Mapfit address entrance to the specified geolocation, with the exact same response shape returned by the Geocode API. Different entrances to an address are returned separately.

Parameters | Accepted Value | Required | Notes
-----------|----------------|----------|------
javascript latlng | String \| Array \| LatLng | yes | lat Double values between (-90, 90) lon Double values between (-180, 180) 
javascript building | Boolean true of false| no. Default is false | Whether to return the building footprint polygon associated with the reverse geocoded address for which the entrance was returned.
javascript radius | Double values between (0, 250). Units are in meters.| no. Default is 75 (meters) | The radius (in meters) around the requested location in which to constrain the reverse-geocode search. 
javascript limit | Integer values between (1, 10). | no. Default is 1 | The number of results to return in the response. This can be up to 10 results, all of which will be ordered by proximity to the request location.

Result Object
The response shape is identical to responses for Geocode API.  The only difference is that - currently - there is no option to aggregate multiple entrances to the same address in a single response object.  Multiple objects - each of which have a different entrance - can be returned for the same address, the display of which must be handled appropriately.  Additionally, the same building footprint (if requested) will be returned in each response object for which that building polygon is associated with an address.  So if, for example, 123 Main St and 125 Main St share the same building, and both are within the specified search area, and the limit  is set >= 2; the building geometry will  appear in both response objects.

Response Example
```
[{
  "street_address": "3223 Grace St NW",
  "country": "USA",
  "admin_1": "DC",
  "locality": "Washington",
  "response_type": 1,
  "neighborhood": "",
  "entrances": [{
    "lon": -77.063941,
    "entrance_type": "pedestrian-primary",
    "lat": 38.904022
  }],
  "postal_code": "20007"
}]
```