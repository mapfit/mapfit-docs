---
title: "MapShoveGestureDelegate"
excerpt: ""
---
## MapShoveGestureDelegate
```swift
public protocol MapShoveGestureDelegate : class
```

Method	|Description
--|--
mapView(_ view: MFTMapView, didShoveMap displacement: CGPoint)|Informs the delegate the map just shoved.

Parameter	|Description
--|--
controller|The MFTMapView that recognized the shove.
displacement|The distance in pixels that the screen was moved by the gesture.