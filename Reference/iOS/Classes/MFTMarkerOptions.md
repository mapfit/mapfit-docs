---
title: "MFTMarkerOptions"
excerpt: ""
---
## MFTMarkerOptions
`MFTMarkerOptions` defines options for a marker.

```swift
public class MFTMarkerOptions : NSObject
```
Method	|Description
--|--
setPosition(position: CLLocationCoordinate2D, reverseGeocode: Bool)|Sets the position for the marker. If reverse geocode is set to true and a validAPI key is stored in the MFTManager, the marker will be utilize the mapfit reverse geocoder API and assign a street address and override the given position.
setFlat(_ flat: Bool)|Sets whether the marker will be flat when the map view is tilted.
setTag(_ tag: Any)|Sets the tag for the marker.
addBuildingPolygon(_ building: Bool, options: MFTPolygonOptions)|If the address returns a building polygon and building is set to true, thisfunction will utilize the MFTPolygonOptions given to style a building polygon upon creation of the marker.
setInteractivity(_ interactive: Bool)|Sets whether the marker is interactive.
setVisibility(_ visible: Bool)|Sets the visibility of the marker.
setStreetAddress(streetAddress: String, geocode: Bool)|Sets the street address for the marker. If geocode is set to true and a valid API is storedin the MFTManager, the mapfit geocoder API will be used to assign a position to the marker.
setDrawOrder(drawOrder: Int)|Sets the draw order index of the marker.
setTitle(_ title: String)|Sets the title for the place info card
setSubTitle1(_ subTitle1: String)|Sets the first subtitle for the place info card
setSubTitle2(_ subTitle2: String)|Sets the second subtitle for the place info card.
setIcon(_ mapfitMarker: MFTMarkerImage)|Sets the marker icon image using a default mapfit marker.
setIcon(_ urlString: String)|Sets the marker icon image from a external or local URL.
setIcon(_ image: UIImage)|Sets the marker icon image using a local asset.
 setAnchorPosition(_ position: MFTAnchorPosition)|Sets the anchor position of the marker.
setHeight(height: Int)|Sets the height for the marker icon in pixels.
setWidth(width: Int)|Sets the width for the marker icon in pixels.