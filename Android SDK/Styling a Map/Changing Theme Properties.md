---
title: "Changing Theme Properties"
excerpt: ""
---
## Changing Theme Properties
It is possible to change the values of the properties inside current theme at runtime.

For a theme with an attribute like below,
```kotlin
...
global:
	show_transit: false
...
```
 We can change the value of `show_transit` as below.
```kotlin
// for path of the property, append scopes with a dot(".")
val sceneUpdate = SceneUpdate("global.show_transit", "true")
mapfitMap.getMapOptions().updateScene(listOf(sceneUpdate))
```
**Note:** Each call of `updateScene` will cause a scene load and if set, [OnMapThemeLoadListener](ref:onmapthemeloadlistener) will be triggered.