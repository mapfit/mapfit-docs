---
title: "MapView"
excerpt: "com.mapfit.android.MapView"
---
## MapView
### com.mapfit.android.MapView

The view the map is drawn to.

```java
class MapView
```
Constructor	|Description
--|--
MapView(context: Context, attributeSet: AttributeSet? = null)|The view the MapfitMap is drawn to.

Method	|Description
--|--
getMapAsync(mapTheme: MapTheme = MapTheme.MAPFIT_DAY, onMapReadyCallback: OnMapReadyCallback)|Instantiates the MapView and the controller asynchronously and returns the MapfitMap instance to the given callback. This method must be invoked to display the map.
getMapAsync(customTheme: String,  onMapReadyCallback: OnMapReadyCallback)|Instantiates the MapView and the controller asynchronously and returns the [MapfitMap]to the given callback. This method must be invoked to display the map. customTheme parameter should be a url or file path of the yaml file.
getPlaceInfoAdapter(): PlaceInfoAdapter?|Returns the PlaceInfoAdapter for handling PlaceInfos and custom views.
onDestroy()|You must call this method from the parent Activity or Fragment's corresponding method.
onLowMemory()|You must call this method from the parent Activity/Fragment's corresponding method.