---
title: "Map View"
excerpt: ""
---
#Map Center
###Get center
[block:code]
{
  "codes": [
    {
      "code": "val centerLatLng = mapfitMap.getCenter()\n",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "LatLng centerLatLng = mapfitMap.getCenter();\n",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
###Set center
[block:code]
{
  "codes": [
    {
      "code": "val latLng = LatLng(40.744043, -73.993209)\n\nmapfitMap.setCenter(latLng)\n\n// alternatively, you can animate centering if you pass duration in milliseconds\nmapfitMap.setCenter(latLng, 200)\n\n// you can also set map center with a horizontal and vertical offset\nmapfitMap.setCenterWithOffset(\n                        latLng, // position that offset will be applied to\n                        300, // horizontal offset in pixels\n                        0, // vertical offset in pixels\n                        300 // duration for the centering animation\n                    )",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "LatLng latLng = new LatLng(40.744043, -73.993209);\n\nmapfitMap.setCenter(latLng);\n\n// alternatively, you can animate centering if you pass duration in milliseconds\nmapfitMap.setCenter(latLng, 200);\n\n// you can also set map center with a horizontal and vertical offset\nmapfitMap.setCenterWithOffset(latLng /* position that offset will be applied to */,\n                        300 /* horizontal offset in pixels */,\n                        0 /* vertical offset in pixels */,\n                        300 /* duration for the centering animation */);",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
###Re-center
You can re-center the map to the last position it was centered at as below.
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.reCenter()\n",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.reCenter();\n",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
#Map Tilt
###Get current tilt angle
[block:code]
{
  "codes": [
    {
      "code": "val tiltAngle: Float = mapfitMap.getTilt() // tilt is in radians",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "Float tiltAngle = mapfitMap.getTilt();  // tilt is in radians\n",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
###Set tilt angle
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.setTilt(0f) // in radians\n\n// alternatively, you can animate tilting if you pass duration in milliseconds\nmapfitMap.setTilt(0f, 200)",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.setTilt(0f); // tilt is in radians\n\n// alternatively, you can animate tilting if you pass duration in milliseconds\nmapfitMap.setTilt(0f, 200);",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
#Map Zoom Level
###Get zoom level
[block:code]
{
  "codes": [
    {
      "code": "val currentZoomLevel = mapfitMap.getZoom()\n",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "Float currentZoomLevel = mapfitMap.getZoom();\n",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
###Set zoom level
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.setZoom(16f)\n\n// alternatively, you can animate zooming if you pass duration in milliseconds\nmapfitMap.setZoom(16f, 200)",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.setZoom(16f);\n\n// alternatively, you can animate zooming if you pass duration in milliseconds\nmapfitMap.setZoom(16f, 200);",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
###Set minimum zoom level
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.getMapOptions().setMinZoom(5f)\n",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.getMapOptions().setMinZoom(5f);\n",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
###Set maximum zoom level
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.getMapOptions().setMaxZoom(15f)\n",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.getMapOptions().setMaxZoom(15f);\n",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
#Map Rotation
###Get current map rotation (compass direction)
[block:code]
{
  "codes": [
    {
      "code": "val currentRotation: Float = mapfitMap.getRotation() // rotation is in radians\n",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "Float currentRotation = mapfitMap.getRotation(); // rotation is in radians\n",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
###Set map rotation (compass direction)
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.setRotation(1f) // rotation is in radians\n\n// alternatively, you can animate rotation if you pass duration in milliseconds\nmapfitMap.setRotation(1f, 200)",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.setRotation(1f); // rotation is in radians\n\n// alternatively, you can animate rotation if you pass duration in milliseconds\nmapfitMap.setRotation(1f, 200);",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
#Map Bounds
###Get current map bounds
[block:code]
{
  "codes": [
    {
      "code": "val currentMapBounds: LatLngBounds = mapfitMap.getLatLngBounds()\n",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "LatLngBounds currentMapBounds = mapfitMap.getLatLngBounds();\n",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
###Set map bounds
[block:code]
{
  "codes": [
    {
      "code": "val boundsBuilder: LatLngBounds.Builder = LatLngBounds.Builder()\nboundsBuilder.include(LatLng(40.744043, -73.993209))\nboundsBuilder.include(LatLng(40.6902223, -73.9770368))\nboundsBuilder.include(LatLng(40.7061326, -74.000769))\n\nval bounds = boundsBuilder.build()\n\nmapfitMap.setLatLngBounds(\n            bounds,\n            0.1f, // optional padding percentage. the padding width will be 10% of the screen size\n            500 // optional animation duration. if set, map will be centered with an animation\n        )",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "LatLngBounds.Builder boundsBuilder = new LatLngBounds.Builder();\nboundsBuilder.include(new LatLng(40.744043, -73.993209));\nboundsBuilder.include(new LatLng(40.6902223, -73.9770368));\nboundsBuilder.include(new LatLng(40.7061326, -74.000769));\n\nLatLngBounds bounds = boundsBuilder.build();\n\nmapfitMap.setLatLngBounds(bounds,\n            0.1f, /* optional padding percentage. the padding width will be 10% of the screen size */\n            500 /* optional animation duration. if set, map will be centered with an animation */);",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]