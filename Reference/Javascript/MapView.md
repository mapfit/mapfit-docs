---
title: "MapView"
excerpt: "mapfit.MapView"
---

# MapView
### mapfit.MapView
This class is used for initializing and drawing a new instance of the map.

Constructor | Description
------------|------------
mapfit.MapView(Div Id: string, {options})| Create an instance of map. The first parameter is the div's id that you would like the map to be drawn into. The second parameter is an object where you can pass various settings for the map. (To see all the optional parameters below.)

Map Options | Description
------------|------------
theme|Set the theme of theme of the map. We have three different themes to choose from 'day', 'night', or 'grayscale'.
center|Specify the center of the map. Takes an array of latitude and longitude.
zoom|Set the zoom level. Takes a numeric value.
maxZoom|Set the maximum zoom level. Takes a numeric value.
minZoom|Set the minimum zoom level. Takes a numeric value.
panEnabled|Turn panning either on or off. Takes a boolean value.
pinchEnabled|Turn pinch either on or off. Takes a boolean value.
zoomControl|Either show or hide the zoom controls. Takes a boolean value.
recenterButton|Either show or hide the recenter button. Takes a boolean value. The recenter button will be linked to the center that you specified. If not center is specified the recenter button will center to New York.
scrollWheel|Either disable or enable the ability to scroll on the map with the scroll wheel. Takes a boolean value.

Method | Description
-------|------------
addLayer(layer: Layer)|Adds the Layer to the map.
addMarker(marker: Marker)|Adds the Marker to the map.
addPolyline(polyline: Polyline)|Adds the Polyline to the map.
addPolygon(polygon: Polygon)|Adds the Polygon to the map.
getCenter(): LatLng|Returns the LatLng displayed at the center of the map.
getLatLngBounds():  LatLngBounds|Returns the LatLngBounds for the map.
getZoom(): Number|Returns the current zoom level of the map.
removeLayer(layer: Layer)|Removes the Layer from the map.
removeMarker(marker: Marker)|Removes the Marker from the map.
removePolyline(polyline: Polyline)|Removes the Polyline from the map.
removePolygon(polygon: Polygon)|Removes the Polygon from the map.
setLatLngBounds(bounds: LatLngBounds)|Sets the map bounds using the LatLngBounds - the southwest and northeast corners of the bounding box.
setCenter(latlng: LatLng, duration: seconds )|Sets the map center to the input coordinate values.
setCenterWithLayer(layer: Layer, topleftpadding: String, bottomrightpadding: String)|Sets the map center to the input layer's coordinate values.
setZoom(zoom: Number)|Sets the map's the current zoom level (0-16).
showUserLocation()|Shows current user location on the map utilizing the browser’s current geolocation.|

Property	Description
dragging|Enables panning.
recenterButton|Sets recenter button visibility.
zoomControl|Sets zoom controls visibility.

Interactions

Event	|Description
--|--
click|This event is fired when the the user clicks/taps the map.
dblclick|This event is fired when the the user double clicks/taps the map.
mousedown|This event is fired when the user initiates a click event, pushing the mouse button on the map.
mousemove|This event is fired when the the user's mouse moves over the map bounds.
mouseover|This event is fired when the the user's mouse enters the map bounds.
mouseout|This event is fired when the the user's mouse leaves the map bounds.
mouseup|This event is fired when the user's releases the mouse button from a click event over the map.