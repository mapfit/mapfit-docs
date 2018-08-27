---
title: "Polylines"
excerpt: ""
---
To add a polyline to your map, you will need to use define the coordinates of each point of the polyline. Those points will need to then be saved into one array which will serve as the polyline. See [Polyline](ref:polyline) for more detail. 
[block:code]
{
  "codes": [
    {
      "code": "//create polyline\nlet myPolyline = mapfit.Polyline([[40.729877, -74.000588],\n                 [40.729171, -74.001191],\n                 [40.728103, -74.002099],\n                 // ... additional points\n                 [40.74398, -73.993293]]);\n\n//add polyline to map\nmapfitMap.addPolyline(myPolyline);\n\n//set map center to polyline\nmap.setCenterWithLayer(myPolyline, 0, 0);",
      "language": "javascript"
    }
  ]
}
[/block]
In the code sample below, you can see a polyline drawn on a map.
[block:embed]
{
  "html": "<iframe height='350' scrolling='no' src='https://codepen.io/mapfit/embed/ELXVYw/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>",
  "url": "https://codepen.io/mapfit/embed/ELXVYw/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true",
  "title": "CodePen Embed - Mapfit Polyline Example V2.4",
  "favicon": "https://codepen.io/favicon.ico"
}
[/block]
To see the Polyline methods, click [here](ref:polyline) .