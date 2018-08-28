---
title: "Geocoder"
excerpt: "com.mapfit.android.geocoder.Geocoder"
---
A class for handling geocoding. Geocoding is used to get coordinates for a given address. The Mapfit geocoder is also capable of returning entrances and building polygons if the given address belongs to a building.

```java
class Geocoder
```

Method	|Description
--|--
geocode(address: String, withBuilding: Boolean = false,     callback: GeocoderCallback)|Returns a list of addresses with entrance points. Optionally returns the associated building polygon (where available).
reverseGeocode(latLng: LatLng, withBuilding: Boolean = false,     callback: GeocoderCallback)|Returns a list of addresses with entrance points. Optionally returns the associated building polygon (where available).