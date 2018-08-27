---
title: "Polylines"
excerpt: ""
---
To add a polyline to your map, you will need to define the coordinates of each point of the polyline and add it to an instance of the [MFTPolylineOptions] class. After the creation of the polyline options class, you can add a polyline to your map. Those points will need to then be saved into one array which will serve as the polyline. 

In the code sample below, you can see a polyline drawn on a map.

```swift
let polylineOptions = MFTPolylineOptions()
polylineOptions.addPoints([[CLLocationCoordinate2D(latitude:40.729877, longitude:-74.000588),
                              CLLocationCoordinate2D(latitude:40.729171, longitude:-74.001191),
                              CLLocationCoordinate2D(latitude:40.728103, longitude:-74.002099),
                              CLLocationCoordinate2D(latitude:40.728248, longitude:-74.002396),
                              CLLocationCoordinate2D(latitude:40.728382, longitude:-74.002663),
                              CLLocationCoordinate2D(latitude:40.72845, longitude:-74.002793),
                              CLLocationCoordinate2D(latitude:40.728519, longitude:-74.002755),
                              CLLocationCoordinate2D(latitude:40.728691, longitude:-74.002671),
                              CLLocationCoordinate2D(latitude:40.728908, longitude:-74.002564),
                              CLLocationCoordinate2D(latitude:40.729602, longitude:-74.002244),
                              CLLocationCoordinate2D(latitude:40.729694, longitude:-74.002198),
                              CLLocationCoordinate2D(latitude:40.729881, longitude:-74.002091),
                              CLLocationCoordinate2D(latitude:40.730461, longitude:-74.001755),
                              CLLocationCoordinate2D(latitude:40.730579, longitude:-74.001687),
                              CLLocationCoordinate2D(latitude:40.73059, longitude:-74.001679),
                              CLLocationCoordinate2D(latitude:40.730827, longitude:-74.001549),
                              CLLocationCoordinate2D(latitude:40.73101, longitude:-74.001442),
                              CLLocationCoordinate2D(latitude:40.731063, longitude:-74.001412),
                              CLLocationCoordinate2D(latitude:40.731124, longitude:-74.001374),
                              CLLocationCoordinate2D(latitude:40.731338, longitude:-74.001214),
                              CLLocationCoordinate2D(latitude:40.731643, longitude:-74.001),
                              CLLocationCoordinate2D(latitude:40.731704, longitude:-74.000954),
                              CLLocationCoordinate2D(latitude:40.731769, longitude:-74.000908),
                              CLLocationCoordinate2D(latitude:40.731853, longitude:-74.000847),
                              CLLocationCoordinate2D(latitude:40.732315, longitude:-74.000512),
                              CLLocationCoordinate2D(latitude:40.732929, longitude:-74.000069),
                              CLLocationCoordinate2D(latitude:40.733169, longitude:-73.999886),
                              CLLocationCoordinate2D(latitude:40.733573, longitude:-73.999589),
                              CLLocationCoordinate2D(latitude:40.733661, longitude:-73.999527),
                              CLLocationCoordinate2D(latitude:40.73376, longitude:-73.999451),
                              CLLocationCoordinate2D(latitude:40.734088, longitude:-73.999222),
                              CLLocationCoordinate2D(latitude:40.734134, longitude:-73.999192),
                              CLLocationCoordinate2D(latitude:40.734214, longitude:-73.999131),
                              CLLocationCoordinate2D(latitude:40.734783, longitude:-73.998711),
                              CLLocationCoordinate2D(latitude:40.734989, longitude:-73.998566),
                              CLLocationCoordinate2D(latitude:40.735031, longitude:-73.998543),
                              CLLocationCoordinate2D(latitude:40.735389, longitude:-73.998276),
                              CLLocationCoordinate2D(latitude:40.73603, longitude:-73.997803),
                              CLLocationCoordinate2D(latitude:40.736293, longitude:-73.997612),
                              CLLocationCoordinate2D(latitude:40.736667, longitude:-73.997338),
                              CLLocationCoordinate2D(latitude:40.737361, longitude:-73.996842),
                              CLLocationCoordinate2D(latitude:40.737934, longitude:-73.996422),
                              CLLocationCoordinate2D(latitude:40.738044, longitude:-73.996338),
                              CLLocationCoordinate2D(latitude:40.738685, longitude:-73.9958729999999),
                              CLLocationCoordinate2D(latitude:40.739273, longitude:-73.9954459999999),
                              CLLocationCoordinate2D(latitude:40.73986, longitude:-73.9950189999999),
                              CLLocationCoordinate2D(latitude:40.74044, longitude:-73.9945909999999),
                              CLLocationCoordinate2D(latitude:40.741031, longitude:-73.9941639999999),
                              CLLocationCoordinate2D(latitude:40.741615, longitude:-73.9937369999999),
                              CLLocationCoordinate2D(latitude:40.742233, longitude:-73.9932939999999),
                              CLLocationCoordinate2D(latitude:40.7429, longitude:-73.9928059999999),
                              CLLocationCoordinate2D(latitude:40.743568, longitude:-73.9923179999999),
                              CLLocationCoordinate2D(latitude:40.744186, longitude:-73.9918749999999),
                              CLLocationCoordinate2D(latitude:40.745384, longitude:-73.9947059999999),
                              CLLocationCoordinate2D(latitude:40.744766, longitude:-73.9951629999999),
                              CLLocationCoordinate2D(latitude:40.74398, longitude:-73.9932939999999)]])

let polyline = mapview.addPolyline(options: polylineOptions)
```
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/377811a-Polyline.png",
        "Polyline.png",
        810,
        1614,
        "#cacbc9"
      ]
    }
  ]
}
[/block]
There is no limit on the number of polylines you can have on a map.

