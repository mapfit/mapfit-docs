---
title: "Directions"
excerpt: "mapfit.Directions"
---

# Directions  
### mapfit.Directions    

Constructor | Description
------------|------------
mapfit.Directions(apiKey:String, apiUrl:String); | Construct a new Directions instance with your api key and the Mapfit api url: https://api.mapfit.com/v2.

Method | Descriptions
-------|-------------
route(originAddress: String, destinationAddress: String,  originLocation: LatLng, estinationLocation: LatLng, directionsType:   DrectionsType): Promise(resolve,reject) | Returns directions for given origin and destination. To have reliable results, you should provide an origin and destination (either addresses or geographical coordinates).  
  
  
<https://codepen.io/mapfit/pen/zamMNa>


# Directions Response
The route results are returned as a trip. This is a JSON object that contains details about the trip, including locations, a summary with basic information about the entire trip, and a list of legs.

Basic trip information includes:

Trip item | Description
----------|------------
status |Status code.
status_message | Status message
units | The specified units of length are returned. Currently will always return miles.
language | The language of the narration instructions. If the user specified a language in the directions options and the specified language was supported - this returned value will be equal to the specified value. Otherwise, this value will be the default (en-US) language.
locations | Location information is returned in the same form as it is entered with additional fields to indicate the side of the street.

The summary JSON object includes:
Summary Item | Description
-------------|------------
time | Estimated elapsed time to complete the trip.
length | Distance traveled for the entire trip. Units are either miles or kilometers based on the input units specified.
min_lat | Minimum latitude of a bounding box containing the route.
min_lon | Minimum longitude of a bounding box containing the route.
max_lat | Maximum latitude of a bounding box containing the route.
max_lon | Maximum longitude of a bounding box containing the route.


## Trip legs and maneuvers

A trip contains one or more legs. For n number of break locations, there are n-1 legs. Through locations do not create separate legs.

Each leg of the trip includes a summary, which is comprised of the same information as a trip summary but applied to the single leg of the trip. It also includes a shape, which is an encoded polyline of the route path (with 6 digits decimal precision), and a list of maneuvers as a JSON array. For more about decoding route shapes, see these code examples.

Each maneuver includes:

Maneuver | item	Description
---------|-----------------
type| Type of maneuver. See below for a list.
instruction|Written maneuver instruction. Describes the maneuver, such as "Turn right onto Main Street".
verbal_transition_alert_instruction|Text suitable for use as a verbal alert in a navigation application. The transition alert instruction will prepare the user for the forthcoming transition. For example: "Turn right onto North Prince Street".
verbal_pre_transition_instruction|Text suitable for use as a verbal message immediately prior to the maneuver transition. For example "Turn right onto North Prince Street, U.S. 2 22".
verbal_post_transition_instruction|Text suitable for use as a verbal message immediately after the maneuver transition. For example "Continue on U.S. 2 22 for 3.9 miles".
street_names|List of street names that are consistent along the entire maneuver.
begin_street_names|When present, these are the street names at the beginning of the maneuver (if they are different than the names that are consistent along the entire maneuver).
time|Estimated time along the maneuver in seconds.
length|Maneuver length in the units specified.
begin_shape_index|Index into the list of shape points for the start of the maneuver.
end_shape_index|Index into the list of shape points for the end of the maneuver.
toll|True if the maneuver has any toll, or portions of the maneuver are subject to a toll.
rough|True if the maneuver is unpaved or rough pavement, or has any portions that have rough pavement.
gate|True if a gate is encountered on this maneuver.
ferry|True if a ferry is encountered on this maneuver.
sign|Contains the interchange guide information at a road junction associated with this maneuver. See below for details.
roundabout_exit_count|The spoke to exit roundabout after entering.
depart_instruction|Written depart time instruction. Typically used with a transit maneuver, such as "Depart: 8:04 AM from 8 St - NYU".
verbal_depart_instruction|Text suitable for use as a verbal depart time instruction. Typically used with a transit maneuver, such as "Depart at 8:04 AM from 8 St - NYU".
arrive_instruction|Written arrive time instruction. Typically used with a transit maneuver, such as "Arrive: 8:10 AM at 34 St - Herald Sq".
verbal_arrive_instruction|Text suitable for use as a verbal arrive time instruction. Typically used with a transit maneuver, such as "Arrive at 8:10 AM at 34 St - Herald Sq".
transit_info|Contains the attributes that describe a specific transit route. See below for details.
verbal_multi_cue|True if the verbal_pre_transition_instruction has been appended with the verbal instruction of the next maneuver.
travel_mode|Travel mode.    - drive    - pedestrian    - bicycle    - transit
travel_type|Travel type for drive.    - car Travel type for pedestrian.     - foot Travel type for bicycle.     - road Travel type for transit.     - Tram or light rail = tram     - Metro or subway = "metro"     - Rail = rail     - Bus = bus      - Ferry = ferry     - Cable car = cable_car     - Gondola = gondola      - Funicular = funicular  

For the maneuver `type`, the following are available:
```
kNone = 0;
kStart = 1;
kStartRight = 2;
kStartLeft = 3;
kDestination = 4;
kDestinationRight = 5;
kDestinationLeft = 6;
kBecomes = 7;
kContinue = 8;
kSlightRight = 9;
kRight = 10;
kSharpRight = 11;
kUturnRight = 12;
kUturnLeft = 13;
kSharpLeft = 14;
kLeft = 15;
kSlightLeft = 16;
kRampStraight = 17;
kRampRight = 18;
kRampLeft = 19;
kExitRight = 20;
kExitLeft = 21;
kStayStraight = 22;
kStayRight = 23;
kStayLeft = 24;
kMerge = 25;
kRoundaboutEnter = 26;
kRoundaboutExit = 27;
kFerryEnter = 28;
kFerryExit = 29;
kTransit = 30;
kTransitTransfer = 31;
kTransitRemainOn = 32;
kTransitConnectionStart = 33;
kTransitConnectionTransfer = 34;
kTransitConnectionDestination = 35;
kPostTransitConnectionDestination = 36;
```