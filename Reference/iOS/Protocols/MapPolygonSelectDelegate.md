---
title: "MapPolygonSelectDelegate"
excerpt: ""
---
## MapPolygonSelectDelegate
```swift
public protocol MapPolygonSelectDelegate : class
```
Method	|Description
--|--
mapView(_ view: MFTMapView, didSelectPolygon polygon: MFTPolygon, atScreenPosition position: CGPoint)|Informs the delegate a polygon on the map wasjust selected.

Parameter	|Description
--|--
controller|The MFTMapView that recognized the selection.
polygon|The polygon that was selected.
atScreenPosition|The screen coordinates of the picked feature.