---
title: "MFTLayer"
excerpt: ""
---
## MFTLayer
`MFTLayer` is a layer class, which can be used to group [MFTAnnotation](ref:mftannotation)s. 

```swift 
public class MFTLayer
```
Method	|Description
--|--
add(annotation: [MFTAnnotation](ref:mftannotation))|Adds the input MFTAnnotation to the layer.
clear()|Removes every MFTAnnotation from the layer and any map the layer has been added to.
getAnnotations(): [MFTAnnotation]|Returns all MFTAnnotations added to the layer.
getLatLngBounds()|Returns the MFTLatLngBounds of the layer, based on the fitted bounds of the added annotations.
getVisibility() : Boolean|Returns the visibility of the layer.
remove(annotation:[Annotation])|Removes the input MFTAnnotation from the layer.
setVisibility(show: Bool)|Will hide or show the layer, based on the boolean input value. A layer is shown by default.