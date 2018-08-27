---
title: "Markers"
excerpt: ""
---
#Add a Marker with Coordinates
In order to add a [Marker](ref:marker) with a given set of geographical coordinates to the map, you must construct a marker instance with your input [LatLng](ref:latlng).
[block:code]
{
  "codes": [
    {
      "code": "// create marker\nmyMarker = mapfit.Marker([40.745934, -73.988280]);\n\n// add marker to map\nmap.addMarker(myMarker);",
      "language": "javascript"
    }
  ]
}
[/block]

[block:embed]
{
  "html": "<iframe height='350' scrolling='no' src='https://codepen.io/mapfit/embed/Qrgbej/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>",
  "url": "https://codepen.io/mapfit/embed/Qrgbej/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true",
  "title": "CodePen Embed - Mapfit Single Point Example V2.4",
  "favicon": "https://codepen.io/favicon.ico"
}
[/block]
#Add a Marker with a Street Address
In order to add a marker using an address string, you must construct a marker instance and then add the address property to your [Marker](ref:marker) object. The address will be geocoded and the marker will be positioned with the resulting coordinates. *Note*:  as this functionality relies on our geocoder, **adding a marker with a street address only works with an API Key**.
[block:code]
{
  "codes": [
    {
      "code": "//specify my API key\nmapfit.apikey = \"my_api_key\";\n\n// create marker\nmyMarker = mapfit.Marker();\n\n// set address property\nmyMarker.address = \"9 w 57th st, new york, ny\";\n\n// add marker to map\nmap.addMarker(myMarker);",
      "language": "javascript"
    }
  ]
}
[/block]
##Returning Promises for Marker Position
When using a geocoded marker, you'll need to return a promise to access information about the marker, to ensure the geocoding request completes prior to the request for marker data. In the example snippet below, we return the position and set the map center based on the marker's returned position from the geocoder.
[block:code]
{
  "codes": [
    {
      "code": "//add marker to the map\nmap.addMarker(myMarker).then(function(){\n  map.setCenter(myMarker.getPosition());  //set center on the geocoded marker's position\n});",
      "language": "javascript"
    }
  ]
}
[/block]

[block:embed]
{
  "html": "<iframe height='350' scrolling='no' src='https://codepen.io/mapfit/embed/XqabpJ/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>",
  "url": "https://codepen.io/mapfit/embed/XqabpJ/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true",
  "title": "CodePen Embed - Mapfit Single Point Geocoded Example V2.4",
  "favicon": "https://codepen.io/favicon.ico"
}
[/block]
#Choose a Category Marker
We have a wide selection of category icons to choose from for your marker. You can choose from any of the following markers.

To use Mapfit category markers, you must instantiate the Icon class with your selected icon name (via the `setIconUrl` method), and associate the instance with your marker (via the `setIcon` method) - as demonstrated below:
[block:code]
{
  "codes": [
    {
      "code": "// create icon\nlet myIcon = mapfit.Icon();\n\n// set icon category\nmyIcon.setIconUrl('arts');\n\n// assign icon to marker\nmyMarker.setIcon(myIcon);",
      "language": "javascript"
    }
  ]
}
[/block]

[block:embed]
{
  "html": "<iframe height='350' scrolling='no' src='https://codepen.io/mapfit/embed/bMrdrm/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>",
  "url": "https://codepen.io/mapfit/embed/bMrdrm/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true",
  "title": "CodePen Embed - Mapfit Category Icon Example V2.4",
  "favicon": "https://codepen.io/favicon.ico"
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d5bbf77-MarkerIcons-Docs.png",
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
#Adding a Custom Marker
If you'd like to use your own marker, you may do so by doing the following:
1. Create the Icon object.
2. Set icon image with either a custom image (by entering the url to your image) or by entering the name of one of our custom markers. 
3. Create your marker object by either passing in geographical coordinates or by adding an address attribute set to a string address. 
4. Add the icon to the marker object. 
5. Add your marker to the map.
[block:code]
{
  "codes": [
    {
      "code": "// create custom icon\nlet myCustomIcon = mapfit.Icon();\n\n// specify icon url or filepath\nmyCustomIcon.setIconUrl('http://cdn.stg.mapfit.com/v2-2/assets/images/markers/custom/example-custom-pin.png');\n\n// specify icon dimensions\nmyCustomIcon.setWidth(75);\nmyCustomIcon.setHeight(84);\n\n// create a marker\nlet marker = mapfit.Marker([40.745934, -73.988280]);\n\n// associate icon with marker\nmarker.setIcon(myCustomIcon);\n\n// add custom marker to map\nmap.addMarker(marker);",
      "language": "javascript"
    }
  ]
}
[/block]
To see the Marker methods, click [here](ref:marker)
[block:embed]
{
  "html": "<iframe height='350' scrolling='no' src='https://codepen.io/mapfit/embed/ZoJGKz/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>",
  "url": "https://codepen.io/mapfit/embed/ZoJGKz/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true",
  "title": "CodePen Embed - Mapfit Custom Icon Example V2.4",
  "favicon": "https://codepen.io/favicon.ico"
}
[/block]
#Adding Multiple Markers
Adding multiple markers can be handled the same as adding a single marker. You may, however, want to add your markers to a [Layer](ref:layer) for more dynamic control over setting the map center.
[block:code]
{
  "codes": [
    {
      "code": "   //create markers and add markers to map\n    let moma = mapfit.Marker([40.7620952,-73.9794267]);\n    let mad = mapfit.Marker([40.7634685,-73.9812614]);\n    map.addMarker(moma);\n    map.addMarker(mad);\n\n  // create layer with markers\n    let museums = mapfit.Layer();\n    museums.add(moma);\n    museums.add(mad);\n    \n   // add layer to map\n    map.addLayer(museums);\n   \n   // set center with layer and padding\n    map.setCenterWithLayer(museums, 90, 90); ",
      "language": "javascript"
    }
  ]
}
[/block]

[block:embed]
{
  "html": "<iframe height='350' scrolling='no' src='https://codepen.io/mapfit/embed/WJEvOL/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>",
  "url": "https://codepen.io/mapfit/embed/WJEvOL/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true",
  "title": "CodePen Embed - Mapfit Map - Multiple Points V2.4",
  "favicon": "https://codepen.io/favicon.ico"
}
[/block]