---
title: "MapOptions"
excerpt: "com.mapfit.android.MapOptions"
---
## MapOptions
### com.mapfit.android.MapOptions

Map settings and options are manipulated through this class.
```java
class MapOptions
```
Method	Description
setMaxZoom(zoomLevel: Float)
Sets the maximum zoom level to be displayed on the map. Valid numeric range: 0-20.

setMinZoom(zoomLevel: Float)
Sets the minimum zoom level to be displayed on the map. Valid numeric range: 0-20.

updateScene(sceneUpdates: List<SceneUpdate>)
Applies SceneUpdates to the current scene asynchronously. When the updates are finished. OnMapThemeListener will be triggered if set.

setUserLocationEnabled(enable: Boolean, locationPriority: LocationPriority = LocationPriority.HIGH_ACCURACY, listener: LocationListener? = null )
Enables user location updates and put marker on the map. You MUST have [Manifest.permission.ACCESS_FINE_LOCATION] before enabling. User's location marker will be updated on each location update.

getUserLocationEnabled(): Boolean
Returns user location display status.

Property	|Description
--|--
isCompassButtonVisible: Boolean|Compass control button enabled on the map.
isPanEnabled: Boolean|The enabled/disabled state of the Pan control.
isPinchEnabled: Boolean|The enabled/disabled state of the Pinch control.
isRecenterButtonVisible: Boolean|The enabled/disabled state of the Recenter control.
isRotateEnabled: Boolean|The enabled/disabled state of the Rotate control.
theme: MapTheme?|The map theme. See: MapTheme.
isTiltEnabled: Boolean|The enabled/disabled state of the Tilt control.
isZoomControlVisible: Boolean|The enabled/disabled state of the Zoom Control buttons.
is3dBuildingsEnabled: Boolean|The enabled/disabled state of the 3d buildings.
gesturesEnabled: Boolean|The enabled/disabled state of the gestures; pan, pinch, rotate and tilt.
customTheme: String|Custom map theme path. Eighter a URL or a file path.
cameraType: CameraType = CameraType.PERSPECTIVE|CameraType of the map.
isTransitLayerEnabled: Boolean = false|The enabled/disabled state of the transit layer.
isUserLocationButtonVisible = true|The enabled/disabled state of the user's location button. The button is only shown if user location is enabled.

Constant	|Description
--|--
MAP_MAX_ZOOM: Double|The maximum zoom level which will be displayed on the map. The constant value is 20.0
MAP_MIN_ZOOM: Double|The minimum zoom level which will be displayed on the map. The constant value is 0