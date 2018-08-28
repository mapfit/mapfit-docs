---
title: "UI Features"
excerpt: ""
---
## UI Features
We provide onscreen buttons which control certain aspects of the map.

#Zoom Controls
Turning this on places a zoom in / zoom out button on the bottom right of the map. 
```kotlin
mapfitMap.getMapOptions().isZoomControlVisible = true
```
#Compass
Turning this on places a compass button on the bottom right of the map. Tapping this button allows you to reset rotation to the north.
```kotlin
mapfitMap.getMapOptions().isCompassButtonVisible = true
```
#Recenter
Turning this on places a re-center button on the bottom right of the map. Tapping this button allows you to recenter the map to the position previously set as the center.
```kotlin
mapfitMap.getMapOptions().isRecenterButtonVisible = true 
```
