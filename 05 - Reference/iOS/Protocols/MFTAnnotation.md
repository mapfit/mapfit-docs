---
title: "MFTAnnotation"
excerpt: ""
---
## MFTAnnotation
`MFTAnnotation` is the base protocol for polylines, polygons and markers.

```swift
public protocol MFTAnnotation
```
Property	|Description
--|--
isVisible|Visibility of the annotation. Can only be changed by calling ‘setVisibility(show: Bool)’.
uuid|Unique Identifier for the annotation.

Method	|Description
--|--
setVisibility(show: Bool)|Sets visibility of the annotation.