---
title: "MFTMapView"
excerpt: ""
---
## MFTMapView
`MFTMapView` is the main class of the Mapfit SDK for iOS and is the entry point for methods related to the map.

```swift
open class MFTMapView: UIView
```

Method	|Description
--|--
addLayer(layer: MFTLayer)|Add the specified input MFTLayer to the map. All annotations in the layer will be added to the map.
addMarker(position: CLLocationCoordinate2D)|Adds the marker to the map at the input coordinate position. Returns MFTMarker for styling and placeinfo customization.
addMarker(address: String, completion:@escaping ( marker: MFTMarker?, errror: Error?)->Void)|Adds the marker to the map at the coordinate positionreturned by geocoding the input address. Returns MFTMarker for styling and place info customization.
addPolygon(polygon: List<List>): MFTPolygon|Adds the polygon to the map. Returns theMFTPolygon for styling.
addPolyline(line: List<LatLng>): MFTPolyline|Adds the polyline to the map. Returns MFTPolyline for styling.
getCenter(): CLLocationCoordinate2D|Returns the center coordinates of the map.
getLatLngBounds(): MFTLatLngBounds|Returns the bounding coordinates, MFTLatLngBounds, for the map.
getLayers(): [MFTLayer]|Returns the MFTLayers added to the map.
getRotation(): Float|Returns the current rotation of the map.
getTilt(): Float|Returns the current tilt level of the map.
getZoom() : UInt|Returns the current zoom level of the map.
reCenter() : Unit|Map will be re-centered to the last position set as center with the setCenter method.
removeLayer(layer: MFTLayer)|Removes the specified input layer from the map.
removeMarker(marker: Marker )|Removes the marker from the map.
removePolygon(polygon: Polygon )|Removes the polygon from the map.
removePolyline(polyline: Polyline )|Removes the polyline from the map.
setLatLngBounds(bounds: MFTLatLngBounds, padding: Float)|Sets the map bounds using the MFTLatLngBounds - the southwest and northeast corners of thebounding box.
setLatLngBounds(bounds: MFTLatLngBounds, padding: Float, duration: Float)|Sets the map bounds with animation duration using the MFTLatLngBounds -the southwest and northeast corners of the bounding box.
setCenter(position: CLLocationCoordinate2D)|Sets the map center to the input coordinate values.
setCenter(position: CLLocationCoordinate2D, duration: Float)|Sets the map center to the input coordinate values and the duration of the enteringanimation
setCenterWithLayer(layer : Layer )|Sets the map center to the center of the input layer's MFTLatLngBounds.
setCenterWithOffset(latLng: CLLocationCoordinate2D, offsetX: Int, offsetY: Int, duration: Float)|Sets the center coordinate of the path using anoffset.
setPlaceInfoAdapter(adapter: MFTPlaceInfoAdapter)|Sets MFTPlaceInfoAdapter, enabling customization of the place info view, which is displayed when amarker is tapped.
setRotation(rotationLevel: Float)|Sets the current rotation level of the map.
setRotation(rotationLevel: Float, duration: Float)|Sets the current rotation level of the map and the duration of the rotation animation.
setTilt(zoomLevel: Float)|Sets the current tilt level of the map.
setTilt(tiltLevel: Float, duration: Float)|Sets the current tilt level of the map and the duration of the tilt animation.
setZoom(zoomLevel: UInt)|Sets the current zoom level of the map.
setZoom(zoomLevel: UInt, duration: Float)|Sets the current zoom level of the map and the duration of the zoom animation.
screenPositionToLatLng(_ point: CGPoint)|Returns a CLLocationCoordinate based on the point provided.
latLngToScreenPosition(_ latLng: CLLocationCoordinate2D)|Returns a point based on the CLLocationCoordinate provided.