# Events
## Track click events

In `viewDidLoad` set delegates
```swift
        mapView.singleTapGestureDelegate = self
        mapView.doubleTapGestureDelegate = self
        mapView.longPressGestureDelegate = self
        mapView.panDelegate = self
        mapView.pinchDelegate = self
        mapView.rotateDelegate = self        
        mapview.polygonSelectDelegate = self
        mapview.polylineSelectDelegate = self
        mapview.markerSelectDelegate = self
        mapview.mapOptions.userLocationDelegate = self

```

### Single Tap Listener
```swift
extension ViewController: MapSingleTapGestureDelegate {
    func mapView(_ view: MFTMapView, recognizer: UIGestureRecognizer, shouldRecognizeSingleTapGesture location: CGPoint) -> Bool {
        
    }
    
    func mapView(_ view: MFTMapView, recognizer: UIGestureRecognizer, didRecognizeSingleTapGesture location: CGPoint) {
        
    }
}
```
### Double Tap Listener
```swift
extension ViewController: MapDoubleTapGestureDelegate {
    func mapView(_ view: MFTMapView, recognizer: UIGestureRecognizer, shouldRecognizeDoubleTapGesture location: CGPoint) -> Bool {
        
    }
    
    func mapView(_ view: MFTMapView, recognizer: UIGestureRecognizer, didRecognizeDoubleTapGesture location: CGPoint) {
        
    }
}
```
### Long Press Listener 
```swift
extension ViewController : MapLongPressGestureDelegate {
    func mapView(_ view: MFTMapView, recognizer: UIGestureRecognizer, shouldRecognizeLongPressGesture location: CGPoint) -> Bool {
       
    }
    
    func mapView(_ view: MFTMapView, recognizer: UIGestureRecognizer, didRecognizeLongPressGesture location: CGPoint) {
        
    }
}
```

### Pan Listener
```swift
extension ViewController : MapPanGestureDelegate {
    func mapView(_ view: MFTMapView, didPanMap displacement: CGPoint) {
        
    }
}
```

### Pinch Listener
```swift
extension ViewController : MapPinchGestureDelegate {
    func mapView(_ view: MFTMapView, didPinchMap location: CGPoint) {
        
    }
}
```

### Rotate Listener
```swift
extension ViewController : MapRotateGestureDelegate {
    func mapView(_ view: MFTMapView, didRotateMap location: CGPoint) {
        
    }
}
```

### Marker
```swift
extension ViewController: MapMarkerSelectDelegate {
    func mapView(_ view: MFTMapView, didSelectMarker marker: MFTMarker, atScreenPosition position: CGPoint) {
        
    }
}
```

### Polygon
```swift
extension ViewController : MapPolygonSelectDelegate {
    func mapView(_ view: MFTMapView, didSelectPolygon polygon: MFTPolygon, atScreenPosition position: CGPoint) {
        
    } 
}
```

### Polyline
```swift
extension ViewController : MapPolylineSelectDelegate {
    func mapView(_ view: MFTMapView, didSelectPolyline polygon: MFTPolyline, atScreenPosition position: CGPoint) {
        
    }
}
```

### User Location
```swift
extension ViewController : LocationUpdateDelegate {
    func didRecieveLocationUpdate(_ location: CLLocation) {

    }
}
```