---
title: "Geocoding"
excerpt: ""
---
# Geocoding API Quick Start Guide - iOS
Mapfit Geocoding API is a service to convert addresses to entrance-aligned latitude/longitude and to find any place, region or point of interest by name. You can use the Geocoding API directly from the iOS SDK.

## Pre-requirements

This tutorial assumes that you have already implemented Mapfit Maps SDK in your project. If you haven't implemented it yet, see [Getting Started].


## Obtain coordinates for an address
	
To obtain coordinates for an address, you can use the `MFTGeocoder` class as below. Specify an address to receive the coordinates for its primary entrance.

```swift
  MFTGeocoder.sharedInstance.geocode(address: "119 w 24th street new york, ny", includeBuilding: true) { (address, errror) in
            
        }

```

## Obtain address for coordinates

To obtain an address for coordinates, you can use the `MFTGeocoder` class as below. Specify the coordinates to receive the address for its primary entrance.

```swift
  MFTGeocoder.sharedInstance.reverseGeocode(latLng: CLLocationCoordinate2DMake(40.74405, -73.99324), includeBuilding: true) { (addresses, error) in
   
        }

```