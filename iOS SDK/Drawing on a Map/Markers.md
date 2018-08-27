---
title: "Markers"
excerpt: ""
---
#Add a marker with position

In order to add your first marker to the map, you must create an instance of MFTMarkerOptions. After setting the position property in the marker options you can draw the marker on the map.

```swift
let markerOptions = MFTMarkerOptions()
markerOptions.setPosition(CLLocationCoordinate2D(latitude: 40.74699, longitude: -73.98742))
let marker = mapView.addMarker(options: markerOptions)
```


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4f8fbd6-DefaultMaker.png",
        "DefaultMaker.png",
        810,
        1614,
        "#afc1c8"
      ]
    }
  ]
}
[/block]
## Add a marker with a street address

```swift
markerOptions.setStreetAddress(streetAddress: "119 w 24th street new york, NY", geocode: true)
let marker = mapView.addMarker(address: "119 west 24th street NY, NY") { (marker, error) in

mapView.addMarker(markerOptions) { (marker, error) in

} 


        }
```

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f8147a7-Marker_with_Street.png",
        "Marker with Street.png",
        810,
        1614,
        "#c7c7c5"
      ]
    }
  ]
}
[/block]
#Choose a category marker
We have a wide selection of category icons to choose from for your marker. You can choose from any of the following markers.

You must specify which icon you'd like to use in the following method:
```swift
markerOptions.setIcon(.cafe)
```
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/08224eb-MarkerIcons-Docs.png",
        "MarkerIcons-Docs.png",
        1028,
        1430,
        "#ebf0fb"
      ],
      "border": false,
      "sizing": "80"
    }
  ]
}
[/block]
#Adding a custom marker
If you'd like to use your own marker, you may do so by using the following method and substituting a url that directs to your own custom marker:
```swift
markerOptions.setIcon("http://cdn.stg.mapfit.com/v2/assets/images/markers/custom/example-custom-pin.png")
```
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e82d041-customMarker.png",
        "customMarker.png",
        810,
        1614,
        "#b0c2c8"
      ]
    }
  ]
}
[/block]