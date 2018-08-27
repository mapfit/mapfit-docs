---
title: "MapfitMap"
excerpt: "com.mapfit.android.MapfitMap"
---
## MapfitMap
## com.mapfit.android.MapfitMap

Controller for the map.
```java
abstract class MapfitMap
```

Method	|Description
--|--
addLayer(layer: Layer)|Add the specified input Layer to the map. All annotations in the layer will be added to the map.
addMarker(latLng: LatLng): Marker|Adds the Marker to the map at the input coordinate position. Returns marker for styling and place info customization.
addMarker(address: String, withBuilding: Boolean = true, onMarkerAddedCallback: OnMarkerAddedCallback)|Adds the Marker to the map at the coordinate position returned by geocoding the input address. Returns marker for styling and place info customization.
addPolygon(polygon: List<List<LatLng>>): Polygon|Removes the Polygon from the MapView.
addPolyline(line: List<LatLng>): Polyline|Adds the Polyline to the MapView. Returns polyline for styling.
getCenter(): LatLng|Returns the center coordinates of the MapView.
getDirectionsOptions(): DirectionsOptions|Returns DirectionsOptions to interact with Directions to drawing directions.
getLatLngBounds(): LatLngBounds|Returns the bounding coordinates for the MapView.
getLayers(): List<Layer>|Returns the list of layers bound to the MapView.
getMapOptions(): MapOptions|MapOptions can be used to change options for the map. For instance, setting maximum zoom level or turning zoom controls off.
getRotation(): Float|Returns the current rotation of the MapView.
getTilt(): Float|Returns the current tilt level of the MapView.
getZoom(): Float|Returns the current zoom level of the MapView.
reCenter()|Map will be re-centered to the last position it was centered.
removeLayer(layer: Layer)|Removes given Layer from the MapView.
removeMarker(marker: Marker)|Removes given Marker from the MapView.
removePolygon(polygon: Polygon)|Removes given Polygon from the MapView.
removePolyline(polyline: Polyline)|Removes given Polyline from the MapView.
setCenter(latLng: LatLng, duration: Long = 0, easeType: MapController.EaseType)|Sets the map center to the given LatLng values and the duration of the centering animation.
setCenterWithLayer(layer: Layer)|Sets the map center to the input layer's coordinate values.
setCenterWithOffset(latLng: LatLng, offsetX: Float = 0, offsetY: Float = 0, duration: Long = 0, easeType: MapController.EaseType)|Sets the map center to the given LatLng with optional horizontal and vertical offsets and duration.
setLatLngBounds(bounds: LatLngBounds, padding: Float = 0f, duration: Long = 0, easeType: MapController.EaseType)|Sets the map bounds using the LatLngBounds - the southwest and northeast corners of the bounding box.
setOnMapClickListener(listener: OnMapClickListener)|Sets OnMapClickListener for MapView that single click events will be passed to.
setOnMapDoubleClickListener(listener: OnMapDoubleClickListener)|Sets OnMapDoubleClickListener for MapView that double click events will be passed to.
setOnMapLongClickListener(listener: OnMapLongClickListener)|Sets [OnMapLongClickListener for MapView that long click events will be passed to.
setOnMapPanListener(listener: OnMapPanListener)|Sets OnMapPanListener for MapView that pan events will be passed to.
setOnMapPinchListener(listener: OnMapPinchListener)|Sets OnMapPinchListener for MapView that pinch events will be passed to.
setOnMarkerClickListener(listener: OnMarkerClickListener)|Sets OnMarkerClickListener for MapView that marker click events will be passed to.
setOnPlaceInfoClickListener(listener: OnPlaceInfoClickListener)|Sets a callback that's invoked when the user clicks on an info window.
setPlaceInfoAdapter(adapter: PlaceInfoAdapter)|Enables customization of the place info view, which is displayed when a marker is tapped.
setRotation(rotation: Float)|Sets the current rotation level of the MapView.
setRotation(rotation: Float, duration: Long = 0, easeType: MapController.EaseType)|Sets the current rotation level of the MapView and the duration of the rotation animation.
setTilt(angle: Float)|Sets the current tilt level of the MapView.
setTilt(angle: Float, duration: Long, easeType: MapController.EaseType)|Sets the current tilt level of the MapView and the duration of the tilt animation.
setZoom(zoomLevel: Float)|Sets the current zoom level of the MapView.
setZoom(zoomLevel: Float, duration: Long = 0, easeType: MapController.EaseType)|Sets the current zoom level of the MapView and the duration of the zoom animation.
screenPositionToLatLng(pointF: PointF): LatLng|Returns LatLng for the given screen position as PointF
latLngToScreenPosition(latLng: LatLng): PointF|Returns the screen position as PointF for the given LatLng coordinate.
extrudeBuilding(latLng: LatLng, buildingOptions: BuildingOptions = BuildingOptions())|Extrudes the building on given LatLng. To extrude, the buildings should be visible in thecurrent map view. Else it will be ignored. Additionally, this call will force a scene update.
See BuildingOptions.extrudeBuilding(latLngs: List<LatLng>, buildingOptions: BuildingOptions = BuildingOptions())|Extrudes the buildings on given list of LatLngs. To extrude, the buildings should be visible in thecurrent map view. Else it will be ignored. Additionally, this call will force a scene update.
See BuildingOptions.flattenBuilding(latLng: LatLng)|Flattens the extruded building on given LatLng. This call will force a scene update.
flattenBuilding(latLngs: List<LatLng>)|Flattens the extruded buildings on given LatLng. This call will force a scene update.