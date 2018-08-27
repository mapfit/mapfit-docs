---
title: "UI Features"
excerpt: ""
---
We provide onscreen buttons which control certain aspects of the map.

#Zoom Controls
Turning this on places a zoom in / zoom out button on the bottom right of the map. 
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.getMapOptions().isZoomControlVisible = true\n",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.getMapOptions().setZoomControlsEnabled(true);\n",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
#Compass
Turning this on places a compass button on the bottom right of the map. Tapping this button allows you to reset rotation to the north.
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.getMapOptions().isCompassButtonVisible = true\n",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.getMapOptions().setCompassButtonEnabled(true);\n",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
#Recenter
Turning this on places a re-center button on the bottom right of the map. Tapping this button allows you to recenter the map to the position previously set as the center.
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.getMapOptions().isRecenterButtonVisible = true\n",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.getMapOptions().setRecenterButtonEnabled(true);\n",
      "language": "text",
      "name": "java"
    }
  ]
}
[/block]