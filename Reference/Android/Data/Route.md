---
title: "Route"
excerpt: "com.mapfit.android.directions.model.Route"
---
## Route
### com.mapfit.android.directions.model.Route

Route of a trip from the origin to the destination.
```java
data class Route
```
Constructor	|Description
--|--
Route(trip: Trip, destinationLocation: List<Double>,     sourceLocation: List<Double>, viewport: LatLngBounds)|Route of a trip from the origin to the destination.

Property	|Description
--|--
destinationLocation: List<Double>|The geographical coordinates of the destination location (WGS84).
originLocation: List<Double>|The geographical coordinates of the origin location (WGS84).
trip: Trip|The Trip.
viewport: LatLngBoun|sThe LatLngBounds for the whole route.