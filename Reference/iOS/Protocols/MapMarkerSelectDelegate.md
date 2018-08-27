---
title: "MapMarkerSelectDelegate"
excerpt: ""
---
## MapMarkerSelectDelegate
```swift
public protocol MapMarkerSelectDelegate : class
```
Method	|Description
--|--
mapView(_ view: MFTMapView, didSelectFeature feature: [String : String],    atScreenPosition position: CGPoint)|Informs the delegate a marker of themap was just selected.

Parameter	|Description
--|--
controller|The MFTMapView that recognized the selection.
markerPickResult|A marker selection returned as an instance conforming to GenericMarker.
atScreenPosition|The screen coordinates of the picked marker.