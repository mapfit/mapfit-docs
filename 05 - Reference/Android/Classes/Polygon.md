---
title: "Polygon"
excerpt: "com.mapfit.android.annotations.Polygon"
---
## Polygon
### com.mapfit.android.annotations.Polygon

`Polygon`  defines a polygon that appears on the map. Polygon is a closed Polyline where the end point and start point are equal. The polygon consists of an ordered sequence of coordinate points.

```java
class Polygon : Annotation
```
Constructor	|Description
--|--
Polygon(context: Context, polygonId: Long, mapController: |    MapController, polygon: MutableList<List<LatLng>>)

Method	|Description
--|--
getLatLngBounds(): LatLngBounds|Returns the LatLngBounds of the polygon outline.
remove()|Removes the polygon from all map instances.

Property	|Description
--|--
points: MutableList<List<LatLng>>|The array of geographical coordinate points which define the polygon.
fillColor: String|Sets the fill color of the polygon.
strokeWidth: Int|Sets stroke width of the line.
strokeColor: String|Sets stroke color of the line.
strokeOutlineColor: String|Sets stroke outline color of the line.
strokeOutlineWidth: Int|Sets stroke outline width of the line.
lineJoinType: JoinType|Sets the JoinType of the joints in multi-segment lines.
drawOrder: Int|Sets the drawing order.

