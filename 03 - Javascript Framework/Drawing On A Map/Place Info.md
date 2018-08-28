# Place Info
You can define the information such as title and description of your location, which will appear in place of your marker icon, on click. If this information is not defined, the place info title will default to show the address (if set) or the latitude, longitude (if the address is not set). See [PlaceInfo](ref:infocard) for more detail.

Note: the Place Info description and title can be customized with html within the input string, as shown below.
```javascript
//add place info to an existing marker
let placeInfo = mapfit.PlaceInfo();
placeInfo.setTitle('Artichoke Basille\'s Pizza & Brewery');
placeInfo.setDescription('<p>111 Macdougal St (btwn Bleeker & W 3rd St)</br>Pizza, Italian</p>');
myMarker.setPlaceInfo(placeInfo);
```

###### Click on marker to view Place Info window

<iframe height='350' scrolling='no' src='https://codepen.io/mapfit/embed/LmLpPm/?height=265&theme-id=light&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>