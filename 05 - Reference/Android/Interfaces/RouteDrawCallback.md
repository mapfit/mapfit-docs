---
title: "RouteDrawCallback"
excerpt: "com.mapfit.android.DirectionsOptions.RouteDrawCallback"
---
## RouteDrawCallback
### com.mapfit.android.DirectionsOptions.RouteDrawCallback
Callback to be invoked when the route is drawn or there is an error.
```java
interface RouteDrawCallback
```

Method	|Description
--|--
onError(message: String, e: Exception)|Called when route is not drawn and an error has occurred.
onRouteDrawn(route: Route, legs: List<Polyline>)|Called when route is drawn.