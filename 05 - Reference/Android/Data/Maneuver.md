---
title: "Maneuver"
excerpt: "com.mapfit.android.directions.model.Maneuver"
---
## Maneuver
### com.mapfit.android.directions.model.Maneuver
A data class representing the components of a leg within a given trip.

```java
data class Maneuver
```

Constructor	|Description
--|--
Maneuver(beginShapeIndex: Int, travelMode: String, instruction: String,     length: Double, streetNames: List<String>, endShapeIndex: Int,     time: Int, type: Int, verbalPreTransitionInstruction: String,     travelType: String)|Maneuvers are components of Legs within a Trip.

Property	|Description
--|--
beginShapeIndex: Int|Index into the list of shape points for the start of the maneuver.
endShapeIndex: Int|Index into the list of shape points for the end of the maneuver.
instruction: String|Written maneuver instruction. Describes the maneuver, such as “Turn right onto Main Street”.
length: Double|Maneuver length in the units specified.
streetNames: List<String>|List of street names that are consistent along the entire maneuver.
time: Int|Estimated time along the maneuver in seconds.
travelMode: String|Travel mode.    - drive    - pedestrian    - bicycle    - transit
travelType: String|Travel type for drive.    - car Travel type for pedestrian.    - foot Travel type for bicycle.    - road Travel type for transit.    - Tram or light rail = tram    - Metro or subway = metro    - Rail = rail    - Bus = bus    - Ferry = ferry    - Cable car = cable_car    - Gondola = gondola    - Funicular = funicular
type: Int|Type of maneuver.    - kNone = 0;    - kStart = 1;    - kStartRight = 2;    - kStartLeft = 3;    - kDestination = 4;    - kDestinationRight = 5;    - kDestinationLeft = 6;    - kBecomes = 7;    - kContinue = 8;    - kSlightRight = 9;    - kRight = 10;    - kSharpRight = 11;    - kUturnRight = 12;    - kUturnLeft = 13;    - kSharpLeft = 14;    - kLeft = 15;    - kSlightLeft = 16;    - kRampStraight = 17;    - kRampRight = 18;    - kRampLeft = 19;    - kExitRight = 20;    - kExitLeft = 21;    - kStayStraight = 22;    - kStayRight = 23;    - kStayLeft = 24;    - kMerge = 25;    - kRoundaboutEnter = 26;    - kRoundaboutExit = 27;    - kFerryEnter = 28;    - kFerryExit = 29;    - kTransit = 30;    - kTransitTransfer = 31;    - kTransitRemainOn = 32;    - kTransitConnectionStart = 33;    - kTransitConnectionTransfer = 34;    - kTransitConnectionDestination = 35;    - kPostTransitConnectionDestination = 36;
verbalPreTransitionInstruction: String|Text suitable for use as a verbal message immediately prior to the maneuver transition. For example “Turn right onto North Prince Street, U.S. 2 22”.