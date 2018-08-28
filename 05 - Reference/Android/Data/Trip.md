---
title: "Trip"
excerpt: "com.mapfit.android.directions.model.Trip"
---
## Trip
### com.mapfit.android.directions.model.Trip
The results of the returned route, represented as a JSON object.

```java
data class Trip
```

Constructor	|Description
--|--
Trip(summary: Summary, status_message: String, legs: List<Leg>,    language: String, locations: List<Location>, units: String, status: Int)|The results of the returned route, represented as a JSON object, containing details aboutthe trip, including locations, a summary with basic information about the entire trip, and a list of legs.

Property	|Description
--|--
language: String|The language of the narration instructions. This value is set to en-US.
legs: List<Leg>|The Legs of the trip.
locations: List<Location>|The origin and destination locations.
status: Int|Status code.
statusMessage: String|Status message.
summary: Summary|The Summary of the trip.
units: String|Distance units, returned as miles.