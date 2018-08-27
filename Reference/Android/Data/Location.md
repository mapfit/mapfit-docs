---
title: "Location"
excerpt: "com.mapfit.android.directions.model.Location"
---
## Location
### com.mapfit.android.directions.model.Location
A data class representing the origin and destination locations.

```java
data class Location
```

Constructor	|Description
--|--
Location(lon: Double, sideOfStreet: String, type: String, lat: Double)|A JSON object representing the origin and destination locations.

Property	|Description
--|--
lat: Double|The latitude (WGS84).
lon: Double|The longitude (WGS84).
sideOfStreet: String|The side of street of a break location that is determined based on the actual route when the location is offset from the street. The possible values are left and right.
type: String|Type of location, always returned as break - indicating a stop.