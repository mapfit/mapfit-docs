---
title: "Route"
excerpt: ""
---
## Route
Route of a trip from the origin to the destination.

```
public struct RouteObject : Decodable
```

Property	|Description
--|--
destinationLocation: [Double]|The geographical coordinates of the destination location (WGS84).
sourceLocation: [Double]|The geographical coordinates of the origin location (WGS84).
trip: Trip|The Trip.