---
title: "Events"
excerpt: ""
---
## Events
Below is a list of events that you can listen for and handle programmatically

# Map Events
## Single click
Set your [OnMapClickListener](https://mapfit-android.readme.io/v1.0.0/reference#onmapclicklistener) to listen to map click events as below.

```kotlin
mapfitMap.setOnMapClickListener(object : OnMapClickListener {
            override fun onMapClicked(latLng: LatLng) {

            }
        })
```
## Double-click
Set your [OnMapDoubleClickListener](https://mapfit-android.readme.io/v1.0.0/reference#onmapdoubleclicklistener-1) to listen to map double-click events as below.
```kotlin
mapfitMap.setOnMapDoubleClickListener(object : OnMapDoubleClickListener {
            override fun onMapDoubleClicked(latLng: LatLng) {

            }
        })
```
## Long click
Set your [OnMapLongClickListener](https://mapfit-android.readme.io/v1.0.0/reference#onmaplongclicklistener-1) to listen to map long click events as below.
```kotlin
mapfitMap.setOnMapLongClickListener(object : OnMapLongClickListener {
            override fun onMapLongClicked(latLng: LatLng) {

            }
        })
```
## Pan
Set your [OnMapPanListener](https://mapfit-android.readme.io/v1.0.0/reference#onmappanlistener-1) to listen to map pan events as below. 
```kotlin
mapfitMap.setOnMapPanListener(object : OnMapPanListener {
            override fun onMapPan() {

            }
        })
```
## Pinch
Set your [OnMapPinchListener](https://mapfit-android.readme.io/v1.0.0/reference#onmappinchlistener-1) to listen to map pinch events as below. 
```kotlin
mapfitMap.setOnMapPinchListener(object : OnMapPinchListener {
            override fun onMapPinch() {

            }
        })

```
# Marker, Polyline, & Polygon Events
## Marker click event
Set your [OnMarkerClickListener](ref:onmarkerclicklistener-1) to listen [Marker](ref:marker-1) click events on the map. 
```kotlin
 mapfitMap.setOnMarkerClickListener(object:OnMarkerClickListener{
            override fun onMarkerClicked(marker: Marker) {
                
            }
        })
```
## Polyline click
Set your [OnPolylineClickListener](ref:onpolylineclicklistener-1) to listen [Polyline](ref:polyline) click events on the map. 
```kotlin
 mapfitMap.setOnPolylineClickListener(object: OnPolylineClickListener{
            override fun onPolylineClicked(polyline: Polyline) {
                
            }
        })
```
## Polygon click
Set your [OnPolygonClickListener](ref:onpolygonclicklistener-1)  to listen [Polygon](ref:polygon-1)  click events on the map.

```kotlin
 mapfitMap.setOnPolygonClickListener(object: OnPolygonClickListener{
            override fun onPolygonClicked(polygon: Polygon) {
                
            }
        })
```
# User Location Events
## Listen to location updates
Once you enable user location, you can also listen to the location updates with [LocationListener](ref:locationlistener).

```kotlin
  mapfitMap.getMapOptions().setUserLocationEnabled(
            enable = true,
            locationPriority = LocationPriority.HIGH_ACCURACY,
            listener = object : com.mapfit.android.location.LocationListener {
                override fun onLocation(location: Location) {
                }

                override fun onProviderStatus(availability: ProviderStatus) {
                }

            })
```