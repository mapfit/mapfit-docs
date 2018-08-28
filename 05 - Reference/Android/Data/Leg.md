---
title: "Leg"
excerpt: "com.mapfit.android.directions.model.Leg"
---
## Leg
### com.mapfit.android.directions.model.Leg
A data class of the individual step within the set of directions returned by the Directions API wrapper - [Directions](doc:directions-1).

```java
data class Leg
```
Constructor	|Description
--|--
Leg(summary: Summary, shape: String, maneuvers: List<Maneuver>)|An individual step within the set of directions returned by the Directions API wrapper - Directions.

Property	|Description
--|--
maneuvers: List<Maneuver>|A list of Maneuvers.
shape: String|The encoded Polyline of the leg.
summary: Summary|The Summary of the leg.