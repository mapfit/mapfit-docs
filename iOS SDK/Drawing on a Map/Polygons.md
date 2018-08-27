---
title: "Polygons"
excerpt: ""
---
To add a polygon to your map, you will need to define the coordinates of each point of the polygon and add it to an instance of the [MFTPolygonOptions] class. After the creation of the polygon options class, you can add a polygon to your map. In the code sample below, you can see 8 clearly defined lat/long points for a polygon.

```swift
let polygonOptions = MFTPolygonOptions()
polygonOptions.addPoints([[CLLocationCoordinate2D(latitude: 40.7368876593604, longitude: -73.9785409464787),
                                     CLLocationCoordinate2D(latitude: 40.7313501345546, longitude: -73.982556292978),
                                     CLLocationCoordinate2D(latitude:  40.7344347901369, longitude: -73.9899029597005),
                                     CLLocationCoordinate2D(latitude: 40.7354082589172, longitude: -73.9898742137078),
                                     CLLocationCoordinate2D(latitude: 40.7433247184166, longitude: -73.9840748526015),
                                     CLLocationCoordinate2D(latitude:  40.7419697680819, longitude:-73.9808596541241),
                                     CLLocationCoordinate2D(latitude: 40.739498439778, longitude: -73.9826675979102),
                                     CLLocationCoordinate2D(latitude: 40.7375539536562, longitude: -73.9780522649762),
                                     CLLocationCoordinate2D(latitude: 40.7368876593604, longitude: -73.9785409464787)
                                     ]])

let polygon = mapView.addPolygon(options: polygonOptions)
```

When rendered on a map, it will look like this.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/327ab62-Polygon.png",
        "Polygon.png",
        810,
        1614,
        "#c4c8c9"
      ]
    }
  ]
}
[/block]
There is no limit on the number of polygons you can have on a map.

#Styling a Polygon
You can style a polygon through it's [MFTPolygonOptions](ref:mftpolygonoptions) object. The following attributes can be edited: 
- Fill color
- Stroke color
- Stroke width
- Stroke outline color
- Stroke outline width
- Join type

Changing styling attributes are optional.

##Color
Color attributes are set with a hex string in the format `#AARRGGBB`. The first two digits will represent the alpha and are optional.

##Width
You can set the pixel width attributes with positive integers. The default width of the stroke outline width is `0`.

##Join type
You can change the shape of intersection between two lines. You can define it as a miter, bevel or round. Rounding is done by adding extra points. See reference for [MFTLineJoinType](ref:mftlinejointype).

##The code
The code below demonstrates how to change all of the style attributes.

##Before Polygon Creation
It is advisable to create a polygon options class with your desired attributes before creating the polygon. 
```swift
         let polygonOptions = MFTPolygonOptions()
         polygonOptions.setStrokeOutlineWidt(8)
         polygonOptions.setStrokeWidth(3)
         polygonOptions.setStrokeColor("#32b3ff")
         polygonOptions.setStrokeOutlineColor("#5932b3ff")
         polygonOptions.setFillColor("#2732b3ff")
         polygonOptions.setLineJoinType(.miter)
         polygonOptions.setLineCapType(.round)
         let polygon = mapView.addPolygon(options: polygonOptions)
```
##After Polygon Creation
If you need to edit the attributes at a later time, you can access them directly from the polygon class.
```swift
         polygon.strokeOutlineWidth = 8
         polygon.strokeWidth = 3
         polygon.strokeColor = "#32b3ff"
         polygon.strokeOutlineColor = "#5932b3ff"
         polygon.fillColor = "#2732b3ff"
         polygon.lineJoinType = .round
```

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9167189-polygonCustom.png",
        "polygonCustom.png",
        810,
        1614,
        "#bdc2c6"
      ]
    }
  ]
}
[/block]