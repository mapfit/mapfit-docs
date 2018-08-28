# Create your first map
## Audience
This documentation is designed for people familiar with Swift programming and object-oriented programming concepts. You should also be familiar with [Mapfit](http://mapfit.com) from a user's point of view. There are many Swift tutorials available on the Web.

This conceptual documentation is designed to let you quickly start exploring and developing applications with the Mapfit iOS SDK. We also publish the Mapfit iOS Reference.
## Set up your environment
You will need to have Xcode installed on your machine in order to use Mapfit iOS SDK. You can obtain the latest version of Xcode from [here](https://developer.apple.com/xcode/) or from the Mac App Store.

### Cocoapods
Adding a map to your app is as simple as adding the following to your app’s podfile:

```
pod 'Mapfit'
```

Run pod install in your project's directory.
### Set your API Key
Now you must set your API key in order to be able to use the geocoding and polygon APIs. In your appDelegate, enter the key as seen below.

To get an API key see: [Get API Key](doc:get-api-key).
```swift
import Mapfit

@UIApplicationMain
class AppDelegate: UIResponder, UIApplicationDelegate {
    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplicationLaunchOptionsKey: Any]?) -> Bool {
      MFTManager.sharedManager.apiKey = "API_KEY"
      return true
    }
}
```


## Create your map
Next you can create a map instance with the following function.
```swift
let mapView = MFTMapView(frame: view.bounds)
```

## Add map to view
In order to actually add it to your view, add the following:
```swift
view.addSubview(mapView)
```

## Add a marker to your map

In order to add your first marker to the map, you must create a marker instance with the following function:
```swift
let marker = mapView.addMarker(position:  CLLocationCoordinate2D(latitude: 40.74699, longitude: -73.98742))
```

## Set meta data for your marker
You can set specific metadata for your marker as follows:
```swift
marker.title = "Mapfit"
marker.subtitle1 = "119 w 24th street"
marker.subtitle2 = "New York, NY"
```

## Draw a route on your map

This code snippet shows you how you can draw a route on top of your map.
```swift
 MFTDirections.sharedInstance.route(origin: nil, originAddress: "119 w 24th street new york, ny", destination: nil, destinationAddress: "33 west 3rd street new york", includesBuilding: false, directionsType: .walking) { (route, error) in
            
            if error == nil {
                if let route = route{
                    mapView.directionsOptions.drawRoute(route: route, completion: { (polyline, error) in
                        
                    })
                }
            }
        }
```