---
title: "Building"
excerpt: ""
---
## Building
Data class representing the Building polygon and the polygon type.
```swift
public struct Building: Decodable
```

Property	|Description
--|--
polygon: List<List<LatLng>>|Represents the building polygon(s).
type: String|Type of the polygon. This can be Polygon or MultiPolygon.