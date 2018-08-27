---
title: "Place Info"
excerpt: ""
---
To display a PlaceInfo you need to specify a title or two subtitles for your [Marker](https://mapfit-android.readme.io/v1.0.0/reference#marker-1). If you set any, when [Marker](https://mapfit-android.readme.io/v1.0.0/reference#marker-1) is clicked, a  PlaceInfo will be displayed. 
You can add a title and subtitles as below.
[block:code]
{
  "codes": [
    {
      "code": " mapfitMap.addMarker(MarkerOptions()\n            .position(LatLng())\n            .title(\"Artichoke Basille's Pizza & Brewery\")\n            .subtitle1(\"111 Macdougal St (btwn Bleecker & W 3rd St)\")\n            .subtitle2(\"Pizza, Italian\"))",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": " mapfitMap.addMarker(new MarkerOptions()\n            .position(new LatLng())\n            .title(\"Artichoke Basille's Pizza & Brewery\")\n            .subtitle1(\"111 Macdougal St (btwn Bleecker & W 3rd St)\")\n            .subtitle2(\"Pizza, Italian\"));",
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
        "https://files.readme.io/94cad69-place-info-ss.png",
        "place-info-ss.png",
        1772,
        3401,
        "#b2b2b0"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]
#Listen to Place Info Clicks
Click events are can be listened by setting an [OnPlaceInfoClickListener](ref:onplaceinfoclicklistener) as below. 
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.setOnPlaceInfoClickListener(object : MapfitMap.OnPlaceInfoClickListener {\n            override fun onPlaceInfoClicked(marker: Marker) {\n                \n            }\n        })",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.setOnPlaceInfoClickListener(new MapfitMap.OnPlaceInfoClickListener() {\n    @Override\n    public void onPlaceInfoClicked(@NotNull Marker marker) {\n        \n    }\n});",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
#Custom Place Info View
If you'd like to use your [PlaceInfo](ref:placeinfo) for your [Marker](ref:marker-1), you can do it by setting a [PlaceInfoAdapter](ref:placeinfoadapter) using [MapfitMap](ref:mapfitmap) as below. 
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.setPlaceInfoAdapter(object : MapfitMap.PlaceInfoAdapter {\n    override fun getPlaceInfoView(marker: Marker): View {\n\n      // invoked when the marker is clicked\n      // here you can inflate a view that is related to the marker\n      return TextView(context)\n    }\n})",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.setPlaceInfoAdapter(new MapfitMap.PlaceInfoAdapter() {\n    @NotNull\n    @Override\n    public View getPlaceInfoView(@NotNull Marker marker) {\n      // invoked when the marker is clicked\n      // here you can inflate a view that is related to the marker\n      return new TextView(context);\n    }\n});\n",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]