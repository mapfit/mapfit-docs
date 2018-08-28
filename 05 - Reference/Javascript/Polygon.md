---
title: "Polygon"
excerpt: "mapfit.Polygon"
---
# Polygon
### mapfit.Polygon

`Polygon` defines a polygon that appears on the map. Polygon is a closed Polyline where the end point and start point are equal. The polygon consists of an ordered sequence of coordinate points.

Constructor | Description
------------|------------
mapfit.Polygon(points:<LatLng[]>)| Construct polygon with input array of coordinate point arrays.

Method	|Description
--|--
addPoints(points:<LatLng[]>)|Extend Polygon shape with an additional geographic coordinate point.
getPoints(): LatLng[]|Returns an array of the points defining the polygon outline.
getLatLngBounds(): LatLngBounds|Returns the LatLngBounds of the polygon outline.
getPolygonOptions(): Object|Returns a JSON object of the polygon options, including settings for fillColor ,strokeColor, and strokeWidth. See PolygonOptions for detail.

Interactions

Interaction |Event	Description
--|--
click|This event is fired when the user clicks/taps the polygon.
dblclick|This event is fired when the user double clicks/taps the polygon.
mousedown|This event is fired when the user initiates a click event, pushing the mouse button on the polygon.
mouseover|This event is fired when the user's mouse enters the polygon bounds.
mouseout|This event is fired when the user's mouse leaves the polygon bounds.
mouseup|This event is fired when the user's releases the mouse button from a click event over the polygon.