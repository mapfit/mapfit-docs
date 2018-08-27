# Polygons
To add a polygon to your map, you will need to define the coordinates of each point of the polygon. In the code sample below, you can see clearly defined geographical coordinates for a polygon. See [Polygon](ref:polygon) for more detail.
```javascript
//create polygon
let gramercy = mapfit.Polygon([[40.7368876593604,-73.9785409464787],
                               [40.7313501345546,-73.982556292978],
                               // ... additional points
                               [40.7375539536562,-73.9780522649762],
                               [40.7368876593604,-73.9785409464787]]);

//add polygon to map
map.addPolygon(gramercy);

//set map center to polygon
map.setCenterWithLayer(gramercy, 0, 0);
```

When rendered on a map, it will look like this.
<iframe height='350' scrolling='no' src='https://codepen.io/mapfit/embed/ZoybzL/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>
There is no limit on the number of polygons you can have on a map. Note that if polygons overlap, the fill colors will get darker on the overlapped regions (due to the default opacity setting).

To see the Polygon methods, click [here](ref:polygon).