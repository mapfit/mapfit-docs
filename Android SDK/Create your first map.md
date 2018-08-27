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
[block:code]
{
  "codes": [
    {
      "code": "allprojects {\n    repositories {\n        jcenter()\n    }\n}",
      "language": "groovy"
    }
  ]
}
[/block]
Second, you must add the dependency to your module level `build.gradle` file
[block:code]
{
  "codes": [
    {
      "code": "dependencies {\n    \timplementation 'com.mapfit:android-sdk:2.1.1'\n}",
      "language": "groovy"
    }
  ]
}
[/block]
#Adding a map to your view
Inside your `activity_main.xml` file, add Mapview as seen below.
[block:code]
{
  "codes": [
    {
      "code": "<?xml version=\"1.0\" encoding=\"utf-8\"?>\n<android.support.constraint.ConstraintLayout xmlns:android=\"http://schemas.android.com/apk/res/android\"\n    android:layout_width=\"match_parent\"\n    android:layout_height=\"match_parent\">\n\n    <com.mapfit.android.MapView\n        android:id=\"@+id/mapView\"\n        android:layout_width=\"match_parent\"\n        android:layout_height=\"match_parent\" />\n\n</android.support.constraint.ConstraintLayout>",
      "language": "xml"
    }
  ]
}
[/block]
#Initializing Mapfit and MapView
Inside your Activity, initialize [Mapfit](ref:mapfit) class with your API key and then initialize [MapView](ref:mapview) as below.
[block:code]
{
  "codes": [
    {
      "code": "    class MainActivity : AppCompatActivity() {\n\n        lateinit var mapView: MapView\n\n        override fun onCreate(savedInstanceState: Bundle?) {\n            super.onCreate(savedInstanceState)\n\n            // if you have an Application class, you should instantiate Mapfit in it\n            Mapfit.getInstance(this, YOUR_API_KEY)\n\n            setContentView(R.layout.activity_coffee_shops)\n\n            mapView = findViewById(R.id.mapView)\n\n            mapView.getMapAsync(onMapReadyCallback = object : OnMapReadyCallback {\n                override fun onMapReady(mapfitMap: MapfitMap) {\n                    // mapfitMap is ready to be used!\n                }\n            })\n\n        }\n\n        override fun onDestroy() {\n            super.onDestroy()\n            mapView.onDestroy()\n        }\n\n        override fun onLowMemory() {\n            super.onLowMemory()\n            mapView.onLowMemory()\n        }\n\n    }",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "public class MainActivity extends AppCompatActivity {\n\n    MapView mapView;\n\n    @Override\n    protected void onCreate(Bundle savedInstanceState) {\n        super.onCreate(savedInstanceState);\n\n        // if you have an Application class, you should call this from it\n        Mapfit.getInstance(this, YOUR_API_KEY);\n\n        setContentView(R.layout.activity_main);\n\n        mapView = findViewById(R.id.mapView);\n      \n        mapView.getMapAsync(new OnMapReadyCallback() {\n            @Override\n            public void onMapReady(@NotNull MapfitMap mapfitMap) {\n                // mapfitMap is ready to be used!\n            }\n        });\n\n    }\n\n    @Override\n    protected void onDestroy() {\n        super.onDestroy();\n        mapView.onDestroy();\n    }\n\n    @Override\n    public void onLowMemory() {\n      \tsuper.onLowMemory();\n      \tmapView.onLowMemory();\n    }\n}",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
#Setup your device
If you have a device, you can plug it into your computer. Developer options on your device should be enabled to deploy your app. If you need help with enabling developer options, see [instructions](https://developer.android.com/studio/run/device.html).

Alternatively, you can use Android Emulator to test your app. You need to create a virtual device of your choice. If you need more information, see [Android Virtual Device (AVD) Manager](https://developer.android.com/studio/run/managing-avds.html).

#Build and run your app
In Android Studio, click Run `app` button or [Control + R] on MacOS or [Shift + F10] on Windows to build your app.

It will take a few seconds for Android Studio to build the project. After it is built, you can select your device to deploy your app.
[block:image]
{
  "images": [
    {
      "image": []
    }
  ]
}
[/block]
#Add a Marker
After instantiating your [MapView](https://mapfit-android.readme.io/v1.0.0/reference#mapview), you can add a [Marker](https://mapfit-android.readme.io/v1.0.0/reference#marker-1) as below.
[block:code]
{
  "codes": [
    {
      "code": "override fun onCreate(savedInstanceState: Bundle?) {\n        super.onCreate(savedInstanceState)\n\n        mapView.getMapAsync(onMapReadyCallback = object : OnMapReadyCallback {\n            override fun onMapReady(mapfitMap: MapfitMap) {\n\n                val latLng = LatLng(40.744023, -73.993150)\n                mapfitMap.addMarker(MarkerOptions().position(latLng))\n\n            }\n        })\n}",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "@Override\nprotected void onCreate(Bundle savedInstanceState) {\n      super.onCreate(savedInstanceState);\n\n      mapView.getMapAsync(new OnMapReadyCallback() {\n          @Override\n          public void onMapReady(MapfitMap mapfitMap) {\n\n              LatLng latLng = new LatLng(40.744023, -73.993150);\n              mapfitMap.addMarker(new MarkerOptions().position(latLng));\n\n            }\n        });\n}",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": []
    }
  ]
}
[/block]
Now, run your application again, you should see a [Marker](ref:marker-1)  added to the position you set.