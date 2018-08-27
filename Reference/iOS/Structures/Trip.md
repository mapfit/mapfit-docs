---
title: "Trip"
excerpt: ""
---
## Trip
The results of the returned route, represented as a JSON object, containing details about the trip, including locations, a summary with basic information about the entire trip, and a list of legs.

```swift
public struct Trip : Decodable
```
Property	|Description
--|--
language: String|The language of the narration instructions. This value is set to en-US.
legs: List<Leg>|The Legs of the trip.
locations: List<Location>|The origin and destination locations.
status: Int|Status code.
statusMessage: String|Status message.
summary: Summary|The Summary of the trip.
units: String|Distance units, returned as miles.