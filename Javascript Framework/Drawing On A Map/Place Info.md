---
title: "Place Info"
excerpt: ""
---
You can define the information such as title and description of your location, which will appear in place of your marker icon, on click. If this information is not defined, the place info title will default to show the address (if set) or the latitude, longitude (if the address is not set). See [PlaceInfo](ref:infocard) for more detail.

Note: the Place Info description and title can be customized with html within the input string, as shown below.
[block:code]
{
  "codes": [
    {
      "code": "//add place info to an existing marker\nlet placeInfo = mapfit.PlaceInfo();\nplaceInfo.setTitle('Artichoke Basille\\'s Pizza & Brewery');\nplaceInfo.setDescription('<p>111 Macdougal St (btwn Bleeker & W 3rd St)</br>Pizza, Italian</p>');\nmyMarker.setPlaceInfo(placeInfo);\n",
      "language": "javascript"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "warning",
  "body": "",
  "title": "Click on marker to view Place Info window."
}
[/block]

[block:embed]
{
  "html": "<iframe height='350' scrolling='no' src='https://codepen.io/mapfit/embed/LmLpPm/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>",
  "url": "https://codepen.io/mapfit/embed/LmLpPm/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true",
  "title": "CodePen Embed - Mapfit Place Info Example V2.4",
  "favicon": "https://codepen.io/favicon.ico"
}
[/block]