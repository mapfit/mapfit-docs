---
title: "MapOptions"
excerpt: "mapfit.MapOptions"
---
# MapOptions
### mapfit.MapOptions
`MapOptions` controls options for and inherits from [MapView](ref:mapview).

Method | Description
-------|------------
getMinZoomLevel(): Number|Returns the minimum zoom level accessible to the user of the map.
getMaxZoomLevel(): Number|Returns the maximum zoom level accessible to the user of the map.
getPanEnabled(): Boolean|Return the enabled/disabled state of the pan control.
getPinchEnabled(): Boolean|Return the enabled/disabled state of the pinch control.
getZoomControlVisibility(): Boolean|Return the enabled/disabled state of the zoom control buttons.
getRecenterButtonEnabled(): Boolean|Return the enabled/disabled state of the Recenter button.
getScrollWheelEnabled(): Boolean|Return the enabled/disabled state of the scroll wheel functionality.
setMaxZoomLevel(zoom: Number)|Sets the maximum zoom level accessible to the user of the map. Valid numeric range: 0-20.
setMinZoomLevel(zoom: Number)|Sets the minimum zoom level accessible to the user of the map. Valid numeric range: 0-20.
setPanEnabled(bool: Boolean)|Set the enabled/disabled state of the pan control.
setPinchEnabled(bool: Boolean)|Set the enabled/disabled state of the pinch control.
setZoomControlVisibility(bool: Boolean)|Set the enabled/disabled state of the zoom control buttons.
setRecenterButtonEnabled(bool: Boolean)|Set the enabled/disabled state of the recenter button.
setScrollWheelEnabled(bool: Boolean)|Set the enabled/disabled state of the scroll wheel functionality.
setZoom(zoom: Number)|Set the zoom level by passing in a numeric value.
setZoomAnimation(zoom: Number, latLng: Array, options: Object)|Set the zoom level, latitude and longitude for the mapview, and the last parameter is for the animation. The third parameter will take an object for the animation effects, example: {animation: true, duration: 10}. Animation takes a boolean value and duration takes a numeric value.













































