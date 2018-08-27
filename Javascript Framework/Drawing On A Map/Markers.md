# Markers
### Add a Marker with Coordinates
In order to add a [Marker](ref:marker) with a given set of geographical coordinates to the map, you must construct a marker instance with your input [LatLng](ref:latlng).

```javascript
// create marker
myMarker = mapfit.Marker([40.745934, -73.988280]);

// add marker to map
map.addMarker(myMarker);
```

<iframe height='350' scrolling='no' src='https://codepen.io/mapfit/embed/Qrgbej/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>

## Add a Marker with a Street Address
In order to add a marker using an address string, you must construct a marker instance and then add the address property to your [Marker](ref:marker) object. The address will be geocoded and the marker will be positioned with the resulting coordinates. *Note*:  as this functionality relies on our geocoder, **adding a marker with a street address only works with an API Key**.

```javascript
//specify my API key
mapfit.apikey = "my_api_key";

// create marker
myMarker = mapfit.Marker();

// set address property
myMarker.address = "9 w 57th st, new york, ny";

// add marker to map
map.addMarker(myMarker);
```

## Returning Promises for Marker Position
When using a geocoded marker, you'll need to return a promise to access information about the marker, to ensure the geocoding request completes prior to the request for marker data. In the example snippet below, we return the position and set the map center based on the marker's returned position from the geocoder.

```javascript
//add marker to the map
map.addMarker(myMarker).then(function(){
  map.setCenter(myMarker.getPosition());  //set center on the geocoded marker's position
});
```

<iframe height='350' scrolling='no' src='https://codepen.io/mapfit/embed/XqabpJ/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>

## Choose a Category Marker
We have a wide selection of category icons to choose from for your marker. You can choose from any of the following markers.

To use Mapfit category markers, you must instantiate the Icon class with your selected icon name (via the `setIconUrl` method), and associate the instance with your marker (via the `setIcon` method) - as demonstrated below:

```javascript
// create icon
let myIcon = mapfit.Icon();

// set icon category
myIcon.setIconUrl('arts');

// assign icon to marker
myMarker.setIcon(myIcon);
```


<iframe height='350' scrolling='no' src='https://codepen.io/mapfit/embed/bMrdrm/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>

![](https://files.readme.io/d5bbf77-MarkerIcons-Docs.png)

## Adding a Custom Marker
If you'd like to use your own marker, you may do so by doing the following:
1. Create the Icon object.
2. Set icon image with either a custom image (by entering the url to your image) or by entering the name of one of our custom markers. 
3. Create your marker object by either passing in geographical coordinates or by adding an address attribute set to a string address. 
4. Add the icon to the marker object. 
5. Add your marker to the map.
```javascript
// create custom icon
let myCustomIcon = mapfit.Icon();

// specify icon url or filepath
myCustomIcon.setIconUrl('http://cdn.stg.mapfit.com/v2-2/assets/images/markers/custom/example-custom-pin.png');

// specify icon dimensions
myCustomIcon.setWidth(75);
myCustomIcon.setHeight(84);

// create a marker
let marker = mapfit.Marker([40.745934, -73.988280]);

// associate icon with marker
marker.setIcon(myCustomIcon);

// add custom marker to map
map.addMarker(marker);
```

To see the Marker methods, click [here](ref:marker)
<iframe height='350' scrolling='no' src='https://codepen.io/mapfit/embed/ZoJGKz/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>

## Adding Multiple Markers
Adding multiple markers can be handled the same as adding a single marker. You may, however, want to add your markers to a [Layer](ref:layer) for more dynamic control over setting the map center.
```javascript
   //create markers and add markers to map
    let moma = mapfit.Marker([40.7620952,-73.9794267]);
    let mad = mapfit.Marker([40.7634685,-73.9812614]);
    map.addMarker(moma);
    map.addMarker(mad);

  // create layer with markers
    let museums = mapfit.Layer();
    museums.add(moma);
    museums.add(mad);
    
   // add layer to map
    map.addLayer(museums);
   
   // set center with layer and padding
    map.setCenterWithLayer(museums, 90, 90); 
```

<iframe height='350' scrolling='no' src='https://codepen.io/mapfit/embed/WJEvOL/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>