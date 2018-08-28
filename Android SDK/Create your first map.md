---
title: "Create your first map"
excerpt: ""
---
#Audience
This documentation is designed for people familiar with Kotlin or Java programming and object-oriented programming concepts. You should also be familiar with [Mapfit](http://mapfit.com) from a user's point of view.

This conceptual documentation is designed to let you quickly start exploring and developing applications with the Mapfit Android SDK. We also publish the Mapfit Android Reference.

#Get your Mapfit API key
To use Mapfit Maps and services, your application will need an API key. To get an API Key, see: [Get API Key](doc:get-api-key).

#Set up your environment
You will need to have Android Studio in order to use Mapfit Maps SDK. You can obtain the latest version of Android Studio from [here](https://developer.android.com/studio/index.html).

#Create an Android Studio Project
1. Start Android Studio.
2. Create a new project with the following options
	- Under "Target Android Devices", select "Phone and Tablet".
	- For minimum API level, select "API 16: Android 4.1(Jelly Bean)". API level 16 is the lowest API level supported by Mapfit Maps SDK.
3. Under "Add an Activity to Mobile", choose "Empty Activity" or a template of your choice.

If you need help with creating your first project, see the [Android Studio documentation](https://developer.android.com/studio/intro/index.html).

#Install the Mapfit Android SDK
First, make sure `JCenter` is included in the repositories scope inside project level `build.gradle` file.
```groovy
allprojects {
    repositories {
        jcenter()
    }
}
```
Second, you must add the dependency to your module level `build.gradle` file
```groovy
dependencies {
    	implementation 'com.mapfit:android-sdk:2.1.1'
}
```

#Adding a map to your view
Inside your `activity_main.xml` file, add Mapview as seen below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <com.mapfit.android.MapView
        android:id="@+id/mapView"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />

</android.support.constraint.ConstraintLayout>
```

#Initializing Mapfit and MapView
Inside your Activity, initialize [Mapfit](ref:mapfit) class with your API key and then initialize [MapView](ref:mapview) as below.
```kotlin
    class MainActivity : AppCompatActivity() {

        lateinit var mapView: MapView

        override fun onCreate(savedInstanceState: Bundle?) {
            super.onCreate(savedInstanceState)

            // if you have an Application class, you should instantiate Mapfit in it
            Mapfit.getInstance(this, YOUR_API_KEY)

            setContentView(R.layout.activity_coffee_shops)

            mapView = findViewById(R.id.mapView)

            mapView.getMapAsync(onMapReadyCallback = object : OnMapReadyCallback {
                override fun onMapReady(mapfitMap: MapfitMap) {
                    // mapfitMap is ready to be used!
                }
            })

        }

        override fun onDestroy() {
            super.onDestroy()
            mapView.onDestroy()
        }

        override fun onLowMemory() {
            super.onLowMemory()
            mapView.onLowMemory()
        }

    }
```
#Setup your device
If you have a device, you can plug it into your computer. Developer options on your device should be enabled to deploy your app. If you need help with enabling developer options, see [instructions](https://developer.android.com/studio/run/device.html).

Alternatively, you can use Android Emulator to test your app. You need to create a virtual device of your choice. If you need more information, see [Android Virtual Device (AVD) Manager](https://developer.android.com/studio/run/managing-avds.html).

#Build and run your app
In Android Studio, click Run `app` button or [Control + R] on MacOS or [Shift + F10] on Windows to build your app.

It will take a few seconds for Android Studio to build the project. After it is built, you can select your device to deploy your app.

#Add a Marker
After instantiating your [MapView](https://mapfit-android.readme.io/v1.0.0/reference#mapview), you can add a [Marker](https://mapfit-android.readme.io/v1.0.0/reference#marker-1) as below.


```kotlin
override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        mapView.getMapAsync(onMapReadyCallback = object : OnMapReadyCallback {
            override fun onMapReady(mapfitMap: MapfitMap) {

                val latLng = LatLng(40.744023, -73.993150)
                mapfitMap.addMarker(MarkerOptions().position(latLng))

            }
        })
}
```
Now, run your application again, you should see a [Marker](ref:marker-1)  added to the position you set.