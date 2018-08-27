---
title: "Entrance"
excerpt: "com.mapfit.android.geocoder.model.Entrance"
---
## Entrance
### com.mapfit.android.geocoder.model.Entrance

Data class for defining an entrance point of a place.
```java
data class Entrance
```
Constructor	|Description
--|--
Entrance(lat: Double, lng: Double, entranceType: EntranceType?)|Data class for defining an entrance point of a place.

Property	|Description
--|--
entranceType: EntranceType?|The EntranceType of the entrance.
lat: Double|The latitude (WGS84).
lng: Double|The longitude (WGS84).