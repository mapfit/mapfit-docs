---
title: "MapPinchGestureDelegate"
excerpt: ""
---
```swift
public protocol MapPinchGestureDelegate : class
```

Method	|Description
--|--
mapView(_ view: MFTMapView, didPinchMap location: CGPoint)|Informs the delegate the map just zoomed via a pinch gesture.

Parameter	|Description
--|--
controller|The MFTMapView that recognized the pinch.
location|The screen coordinate the map was pinched at.