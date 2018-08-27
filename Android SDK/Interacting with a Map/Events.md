---
title: "Events"
excerpt: ""
---
Below is a list of events that you can listen for and handle programmatically

# Map Events
## Single click
Set your [OnMapClickListener](https://mapfit-android.readme.io/v1.0.0/reference#onmapclicklistener) to listen to map click events as below.
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.setOnMapClickListener(object : OnMapClickListener {\n            override fun onMapClicked(latLng: LatLng) {\n\n            }\n        })",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.setOnMapClickListener(new OnMapClickListener() {\n            @Override\n            public void onMapClicked(@NotNull LatLng latLng) {\n\n            }\n        });",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
## Double-click
Set your [OnMapDoubleClickListener](https://mapfit-android.readme.io/v1.0.0/reference#onmapdoubleclicklistener-1) to listen to map double-click events as below.
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.setOnMapDoubleClickListener(object : OnMapDoubleClickListener {\n            override fun onMapDoubleClicked(latLng: LatLng) {\n\n            }\n        })",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.setOnMapDoubleClickListener(new OnMapDoubleClickListener() {\n            @Override\n            public void onMapDoubleClicked(@NotNull LatLng latLng) {\n\n            }",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
## Long click
Set your [OnMapLongClickListener](https://mapfit-android.readme.io/v1.0.0/reference#onmaplongclicklistener-1) to listen to map long click events as below.
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.setOnMapLongClickListener(object : OnMapLongClickListener {\n            override fun onMapLongClicked(latLng: LatLng) {\n\n            }\n        })",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.setOnMapLongClickListener(new OnMapLongClickListener() {\n            @Override\n            public void onMapLongClicked(@NotNull LatLng latLng) {\n\n            }\n        });",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
## Pan
Set your [OnMapPanListener](https://mapfit-android.readme.io/v1.0.0/reference#onmappanlistener-1) to listen to map pan events as below.
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.setOnMapPanListener(object : OnMapPanListener {\n            override fun onMapPan() {\n\n            }\n        })",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.setOnMapPanListener(new OnMapPanListener() {\n            @Override\n            public void onMapPan() {\n\n            }\n        });",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
## Pinch
Set your [OnMapPinchListener](https://mapfit-android.readme.io/v1.0.0/reference#onmappinchlistener-1) to listen to map pinch events as below.
[block:code]
{
  "codes": [
    {
      "code": "mapfitMap.setOnMapPinchListener(object : OnMapPinchListener {\n            override fun onMapPinch() {\n\n            }\n        })\n",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.setOnMapPinchListener(new OnMapPinchListener() {\n            @Override\n            public void onMapPinch() {\n\n            }\n        });",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
# Marker, Polyline, & Polygon Events
## Marker click event
Set your [OnMarkerClickListener](ref:onmarkerclicklistener-1) to listen [Marker](ref:marker-1) click events on the map.
[block:code]
{
  "codes": [
    {
      "code": " mapfitMap.setOnMarkerClickListener(object:OnMarkerClickListener{\n            override fun onMarkerClicked(marker: Marker) {\n                \n            }\n        })",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "mapfitMap.setOnMarkerClickListener(new OnMarkerClickListener() {\n            @Override\n            public void onMarkerClicked(@NotNull Marker marker) {\n                \n            }\n        });",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
## Polyline click
Set your [OnPolylineClickListener](ref:onpolylineclicklistener-1) to listen [Polyline](ref:polyline) click events on the map.
[block:code]
{
  "codes": [
    {
      "code": " mapfitMap.setOnPolylineClickListener(object: OnPolylineClickListener{\n            override fun onPolylineClicked(polyline: Polyline) {\n                \n            }\n        })",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": " mapfitMap.setOnPolylineClickListener(new OnPolylineClickListener() {\n            @Override\n            public void onPolylineClicked(@NotNull Polyline polyline) {\n                \n            }\n        });",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
## Polygon click
Set your [OnPolygonClickListener](ref:onpolygonclicklistener-1)  to listen [Polygon](ref:polygon-1)  click events on the map.
[block:code]
{
  "codes": [
    {
      "code": " mapfitMap.setOnPolygonClickListener(object: OnPolygonClickListener{\n            override fun onPolygonClicked(polygon: Polygon) {\n                \n            }\n        })",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": " mapfitMap.setOnPolygonClickListener(new OnPolygonClickListener() {\n            @Override\n            public void onPolygonClicked(@NotNull Polygon polygon) {\n                \n            }\n        });",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
# User Location Events
## Listen to location updates
Once you enable user location, you can also listen to the location updates with [LocationListener](ref:locationlistener).
[block:code]
{
  "codes": [
    {
      "code": "  mapfitMap.getMapOptions().setUserLocationEnabled(\n            enable = true,\n            locationPriority = LocationPriority.HIGH_ACCURACY,\n            listener = object : com.mapfit.android.location.LocationListener {\n                override fun onLocation(location: Location) {\n                }\n\n                override fun onProviderStatus(availability: ProviderStatus) {\n                }\n\n            })",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "    mapfitMap.getMapOptions().setUserLocationEnabled(\n      \t\t\t\ttrue,\n              LocationPriority.HIGH_ACCURACY,\n              new LocationListener() {\n                  @Override\n                  public void onLocation(@NotNull Location location) {\n\n                  }\n\n                  @Override\n                  public void onProviderStatus(@NotNull ProviderStatus status) {\n\n                  }\n              });",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]