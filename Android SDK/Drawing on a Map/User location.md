---
title: "User location"
excerpt: ""
---
To display the user's location on the map, follow the steps below.

## Location Permission
To access the device's location, you must have location permission granted.
## Add permissions to the manifest file
[block:code]
{
  "codes": [
    {
      "code": "<manifest xmlns:android=\"http://schemas.android.com/apk/res/android\">\n \n  <uses-permission android:name=\"android.permission.ACCESS_COARSE_LOCATION\"/>\n  <uses-permission android:name=\"android.permission.ACCESS_FINE_LOCATION\"/>\n\n\t...\n\n</manifest>",
      "language": "xml"
    }
  ]
}
[/block]
## Request runtime permissions (Android 6.0 and above)
If your application is targeting API level 23 or above, you must handle the case where users did not grant location permission.

### Check if user granted location permission
The example below checks if location permission is granted before enabling user location using Support library. If you call `setUserLocationEnabled` without a granted permission, the user's location won't be displayed.
[block:code]
{
  "codes": [
    {
      "code": " if (ActivityCompat.checkSelfPermission(\n                context,\n                Manifest.permission.ACCESS_FINE_LOCATION\n            ) != PackageManager.PERMISSION_GRANTED\n        ) {\n\n            mapfitMap.getMapOptions().setUserLocationEnabled(true)\n\n        } else {\n            // request location permission\n        }",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": " if (ActivityCompat.checkSelfPermission(context,\n                Manifest.permission.ACCESS_FINE_LOCATION) != PackageManager.PERMISSION_GRANTED) {\n\n            mapfitMap.getMapOptions().setUserLocationEnabled(true);\n            \n        } else {\n            // request location permission\n        }",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
### Requesting location permission
You can request location permission as below
[block:code]
{
  "codes": [
    {
      "code": " ActivityCompat.requestPermissions(\n            activity,\n            arrayOf(Manifest.permission.ACCESS_FINE_LOCATION),\n            LOCATION_PERMISSION_REQUEST_CODE\n        )",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "ActivityCompat.requestPermissions(activity,\n                new String[]{Manifest.permission.ACCESS_FINE_LOCATION},\n                LOCATION_PERMISSION_REQUEST_CODE);",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
### Check the result of the permission request
[block:code]
{
  "codes": [
    {
      "code": " override fun onRequestPermissionsResult(\n        requestCode: Int,\n        permissions: Array<String>,\n        grantResults: IntArray\n    ) {\n        if (requestCode == LOCATION_PERMISSION_REQUEST_CODE) {\n            if (permissions.size == 1 &&\n                permissions[0] === Manifest.permission.ACCESS_FINE_LOCATION &&\n                grantResults[0] == PackageManager.PERMISSION_GRANTED\n            ) {\n            \n                // permission is granted\n                mapfitMap.getMapOptions().setUserLocationEnabled(true)\n                \n            } else {\n                // permission was denied\n            }\n        }\n    }",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": " @Override\n  public void onRequestPermissionsResult(int requestCode, String[] permissions, int[] grantResults) {\n        if (requestCode == LOCATION_PERMISSION_REQUEST_CODE) {\n            if (permissions.length == 1 &&\n                    permissions[0] == Manifest.permission.ACCESS_FINE_LOCATION &&\n                    grantResults[0] == PackageManager.PERMISSION_GRANTED) {\n              \n                // permission is granted\n                mapfitMap.getMapOptions().setUserLocationEnabled(true)\n                  \n            } else {\n                // permission was denied\n            }\n        }\n    }",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
For more documentation about runtime permission requests, you can check official documentation [here](https://developer.android.com/training/permissions/requesting.html)

## Location Priority
You can also set the [LocationPriority](ref:locationpriority) for the location updates as below.
[block:code]
{
  "codes": [
    {
      "code": "// high accuracy and power consumption\nmapfitMap.getMapOptions().setUserLocationEnabled(true, LocationPriority.HIGH_ACCURACY)\n\n// low accuracy and power consumption\nmapfitMap.getMapOptions().setUserLocationEnabled(true, LocationPriority.LOW_ACCURACY)",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "// high accuracy and power consumption\nmapfitMap.getMapOptions().setUserLocationEnabled(true, LocationPriority.HIGH_ACCURACY);\n\n// low accuracy and power consumption\nmapfitMap.getMapOptions().setUserLocationEnabled(true, LocationPriority.LOW_ACCURACY);\n",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
## Listen Location Updates
You can also listen to the location updates with [LocationListener](ref:locationlistener).
[block:code]
{
  "codes": [
    {
      "code": "    mapfitMap.getMapOptions().setUserLocationEnabled(\n            enable = true,\n            locationPriority = LocationPriority.HIGH_ACCURACY,\n            listener = object : com.mapfit.android.location.LocationListener {\n                override fun onLocation(location: Location) {\n                }\n\n                override fun onProviderStatus(availability: ProviderStatus) {\n                }\n\n            })",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "    mapfitMap.getMapOptions().setUserLocationEnabled(true,\n              LocationPriority.HIGH_ACCURACY,\n              new LocationListener() {\n                  @Override\n                  public void onLocation(@NotNull Location location) {\n\n                  }\n\n                  @Override\n                  public void onProviderStatus(@NotNull ProviderStatus status) {\n\n                  }\n              });",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]