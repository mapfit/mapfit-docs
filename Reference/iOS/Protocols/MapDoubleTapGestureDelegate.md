---
title: "MapDoubleTapGestureDelegate"
excerpt: ""
---
## MapDoubleTapGestureDelegate
```swift
public protocol MapDoubleTapGestureDelegate : class
```
Method	|Description
--|--
mapView(_ view: MFTMapView, recognizer: UIGestureRecognizer,    shouldRecognizeDoubleTapGesture location: CGPoint): Bool|Asks the delegate if the mapshould recognize this double tap and perform default functionality (which is nothing, currently). Return true for default functionality or false for unrecognized (or if you plan on handling it yourself).
mapView(_ view: MFTMapView, recognizer: UIGestureRecognizer,    didRecognizeDoubleTapGesture location: CGPoint)|Informs the delegate the maprecognized a double tap gesture.

Parameter	|Description
--|--
controller|The MFTMapView that recognizes the tap.
recognizer|The recognizer that initially recognized the tap.
location|The screen coordinates that the tap occured in relative to the bounds of the map.