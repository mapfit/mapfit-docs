---
title: "MapSingleTapGestureDelegate"
excerpt: ""
---
## MapSingleTapGestureDelegate
```swift
public protocol MapSingleTapGestureDelegate : class
```
Method	|Description
--|--
mapView(_ view: MFTMapView, recognizer: UIGestureRecognizer, shouldRecognizeSingleTapGesture location: CGPoint): Bool|Asks the delegate if the mapshould recognize this single tap and perform default functionality (which is nothing, currently). Return true for default functionality or false for unrecognized (or if you plan on handling it yourself).
mapView(_ view: MFTMapView, recognizer: UIGestureRecognizer, didRecognizeSingleTapGesture location: CGPoint)|Informs the delegate the map recognized asingle tap gesture.

Parameter	|Description
--|--
controller|The MFTMapView that recognizes the tap.
recognizer|The recognizer that initially recognized the tap.
location|The screen coordinates that the tap occured in relative to the bounds of the map.