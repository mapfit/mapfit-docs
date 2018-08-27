# Map View
## Map Center
### Get Center
```swift
mapView.getCenter()
```

### Set Center
```swift
mapView.setCenter(position: CLLocationCoordinate2D(latitude: 40, longitude: -73))

//center with animation
mapView.setCenter(position: CLLocationCoordinate2D(latitude: 40, longitude: -73), duration: 0.5)

```

### Set center with offset
```swift
mapView.setCenterWithOffset(latLng: CLLocationCoordinate2D(latitude: 40, longitude: -73), offsetX: 500, offsetY: 500, duration: 2)
```

### Re Center
```swift
mapView.reCenter()
```

## Map Tilt
### Get current tilt angle
```swift
 mapView.getTilt()
```

### Set tilt angle
```swift
mapView.setTilt(tiltValue: 4)

//Set tilt with animation
mapView.setTilt(tiltValue: 4, duration: 0.5)
```


## Map Zoom Level
### Get current zoom level
```swift
mapView.getZoom()
```

### Set zoom level
```swift
mapView.setZoom(zoomLevel: 4)

//set zoom with animation
mapView.setZoom(zoomLevel: 4, duration: 0.5)


```
### Set maximum zoom level
```swift
mapView.mapOptions.setMaxZoomLevel(zoomLevel: 13)
```
### Set minimum zoom level
```swift
mapView.mapOptions.setMinZoomLevel(zoomLevel: 4)
```


## Map Rotation
### Get current map rotation (compass direction)
```swift
mapView.getRotation()
```

### Set map rotation (compass direction)
```swift
mapView.setRotation(rotationValue: 4)

// Set Rotation with animation
mapView.setRotation(rotationValue: 4, durations: 0.5)
```


## Map Bounds
### Get current map bounds
```swift
 mapView.getLatLngBounds()
``` 

### Set map bounds
```swift
var builder = MFTLatLngBounds.Builder()

        builder.add(latLng: CLLocationCoordinate2D(latitude: 40.7368876593604, longitude: -73.9785409464787))
        builder.add(latLng: CLLocationCoordinate2D(latitude: 40.7313501345546, longitude: -73.982556292978))
        builder.add(latLng: CLLocationCoordinate2D(latitude:  40.7344347901369, longitude: -73.9899029597005))
        builder.add(latLng: CLLocationCoordinate2D(latitude: 40.7354082589172, longitude: -73.9898742137078))
        builder.add(latLng: CLLocationCoordinate2D(latitude: 40.7433247184166, longitude: -73.9840748526015))
        builder.add(latLng: CLLocationCoordinate2D(latitude:  40.7419697680819, longitude:-73.9808596541241))
        builder.add(latLng: CLLocationCoordinate2D(latitude: 40.739498439778, longitude: -73.9826675979102))
        builder.add(latLng:  CLLocationCoordinate2D(latitude: 40.7375539536562, longitude: -73.9780522649762))
        builder.add(latLng: CLLocationCoordinate2D(latitude: 40.7368876593604, longitude: -73.9785409464787))

let bounds = builder.build()
let paddingPercentage = Float(1)

mapView.setLatLngBounds(bounds: bounds, padding: paddingPercentage)

// With Centering Animation

mapView.setLatLngBounds(bounds: bounds, padding: paddingPercentage, duration: 2)
```

### Get latitude and longitude from screen postion
```swift
let latLng = mapview.screenPositionToLatLng(position)
```
           
### Get Screen position from latitude and longitude
```swift
let point = mapview.LatLngToScreenPosition(latLng)
```