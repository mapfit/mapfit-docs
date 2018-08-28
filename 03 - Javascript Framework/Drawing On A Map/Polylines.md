# Polylines
To add a polyline to your map, you will need to use define the coordinates of each point of the polyline. Those points will need to then be saved into one array which will serve as the polyline. See [Polyline](ref:polyline) for more detail. 
```javascript
//create polyline
let myPolyline = mapfit.Polyline([[40.729877, -74.000588],
                 [40.729171, -74.001191],
                 [40.728103, -74.002099],
                 // ... additional points
                 [40.74398, -73.993293]]);

//add polyline to map
mapfitMap.addPolyline(myPolyline);

//set map center to polyline
map.setCenterWithLayer(myPolyline, 0, 0);
```

In the code sample below, you can see a polyline drawn on a map.

<iframe height='350' scrolling='no' src='https://codepen.io/mapfit/embed/ELXVYw/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>
To see the Polyline methods, click [here](ref:polyline) .