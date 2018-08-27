---
title: "Map View"
excerpt: ""
---
## Map View
#Map Center
###Get center

```kotlin
val centerLatLng = mapfitMap.getCenter() 
```
###Set center
```kotlin
val latLng = LatLng(40.744043, -73.993209)

mapfitMap.setCenter(latLng)

// alternatively, you can animate centering if you pass duration in milliseconds
mapfitMap.setCenter(latLng, 200)

// you can also set map center with a horizontal and vertical offset
mapfitMap.setCenterWithOffset(
                        latLng, // position that offset will be applied to
                        300, // horizontal offset in pixels
                        0, // vertical offset in pixels
                        300 // duration for the centering animation
                    )
```
###Re-center
You can re-center the map to the last position it was centered at as below.
```kotlin
mapfitMap.reCenter()
```
#Map Tilt
###Get current tilt angle
```kotlin
val tiltAngle: Float = mapfitMap.getTilt() // tilt is in radians
```
###Set tilt angle
```kotlin
mapfitMap.setTilt(0f) // in radians

// alternatively, you can animate tilting if you pass duration in milliseconds
mapfitMap.setTilt(0f, 200)
```
#Map Zoom Level
###Get zoom level
```kotlin
val currentZoomLevel = mapfitMap.getZoom()
```
###Set zoom level
```kotlin
mapfitMap.setZoom(16f)

// alternatively, you can animate zooming if you pass duration in milliseconds
mapfitMap.setZoom(16f, 200)
```
###Set minimum zoom level
```kotlin
mapfitMap.getMapOptions().setMinZoom(5f)
```
###Set maximum zoom level
```kotlin
mapfitMap.getMapOptions().setMaxZoom(15f)
```
#Map Rotation
###Get current map rotation (compass direction)
```kotlin
val currentRotation: Float = mapfitMap.getRotation() // rotation is in radians
```
###Set map rotation (compass direction)
```kotlin
mapfitMap.setRotation(1f) // rotation is in radians

// alternatively, you can animate rotation if you pass duration in milliseconds
mapfitMap.setRotation(1f, 200)
```
#Map Bounds
###Get current map bounds
```kotlin
val currentMapBounds: LatLngBounds = mapfitMap.getLatLngBounds()
```
###Set map bounds
```kotlin
val boundsBuilder: LatLngBounds.Builder = LatLngBounds.Builder()
boundsBuilder.include(LatLng(40.744043, -73.993209))
boundsBuilder.include(LatLng(40.6902223, -73.9770368))
boundsBuilder.include(LatLng(40.7061326, -74.000769))

val bounds = boundsBuilder.build()

mapfitMap.setLatLngBounds(
            bounds,
            0.1f, // optional padding percentage. the padding width will be 10% of the screen size
            500 // optional animation duration. if set, map will be centered with an animation
        )
```