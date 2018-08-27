---
title: "Themes"
excerpt: ""
---
#Setting a map theme

## Theme options

Setting the map theme is an option on the map. Theme options include: `day`, `night`, or `grayscale`.  The default theme is 'day'. To set the theme of your map, pass the theme parameter during map initialization. 

Alternatively, you can include your own design using a custom yaml file. We've got you covered with [Mapfit Paint](https://mapfit.com/paint), a custom theme builder.

###Day Theme

[block:code]
{
  "codes": [
    {
      "code": "let map = mapfit.MapView('mapfit', {theme: 'day'});",
      "language": "javascript"
    }
  ]
}
[/block]

[block:embed]
{}
[/block]
###Night Theme

[block:code]
{
  "codes": [
    {
      "code": "let map = mapfit.MapView('mapfit', {theme: 'night'});",
      "language": "javascript"
    }
  ]
}
[/block]

[block:embed]
{
  "html": "<iframe height='350' scrolling='no' src='https://codepen.io/mapfit/embed/LmLVKm/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>",
  "url": "https://codepen.io/mapfit/embed/LmLVKm/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true",
  "title": "CodePen Embed - Mapfit Map - Night Theme V2.4",
  "favicon": "https://codepen.io/favicon.ico"
}
[/block]
###Grayscale Theme


[block:code]
{
  "codes": [
    {
      "code": "let map = mapfit.MapView('mapfit', {theme: 'grayscale'});",
      "language": "javascript"
    }
  ]
}
[/block]

[block:embed]
{
  "html": "<iframe height='350' scrolling='no' src='https://codepen.io/mapfit/embed/mLwJZv/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>",
  "url": "https://codepen.io/mapfit/embed/mLwJZv/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true",
  "title": "CodePen Embed - Mapfit Map - Grayscale Theme V2.4",
  "favicon": "https://codepen.io/favicon.ico"
}
[/block]
###Custom Theme
[block:code]
{
  "codes": [
    {
      "code": "let map = mapfit.MapView('mapfit', {\n        theme: 'https://raw.githubusercontent.com/mapfit/map-themes/master/mapfit-grayscale.yaml?token=AB1OJ6EFIeMpTK2ZzYL198iXHyMZG1urks5a9JSpwA%3D%3D'\n      });\n",
      "language": "javascript"
    }
  ]
}
[/block]

[block:embed]
{
  "html": "<iframe height='350' scrolling='no' src='https://codepen.io/mapfit/embed/KRvPaE/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>",
  "url": "https://codepen.io/mapfit/embed/KRvPaE/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true",
  "title": "CodePen Embed - Adding a custom yaml file V2.4",
  "favicon": "https://codepen.io/favicon.ico"
}
[/block]