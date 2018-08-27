---
title: "Layer"
excerpt: "mapfit.Layer"
---
`Layer` is a layer class, which can be used to group [Marker](ref:marker)s, [Polygon](ref:polygon)s, and [Polyline](ref:polyline)s.

Constructor | Description
------------|------------
mapfit.Layer()| Creates a new map layer.

Method | Description
-------|------------
add(element:Object)| Adds an element to the layer. 
getLatLngBounds(): LatLngBounds| Return Value: LatLngBounds 
getVisibility(): Boolean| Returns the layer visibility. 
remove(element:Object)| Removes the input object from the layer. 
setVisibility(bool:Boolean)| Will hide or show the layer, based on the boolean input value. A layer is shown by default.