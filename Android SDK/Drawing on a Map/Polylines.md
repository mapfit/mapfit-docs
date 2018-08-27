---
title: "Polylines"
excerpt: ""
---
#Add a Polyline
To add a [Polyline](https://mapfit-android.readme.io/v1.0.0/reference#polyline) to your map, you will need a `List<LatLng>` object which includes the coordinates of your line.
Once you have your `List<LatLng>`, you can add it to your map as below. See [PolylineOptions](ref:polylineoptions).
[block:code]
{
  "codes": [
    {
      "code": "val linePoints: List<LatLng> = getLinePoints()\n\nval polyline = mapfitMap.addPolyline(PolylineOptions().points(linePoints))\n",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "List<LatLng> linePoints = getLinePoints();\n  \nPolyline polyline = mapfitMap.addPolyline(new PolylineOptions().points(linePoints));",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/639af95-polyline-ss.png",
        "polyline-ss.png",
        1772,
        3401,
        "#b4b5b3"
      ]
    }
  ]
}
[/block]
There is no limit on the number of polylines you can have on a map. Note that, adding an excessive amount of polylines can reduce performance.

# Extend Polyline
You can add points to the [Polyline](ref:polyline) after you create it as below.
[block:code]
{
  "codes": [
    {
      "code": "// you can add a sigle LatLng\npolyline.addPoints(LatLng(40.744023, -73.993150))\n\n// you can add multiple LatLngs\npolyline.addPoints(LatLng(40.74402, -73.9931),\n                   LatLng(40.74403, -73.9932),\n                   LatLng(40.74404, -73.9933))",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "// you can add a sigle LatLng\npolyline.addPoints(new LatLng(40.744023, -73.9931));\n\n// you can add multiple LatLngs\npolyline.addPoints(new LatLng(40.74402, -73.9932),\n                   new LatLng(40.74403, -73.9933),\n                   new LatLng(40.74404, -73.9934));",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
#Styling a Polyline
You can style a polyline trough it's [PolylineOptions](ref:polylineoptions) object. You can change a polyline's
- Stroke color
- Stroke width
- Stroke outline color
- Stroke outline width
- Join type
- Cap type

Changing styling attributes are optional. The attributes that aren't changed will stay as default.

##Color
Color attributes are set via hex string with format `#AARRGGBB` where first two digits are representing alpha and optional.

##Width
You can set width attributes with positive integer values as pixels. The default width of the stroke outline width is `0`.

##Join type
You can change the type of outlining line's joining. You can define it as bound, bevel or round. Rounding is done by adding extra points. See reference for [JoinType](ref:jointype).

##Cap type
You can change the type of the caps of the line. You can define it as bound, square or round. 
Rounding is done by adding extra points. See reference for [CapType](ref:captype)

##Draw order
You can change the draw order of a [Polyline](ref:polyline) to set its z-depth. The value must be an integer.

##The code
The code below demonstrates how to change all of the style attributes.
[block:code]
{
  "codes": [
    {
      "code": " val polyline = mapfitMap.addPolyline(\n                    PolylineOptions()\n                        .points(line)\n                        .strokeWidth(3)\n                        .strokeOutlineWidth(8)\n                        .strokeColor(\"#4353ff\")\n                        .strokeOutlineColor(\"#4c4353ff\")\n                        .lineJoinType(JoinType.ROUND)\n                        .drawOrder(600)\n                        .lineCapType(CapType.ROUND)\n                )\n\n// after initializing the polyline, you can change the style for each attribute like below\npolyline.strokeWidth = 10",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "Polyline polyline = mapfitMap.addPolyline(new PolylineOptions()\n                .points(line)\n                .strokeWidth(3)\n                .strokeOutlineWidth(8)\n                .strokeColor(\"#4353ff\")\n                .strokeOutlineColor(\"#4c4353ff\")\n                .lineJoinType(JoinType.ROUND)\n                .drawOrder(600)\n                .lineCapType(CapType.ROUND));\n\n// after initializing the polyline, you can change the style for each attribute like below\npolyline.setStrokeWidth(10);",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
This is how the polyline looks like after styling.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a0e2b0f-styled-polyline.png",
        "styled-polyline.png",
        1772,
        3401,
        "#b0b0b1"
      ]
    }
  ]
}
[/block]