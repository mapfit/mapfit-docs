---
title: "User Location"
excerpt: ""
---
##User Location

To add and track a user's location, you will first have add the NSLocationWhenInUseUsageDescription key to your app's Info.plist file. Note: Xcode displays this key as "Privacy - Location When In Use Usage Description" in the Info.plist editor.

After setting the plist, you will need to enable user location in [MFTMapOptions](ref:mftmapoptions) with `high` or `low` accuracy. Mapfit's high accuracy setting utilizes core location's kCLLocationAccuracyBest, which is the highest level of accuracy. Mapfit's low accuracy setting uses kCLLocationAccuracyKilometer, which is accurate to the nearest kilometer. To listen to location updates see [Listeners](doc:listeners). 

```swift
//set user location to low accuracy
mapview.mapOptions.setUserLocationEnabled(true, accuracy: .low)
```

```swift
//set user location to high accuracy
mapview.mapOptions.setUserLocationEnabled(true, accuracy: .high)
```