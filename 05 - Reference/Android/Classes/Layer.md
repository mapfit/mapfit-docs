---
title: "Layer"
excerpt: "com.mapfit.android.Layer"
---
## Layer
### com.mapfit.android.Layer

`Layer` structure is to re-use Annotations and have them synchronised across maps.
```java
class Layer
```

Method	|Description
--|--
add(annotation: Annotation)|Adds the input Annotation to the layer.
clear()|Removes every Annotation from the layer and any map the layer has been added to.
getLatLngBounds()|Returns the LatLngBounds -the bounding coordinates for the layer.
remove(vararg annotation: Annotation)|Removes the input Annotation from the layer.


Property	|Description
--|--
annotations: List<Annotation>|The annotations added to the layer.
visibility: Boolean|The visibility for the layer.