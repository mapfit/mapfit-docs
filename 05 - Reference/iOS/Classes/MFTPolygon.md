---
title: "MFTPolygon"
excerpt: ""
---
## MFTPolygon
`MFTPolygon`  defines a polygon that appears on the map. A polygon defines a series of connected geographical coordinates in an ordered sequence, forming a closed loop and defining a filled region.

```swift
public class MFTPolygon : NSObject, MFTAnnotation
```

Method	|Description
--|--
getLatLngBounds() : LatLngBounds|Returns the MFTLatLngBounds of the polygon outline.
getVisibility(): Boolean|Returns the visibility of the polygon.
remove()|Removes the polygon from all map instances.
setVisibility(visible: Boolean)|Set the visibility of the polygon.

Property	|Description
--|--
id: UUID|The unique identifier for the polygon.
points: [CLLocationCoordinate2D]|The array of geographical coordinate points which define the polygon.