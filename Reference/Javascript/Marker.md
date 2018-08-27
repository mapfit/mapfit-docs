---
title: "Marker"
excerpt: "mapfit.Marker"
---

# Marker
### mapfit.Marker

Constructor	|Description
--|--
mapfi|.Marker(?latLng: LatLng)Construct marker object with an optional input geographical coordinate point.
Example
```myMarker = mapfit.Marker([40.745934, -73.988280])```
Method	|Description
--|--
getPlaceInfo(): PlaceInfo|Returns the PlaceInfo object associated with the marker.
getIconUrl(): String|Returns the image URL of the marker icon.
getMarkerOptions(): Object[]|Returns marker options as a JSON object. See properties table below.
getPosition(): LatLng|Get the geographical coordinate position of the marker if you created the marker with lat long coordinates. Return a Promise to get the geographical coordinate position of the marker if you created the marker with an address or directly using the Geocoder. For details, see: https://javascript.mapfit.com/v2.3/docs/markers#section-setting-the-map-center-on-a-geocoded-marker
getPlaceInfoVisibility(): Boolean|Returns the visibility of the place info window on the marker.
setIcon(url: MarkerIcon)|Sets the marker icon with the given image URL.
setPlaceInfo(placeinfo: PlaceInfo)|Binds the input PlaceInfo to the marker.
setPosition(latlng: LatLng)|Set the geographical coordinate position of the marker.
setMarkerOptions(options: Object[])|Set the marker options. See properties table below.
setPlaceInfoVisibility(bool: Boolean)|Open/Close PlaceInfo window.

Marker Options

Property	|Description
--|--
icon: Icon|The marker's associated Icon object.
placeInfo: PlaceInfo|The marker's associated PlaceInfo object.
position: LatLng|The marker's associated LatLng.
address: String|The marker's address, which can be used in positioning the marker.