---
title: "Directions"
excerpt: ""
---
# Directions API Quick Start Guide - Android

Mapfit Directions API is a service to obtain directions between locations. You can use Directions API directly from the Android SDK.

## Pre-requirements

This tutorial assumes that you have already implemented Mapfit Maps SDK in your project. If you haven't implemented it yet, see [Create your first map](doc:create-a-map).


## Getting directions
	
To obtain directions, you can use the [Directions](https://mapfit-android.readme.io/v1.0.0/reference#commapfitmapfitsdkdirections) class as below. Specify an origin and destination address or coordinate to get the [Route](https://mapfit-android.readme.io/v1.0.0/reference#route).

```kotlin
Directions().route(
                originAddress = "119 W 24th St new york",
                destinationAddress = "1000 5th Ave, New York, NY 10028",
                callback = callback
             )

val callback = object : DirectionsCallback {
    override fun onSuccess(route: Route) {
       // you can draw and show the route now!
    }
    override fun onError(message: String, e: Exception) {
        // handle the error 
    }
}
```
Instead of street address, you can also pass coordinates as follow,
```kotlin
Directions().route(
                originLocation = LatLng(40.744043, -73.993209),
                destinationLocation = LatLng(40.7794406, -73.9654327),
                callback = callback
            )
```

### Setting directions type

You can specify [DirectionsType](https://mapfit-android.readme.io/v1.0.0/reference#directionstype) as you would like to driving, walking or cycling. The default directions type is `driving`.
```kotlin
Directions().route(
                originLocation = LatLng(40.744043, -73.993209),
                destinationLocation = LatLng(40.7794406, -73.9654327),
                directionsType = DirectionsType.CYCLING,
                callback = callback
            )
```

## Drawing directions on Map
	
You can also draw the [Route](https://mapfit-android.readme.io/v1.0.0/reference#route) simply with [MapfitMap](https://mapfit-android.readme.io/v1.0.0/reference#mapfitmap). 
```kotlin
mapfitMap.getDirectionsOptions()
	            .setDestination(LatLng(40.744043, -73.993209))
	            .setOrigin(LatLng(40.7794406, -73.9654327))
	            .setType(DirectionsType.CYCLING)
	            .showDirections(object : DirectionsOptions.RouteDrawCallback {
             	   		override fun onRouteDrawn(route: Route, legs: List<Polyline>) {
             	   		    /* the route is drawn on map. drawn polylines are returned as legs. 
             	   		    you may want to add a marker to the origin and destination 
             	   		    location inside route object. */
             	   		}
		
              	 		override fun onError(message: String, e: Exception) {
                			    // handle the error
              	 		}
            	})
```