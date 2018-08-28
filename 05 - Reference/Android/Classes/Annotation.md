---
title: "Annotation"
excerpt: "com.mapfit.android.annotations.Annotation"
---
## Annotation
### com.mapfit.android.annotations.Annotation
Base class for [Marker](ref:marker-1), [Polyline](ref:polyline) and [Polygon](ref:polygon-1).

```java
abstract class Annotation
```
Constructor	|Description
--|--
Annotation(id: Long, mapController: MapController)|Base class for Marker, Polyline and Polygon.

Method	|Description
--|--
getLatLngBounds(): LatLngBounds|Returns the bounding coordinates for the annotation.
remove()|Remove the annotation from all map and layer instances.

Property	|Description
--|--
id: Long|Annotation's unique identifier.
visibility: Boolean|The visibility of the annotation.
data: Any|An object related to the Annotation. Setting a related object of the annotation as it's data makes iteasier to reach the object rather than storing a Map data structure.