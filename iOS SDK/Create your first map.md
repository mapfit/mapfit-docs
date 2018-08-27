---
title: "Create your first map"
excerpt: ""
---
[block:api-header]
{
  "title": "Audience"
}
[/block]
This documentation is designed for people familiar with Swift programming and object-oriented programming concepts. You should also be familiar with [Mapfit](http://mapfit.com) from a user's point of view. There are many Swift tutorials available on the Web.

This conceptual documentation is designed to let you quickly start exploring and developing applications with the Mapfit iOS SDK. We also publish the Mapfit iOS Reference.
[block:api-header]
{
  "title": "Set up your environment"
}
[/block]
You will need to have Xcode installed on your machine in order to use Mapfit iOS SDK. You can obtain the latest version of Xcode from [here](https://developer.apple.com/xcode/) or from the Mac App Store.

[block:api-header]
{
  "title": "Cocoapods"
}
[/block]
Adding a map to your app is as simple as adding the following to your app’s podfile:

```
pod 'Mapfit'
```

Run pod install in your project's directory.
[block:api-header]
{
  "title": "Set your API Key"
}
[/block]
Now you must set your API key in order to be able to use the geocoding and polygon APIs. In your appDelegate, enter the key as seen below.

To get an API key see: [Get API Key](doc:get-api-key).
[block:code]
{
  "codes": [
    {
      "code": "import Mapfit\n\n@UIApplicationMain\nclass AppDelegate: UIResponder, UIApplicationDelegate {\n    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplicationLaunchOptionsKey: Any]?) -> Bool {\n      MFTManager.sharedManager.apiKey = \"API_KEY\"\n      return true\n    }\n}",
      "language": "swift"
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Create your map"
}
[/block]
Next you can create a map instance with the following function.
[block:code]
{
  "codes": [
    {
      "code": "let mapView = MFTMapView(frame: view.bounds)",
      "language": "swift"
    }
  ]
}
[/block]
## Add map to view
In order to actually add it to your view, add the following:
[block:code]
{
  "codes": [
    {
      "code": "view.addSubview(mapView)",
      "language": "swift"
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Add a marker to your map"
}
[/block]
In order to add your first marker to the map, you must create a marker instance with the following function:
[block:code]
{
  "codes": [
    {
      "code": "let marker = mapView.addMarker(position:  CLLocationCoordinate2D(latitude: 40.74699, longitude: -73.98742))",
      "language": "swift"
    }
  ]
}
[/block]
## Set meta data for your marker
You can set specific metadata for your marker as follows:
```swift
marker.title = "Mapfit"
marker.subtitle1 = "119 w 24th street"
marker.subtitle2 = "New York, NY"
```
[block:api-header]
{
  "title": "Draw a route on your map"
}
[/block]
This code snippet shows you how you can draw a route on top of your map.
[block:code]
{
  "codes": [
    {
      "code": " MFTDirections.sharedInstance.route(origin: nil, originAddress: \"119 w 24th street new york, ny\", destination: nil, destinationAddress: \"33 west 3rd street new york\", includesBuilding: false, directionsType: .walking) { (route, error) in\n            \n            if error == nil {\n                if let route = route{\n                    mapView.directionsOptions.drawRoute(route: route, completion: { (polyline, error) in\n                        \n                    })\n                }\n            }\n        }",
      "language": "swift"
    }
  ]
}
[/block]