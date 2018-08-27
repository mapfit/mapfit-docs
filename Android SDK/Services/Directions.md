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
[block:code]
{
  "codes": [
    {
      "code": "Directions().route(\n                originAddress = \"119 W 24th St new york\",\n                destinationAddress = \"1000 5th Ave, New York, NY 10028\",\n                callback = callback\n             )\n\nval callback = object : DirectionsCallback {\n    override fun onSuccess(route: Route) {\n       // you can draw and show the route now!\n    }\n    override fun onError(message: String, e: Exception) {\n        // handle the error \n    }\n}",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "new Directions().route(\n        \"119 W 24th St new york\",\n        \"1000 5th Ave, New York, NY 10028\",\n        callback);\n\nDirectionsCallback callback = new DirectionsCallback() {\n    @Override\n    public void onSuccess(@NotNull Route route) {\n      // you can draw and show the route now!\n    }\n\n    @Override\n    public void onError(@NotNull String message, @NotNull Exception e) {\n      // handle the error\n    }\n};",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
Instead of street address, you can also pass coordinates as follow,
[block:code]
{
  "codes": [
    {
      "code": "Directions().route(\n                originLocation = LatLng(40.744043, -73.993209),\n                destinationLocation = LatLng(40.7794406, -73.9654327),\n                callback = callback\n            )",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "new Directions().route(\n                new LatLng(40.744043, -73.993209),\n                new LatLng(40.7794406, -73.9654327),\n                callback);",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
### Setting directions type

You can specify [DirectionsType](https://mapfit-android.readme.io/v1.0.0/reference#directionstype) as you would like to driving, walking or cycling. The default directions type is `driving`.
[block:code]
{
  "codes": [
    {
      "code": "Directions().route(\n                originLocation = LatLng(40.744043, -73.993209),\n                destinationLocation = LatLng(40.7794406, -73.9654327),\n                directionsType = DirectionsType.CYCLING,\n                callback = callback\n            )",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "new Directions().route(\n                new LatLng(40.744043, -73.993209),\n                new LatLng(40.7794406, -73.9654327),\n                DirectionsType.CYCLING,\n                callback);",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
## Drawing directions on Map
	
You can also draw the [Route](https://mapfit-android.readme.io/v1.0.0/reference#route) simply with [MapfitMap](https://mapfit-android.readme.io/v1.0.0/reference#mapfitmap). 
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.getDirectionsOptions()\n\t            .setDestination(LatLng(40.744043, -73.993209))\n\t            .setOrigin(LatLng(40.7794406, -73.9654327))\n\t            .setType(DirectionsType.CYCLING)\n\t            .showDirections(object : DirectionsOptions.RouteDrawCallback {\n             \t   \t\toverride fun onRouteDrawn(route: Route, legs: List<Polyline>) {\n             \t   \t\t    /* the route is drawn on map. drawn polylines are returned as legs. \n             \t   \t\t    you may want to add a marker to the origin and destination \n             \t   \t\t    location inside route object. */\n             \t   \t\t}\n\t\t\n              \t \t\toverride fun onError(message: String, e: Exception) {\n                \t\t\t    // handle the error\n              \t \t\t}\n            \t})",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.getDirectionsOptions()\n                .setDestination(new LatLng(40.744043, -73.993209))\n                .setOrigin(new LatLng(40.7794406, -73.9654327))\n                .setType(DirectionsType.CYCLING)\n                .showDirections(new DirectionsOptions.RouteDrawCallback() {\n             \t   \t\t@Override\n             \t   \t\tpublic void onRouteDrawn(Route route, List<Polyline> legs) {\n             \t   \t\t    /* the route is drawn on map. drawn polylines are returned as legs. \n             \t   \t\t    you may want to add a marker to the origin and destination \n             \t   \t\t    location inside route object. */\n             \t   \t\t}\n    \t\t\t\t\t\t\t\t\n             \t   \t\t@Override\n             \t   \t\tpublic void onError(@NotNull String message, @NotNull Exception e) {\n      \t\t\t\t\t\t\t\t// handle the error\n             \t   \t\t}\n                });",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]