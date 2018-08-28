---
title: "MapPolylineSelectDelegate"
excerpt: ""
---
## MapPolylineSelectDelegate
```swift
public protocol MapPolylineSelectDelegate : class
```
Method	|Description
--|--
mapView(_ view: MFTMapView, didSelectPolygon polyline: MFTPolyline, atScreenPosition position: CGPoint)|Informs the delegate a polyline on the map wasjust selected.

Parameter	|Description
--|--
controller|The MFTMapView that recognized the selection.
polyline|The polyline that was selected.
atScreenPosition|The screen coordinates of the picked feature.