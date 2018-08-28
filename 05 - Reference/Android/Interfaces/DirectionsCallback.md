---
title: "DirectionsCallback"
excerpt: "com.mapfit.android.directions.DirectionsCallback"
---
## DirectionsCallback
### com.mapfit.android.directions.DirectionsCallback
Callback to listen to a Directions result.

```java
interface DirectionsCallback```

Method	|Description
--|--
onError(message: String, e: Exception)|Called when a Directions request fails.
onSuccess(route: Route)|Called when a Directions result sucessfully returns.