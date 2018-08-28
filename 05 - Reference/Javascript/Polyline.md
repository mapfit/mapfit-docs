---
title: "Polyline"
excerpt: "mapfit.Polyline"
---
# Polyline
### mapfit.Polyline

`Polyline` defines a polyline that appears on the map. A polyline defines a series of connected geographical coordinates in an ordered sequence.

Constructor	|Description
--|--
mapfit.Polyline(points:<LatLng[]>)|Construct polyline with input array of coordinate point arrays.

Method	|Description
--|--
addPoints(points:LatLng[]>)|Return Value: NoneExtend polyline shape with an additional geographic coordinate points.
getPoints(): LatLng[]Return Value: <LatLng[]>|Returns an array of the points defining the polyline outline.
getLatLngBounds(): LatLngBounds|Returns the LatLngBounds of the polyline outline.
getPolylineOptions(): Object|Return Value: ObjectReturns a JSON object of the polyline options, including settings for strokeColor and strokeWidth.
setStrokeColor(color:String)|Sets the polyline color to the input color value, which can be specified as an HTML color name (e.g. 'red'), rgb value, or hex value.
setStrokeWidth(width:Numeric)|Sets the polyline stroke width to the input width value, which can be specified as an HTML color name (e.g. 'red'), rgb value, or hex value.

Interaction |Event	Description
--|--
click|This event is fired when the the user clicks/taps the polyline.
dblclick|This event is fired when the the user double clicks/taps the polyline.
mousedown|This event is fired when the user initiates a click event, pushing the mouse button on the polyline.
mouseover|This event is fired when the user's mouse enters the polyline bounds.
mouseout|This event is fired when the user's mouse leaves the polyline bounds.
mouseup|This event is fired when the user's releases the mouse button from a click event over the polyline.