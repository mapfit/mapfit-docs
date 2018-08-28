---
title: "MarkerOptions"
excerpt: "com.mapfit.android.annnotations.MarkerOptions"
---
## MarkerOptions
### com.mapfit.android.annnotations.MarkerOptions

Defines options for [Marker](ref:marker-1) .
```java
class MarkerOptions
```

Method	|Description
--|--
drawOrder(drawdrawOrder: Int): MarkerOptions|Sets the draw order index of the marker.
height(height: Int): MarkerOptions|Sets the height of the marker icon in pixels.
width(width: Int): MarkerOptions|Sets the width of the marker icon in pixels.
flat(flat: Boolean): MarkerOptions|Sets the enabled/disabled state of flat marker icon drawing.
anchor(anchor: Anchor): MarkerOptions|Sets the Anchor for the marker icon.
streetAddress(address: String, geocode: Boolean = false): MarkerOptions|Sets the street address of the marker. Optionally, this address can be geocoded and placed accordingly to the geocoded position.
position(position: String, reverseGeocode: Boolean = false): MarkerOptions): MarkerOptions|Sets the position. Optionally, this position can be reverse geocoded and placed accordingly to the geocoded position.
data(data: Any): MarkerOptions|Sets the given related Object of the Marker . Setting a related object of the marker as it's data makes easier to reach the object rather than storing a Map data structure.
addBuildingPolygon(buildingPolygon: Boolean, options: PolygonOptions): MarkerOptions|Adds building polygon for the Marker position or address if applicable. Setting Polygon true forces geocoding the address or reverse geocoding the position.
interactive(interactive: Boolean): MarkerOptions|Sets if the marker will be interactive or not. Non-interactive markers are not clickable won't be accessible trough the click listeners.
visible(visible: Boolean): MarkerOptions|Sets if marker is visible or invisible.
drawOrder(drawOrder: Int): MarkerOptions|Sets the marker's drawing order. The marker with higher draw order will be drawn the ones have lesser draw order.
title(title: String): MarkerOptions|The title of the marker to be shown on the PlaceInfo window.. If the title is empty, place info won't be shown.
subtitle1(subtitle: String): MarkerOptions|The first subtitle of the marker to be shown on the PlaceInfo window.
subtitle2(subtitle: String): MarkerOptions|The second subtitle of the marker to be shown on the PlaceInfo window.
setIcon(drawable: Drawable): MarkerOptions|Sets the marker icon with the given drawable.
setIcon(drawableId: Int): MarkerOptions|Sets the marker icon with the given drawable resource id.
setIcon(mapfitMarker: MapfitMarker): MarkerOptions|Sets the marker icon with the given MapfitMarker.
setIcon(imageUrl: String: MarkerOptions)|Sets the marker icon with the given image URL.
setIcon(bitmap: Bitmap): MarkerOptions|Sets the marker icon with the given bitmap object.