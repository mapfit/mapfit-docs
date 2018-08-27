---
title: "Polygons"
excerpt: ""
---
To add a polygon to your map, you will need to define the coordinates of each point of the polygon. In the code sample below, you can see clearly defined geographical coordinates for a polygon. See [Polygon](ref:polygon) for more detail.
[block:code]
{
  "codes": [
    {
      "code": "//create polygon\nlet gramercy = mapfit.Polygon([[40.7368876593604,-73.9785409464787],\n                               [40.7313501345546,-73.982556292978],\n                               // ... additional points\n                               [40.7375539536562,-73.9780522649762],\n                               [40.7368876593604,-73.9785409464787]]);\n\n//add polygon to map\nmap.addPolygon(gramercy);\n\n//set map center to polygon\nmap.setCenterWithLayer(gramercy, 0, 0);",
      "language": "javascript"
    }
  ]
}
[/block]
When rendered on a map, it will look like this.
[block:embed]
{
  "html": "<iframe height='350' scrolling='no' src='https://codepen.io/mapfit/embed/ZoybzL/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>",
  "url": "https://codepen.io/mapfit/embed/ZoybzL/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true",
  "title": "CodePen Embed - Mapfit Polygon Example V2.4",
  "favicon": "https://codepen.io/favicon.ico"
}
[/block]
There is no limit on the number of polygons you can have on a map. Note that if polygons overlap, the fill colors will get darker on the overlapped regions (due to the default opacity setting).

To see the Polygon methods, click [here](ref:polygon).