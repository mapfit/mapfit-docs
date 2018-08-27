---
title: "MFTMarker"
excerpt: ""
---
## MFTMarker
`MFTMarker` is the class for creating and controlling markers. Inherits from [MFTAnnotation](ref:mftannotation).

```swift
public class MFTMarker : NSObject, [MFTAnnotation](ref:mftannotation) 
```
Method	|Description
--|--
getPosition() : CLLocationCoordinate2D|Get the geographical coordinate position of the marker.
getVisibility() : Bool|Return the visibility of the marker.
setIcon(_ mapfitMarker: MFTMarkerImage)|Sets the marker icon with the given Marker.
setIcon(_ urlString: String)|Sets the marker icon with the given image URL.
setIcon(_ image: UIImage)|Sets the marker icon with the given image.
setPosition(_ position: CLLocationCoordinate2D)|Sets the geographical coordinate position of the marker.
setVisibility(show: Bool)|Sets the visibility of the marker.

Property	|Description
--|--
icon: UIImage?|Icon of the marker. Can only be changed by calling one of the setIcon methods.
isVisible: Bool|Visibility of the marker. Can be changed by calling the setVisibility method on the Marker itself or the Layer holding the Marker.
markerOptions: MarkerOptions?|The options available on MFTMarker .
position: CLLocationCoordinate2D|Position of marker. Can only be changed by calling setPosition(position: CLLocationCoordinate2D).
subtitle1: String|The first subtitle displayed on the Place Info window.
subtitle2: String|The second subtitle displayed on the Place Info window.
title: String|The title displayed on the Place Info window.
uuid: UUID|The marker's unique identifier.