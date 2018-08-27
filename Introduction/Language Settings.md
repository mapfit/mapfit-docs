# Language Settings

## Changing Language of the Map

### Statically on the YAML File
Language can be changed statically within the Mapfit provided YAML files by setting expected language code value to the `language` field as below. 

```yaml
language: en      # ISO 639-1 two-letter language code
```

##### Edit Themes using Mapfit Paint
###### Remember that you can always edit, test, or even create your own themes using [Mapfit Paint](https://paint.mapfit.com). We recommend making adjustments to the YAML file here so you can preview your map and the changes in real-time."

## Dynamically Using Mapfit Mobile SDKs

###iOS
###### Swift
```swift
let update = MFTSceneUpdate(path: \"global.language\", value: \"en\")\nmapview.updateScene(updates: [update])
```
### Android
###### Kotlin
```kotlin
val sceneUpdate = SceneUpdate(\"global.language\", \"en\")\nmapfitMap.getMapOptions().updateScene(listOf(sceneUpdate))
```
###### Java
```java
SceneUpdate sceneUpdate = new SceneUpdate(\"global.language\", \"en\");\n\nList<SceneUpdate> sceneUpdates = new ArrayList<>();\nsceneUpdates.add(sceneUpdate);\n\nmapfitMap.getMapOptions().updateScene(sceneUpdates)
```