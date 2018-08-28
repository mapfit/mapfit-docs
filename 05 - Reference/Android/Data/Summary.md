---
title: "Summary"
excerpt: "com.mapfit.android.directions.model.Summary"
---
## Summary
### com.mapfit.android.directions.model.Summary
Provides a summary of the trip, including total distance, travel time, and bounding coordinates of the route polyline.

```java
data class Summary
```

Constructor	|Description
--|--
Summary(min_lon: Double, max_lat: Double, max_lon: Double,     length: Double, time: Int, min_lat: Double)|Provides a summary of the trip, including total distance, travel time, and bounding coordinates of the route polyline.

Property	|Description
--|--
length: Double|Distance traveled for the entire Trip. Units are in miles.
maxLat: Double|Maximum latitude of a bounding box containing the Route.
maxLon: Double|Maximum longitude of a bounding box containing the Route.
minLat: Double|Minimum latitude of a bounding box containing the Route.
minLon: Double|Minimum longitude of the bounding box containing the Route.
time: Int|Estimated elapsed time to complete the Trip.