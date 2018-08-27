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
[block:code]
{
  "codes": [
    {
      "code": "Geocoder().geocode(\"119w 24th st new york ny\",\n            true, // if set true, resulting addresses will include building data\n            object : GeocoderCallback {\n                override fun onSuccess(addressList: List<Address>) {\n\n                }\n                \n                override fun onError(message: String, e: Exception) {\n                    \n                }\n            })",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "new Geocoder().geocode(\"119w 24th st new york ny\",\n                true, // if set true, resulting addresses will include building data\n\t\t\t\t\t\t\t\tnew GeocoderCallback() {\n                  \t@Override\n                  \tpublic void onSuccess(@NotNull List<Address> addressList) {\n                  \t  \n                  \t}\n                  \t\n                  \t@Override\n                  \tpublic void onError(@NotNull String message, @NotNull Exception e) {\n                  \t  \n                  \t}\n                });",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
## Obtain address for coordinates
To obtain an [Address](https://mapfit-android.readme.io/v1.0.0/reference#address) with your coordinates as [LatLng](ref:latlng) , you can use [Geocoder](https://mapfit-android.readme.io/v1.0.0/reference#geocoder) class as below.
[block:code]
{
  "codes": [
    {
      "code": "  Geocoder().reverseGeocode(LatLng(40.74405, -73.99324),\n            true, // if set true, resulting addresses will include building data\n            object : GeocoderCallback {\n                override fun onSuccess(addressList: List<Address>) {\n                \n                }\n                \n                override fun onError(message: String, e: Exception) {\n                   \n                }\n            })",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": " new Geocoder().reverseGeocode(new LatLng(40.744023, -73.993150),\n                true, // if set true, resulting addresses will include building data\n                new GeocoderCallback() {\n                    @Override\n                    public void onSuccess(@NotNull List<Address> addressList) {\n\n                    }\n\n                    @Override\n                    public void onError(@NotNull String message, @NotNull Exception e) {\n\n                    }\n                });\n",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]