---
title: "Themes"
excerpt: ""
---
#Setting a map theme

# Theme options

We currently have 3 [MapTheme](ref:maptheme) available for use.

### Day Theme
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.getMapOptions().theme = MapTheme.MAPFIT_DAY\n",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.getMapOptions().setTheme(MapTheme.MAPFIT_DAY);\n",
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
        "https://files.readme.io/f8f68c0-theme-day-ss.png",
        "theme-day-ss.png",
        1772,
        3401,
        "#9eaeb2"
      ]
    }
  ]
}
[/block]
### Night Theme
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.getMapOptions().theme = MapTheme.MAPFIT_NIGHT\n",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.getMapOptions().setTheme(MapTheme.MAPFIT_NIGHT);",
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
        "https://files.readme.io/7ba746e-theme-night-ss.png",
        "theme-night-ss.png",
        1772,
        3401,
        "#121b24"
      ],
      "sizing": "smart",
      "border": false
    }
  ]
}
[/block]
### Grayscale Theme
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.getMapOptions().theme = MapTheme.MAPFIT_GRAYSCALE\n",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.getMapOptions().setTheme(MapTheme.MAPFIT_MAPFIT_GRAYSCALE);",
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
        "https://files.readme.io/309fbab-theme-grayscale-ss.png",
        "theme-grayscale-ss.png",
        1772,
        3401,
        "#adadad"
      ]
    }
  ]
}
[/block]
###Initializing MapView With A Default Theme
You also can initialize the [MapView](ref:mapview) with default themes.
[block:code]
{
  "codes": [
    {
      "code": " mapView.getMapAsync(\n            mapTheme = MapTheme.MAPFIT_GRAYSCALE,\n            onMapReadyCallback = object : OnMapReadyCallback {\n                override fun onMapReady(mapfitMap: MapfitMap) {\n                    // mapfitMap is ready to be used!\n                }\n            })",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": " mapView.getMapAsync(MapTheme.MAPFIT_GRAYSCALE,\n                new OnMapReadyCallback() {\n                    @Override\n                    public void onMapReady(@NotNull MapfitMap mapfitMap) {\n                         // mapfitMap is ready to be used!\n                    }\n                });",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
## Custom Theme
You can set your own theme with your YAML file as below.
[block:code]
{
  "codes": [
    {
      "code": "// if the file is in assets folder\nmapfitMap.getMapOptions().customTheme = \"sample.yaml\"\n\n// if the file is in another folder\nmapfitMap.getMapOptions().customTheme = \"file://data/.../sample.yaml\"\n\n// if the file is hosted in web\nmapfitMap.getMapOptions().customTheme = \"https://mywebsite.com/sample.yaml\"",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "// if the file is in assets folder\nmapfitMap.getMapOptions().setCustomTheme(\"sample.yaml\");\n\n// if the file is in another folder\nmapfitMap.getMapOptions().setCustomTheme(\"file://data/.../sample.yaml\");\n\n// if the file is hosted in web\nmapfitMap.getMapOptions().setCustomTheme(\"https://mywebsite.com/sample.yaml\");",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
###Initializing MapView With A Custom Theme
You can also initialize [MapView](ref:mapview) with a URL or file path of your YAML file.
[block:code]
{
  "codes": [
    {
      "code": "mapView.getMapAsync(\n            \"YOUR_YAML_FILE_URL_OR_PATH\",\n            onMapReadyCallback = object : OnMapReadyCallback {\n                override fun onMapReady(mapfitMap: MapfitMap) {\n                   // mapfitMap is ready to be used!\n                }\n            })",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapView.getMapAsync(\"YOUR_YAML_FILE_URL_OR_PATH\",\n                new OnMapReadyCallback() {\n                    @Override\n                    public void onMapReady(@NotNull MapfitMap mapfitMap) {\n                        // mapfitMap is ready to be used!\n                    }\n                });",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]