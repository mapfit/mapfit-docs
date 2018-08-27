# Migrating from Google Maps
![](https://files.readme.io/c282839-MigratingToMapfit.png)

🎉 🎉 🎉 Congratulations on taking your first step towards mapping excellence! We know switching frameworks can be difficult so we created this readme to ease your migration. Whether you're programming in javascript for web, kotlin for android or swift for iOS, the snippets below will have your map up and running in no time.

Looking for something specific? Check out the table of contents on the right!  


# Web

## Import Mapfit Web
```html
<script src="http://cdn.mapfit.com/v2-4/assets/js/mapfit.js"></script>
```
## Replace the API Key Web
#### Google
##### google_maps_api.xml
```html
<script>
src="https://maps.googleapis.com/maps/api/js?key="Your-API-Key"&callback=initMap"
</script>
```

#### Mapfit
```html
<script>
mapfit.apikey = "YOUR-API-KEY"
</script>
```

## Replace the Map Web
#### Google
```html
<html lang="en">
  <head>
    <title>Simple Map</title>
    <meta name="viewport" content="initial-scale=1.0">
    <meta charset="utf-8">
    <style>
      /* Always set the map height explicitly to define the size of the div
       * element that contains the map. */
      #map {
        height: 100%;
      }
      /* Optional: Makes the sample page fill the window. */
      html, body {
        height: 100%;
        margin: 0;
        padding: 0;
      }
    </style>
  </head>
  <body>
    <div id="map"></div>
    <script>
      var map;
      function initMap() {
        map = new google.maps.Map(document.getElementById('map'), {
          center: {lat: -34.397, lng: 150.644},
          zoom: 8
        });
      }
    </script>
    <script src="https://maps.googleapis.com/maps/api/js?key=&callback=initMap"
    async defer></script>
  </body>
</html>
```

#### Mapfit
```html
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">
        <title>Mapfit Map</title>
        <link href="http://cdn.mapfit.com/v2-4/assets/css/mapfit.css" rel='stylesheet' />
        <link rel="stylesheet" href="./reset.css">
    </head>
    <body>
        <div id="mapfit"></div>
        <script src="http://cdn.mapfit.com/v2-4/assets/js/mapfit.js"></script>
        <script>
                var map;
                //mapfit.apikey = "YOUR-API-KEY"
                  map = mapfit.MapView('mapfit', {
                    theme: 'day',
                    center: [-34.397,150.644],
                    zoom: 8
                  });
              </script>
    </body>
</html>
```

## Replace a Marker Web
#### Google
```html
<html lang="en">
  <head>
    <title>Simple Map</title>
    <meta name="viewport" content="initial-scale=1.0">
    <meta charset="utf-8">
    <style>
      /* Always set the map height explicitly to define the size of the div
       * element that contains the map. */
      #map {
        height: 100%;
      }
      /* Optional: Makes the sample page fill the window. */
      html, body {
        height: 100%;
        margin: 0;
        padding: 0;
      }
    </style>
  </head>
  <body>
    <div id="map"></div>
    <script>
      var map;
      function initMap() {
        map = new google.maps.Map(document.getElementById('map'), {
          center: {lat: -34.397, lng: 150.644},
          zoom: 8
        });
        
        //Add a marker
        var location = {lat: -25.344, lng: 131.036};
        var marker = new google.maps.Marker({position: location, map: map});
        
      }
    </script>
    <script src="https://maps.googleapis.com/maps/api/js?key=&callback=initMap"
    async defer></script>
  </body>
</html>
```

#### Mapfit
```html
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">
        <title>Mapfit Map</title>
        <link href="http://cdn.mapfit.com/v2-4/assets/css/mapfit.css" rel='stylesheet' />
        <link rel="stylesheet" href="./reset.css">
    </head>
    <body>
        <div id="mapfit"></div>
        <script src="http://cdn.mapfit.com/v2-4/assets/js/mapfit.js"></script>
        <script>
                var map;
                  mapfit.apikey = "YOUR-API-KEY"
                  map = mapfit.MapView('mapfit', {
                    theme: 'day',
                    center: [-34.397,150.644],
                    zoom: 8
                  });

                  // Add a Marker
                  myMarker = mapfit.Marker([-25.344, 131.036]);
                  map.addMarker(myMarker);

              </script>
    </body>
</html>
```
## Replacing a Route Web
#### Google
```html
<html>
    <head>
      <meta name="viewport" content="initial-scale=1.0, user-scalable=no">
      <meta charset="utf-8">
      <title>Directions service</title>
      <style>
        /* Always set the map height explicitly to define the size of the div
         * element that contains the map. */
        #map {
          height: 100%;
        }
        /* Optional: Makes the sample page fill the window. */
        html, body {
          height: 100%;
          margin: 0;
          padding: 0;
        }
      </style>
    </head>
    <body>
      <div id="map"></div>
      <script>
        function initMap() {
          var directionsService = new google.maps.DirectionsService;
          var directionsDisplay = new google.maps.DirectionsRenderer;
          var map = new google.maps.Map(document.getElementById('map'), {
            zoom: 7,
            center: {lat: 41.85, lng: -87.65}
          });
          directionsDisplay.setMap(map);
            calculateAndDisplayRoute(directionsService, directionsDisplay);
        }
  
        function calculateAndDisplayRoute(directionsService, directionsDisplay) {
          directionsService.route({
            origin: "119 w 24th street ny NY",
            destination: "81 pearl street brooklyn ny",
            travelMode: 'DRIVING'
          }, function(response, status) {
            if (status === 'OK') {
              directionsDisplay.setDirections(response);
            } else {
              window.alert('Directions request failed due to ' + status);
            }
          });
        }
      </script>
      <script async defer
      src="https://maps.googleapis.com/maps/api/js?key=&callback=initMap">
      </script>
    </body>
  </html>
```

#### Mapfit
```html
<html lang="en">
        <head>
            <meta charset="UTF-8">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
            <meta http-equiv="X-UA-Compatible" content="ie=edge">
            <title>Mapfit Map</title>
            <link href="https://cdn.mapfit.com/v2-4/assets/css/mapfit.css" rel='stylesheet' />
        </head>
        <body>
            <div id="mapfit" style="width: 100%; height: 100%;"></div>
            <script src="https://cdn.mapfit.com/v2-4/assets/js/mapfit.js"></script>
            <script>
              mapfit.apikey = "YOUR-API-KEY";
              let key = "YOUR-API-KEY"
              let map = mapfit.MapView('mapfit', {theme: 'day'})
        
                  let directionsReq = new mapfit.Directions(key, "https://api.mapfit.com/v2");
        
                  let encodedRoute;
              
                  let pointsArray
                  // start marker
                  let startMarkerIcon = mapfit.Icon();
                  startMarkerIcon.setIconUrl('commercial');
                  let startMarker = mapfit.Marker();
                  startMarker.address = '119 West 24th Street, New York, NY';
                  startMarker.setIcon(startMarkerIcon);
                  map.addMarker(startMarker)
                  // end marker 
                  let endMarker = mapfit.Marker();
                  endMarker.address = '81 Pearl St, Brooklyn, NY';
                  map.addMarker(endMarker)
                  directionsReq.route('119 West 24th Street, New York, NY', '81 Pearl St, Brooklyn, NY', 'driving')
                    .then(function(data) {
                      encodedRoute = data.trip.legs[0].shape;
                      pointsArray = decodePolyline(encodedRoute)
                      let directionPolyline = mapfit.Polyline(pointsArray)
                      map.addPolyline(directionPolyline)
                      map.setCenterWithLayer(directionPolyline, 10, 40);
                    })
              
                  function decodePolyline(encoded) {
                      let polyLineArrayCompiled = [];
                      var index = 0,
                          len = encoded.length;
                      var lat = 0,
                          lng = 0;
                      while (index < len) {
                          var b, shift = 0,
                              result = 0;
                          do {
                              b = encoded.charAt(index++).charCodeAt(0) - 63;
                              result |= (b & 0x1f) << shift;
                              shift += 5;
                          } while (b >= 0x20);
        
                          var dlat = ((result & 1) != 0 ? ~(result >> 1) : (result >> 1));
                          lat += dlat;
                          shift = 0;
                          result = 0;
        
                          do {
                              b = encoded.charAt(index++).charCodeAt(0) - 63;
                              result |= (b & 0x1f) << shift;
                              shift += 5;
                          } while (b >= 0x20);
                          var dlng = ((result & 1) != 0 ? ~(result >> 1) : (result >> 1));
                          lng += dlng;
        
                          polyLineArrayCompiled.push([(lat / 1E6), (lng / 1E6)])
                      }
                    return polyLineArrayCompiled
                  }
            </script>
        </body>
        </html>
```


# iOS
## Replace the Cocoapod in the Podfile
#### Google
```
pod 'GoogleMaps' 
```

#### Mapfit

```
pod 'Mapfit' 
```

## Replace your API Key in the AppDelegate
#### Google
###### Swift
```Swift
GMSServices.provideAPIKey("YOUR-API-KEY")
```

#### Mapfit
###### Swift
```Swift
MFTManager.sharedManager.apiKey = "YOUR-API-KEY"
```

## Replace the Map iOS
#### Google
###### Swift
```Swift
    let camera = GMSCameraPosition.camera(withLatitude: -33.86, longitude: 151.20, zoom: 6.0)
    let mapView = GMSMapView.map(withFrame: CGRect.zero, camera: camera)
    view = mapView
```

#### Mapfit
###### Swift
```Swift
   let mapView = MFTMapView(frame: self.view.bounds)
   view = mapView
```

## Replace a Marker iOS
#### Google
###### Swift
```Swift
    // Create a marker
    let marker = GMSMarker()
        
    // Custom marker styling
    marker.icon = UIImage(named: "custom-icon")!
        
    // Assign a position
    marker.position = CLLocationCoordinate2D(latitude: -33.86, longitude: 151.20)
        
    // Assign custom data
    marker.title = "Sydney"
    marker.snippet = "Australia"
        
    // Add to the MapView
    marker.map = mapView
```

#### Mapfit
###### Swift
```Swift
    // Create a options for your marker
    let markerOptions = MFTMarkerOptions()
        
    // Custom marker styling
    markerOptions.setIcon(UIImage(named: "custom-icon")!)
        
    // Assign a position
    marker.position = CLLocationCoordinate2D(latitude: -33.86, longitude: 151.20)
        
    // Assign custom data
     markerOptions.setTitle("Sydney")
     markerOptions.setSubTitle1("Australia")
        
    // Add to the MapView
     mapView.addMarker(markerOptions) { (marker, error) in }
```

## Replace a Route iOS
#### Google
###### Swift
```Swift
    //Set Origin and Destination
     let originMarker = GMSMarker()
     let destinationMarker = GMSMarker()
        
     //Set postion for markers
      originMarker.position = CLLocationCoordinate2D(latitude: -32.86, longitude: 151.20)
      destinationMarker.position = CLLocationCoordinate2D(latitude: -30.86, longitude: 149.10)

     //Assign Map
      originMarker.map = mapView
      destinationMarker.map = mapView
        
     //Request Route   
      let origin = "\(originMarker.position.latitude),\(originMarker.position.longitude)"
      let destination = "\(destinationMarker.position.latitude),\(destinationMarker.position.longitude)"
        
      let config = URLSessionConfiguration.default
      let session = URLSession(configuration: config)
        
      let url = URL(string: "https://maps.googleapis.com/maps/api/directions/json?origin=\(origin)&destination=\(destination)&sensor=false&mode=driving&key=AIzaSyAIxFxztbSzpQ29eLU3ZbchxHH78NfJRNE")!
        
        let task = session.dataTask(with: url, completionHandler: {
            (data, response, error) in
            if error != nil {
                print(error!.localizedDescription)
            }else{
                do {
                    if let json : [String:Any] = try JSONSerialization.jsonObject(with: data!, options: .allowFragments) as? [String: Any]{
                        
                        let routes = json["routes"] as? [Any]
                        let overview_polyline = routes?[0] as? [String:Any]
                        let polyString = overview_polyline?["points"] as?String
                        
                        //Draw path on map
                        let path = GMSPath(fromEncodedPath: polyString!)
                        let polyline = GMSPolyline(path: path)
                        polyline.strokeWidth = 3.0
                        polyline.map = mapView // Your map view
                    }
                    
                }catch{
                    print("error in JSONSerialization")
                }
            }
        })
        task.resume()
```

#### Mapfit
###### Swift
```Swift
        //Create options classes for annotations
        let polylineOptions = MFTPolylineOptions()
        let originMarkerOptions = MFTMarkerOptions()
        let destinationMarkerOptions = MFTMarkerOptions()
        
        //Set origin and destination positions
        let origin = CLLocationCoordinate2D(latitude: -32.86, longitude: 151.20)
        let destination = CLLocationCoordinate2D(latitude: -30.86, longitude: 149.10)
        
        originMarkerOptions.setPosition(position: origin, reverseGeocode: false)
        destinationMarkerOptions.setPosition(position: destination, reverseGeocode: false)
        
        mapView.directionsOptions.setOrigin(origin)
        mapView.directionsOptions.setDestination(destination)
        mapView.directionsOptions.setType(.driving)
        
        //add annotations to the map
        mapView.addMarker(originMarkerOptions) { (marker, error) in }
        mapView.addMarker(destinationMarkerOptions) { (marker, error) in }
        mapView.directionsOptions.showDirections(options: polylineOptions) { (polyline, error) in } }
```



# Android
## Import Mapfit Android
###### Kotlin
```Kotlin
implementation 'com.mapfit:android-sdk:2.0.1'
```

## Replace the API Key 
#### Google
##### google_maps_api.xml
###### Swift
```Swift
<resources>
    <string name="google_maps_key" templateMergeStrategy="preserve" translatable="false">YOUR-API-KEY</string>
</resources>
```

#### Mapfit
###### Swift
```Swift
  override fun onCreate(savedInstanceState: Bundle?) {
        Mapfit.getInstance(this, "591dccc4e499ca0001a4c6a4413a1efe64344fb599b501aaeef6937d")
    }
```

## Replace the Map Android
#### Google
###### Kotlin
```Kotlin
     val mapFragment = supportFragmentManager
                .findFragmentById(R.id.map) as SupportMapFragment
          mapFragment.getMapAsync({ googleMap ->
```

#### Mapfit
###### Kotlin
```Kotlin
      mapfitMapView.getMapAsync(onMapReadyCallback = object : com.mapfit.android.OnMapReadyCallback {
           override fun onMapReady(mapfitMap: MapfitMap) {
```

## Replace a Marker on Android
#### Google
###### Kotlin
```Kotlin
     val mapFragment = supportFragmentManager
                .findFragmentById(R.id.map) as SupportMapFragment
        mapFragment.getMapAsync({ googleMap ->
           val mMap = googleMap

            // Add a marker in Sydney and move the camera
       val sydney = LatLng(-34.0, 151.0)
       mMap.addMarker(MarkerOptions().position(sydney).title("Marker in Sydney"))
       mMap.moveCamera(CameraUpdateFactory.newLatLng(sydney))
```
#### Mapfit
###### Kotlin
```kotlin 
			mapfitMapView.getMapAsync(onMapReadyCallback = object : com.mapfit.android.OnMapReadyCallback {
                    override fun onMapReady(mapfitMap: MapfitMap) {
 
       val position = LatLng(-34.0, 151.0)
       mapfitMap.setCenter(position)
       mapfitMap.addMarker(MarkerOptions()
                                        .position(position)
                                        .icon(MapfitMarker.DEFAULT))
```

## Replace a Route on Android
#### Google
###### Kotlin
```kotlin
** Additional imports for URL requests
import java.net.URL
import org.jetbrains.anko.async
import org.jetbrains.anko.uiThread
import com.beust.klaxon.*

 private var mMap: GoogleMap? = null

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_maps)
        // Obtain the SupportMapFragment and get notified when the map is ready to be used.
        val mapFragment = getSupportFragmentManager()
                .findFragmentById(R.id.map) as SupportMapFragment
        mapFragment.getMapAsync(this)
    }

    override fun onMapReady(googleMap: GoogleMap) {
        mMap = googleMap
        // declare bounds object to fit whole route in screen
        val LatLongB = LatLngBounds.Builder()

        // Add markers
        val sydney = LatLng(-34.0, 151.0)
        val opera = LatLng(-33.9320447,151.1597271)
        mMap!!.addMarker(MarkerOptions().position(sydney).title("Marker in Sydney"))
        mMap!!.addMarker(MarkerOptions().position(opera).title("Opera House"))

        // Declare polyline object and set up color and width
        val options = PolylineOptions()
        options.color(Color.RED)
        options.width(5f)

        // build URL to call API
        val url = getURL(sydney, opera)

        async {
            // Connect to URL, download content and convert into string asynchronously
            val result = URL(url).readText()
            uiThread {
                // When API call is done, create parser and convert into JsonObjec
                val parser: Parser = Parser()
                val stringBuilder: StringBuilder = StringBuilder(result)
                val json: JsonObject = parser.parse(stringBuilder) as JsonObject
                // get to the correct element in JsonObject
                val routes = json.array<JsonObject>("routes")
                val points = routes!!["legs"]["steps"][0] as JsonArray<JsonObject>
                // For every element in the JsonArray, decode the polyline string and pass all points to a List
                val polypts = points.flatMap { decodePoly(it.obj("polyline")?.string("points")!!)  }
                // Add  points to polyline and bounds
                options.add(sydney)
                LatLongB.include(sydney)
                for (point in polypts)  {
                    options.add(point)
                    LatLongB.include(point)
                }
                options.add(opera)
                LatLongB.include(opera)
                // build bounds
                val bounds = LatLongB.build()
                // add polyline to the map
                mMap!!.addPolyline(options)
                // show map with route centered
                mMap!!.moveCamera(CameraUpdateFactory.newLatLngBounds(bounds, 100))
            }
        }
    }

    private fun getURL(from : LatLng, to : LatLng) : String {
        val origin = "origin=" + from.latitude + "," + from.longitude
        val dest = "destination=" + to.latitude + "," + to.longitude
        val sensor = "sensor=false"
        val params = "$origin&$dest&$sensor"
        return "https://maps.googleapis.com/maps/api/directions/json?$params"
    }

    /**
     * Method to decode polyline points
     * Courtesy : https://jeffreysambells.com/2010/05/27/decoding-polylines-from-google-maps-direction-api-with-java
     */
    private fun decodePoly(encoded: String): List<LatLng> {
        val poly = ArrayList<LatLng>()
        var index = 0
        val len = encoded.length
        var lat = 0
        var lng = 0

        while (index < len) {
            var b: Int
            var shift = 0
            var result = 0
            do {
                b = encoded[index++].toInt() - 63
                result = result or (b and 0x1f shl shift)
                shift += 5
            } while (b >= 0x20)
            val dlat = if (result and 1 != 0) (result shr 1).inv() else result shr 1
            lat += dlat

            shift = 0
            result = 0
            do {
                b = encoded[index++].toInt() - 63
                result = result or (b and 0x1f shl shift)
                shift += 5
            } while (b >= 0x20)
            val dlng = if (result and 1 != 0) (result shr 1).inv() else result shr 1
            lng += dlng

            val p = LatLng(lat.toDouble() / 1E5,
                    lng.toDouble() / 1E5)
            poly.add(p)
        }

        return poly
    }   
```
#### Mapfit
###### Kotlin
```kotlin

mapfitMap.getDirectionsOptions()
    .setDestination(com.mapfit.android.geometry.LatLng(-34.0, 151.0))
    .setOrigin(com.mapfit.android.geometry.LatLng(-33.9320447, 151.1597271))
    .setType(DirectionsType.DRIVING)
    .showDirections(object : DirectionsOptions.RouteDrawCallback {
        override fun onRouteDrawn(route: Route, legs: List<Polyline>) {
            // at this point, the route is drawn on map. drawn polylines are returned as legs.
            // you may want to add a marker to the origin and destination location inside route
            // object.
        }

        override fun onError(message: String, e: Exception) {
            // handle the error
        }
    })
```