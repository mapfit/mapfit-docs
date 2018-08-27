---
title: "Controls"
excerpt: ""
---
## Controls
Below is a list of controls available when using our maps. Toggling these will either enable or disable these gestures.

#Pan
```kotlin
mapfitMap.getMapOptions().isPanEnabled = false
```
#Pinch (Zoom)
```kotlin
mapfitMap.getMapOptions().isPinchEnabled = false 
```
#Rotate
```kotlin
mapfitMap.getMapOptions().isRotateEnabled = false 
```
#Tilt
```kotlin
mapfitMap.getMapOptions().isTiltEnabled = false
```
#Gestures
Pan, pinch, rotation, and tilting can be enabled or disabled at once as below.
```kotlin
mapfitMap.getMapOptions().gesturesEnabled = false
```
#3D Buildings
```kotlin
mapfitMap.getMapOptions().is3dBuildingsEnabled = true
```