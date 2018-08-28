# Directions
## Directions API Quick Start Guide - iOS

Mapfit Directions API is a service to obtain directions between locations. You can use Directions API directly from the iOS SDK.

## Pre-requirements

This tutorial assumes that you have already implemented Mapfit Maps SDK in your project. If you haven't implemented it yet, see [Getting Started].


## Getting directions
	
To obtain directions, you can use the `MFTDirections` class as below. Specify an origin and destination address or coordinate to get the `Route`.

```swift
     MFTDirections.sharedInstance.route(origin: nil, originAddress: "119 w 24th street new york, ny", destination: nil, destinationAddress: "33 west 3rd street new york", includesBuilding: false, directionsType: .walking) { (route, error) in
            
        }
```

Instead of street address, you can also pass coordinates as follow:

```swift
     MFTDirections.sharedInstance.route(origin: CLLocationCoordinate2D(latitude: 40.744257, longitude: -73.992954), originAddress: nil, destination: CLLocationCoordinate2D(latitude: 40.730610, longitude: -73.935242), destinationAddress: nil, includesBuilding: false, directionsType: .walking) { (route, error) in

        }
```




## Drawing directions on Map
	
You can also draw the route simply with `MFTDirectionsOptions`. 

```swift
    mapView.directionsOptions.setOrigin(CLLocationCoordinate2D(latitude:40.7484, longitude: -73.992954))
    mapView.directionsOptions.setDestination(CLLocationCoordinate2D(latitude: 40.744257, longitude: -73.992954))
    mapView.directionsOptions.showDirections { (polyline, error) in
            
        }
```


### Setting directions type

You can specify the type of directions you would like to get as driving, walking or cycling. Default directions type is driving.

```swift
    mapView.directionsOptions.setType(.walking)
    mapView.directionsOptions.showDirections { (polyline, error) in
            
        }
```
![](https://files.readme.io/878ccad-Directions.png)