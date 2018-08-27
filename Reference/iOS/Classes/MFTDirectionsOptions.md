---
title: "MFTDirectionsOptions"
excerpt: ""
---
## MFTDirectionsOptions
`MFTDirectionsOptions` controls options for [MFTDirections](ref:mftdirections).

```swift 
public class MFTDirectionsOptions
```

Method	|Description
--|--
setDestination(_ position: CLLocationCoordinate2D)|Sets the destination of the route given a coordinate position.
setDestination(_ address: String)|Sets the destination of the route given an address string.
setOrigin(_ position: CLLocationCoordinate2D)|Sets the origin of the route given a coordinate position.
setOrigin(_ address: String)|Sets the origin of the route given an address string.
setType(_type: MFTDirectionsType)|Sets the type of directions to be returned based on the given MFTDirectionsType .
showDirections(callback: RouteDrawCallback)|Shows the route on the map.

Property	|Description
--|--
isVisible: Bool|Visibility of the route on the map. Can be changed by calling the showDirections method.
type: MFTDirectionsType|The type of directions returned. See: MFTDirectionsType for possible return values.