---
title: "MapPanGestureDelegate"
excerpt: ""
---
## MapPanGestureDelegate
```swift
public protocol MapPanGestureDelegate : class```

Method	|Description
--|--
mapView(_ view: MFTMapView, didPanMap displacement: CGPoint)|Informs the delegate the map just panned.

Parameter	|Description
--|--
controller|The MFTMapView that recognized the pan.
displacement|The distance in pixels that the screen was moved by the gesture.