---
title: "MFTManager"
excerpt: ""
---
## MFTManager
`MFTManager` is a singleton object used for managing state between the various dependencies. Right now, it only manages the API key system.

```swift
open class MFTManager: NSObject, MFTManagerProtocol
```
Property	|Description
--|--
sharedManager: NSObject|Type: NSObjectThe single object to be used for all access.
apiKey: String|The Mapfit API key. If this is not set, exceptions will get raised by the various objects in use.