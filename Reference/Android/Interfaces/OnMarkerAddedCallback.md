---
title: "OnMarkerAddedCallback"
excerpt: "com.mapfit.android.annotations.callback.OnMarkerAddedCallback"
---
## OnMarkerAddedCallback
### com.mapfit.android.annotations.callback.OnMarkerAddedCallback

Callback for listening to marker addition to the map with [Geocoder](ref:commapfitmapfitsdkgeocoder) .
```java
interface OnMarkerAddedCallback
```

Method	|Description
--|--
onError(exception: Exception)|Called on error when a marker should have been added to the map via the Geocoder .
onMarkerAdded(marker: Marker)|Called when a marker is added to the map.