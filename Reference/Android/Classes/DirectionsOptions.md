---
title: "DirectionsOptions"
excerpt: "com.mapfit.android.DirectionsOptions"
---
## DirectionsOptions
### com.mapfit.android.DirectionsOptions

Used to obtain route and draw directions on map from an origin to a destination.

```java
class DirectionsOptions
```
Method	|Description
--|--
getType(): DirectionsType|Returns the current DirectionsType .
setDestination(latLng: LatLng): DirectionsOptions|Sets destination for the directions to the given LatLng coordinates.
setDestination(address: String): DirectionsOptions|Sets destination for the directions to the given street address.
setOrigin(latLng: LatLng): DirectionsOptions|Sets origin for the directions to the given LatLng coordinates.
setOrigin(address: String): DirectionsOptions|Sets origin for the directions to the given street address.
setType(type: DirectionsType): DirectionsOptions|Sets type for the directions. See DirectionsType.
showDirections(callback: RouteDrawCallback)|Draws the route as polyline on the map and returns the route details to the given RouteDrawCallback.