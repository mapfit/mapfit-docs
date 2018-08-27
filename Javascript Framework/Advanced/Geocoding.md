---
title: "Geocoding"
excerpt: ""
---
**Geocode**

For most use cases, geocoding can be done through the [Marker](ref:marker) class by setting the `address` property; this will allow your markers to be geocoded within the map view.  For more advanced use cases that require extracting particular data elements from the geocoder response, interacting with the [Geocoder](ref:geocoderapi) may be necessary.

 Note: a typical call is done with HTTP GET, but a POST request with up to 50 objects is possible. See [Geocoder](ref:geocoderapi) for more detail.

```javascript   
 let geo = new mapfit.Geocoder("{{MY_API_KEY}}", "https://api.mapfit.com/v2");
    geo.geocode(address="119 w 24th st, new york, ny", includeBuilding= true)
      .then(data => (console.log("geocode=", data)))
      .catch(error => (console.log(" error = ", error)))
```

The response should look like the following:
```javascript 
[{
"street_address": "119 W 24th St",
"country": "USA",
"admin_1": "NY",
"locality": "New York",
"response_type": 1,
"neighborhood": "",
"entrances": [{
  "lon": -73.99324,
  "entrance_type": "pedestrian-primary",
  "lat": 40.74405
}],
"postal_code": "10011",
"building": {
  "coordinates": [[
    [
      -73.992954,
      40.744257
    ],
    [
      -73.993136,
      40.744006
    ],
    [
      -73.993448,
      40.744138
    ],
    [
      -73.993294,
      40.744349
    ],
    [
      -73.993133,
      40.744281
    ],
    [
      -73.993104,
      40.744321
    ],
    [
      -73.992954,
      40.744257
    ]
  ]],
  "type": "Polygon"
}
}]
```

**Reverse Geocode**

This API accepts a lat, lon and returns a response containing the closest Mapfit address entrance to the specified geolocation, with the exact same response shape returned by the Geocode API.  Different entrances to an address are returned separately.

```javascript   
 let geo = new mapfit.Geocoder("{{MY_API_KEY}}", "https://api.mapfit.com/v2");
    geo.reverseGeocode(latlng=[38.904081,-77.063786], building = true, radius = 75, limit = 1)
      .then(data => (console.log("reverseGeocode=", data)))
      .catch(error => (console.log(" error = ", error)))
```

The response should look like the following:
```javascript 
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
}] ```