---
title: "Icon"
excerpt: "mapfit.Icon"
---

# Icon
### mapfit.Icon

`Icon` is the class for creating and controlling icons for the [Marker](ref:marker) class.
Constructor | Description
------------|------------
mapfit.Icon()| Create an instance of the Icon class to be attached to a given Marker instance via the setIcon method on the Marker class.

Method | Description
-------|------------
setIconUrl(iconUrl: String) | Sets the marker icon with the given input parameter - either a url pointing to a custom image (in 'png' format) or a Mapfit marker, specified by name (e.g. 'active'). 
setHeight(height: Int) | Sets the height for the marker icon in pixels. 
setWidth(width: Int)| Sets the width for the marker icon in pixels.
setAnchorHeight(height: Int)| Set the icon anchor's height by passing in an integer. 
setAnchorWidth(width: Int)| Set the icon anchor's width by passing in an integer.