# Tracking Map Events
Below is a list of events that you can listen for and handle programmatically. See [Map](ref:mapfitmap) for more detail.

# #Map Events
### Single Tap
###### Javascript
```javascript
 // capture user single tap/clicks on map view
    map.on('click', function () {
      console.log("map single click")
    })
```

### Double Tap
###### Javascript
```javascript
// capture user double tap/clicks on map view
    map.on('dblclick', function () {
      console.log("map double click")
    })
```

### Pinch (Zoom)
###### Javascript
```javascript
// capture user zoom changes within map view
    map.on('zoom', function () {
      console.log("map zoom")
    })
```

#Marker, Polyline, & Polygon Events
### Click
###### Javascript
```javascript
 // capture user single tap/clicks on marker
      marker.on('click', function (e) {
        console.log('marker click ')
      })
```

##Double Click
###### Javascript
```javascript
// capture user double tap/clicks on marker
      marker.on('dblclick', function (e) {
        console.log('marker double click ')
      })
```

## Mouse Down
###### Javascript
```javascript
// capture user initiation of a click event, pushing the mouse button on the marker
      marker.on('mousedown', function (e) {
        console.log('marker mouse down')
      })
```

### Mouse Up

###### Javascript
```javascript
// capture user release of a click event on the marker
      marker.on('mouseup', function (e) {
        console.log('marker mouse up ')
      })
```

### Mouse Over
###### javascript
```javascript
// capture user hover over the marker bounds
      marker.on('mouseover', function (e) {
        console.log('marker mouse over ')
      })
```

### Mouse Out
###### Javascript
```javascript
//capture user exit of hover event on marker
      marker.on('mouseout', function (e) {
        console.log('marker mouse out ')
      })
```