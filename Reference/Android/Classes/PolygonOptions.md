---
title: "PolygonOptions"
excerpt: "com.mapfit.android.annotations.PolygonOptions"
---
## PolygonOptions
### com.mapfit.android.annotations.PolygonOptions
Defines options for [Polygon](ref:polygon-1).See [PolyPointAnnotationOptions](ref:polypointannotationoptions) for base options.
```java
class PolygonOptions : PolyPointAnnotationOptions<PolygonOptions>
```

Method	|Description
--|--
points(points: List<List<LatLng>>): PolygonOptions|Sets the points of the polygon.
fillColor(color: String): PolygonOptions|Sets the fill color of the polygon in the format #AARRGGBB where AA is alpha and optional.