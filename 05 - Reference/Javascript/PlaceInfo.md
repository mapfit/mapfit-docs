---
title: "PlaceInfo"
excerpt: "mapfit.PlaceInfo"
---
# PlaceInfo
### mapfit.PlaceInfo

Constructor	|Description
--|--
mapfit.PlaceInfo(marker: Marker)|Construct a Place Info object, to be shown when a click event occurs on the attached Marker.

Method	|Description
--|--
setTitle(title:String)|Adds the input text to the first line of the Place Info window. The string that you pass in can contain HTML syntax (or just plain text).
Example|``` myInfoCard.setTitle('<h1>Mapfit HQ</h1><h2>New York office</h2>')```
setDescription(description:String)|Adds the input text to the second line of the Place Info window. The string that you pass in can contain HTML syntax (or just plain text).
Example|```myInfoCard.setDescription('<p>119 W 24th St, New York, NY</p>')```
enableDirectionsButton(newWindow : boolean)|Adds the 'Get Directions' button to the bottom of the Place Info window and enables the subsequent directions UX flow. If newWindow parameter is set to true, then directions will open in a new window.
setContent(htmlForPopup: string)|You can create a custom popup for your marker by passing in a string as parameter. The string that you pass in should contain all the HTML you would like to use to create the popup.