---
title: "MFTGeocoder"
excerpt: ""
---
## MFTGeocoder
`MFTGeocoder` is used for geocoding an address and displaying a marker on the map.


```swift 
public class MFTGeocoder
```

Method	|Description
--|--
geocode(address: String, includeBuilding: Bool,     completion: @escaping( address: Address,     error: Error?)->Void)|Return the position, normalizedaddress, and optional building polygon from an input address string as a Address object.