#Styling a Polyline
You can style a polyline through it's [MFTPolylineOptions](ref:mftpolylineoptions) object. The following attributes can be edited: 
- Stroke color
- Stroke width
- Stroke outline color
- Stroke outline width
- Cap type


Changing styling attributes are optional.

##Color
Color attributes are set with a hex string in the format `#AARRGGBB`. The first two digits will represent the alpha and are optional.

##Width
You can set the pixel width attributes with positive integers. The default width of the stroke outline width is `0`.

##Cap type
You can change the shape of the end of the polylines. You can define it as a bound, square or round. See reference for [MFTLineCapType](ref:mftlinecaptype).

##Join type
You can change the shape of intersection between two lines. You can define it as a miter, bevel or round. Rounding is done by adding extra points. See reference for [MFTLineJoinType](ref:mftlinejointype).


##The code
The code below demonstrates how to change all of the style attributes.

##Before Polyline Creation
It is advisable to create a polyline options class with your desired attributes before creating the polyline. 
```swift
         let polylineOptions = MFTPolylineOptions()
         polylineOptions.setStrokeOutlineWidt(8)
         polylineOptions.setStrokeWidth(3)
         polylineOptions.setStrokeColor("#32b3ff")
         polylineOptions.setStrokeOutlineColor("#5932b3ff")
         polylineOptions.setFillColor("#2732b3ff")
         polylineOptions.setLineJoinType(.miter)
         polylineOptions.setLineCapType(.round)
         let polyline = mapView.addPolyline(options: polylineOptions)
```
##After Polyline Creation
If you need to edit the attributes at a later time, you can access them directly from the Polyline class.
```swift
         polyline.strokeOutlineWidth = 8
         polyline.strokeWidth = 3
         polyline.strokeColor = "#32b3ff"
         polyline.strokeOutlineColor = "#5932b3ff"
         polyline.fillColor = "#2732b3ff"
         polyline.lineJoinType = .round
```

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f7ad5ac-polylineCustom.png",
        "polylineCustom.png",
        810,
        1614,
        "#c3c4c5"
      ]
    }
  ]
}
[/block]