---
title: "PolyPointAnnotationOptions"
excerpt: "com.mapfit.android.annotations.PolyPointAnnotationOptions"
---
## PolyPointAnnotationOptions
### com.mapfit.android.annotations.PolyPointAnnotationOptions

Base abstract class for composing styling of poly point shapes e.g. [Polyline](ref:polyline), [Polygon](ref:polygon-1).

```java
abstract class PolyPointAnnotationOptions
 ``` 
Property	Description
|layerName: String
--|--
Defines layer styl| name for the poly shape.

Method	|Description
--|--
strokeWidth(width: Int): T|Sets the width of the line in pixels.
strokeColor(color: String): T|Sets the color of the line in the format #AARRGGBB where AA is optional.
strokeOutlineColor(color: String): T|Sets the color of the line outline in the format #AARRGGBB where AA is optional. You must set strokeOutlineWidth, to see it.
strokeOutlineWidth(width: Int): T|Sets the width of the line outline in pixels.
lineJoinType(joinType: JoinType): T|Sets the shape type for the end of the lines.See CapType.
drawOrder(drawOrder: Int): T|Sets the shape type of the joints in multi-segment lines. See JoinType.
data(data: Any): T|Sets the given object related to the poly shape. Setting a related object of the poly shape as it's data makes iteasier to reach the object rather than storing a Map data structure.
layerName(layerName: String): T|Sets the poly shape style with the style name that should existing in the YAML file.
