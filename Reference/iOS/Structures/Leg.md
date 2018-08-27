---
title: "Leg"
excerpt: ""
---
## Leg
A data class of the individual step within the set of directions returned by the Directions API wrapper - [MFTDirections](ref:mftdirections).

```swift
public struct Leg : Decodable
```

Property	|Description
--|--
maneuvers: List<Maneuver>|A list of Manuevers.
shape: String|The encoded MFTPolyline of the leg.
summary: Summary|The Summary of the leg.