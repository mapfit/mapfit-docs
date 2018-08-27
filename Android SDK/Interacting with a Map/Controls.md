---
title: "Controls"
excerpt: ""
---
Below is a list of controls available when using our maps. Toggling these will either enable or disable these gestures.

#Pan
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.getMapOptions().isPanEnabled = false",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.getMapOptions().setPanEnabled(false);",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
#Pinch (Zoom)
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.getMapOptions().isPinchEnabled = false\n",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.getMapOptions().setPinchEnabled(false);",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
#Rotate
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.getMapOptions().isRotateEnabled = false\n",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.getMapOptions().setRotateEnabled(false); \n",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
#Tilt
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.getMapOptions().isTiltEnabled = false\n",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.getMapOptions().setTiltEnabled(false);",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
#Gestures
Pan, pinch, rotation, and tilting can be enabled or disabled at once as below.
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.getMapOptions().gesturesEnabled = false\n",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.getMapOptions().setGesturesEnabled(false);\n",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
#3D Buildings
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.getMapOptions().is3dBuildingsEnabled = true",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.getMapOptions().set3dBuildingsEnabled(true);\n",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]