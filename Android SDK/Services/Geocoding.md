---
title: "Geocoding"
excerpt: ""
---
# Geocoding API Quick Start Guide - Android

Mapfit Geocoding API is a service to convert addresses to entrance-aligned latitude/longitude and to find any place, region or point of interest by name. You can use the Geocoding API directly from the Android SDK.

## Pre-requirements

This tutorial assumes that you have already implemented Mapfit Maps SDK in your project. If you haven't implemented it yet, see [Create your first map](doc:create-a-map).


## Obtain coordinates for an address
	
To obtain coordinates for an [Address](https://mapfit-android.readme.io/v1.0.0/reference#address), you can use [Geocoder](https://mapfit-android.readme.io/v1.0.0/reference#geocoder) class as below.
```kotlin
Geocoder().geocode("119w 24th st new york ny",
            true, // if set true, resulting addresses will include building data
            object : GeocoderCallback {
                override fun onSuccess(addressList: List<Address>) {

                }
                
                override fun onError(message: String, e: Exception) {
                    
                }
            })
```
## Obtain address for coordinates
To obtain an [Address](https://mapfit-android.readme.io/v1.0.0/reference#address) with your coordinates as [LatLng](ref:latlng) , you can use [Geocoder](https://mapfit-android.readme.io/v1.0.0/reference#geocoder) class as below.

```kotlin
  Geocoder().reverseGeocode(LatLng(40.74405, -73.99324),
            true, // if set true, resulting addresses will include building data
            object : GeocoderCallback {
                override fun onSuccess(addressList: List<Address>) {
                
                }
                
                override fun onError(message: String, e: Exception) {
                   
                }
            })
```