---
title: "UI Features"
excerpt: ""
---
We provide onscreen buttons which control certain aspects of the map.

#Recenter
Turning this on places a recenter button on the bottom right of the map. 
```swift
mapView.mapOptions.setRecenterVisibility(true)
```


#Zoom Controls
Turning this on places a zoom in / zoom out button on the bottom right of the map. 

```swift
mapView.mapOptions.setCompassVisibility(true)
```

#Compass
Turning this on places a compass button on the bottom right of the map. Tapping this button allows you to recenter the map to the device's current location as well as reset to due north.

```swift
mapView.mapOptions.setZoomControlVisibility(true)
```


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/229dd23-Controls.png",
        "Controls.png",
        810,
        1614,
        "#b1c2c7"
      ]
    }
  ]
}
[/block]