# Place Info

To display a PlaceInfo you need to specify a title or two subtitles for your [Marker](https://mapfit-android.readme.io/v1.0.0/reference#marker-1). If you set any, when [Marker](https://mapfit-android.readme.io/v1.0.0/reference#marker-1) is clicked, a  PlaceInfo will be displayed. 
You can add a title and subtitles as below.

```kotlin
 mapfitMap.addMarker(MarkerOptions()
            .position(LatLng())
            .title("Artichoke Basille's Pizza & Brewery")
            .subtitle1("111 Macdougal St (btwn Bleecker & W 3rd St)")
            .subtitle2("Pizza, Italian"))
```
![](https://files.readme.io/94cad69-place-info-ss.png)
## Listen to Place Info Clicks
Click events are can be listened by setting an [OnPlaceInfoClickListener](ref:onplaceinfoclicklistener) as below. 
```kotlin
mapfitMap.setOnPlaceInfoClickListener(object : MapfitMap.OnPlaceInfoClickListener {
            override fun onPlaceInfoClicked(marker: Marker) {
                
            }
        })
```
## Custom Place Info View
If you'd like to use your [PlaceInfo](ref:placeinfo) for your [Marker](ref:marker-1), you can do it by setting a [PlaceInfoAdapter](ref:placeinfoadapter) using [MapfitMap](ref:mapfitmap) as below. 

```kotlin
mapfitMap.setPlaceInfoAdapter(object : MapfitMap.PlaceInfoAdapter {
    override fun getPlaceInfoView(marker: Marker): View {

      // invoked when the marker is clicked
      // here you can inflate a view that is related to the marker
      return TextView(context)
    }
})
```