# User location
To display the user's location on the map, follow the steps below.

## Location Permission
To access the device's location, you must have location permission granted.
## Add permissions to the manifest file
```xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android">
 
  <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"/>
  <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>

	...

</manifest>
```
## Request runtime permissions (Android 6.0 and above)
If your application is targeting API level 23 or above, you must handle the case where users did not grant location permission.

### Check if user granted location permission
The example below checks if location permission is granted before enabling user location using Support library. If you call `setUserLocationEnabled` without a granted permission, the user's location won't be displayed.
```kotlin
 if (ActivityCompat.checkSelfPermission(
                context,
                Manifest.permission.ACCESS_FINE_LOCATION
            ) != PackageManager.PERMISSION_GRANTED
        ) {

            mapfitMap.getMapOptions().setUserLocationEnabled(true)

        } else {
            // request location permission
        }
```
### Requesting location permission
You can request location permission as below
```kotlin
 ActivityCompat.requestPermissions(
            activity,
            arrayOf(Manifest.permission.ACCESS_FINE_LOCATION),
            LOCATION_PERMISSION_REQUEST_CODE
        )
```
### Check the result of the permission request
```kotlin
 override fun onRequestPermissionsResult(
        requestCode: Int,
        permissions: Array<String>,
        grantResults: IntArray
    ) {
        if (requestCode == LOCATION_PERMISSION_REQUEST_CODE) {
            if (permissions.size == 1 &&
                permissions[0] === Manifest.permission.ACCESS_FINE_LOCATION &&
                grantResults[0] == PackageManager.PERMISSION_GRANTED
            ) {
            
                // permission is granted
                mapfitMap.getMapOptions().setUserLocationEnabled(true)
                
            } else {
                // permission was denied
            }
        }
    }
```
For more documentation about runtime permission requests, you can check official documentation [here](https://developer.android.com/training/permissions/requesting.html)

## Location Priority
You can also set the [LocationPriority](ref:locationpriority) for the location updates as below.
```kotlin
// high accuracy and power consumption
mapfitMap.getMapOptions().setUserLocationEnabled(true, LocationPriority.HIGH_ACCURACY)

// low accuracy and power consumption
mapfitMap.getMapOptions().setUserLocationEnabled(true, LocationPriority.LOW_ACCURACY)
```
## Listen Location Updates
You can also listen to the location updates with [LocationListener](ref:locationlistener).
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