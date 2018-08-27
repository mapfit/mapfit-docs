---
title: "Markers"
excerpt: ""
---
#Add a Marker with coordinates
After instantiating your [MapView](https://mapfit-android.readme.io/v1.0.0/reference#mapview), you can add a [Marker](https://mapfit-android.readme.io/v1.0.0/reference#marker-1) as below. See [MarkerOptions](ref:markeroptions-1).
[block:code]
{
  "codes": [
    {
      "code": "mapView.getMapAsync(onMapReadyCallback = object : OnMapReadyCallback {\n    override fun onMapReady(mapfitMap: MapfitMap) {\n    \n        val position = LatLng(40.729913, -74.000664)\n        mapfitMap.addMarker(\n            MarkerOptions()\n              .position(position)\n              .icon(MapfitMarker.ARTS))\n                \n    }\n})",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapView.getMapAsync(new OnMapReadyCallback() {\n    @Override\n    public void onMapReady(MapfitMap mapfitMap) {\n\n        LatLng position = new LatLng(40.729913, -74.000664);\n        mapfitMap.addMarker(new MarkerOptions()\n                        .position(position)\n                        .icon(MapfitMarker.ARTS);\n\n  \t}\n});",
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
        "https://files.readme.io/0688a95-marker-ss.png",
        "marker-ss.png",
        1772,
        3401,
        "#9dadb3"
      ]
    }
  ]
}
[/block]
#Add a marker with a street address
Alternatively, you can add a [MapView](https://mapfit-android.readme.io/v1.0.0/reference#mapview) to the map with a street address. This call uses Mapfit Geocoder API. 
[block:code]
{
  "codes": [
    {
      "code": "val markerOptions = MarkerOptions()\n            .streetAddress(\"111 Macdougal Street, New York, NY\", true)\n            .addBuildingPolygon(true)\n            .icon(MapfitMarker.ARTS)\n\nval marker = mapfitMap.addMarker(markerOptions)\n\n// if the marker is being geocoded, add OnMarkerAddedCallback which will be \n// invoked when marker is visible on the map.\nmapfitMap.addMarker(\n            markerOptions,\n                object : OnMarkerAddedCallback {\n                    override fun onMarkerAdded(marker: Marker) {\n\t\t\t\t\t\t\t\t\t\t \n                    }\n\n                    override fun onError(exception: Exception) {\n\n                    }\n                }\n            )",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "MarkerOptions markerOptions = new MarkerOptions()\n                .streetAddress(\"111 Macdougal Street, New York, NY\", true)\n                .addBuildingPolygon(true)\n                .icon(MapfitMarker.ARTS);\n\nMarker marker = mapfitMap.addMarker(markerOptions);\n\n// if the marker is being geocoded, add OnMarkerAddedCallback which will be \n// invoked when marker is visible on the map.\nmapfitMap.addMarker(markerOptions,\n                new OnMarkerAddedCallback() {\n                    @Override\n                    public void onMarkerAdded(@NotNull Marker marker) {\n\n                    }\n\n                    @Override\n                    public void onError(@NotNull Exception exception) {\n\n                    }\n                });",
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
        "https://files.readme.io/53606fd-marker-building.png",
        "marker-building.png",
        1772,
        3401,
        "#b2b2b0"
      ]
    }
  ]
}
[/block]
#Choose a category marker
We have a wide selection of category icons to choose from for your [Marker](ref:marker-1). You can choose from any of the following markers from [MapfitMarker](ref:mapfitmarker-1).
You must specify which icon you'd like to use as below.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4b3987c-MarkerIcons-Docs.png",
        "MarkerIcons-Docs.png",
        1028,
        1430,
        "#ebf0fb"
      ],
      "sizing": "80"
    }
  ]
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "marker.setIcon(MapfitMarker.CAFE)\n",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "marker.setIcon(MapfitMarker.CAFE);\n",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
#Adding a custom marker
If you'd like to use your own icon, you may do so by using the following methods.
[block:code]
{
  "codes": [
    {
      "code": "// with a drawable resource\nmarker.setIcon(R.drawable.ic_custom_marker)\n\n// with a drawable object\nval drawable: Drawable = getCustomDrawable()\nmarker.setIcon(drawable)\n\n// with a url that directs to your custom image\nmarker.setIcon(\"YOUR_MARKER_ICON_URL\")\n\n// with a bitmap object\nmarker.setIcon(bitmap)",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "// with a drawable resource\nmarker.setIcon(R.drawable.ic_custom_marker);\n\n// with a drawable object\nDrawable drawable = getCustomDrawable();\nmarker.setIcon(drawable);\n\n// with a url that directs to your custom image\nmarker.setIcon(\"YOUR_MARKER_ICON_URL\");\n\n// with a bitmap object\nmarker.setIcon(bitmap);",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
# Marker click listener
Set your [OnMarkerClickListener](ref:onmarkerclicklistener-1) to listen [Marker](ref:marker-1) click events on the map.
[block:code]
{
  "codes": [
    {
      "code": " mapfitMap.setOnMarkerClickListener(object:OnMarkerClickListener{\n            override fun onMarkerClicked(marker: Marker) {\n                \n            }\n        })",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.setOnMarkerClickListener(new OnMarkerClickListener() {\n            @Override\n            public void onMarkerClicked(@NotNull Marker marker) {\n                \n            }\n        });",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]