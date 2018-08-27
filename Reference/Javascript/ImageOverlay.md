---
title: "ImageOverlay"
excerpt: "mapfit.ImageOverlay"
---

# ImageOverlay
### mapfit.ImageOverlay

`imageOverlay` will display an image on the map. 

Constructor | Description
------------|------------
mapfit.ImageOverlay(imageUrl: string, imageBounds: array, options: object)| First parameter is a string that will be the url to the image you would like to use, the second parameter is a nested array of the bounds. The third parameter is an optional of an object containing options below.

Options | Description
--------|------------
opacity| Takes a numeric value which will either decrease or increase the opacity of an image. 
alt| Will take a string value which will be show as the value of the image's alt attribute.
interactive| Takes a boolean value. True will enable click events and false will disable those.
errorOverlayUrl| If the image you placed on the map fails to load this image will show for the error state.
zIndex| Takes a numeric value setting the layer's zIndex which the image is on.
className| Takes a string value and will appear as the image's class name.

Method | Description
-------|------------
setOpacity(number)| Takes a numeric value and will either increase or decrease the opacity of the image overlay.
bringToFront()| You call this function on your imageOverlay object and it will then place the image overlay above all other image overlays on the map.
setUrl(string)| Takes a string parameter of a url. The image's path will update to the url you passed in.
setBounds(array)| Takes in LatLngBounds as a parameter and will then update the bounds of the image overlay to the bounds that was passed in.
getBounds()| Will return the bounds of the image overlay that you called this function on.
getElement()| Will return the HTML image element that is used by the current overlay.