---
title: "PolylineOptions"
excerpt: "com.mapfit.android.annotations.PolylineOptions"
---
## PolylineOptions
### com.mapfit.android.annotations.PolylineOptions

Defines options for [Polyline](ref:polyline). See [PolyPointAnnotationOptions](ref:polypointannotationoptions) for base options.

```java
 class PolylineOptions : PolyPointAnnotationOptions
 ```

Methiod	|Description
--|--
points(points: List<LatLng>): PolylineOptions|Sets the points of the polyline.
lineCapType(capType: CapType): PolylineOptions|Sets the CapType for the end of the lines.
<T : PolylineAnimation> animation(animation: T): PolylineOptions|Sets the animation for the polyline.