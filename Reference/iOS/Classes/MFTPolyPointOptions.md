---
title: "MFTPolyPointOptions"
excerpt: ""
---
## MFTPolyPointOptions
`MFTPolyPointOptions` defines options for [MFTPolygon](ref:mftpolygon) and [MFTPolyline](ref:mftpolyline) .

```swift
public protocol MFTPolyPointOptions
```
Function	|Description
--|--
setDrawOrder(_ order: Int)|The draw order index of the annotation.
setStrokeWidth(_ width: Int)|The width of the stroke in pixels.
setOutlineWidth(_ width: Int)|The width of the outline in pixels.
setStrokeColor(_ color: String)|The color of the stroke in hex color code.
setStrokeOutlineColor(_ color: String)|The color of the outline in hex color code.
setLineCapType(_ type: MFTLineCapType)|The shape of the end of the polylines.
setLineJoinType(_ type: MFTLineJoinType)|The shape of intersection between two lines.
addPoints(_ points:[[CLLocationCoordinate2D]])|Adds points to be drawn.