---
title: "Marker"
excerpt: "com.mapfit.android.annotations.Marker"
---
## Marker
### com.mapfit.android.annotations.Marker

Markers are icons placed on a particular location on the map.

```java
class Marker : Annotation
```
Method	|Description
--|--
getLatLngBounds(): LatLngBounds|Returns the bounding coordinates for the marker.
remove()|Removes the marker from every Layer and MapView it is added to.
setIcon(drawable: Drawable)|Sets the marker icon with the given drawable.
setIcon(drawableId: Int)|Sets the marker icon with the given drawable resource id.
setIcon(mapfitMarker: MapfitMarker)|Sets the marker icon with the given MapfitMarker.
setIcon(imageUrl: String)|Sets the marker icon with the given image URL.
setIcon(bitmap: Bitmap)|Sets the marker icon with the given bitmap object.
setSize(width: Int, height: Int)|Sets the width and height of the marker icon in pixels.
setPositionEased(latLng: LatLng, duration: Int, easeType: MapController.EaseType)|Sets marker position with animation.

Property	|Description
--|--
height: Int|The height of the marker icon in pixels.
buildingPolygon: Polygon|Represents the building Polygon when the marker is added with an address.
drawOrder: Int|The draw order index of the marker.
width: Int|The width of the marker icon in pixels.
flat: Int|The enabled/disabled state of flat marker icon drawing.
anchor: Anchor|Anchor for the marker icon.
interactive: Boolean|Defines if the marker is interactive or not. If set to false, the Marker will not be clickable.
position: LatLng|The geographical coordinate position of the Marker
title: String|The title of the marker to be shown on the PlaceInfo window.
subtitle1: String|The first subtitle of the marker to be shown on the PlaceInfo window.
subtitle2: String|The second subtitle of the marker to be shown on the PlaceInfo window.
streetAddress: String|The streed address of the Marker .
address: Address|The Address represents the marker position. The value is not null if the Marker is added trough Geocoding.
data: Any|The given object related with the Marker. Setting related object of marker as a data makes it easier to reach the object rather than storing a Map data structure.