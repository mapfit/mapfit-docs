---
title: "GeocoderCallback"
excerpt: "com.mapfit.android.geocoder.GeocoderCallback"
---
## GeocoderCallback
### com.mapfit.android.geocoder.GeocoderCallback
Callback to listen to a Gecoder result.

```java
interface DirectionsCallback
```

Method	|Description
--|--
onError(message: String, e: Exception)|Called when a Geocoder request fails.
onSuccess(addressList: List<Address>)|Called when a Geocoder result sucessfully returns.