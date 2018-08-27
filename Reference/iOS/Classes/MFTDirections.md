---
title: "MFTDirections"
excerpt: ""
---
## MFTDirections
`MFTDirections` is used for accessing the Mapfit Directions API.

```swift 
public class MFTDirections
```

Method	|Description
--|--
route(origin: CLLocationCoordinate2D?, originAddress: String?,     destination: CLLocationCoordinate2D?, destinationAddress: String?,     includeBuilding: Bool, directionsType: MFTDirectionsType,     completion: @escaping (_ routeDict: RouteObject?, _ error: Error?))|Return the route,given a MFTDirectionsType, an origin and destination address or coordinate values. Optionally return the associated building polygon (where available).