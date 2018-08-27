---
title: "Directions"
excerpt: ""
---
For most use cases, directions can be retrieved through the [PlaceInfo](ref:infocard) class by calling the `enableDirectionsButton()` method; this will prompt a user flow resulting in directions from a specified start location to the clicked marker's location.  For more advanced use cases that require extracting particular data elements from the directions response, interacting with [Directions](ref:directions-2) may be necessary.

To obtain directions, you can use the `Directions` class as below. Specify an origin and destination address or coordinate to get the Route.  See [Directions](ref:directions-2) for more detail.

This request is an HTTP POST request with the following:

* `originAddress` or `originLocation`
* `destinationAddress` or `destinationLocation`

```javascript
// create request object
    let directionsReq = new mapfit.Directions("{{MY_API_KEY}}", "https://api.mapfit.com/v2");

// call `route` method, with origin and destination addresses, and travel type
    directionsReq.route(originAddress="119 w 24th st, new york, ny", destinationAddress="250 7th ave, new york, ny", type="walking")
      .then(data => (console.log("route=", data)))
      .catch(error => (console.log(" error = ", error)))
```

The response should look like the following:
```javascript
{
  "trip": {
    "summary": {
      "min_lon": -73.995056,
      "max_lat": 40.764324,
      "max_lon": -73.975204,
      "length": 1.918,
      "time": 2192,
      "min_lat": 40.744911
    },
    "status_message": "Found route between points",
    "legs": [{
      "summary": {
        "min_lon": -73.995056,
        "max_lat": 40.764324,
        "max_lon": -73.975204,
        "length": 1.918,
        "time": 2192,
        "min_lat": 40.744911
      },
      "shape": "}{zulA`rhclCq\\}T{e@uZce@c[{e@c[se@c[ke@c[if@s[k`@iWqCkBgDyBeZoRmDiCoDyBmd@uZgh@_]if@c[}d@uZ{e@s[ke@c[af@c[me@eZmh@m^gEiCs_@{VkBkAoCiB_^}TyBkAoCyBsa@gYrBcG~eAigD_b@wXsByAoCkBqa@gXsKaHcVuOsB{Aec@gYcBkAwb@wXaCiB}JqGmYcRib@eYiBkAqCkBqL_IwNmJoDyB_DyBw]mUiBkAaC{Aab@wX{e@q[mi@q]ns@m{B",
      "maneuvers": [
        {
          "begin_shape_index": 0,
          "travel_mode": "pedestrian",
          "instruction": "Walk northeast on 7th Avenue.",
          "length": 1.032,
          "street_names": ["7th Avenue"],
          "end_shape_index": 30,
          "time": 1180,
          "type": 3,
          "verbal_pre_transition_instruction": "Walk northeast on 7th Avenue for 1 mile.",
          "travel_type": "foot"
        },
        {
          "begin_shape_index": 30,
          "travel_mode": "pedestrian",
          "instruction": "Turn right onto West 45th Street.",
          "length": 0.17,
          "street_names": ["West 45th Street"],
          "end_shape_index": 32,
          "verbal_transition_alert_instruction": "Turn right onto West 45th Street.",
          "time": 192,
          "verbal_post_transition_instruction": "Continue for 2 tenths of a mile.",
          "type": 10,
          "verbal_pre_transition_instruction": "Turn right onto West 45th Street.",
          "travel_type": "foot"
        },
        {
          "begin_shape_index": 32,
          "travel_mode": "pedestrian",
          "instruction": "Turn left onto 6th Avenue/Avenue of the Americas.",
          "length": 0.598,
          "street_names": [
            "6th Avenue",
            "Avenue of the Americas"
          ],
          "end_shape_index": 58,
          "verbal_transition_alert_instruction": "Turn left onto 6th Avenue.",
          "time": 684,
          "verbal_post_transition_instruction": "Continue for 6 tenths of a mile.",
          "type": 15,
          "verbal_pre_transition_instruction": "Turn left onto 6th Avenue, Avenue of the Americas.",
          "travel_type": "foot"
        },
        {
          "begin_shape_index": 58,
          "travel_mode": "pedestrian",
          "instruction": "Turn right onto West 57th Street.",
          "length": 0.119,
          "street_names": ["West 57th Street"],
          "end_shape_index": 59,
          "verbal_transition_alert_instruction": "Turn right onto West 57th Street.",
          "time": 136,
          "verbal_post_transition_instruction": "Continue for 1 tenth of a mile.",
          "type": 10,
          "verbal_pre_transition_instruction": "Turn right onto West 57th Street.",
          "travel_type": "foot"
        },
        {
          "begin_shape_index": 59,
          "travel_mode": "pedestrian",
          "instruction": "Your destination is on the left.",
          "length": 0,
          "end_shape_index": 59,
          "verbal_transition_alert_instruction": "Your destination will be on the left.",
          "time": 0,
          "type": 6,
          "verbal_pre_transition_instruction": "Your destination is on the left.",
          "travel_type": "foot"
        }
      ]
    }],
    "language": "en-US",
    "locations": [
      {
        "lon": -73.995216,
        "side_of_street": "left",
        "type": "break",
        "lat": 40.74498
      },
      {
        "lon": -73.975044,
        "side_of_street": "left",
        "type": "break",
        "lat": 40.763706
      }
    ],
    "units": "miles",
    "status": 0
  },
  "destinationLocation": [
    -73.975046,
    40.763707
  ],
  "sourceLocation": [
    -73.995218,
    40.74498
  ]
}```