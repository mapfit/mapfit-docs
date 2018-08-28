---
title: "Location"
excerpt: ""
---
## Location
A data class representing the origin and destination locations.

```swift
public struct Location : Decodable
```
Property	|Description
--|--
lat: Double|The latitude (WGS84).
lng: Double|The longitude (WGS84).
sideOfStreet: String|The side of street of a break (origin or destination) location that is determined based on the actual route when the location isoffset from the street. The possible values are left and right.
entranceType: String|The entrance type of the returned geographical coordiate. String returned will be one of the following values:pedestrian-primary, pedestrian-secondary, all, loading, service, parking, OR all- followed by any of the above, OR all-pedestrian.
type: String|Type of location, always returned as break (origin or destination) - indicating a stop.