# Polylines
## Add a Polyline
To add a [Polyline](https://mapfit-android.readme.io/v1.0.0/reference#polyline) to your map, you will need a `List<LatLng>` object which includes the coordinates of your line.
Once you have your `List<LatLng>`, you can add it to your map as below. See [PolylineOptions](ref:polylineoptions).

```kotlin
val linePoints: List<LatLng> = getLinePoints()

val polyline = mapfitMap.addPolyline(PolylineOptions().points(linePoints))

```
![](https://files.readme.io/639af95-polyline-ss.png)
There is no limit on the number of polylines you can have on a map. Note that, adding an excessive amount of polylines can reduce performance.

## Extend Polyline
You can add points to the [Polyline](ref:polyline) after you create it as below.
```kotlin
// you can add a sigle LatLng
polyline.addPoints(LatLng(40.744023, -73.993150))

// you can add multiple LatLngs
polyline.addPoints(LatLng(40.74402, -73.9931),
                   LatLng(40.74403, -73.9932),
                   LatLng(40.74404, -73.9933))
```
## Styling a Polyline
You can style a polyline trough it's [PolylineOptions](ref:polylineoptions) object. You can change a polyline's
- Stroke color
- Stroke width
- Stroke outline color
- Stroke outline width
- Join type
- Cap type

Changing styling attributes are optional. The attributes that aren't changed will stay as default.

### Color
Color attributes are set via hex string with format `#AARRGGBB` where first two digits are representing alpha and optional.

### Width
You can set width attributes with positive integer values as pixels. The default width of the stroke outline width is `0`.

### Join type
You can change the type of outlining line's joining. You can define it as bound, bevel or round. Rounding is done by adding extra points. See reference for [JoinType](ref:jointype).

### Cap type
You can change the type of the caps of the line. You can define it as bound, square or round. 
Rounding is done by adding extra points. See reference for [CapType](ref:captype)

### Draw order
You can change the draw order of a [Polyline](ref:polyline) to set its z-depth. The value must be an integer.

### The code
The code below demonstrates how to change all of the style attributes.
```kotlin
 val polyline = mapfitMap.addPolyline(
                    PolylineOptions()
                        .points(line)
                        .strokeWidth(3)
                        .strokeOutlineWidth(8)
                        .strokeColor("#4353ff")
                        .strokeOutlineColor("#4c4353ff")
                        .lineJoinType(JoinType.ROUND)
                        .drawOrder(600)
                        .lineCapType(CapType.ROUND)
                )

// after initializing the polyline, you can change the style for each attribute like below
polyline.strokeWidth = 10
```
This is how the polyline looks like after styling.
![](https://files.readme.io/a0e2b0f-styled-polyline.png)