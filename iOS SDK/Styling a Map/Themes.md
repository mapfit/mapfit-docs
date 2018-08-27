# Themes
## Setting a map theme

## Theme options

```swift
mapView.mapOptions.setTheme(theme: .day)
mapView.mapOptions.setTheme(theme: .night)
mapView.mapOptions.setTheme(theme: .grayScale)
```

We currently have 3 map styles available for use.

### Day Theme
![](https://files.readme.io/a72540c-DayThemeiOS.png)
### Night Theme
![](https://files.readme.io/f3bf993-DarkTheme.png)
### Grayscale Theme
![](https://files.readme.io/2321b84-GrayScaleTheme.png)
## Custom Theme

```swift
// if the file is hosted in web
mapView.mapOptions.setCustomTheme("https://mywebsite.com/sample.yaml")

// if the file is in a local folder, remember to prefix the path with "file:"
mapView.mapOptions.setCustomTheme("file://data/.../sample.yaml")

```

### Manipulating a Theme
A YAML theme can be updated by creating an MFTSceneUpdate and specifying a path and value. Below is an example of an update that turns on 3D buildings.
 
```swift
let update = MFTSceneUpdate(path: "global.show_3d_buildings", value: "true")
mapview.updateScene(updates: [update])
```