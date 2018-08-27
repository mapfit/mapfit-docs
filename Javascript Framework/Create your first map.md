# Create your first map
## Introduction

This tutorial shows you how to add a simple Mapfit map with a marker to your web page. It suits those with beginner or intermediate knowledge of HTML and CSS, and a little knowledge of Javascript. You should also be familiar with [Mapfit](http://mapfit.com) from a user's point of view. 

This conceptual documentation is designed to let you quickly start exploring and developing applications with the Mapfit JavaScript Library. We also publish the Mapfit [JavaScript API Reference](/reference#javascript).
### Getting Started
There are five steps to creating a Mapfit map with a marker on your web page: 

1. Get an API key
2. Create an HTML page
3. Add the map library
4. Create the map
5. Add a map marker

### Step 1: Get an API key
This section explains how to authenticate your app with Mapfit using your own API key in order to build a map.

[Follow these steps to get an API key.](doc:get-api-key) 

### Step 2: Create an HTML page
Below is the code for a basic HTML web page:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Mapfit Map</title>
</head>
<body>
  <div id="mapfit">
  </div>
</body>
</html>
```

Here you are creating the `div` in which your map will be inserted into. You can give the `div` any ID you would like. In this example, we call it `mapfit`.

### Step 3: Add the map library
This section shows you how to load the Mapfit library files into your web page to render your base map. 

- Add the `http://cdn.mapfit.com/v2-4/assets/css/mapfit.css` to the head
- Add the JavaScript file `http://cdn.mapfit.com/v2-4/assets/js/mapfit.js`  right before the end of the body tag

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Mapfit Map</title>
    <link href="http://cdn.mapfit.com/v2-4/assets/css/mapfit.css" rel='stylesheet' />
</head>
<body>
    <div id="mapfit">
     	 <--! your map will be loaded here -->
  	</div>
  	
    <script src="http://cdn.mapfit.com/v2-4/assets/js/mapfit.js"></script>
    <script>
      // javascript from steps 4 & 5 below will go here
    </script>
</body>
</html>
```

### Step 4:  Create the Map
Between your `<script>` tags:
- Add your Mapfit API key, substituting `MY_API_KEY` [in the code below] with the API key you received from Step 1.
- Create your map, specifying the div name where your map will live (in this example, the id is 'mapfit') and your desired map theme (i.e. 'day','night', or 'grayscale') when initializing `mapfit.MapView`.
- Optionally set the zoom level - otherwise, the default zoom level for your map will be 18.

```javascript
// add api key
mapfit.apikey = "MY_API_KEY";

// draw map
let map = mapfit.MapView('mapfit', {theme: 'day'});

//set zoom
map.setZoom(13); 
```


Your map should now be appearing and look like the following:

<iframe height='350' scrolling='no' src='https://codepen.io/mapfit/embed/bMrdpj/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>


### Step 5: Add a marker
Extending on the code to create your map from Step 3, to add a marker to your map, add the following code (between your `<script>` tags):
```javascript
// create marker
position = mapfit.LatLng([40.745934, -73.988280]);
myMarker = mapfit.Marker(position);

//set the map center on marker position
map.setCenter(position);

//add marker to map
map.addMarker(myMarker);
```

Now your map should have a marker located at the input coordinates.

<iframe height='350' scrolling='no' src='https://codepen.io/mapfit/embed/vjgzPr/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>