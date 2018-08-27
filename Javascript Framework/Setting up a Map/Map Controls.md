---
title: "Map Controls"
excerpt: ""
---
#Map View
When using Mapfit JS, there are parameters to control the look and feel of your map, which can be customized to fit your use case and brand. 


## Zoom Level
The default zoom level is: 18.
[block:code]
{
  "codes": [
    {
      "code": "// change the zoom level\nmap.setZoom(13);",
      "language": "javascript"
    }
  ]
}
[/block]
## Min and Max Zoom Levels
The min and max zoom levels constraint how far the user is able to zoom in or zoom out. The default min zoom level is: 1. The default max zoom level is: 23. Note that these are hard constraints; you may only change the min and max zoom levels between the values 1 and 23.
[block:code]
{
  "codes": [
    {
      "code": "// reduce how far the user can zoom in and out\n\n// change the min zoom level\nmap.setMinZoom(3);\n\n// change the min zoom level\nmap.setMaxZoom(15);",
      "language": "javascript"
    }
  ]
}
[/block]
## Map Center

The map center can be modified given geographical coordinate values (latitude and longitude) with the `setCenter` function. Alternatively, the center can be calculated and set given a [Layer](ref:layer) (including a [Polygon](ref:polygon) or [Polyline](ref:polyline), which are themselves layers) with the the `setCenterWithLayer` function. In the latter case, the fit bounds of the input layer are calculated and used to determine the map center.
[block:code]
{
  "codes": [
    {
      "code": "// set map center with coordinate\nmap.setCenter([40.743049, -74.004189]);\n\n//set map center with layer\nmap.setCenterWithLayer(myPolygon, 0, 0);",
      "language": "javascript"
    }
  ]
}
[/block]
To set the map center with a geocoded marker, you'll need to issue `setCenter` as a callback, after the marker is added to the map.
[block:code]
{
  "codes": [
    {
      "code": "// create marker\nmyMarker = mapfit.Marker();\n\n// geocode marker address\nmyMarker.address = \"9 w 57th st, new york, ny\";\n\n// set center using marker position\nmap.addMarker(myMarker).then(function(){\n  map.setCenter(myMarker.getPosition());  \n});",
      "language": "javascript"
    }
  ]
}
[/block]
#UI Buttons
The functions below allow you to enable or disable UI handlers on a map.
[block:embed]
{
  "html": "<iframe height='350' scrolling='no' src='https://codepen.io/mapfit/embed/QrgbXb/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>",
  "url": "https://codepen.io/mapfit/embed/QrgbXb/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true",
  "title": "CodePen Embed - Mapfit Buttons V2.4",
  "favicon": "https://codepen.io/favicon.ico"
}
[/block]
##Zoom Controls
Toggle the zoom control button. This button is **enabled** by default.
[block:code]
{
  "codes": [
    {
      "code": "// will create the zoom controls, taking a boolean value\n   map.setZoomControlVisibility(true); ",
      "language": "javascript"
    }
  ]
}
[/block]
##Recenter Button
Toggle the recenter button. On click, this button returns the map center to the last set map center. Generally used in conjunction with the pan gesture; if the user has panned to a different part of the map and would like to return to the initial view, the user can click the recenter button. This button is **disabled** by default.
[block:code]
{
  "codes": [
    {
      "code": " // will create the recenter button, taking a boolean value\n  map.setRecenterButtonEnabled(true);",
      "language": "javascript"
    }
  ]
}
[/block]
#Gestures
Below is a list of controls available when using our maps. Toggling these will either enable or disable these gestures.
[block:embed]
{
  "html": "<iframe height='350' scrolling='no' src='https://codepen.io/mapfit/embed/MGowMb/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>",
  "url": "https://codepen.io/mapfit/embed/MGowMb/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true",
  "title": "CodePen Embed - Mapfit Gestures V2.4",
  "favicon": "https://codepen.io/favicon.ico"
}
[/block]
##Pan
If enabled, the user will be able to pan (or drag) the map when clicking, holding and moving the cursor on desktop - or swiping on a trackpad or mobile device screen. If disabled, the user will not be able to change the map view or center with this gesture. This gesture is **enabled** by default.
[block:code]
{
  "codes": [
    {
      "code": "map.setPanEnabled(true);",
      "language": "javascript"
    }
  ]
}
[/block]
##Pinch
If enabled, the user will be able to zoom in and out on the the map with the pinch gesture - using two fingers moving towards each other or away from each other on a trackpad or mobile device screen. If disabled, the user will not be able to change the zoom level with this gesture. This gesture is **disabled** by default.
[block:code]
{
  "codes": [
    {
      "code": "map.setPinchEnabled(true);",
      "language": "javascript"
    }
  ]
}
[/block]
##Scroll Wheel
If enabled, the user can utilize a mouse scroll wheel to change the zoom level on the map. This gesture is **disabled** by default.
[block:code]
{
  "codes": [
    {
      "code": "map.setScrollWheelEnabled(true);",
      "language": "javascript"
    }
  ]
}
[/block]