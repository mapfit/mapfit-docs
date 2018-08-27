---
title: "MapLongPressGestureDelegate"
excerpt: ""
---
## MapLongPressGestureDelegate
```swift
public protocol MapLongPressGestureDelegate : class
```
Method	|Description
--|--
mapView(_ view: MFTMapView, recognizer: UIGestureRecognizer, shouldRecognizeLongPressGesture location: CGPoint): Bool|Asks the delegate if the mapshould recognize this long press and perform default functionality (which is nothing, currently). Return true for default functionality or false for unrecognized (or if you plan on handling it yourself).
mapView(_ view: MFTMapView, recognizer: UIGestureRecognizer, didRecognizeLongPressGesture location: CGPoint)|Informs the delegate the map recognized along press gesture.

Parameter	|Description
--|--
controller|The MFTMapView that recognizes the long press.
recognizer|The recognizer that initially recognized the long press.
location|The screen coordinates that the long press occured in, relative to the bounds of the map.