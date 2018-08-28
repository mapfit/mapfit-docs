---
title: "Polyline"
excerpt: "com.mapfit.android.annotations.Polyline"
---
## Polyline
### com.mapfit.android.annotations.Polyline

`Polyline`  defines a polyline that appears on the map. A polyline defines a series of connected geographical coordinates in an ordered sequence.

```java
class Polyline : Annotation
```
Constructor	|Description
--|--
Polyline(context: Context, polylineId: Long,     mapController: MapController, line: MutableList<LatLng>)|Polyline is an ordered sequence of coordinate points that can be drawn as a line.

Method	|Description
--|--
getLatLngBounds(): LatLngBounds|Returns the LatLngBounds of the polyline.
remove()|Removes the polyline from all map instances.

Property	|Description
--|--
points: MutableList<List<LatLng>>|The array of geographical coordinate points which define the polyline.
strokeWidth: Int|Sets stroke width of the line.
strokeColor: String|Sets stroke color of the line in the format #AARRGGBB where AA is alpha and optional.
strokeOutlineColor: String|Sets stroke outline color of the line in the format #AARRGGBB where AA is alpha and optional.
strokeOutlineWidth: Int|Sets stroke outline width of the line.
lineCapType: CapType|Sets the CapType for the end of the lines.
lineJoinType: JoinType|Sets the JoinType of the joints in multi-segment lines
drawOrder: Int|Sets the drawing order.