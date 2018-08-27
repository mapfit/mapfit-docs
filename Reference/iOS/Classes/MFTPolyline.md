---
title: "MFTPolyline"
excerpt: ""
---
## MFTPolyline
`MFTPolyline`  defines a polyline that appears on the map. A polyline defines a series of connected geographical coordinates in an ordered sequence.

```swift
public class MFTPolyline : NSObject, MFTAnnotation
```

Method	|Description
--|--
addPoint(_ point: CLLocationCoordinate2D)|Adds the input coordinate to the end of the ordered sequence of coordinates defining the polyline.
getLatLngBounds() : LatLngBounds|Returns the MFTLatLngBounds of the polyline outline.
getVisibility(): Boolean|Returns the visibility of the polyline.
remove()|Remove the polyline from all map instances.
setVisibility(visible: Boolean)|Set the visibility of the polyline.

Property	|Description
--|--
uuid: UUID|The unique identifier for the polyline.
points: [CLLocationCoordinate2D]|The array of geographical coordinate points which define the polyline.