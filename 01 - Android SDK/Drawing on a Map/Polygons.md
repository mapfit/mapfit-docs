# Polygons
## Add a Polygon
To add a [Polygon](https://mapfit-android.readme.io/v1.0.0/reference#polygon-1) to your map, you will need a `List<List<LatLng>>` object which includes the coordinates of your shape.
Once you have your `List<List<LatLng>>`, you can add it to your map as below. See [PolygonOptions](ref:polygonoptions-1).

```kotlin
val polyPoints: List<List<LatLng>> = getPolyPoints()

val polygon = mapfitMap.addPolygon(PolygonOptions().points(polyPoints))
```
When rendered on a map, it will look like this.
![](https://files.readme.io/c32a425-polygon-day.png)
There is no limit on the number of polygons you can have on a map. Note that, adding an excessive amount of polygons can reduce performance.

## Styling a Polygon
You can style a polygon trough it's [PolylineOptions](ref:polylineoptions) object. You can change a polygon's
- Fill color
- Stroke color
- Stroke width
- Stroke outline color
- Stroke outline width
- Join type
Changing styling attributes are optional. The attributes that aren't changed will stay as default.

### Color
Color attributes are set via hex string with format `#AARRGGBB` where first two digits are representing alpha and optional.

### Width
You can set width attributes with positive integer values as pixels. The default width of the stroke outline width is `0`.

### Join type
You can change the type of outlining line's joining. You can define it as bound, bevel or round. Rounding is done by adding extra points. See reference for [JoinType](ref:jointype).

### Draw order
You can change the draw order of a polygon to set its z-depth. Draw order for the stroke of the polygon will be 1 less than polygon itself. The value must be an integer.

### The code
The code below demonstrates how to change all of the style attributes.
```kotlin
 val polygon = mapfitMap.addPolygon(PolygonOptions()
		.points(polyPoints)
		.fillColor("#2732b3ff")
		.strokeWidth(3)
		.strokeColor("#32b3ff")
		.lineJoinType(JoinType.ROUND)
		.strokeOutlineColor("#5932b3ff")
		.strokeOutlineWidth(8)
		)
```
This is how the polygon looks like after styling.
![](https://files.readme.io/b4e19c7-styled-polygon.png)