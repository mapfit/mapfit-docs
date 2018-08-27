---
title: "Building"
excerpt: "com.mapfit.android.geocoder.model.Building"
---
## Building
### com.mapfit.android.geocoder.model.Building
Data class representing the Building polygon and the polygon type.
```java
data class Building
```
Property	|Description
--|--
polygon: List<List<LatLng>>|Represents the building polygon(s).
type: String|Type of the polygon. This can be Polygon or MultiPolygon.