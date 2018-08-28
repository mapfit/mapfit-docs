---
title: "MFTMapOptions"
excerpt: ""
---
## MFTMapOptions
`MFTMapOptions` controls options for [MFTMapView](ref:mftmapview) .

```swift
public class MFTMapOptions
```

Method	|Description
--|--
setMapView(mapView: MFTMapView)|Sets the MFTMapView to be controlled by the class.
setMaxZoom(zoomLevel: Float)|Sets the maximum zoom level to be displayed on the map. Valid numeric range: 0-20.
setMinZoom(zoomLevel: Float)|Sets the minimum zoom level to be displayed on the map. Valid numeric range: 0-20.
setTheme(theme: MFTMapStyle)|Sets MFTMapStyle (the map theme) on the MFTMapView.
setUserLocationEnabled(_ show: Bool, accuracy: MFTLocationAccuracy)|Enables user location and sets the accuracy level via MFTLocationAccuracy.
setZoomControlVisibility(_ show: Bool)|Sets zoom control visibility on the MFTMapView.
setCompassVisibility(_ show: Bool)|Sets compass control visibility on the MFTMapView.
set3DBuildingsEnabled(_ show: Bool)|Sets 3D buildings visibility on the MFTMapView.
setGesturesEnabled(_ enabled: Bool)|Enables or disables all map gestures.
updateScene(updates: [MFTSceneUpdate])|Updates the map with one or more instances of MFTSceneUpdate

Property	|Description
--|--
isCompassVisible: Boolean|The visibility of the compass control button.
isZoomControlVisible: Boolean|The visibility of the Zoom Control buttons.
isRecenterControlVisible: Boolean|The visibility of the recenter control button.
isPanEnabled: Boolean|The enabled/disabled state of the Pan control.
isPinchEnabled: Boolean|The enabled/disabled state of the Pinch control.
isRotateEnabled: Boolean|The enabled/disabled state of the Rotate control.
isTiltEnabled: Boolean|The enabled/disabled state of the Tilt control.
isUserLocationEnabled: Boolean|The enabled/disabled state of user's location.
isUserLocationButtonVisible: Boolean|The visibility of the user location button.
is3DBuildingsEnabled: Boolean|The visibility of 3D buildings.
