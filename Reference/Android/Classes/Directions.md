---
title: "Directions"
excerpt: "com.mapfit.android.directions.Directions"
---
## Directions
### com.mapfit.android.directions.Directions

`Directions` is a wrapper for Mapfit Directions API. Used to obtain directions for an origin and destination location or address.

```java
class Directions
```
Constructor	|Description
--|--
Directions()|A wrapper for Mapfit Directions API. Used to obtain directions for an origin and destination location or address.

Method	|Description
--|--
route(originAddress: String, destinationAddress: String, originLocation: LatLng, destinationLocation: LatLng, directionsType: DirectionsType, callback: DirectionsCallback)|Returns directions for given origin and destination. To have reliable results, you should provide an origin and destination.