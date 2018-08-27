---
title: "Summary"
excerpt: ""
---
## Summary
Provides a summary of the trip, including total distance, travel time, and bounding coordinates of the route polyline.

```swift
public struct Summary : Decodable
```
Property	|Description
--|--
length: Double|Distance traveled for the entire Trip. Units are in miles.
maxLat: Double|Maximum latitude of a bounding box containing the Route.
maxLon: Double|Maximum longitude of a bounding box containing the Route.
minLat: Double|Minimum latitude of a bounding box containing the Route.
minLon: Double|Minimum longitude of the bounding box containing the Route.
time: Int|Estimated elapsed time to complete the Trip.
