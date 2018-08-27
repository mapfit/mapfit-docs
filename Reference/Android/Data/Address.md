---
title: "Address"
excerpt: "com.mapfit.android.geocoder.model.Address"
---
## Address
### com.mapfit.android.geocoder.model.Address

Class representing the result from the Mapfit Geocoding API, including the normalized address components, geographical coordinate position and the (optional) building polygon.
```java
data class Address
```

Property	|Description
--|--
adminArea: String|The principal subdivision's 2-character ISO 3166-2 name. For example, in the US, adminArea would be the associated with the state's 2-character code, like "NY" for "New York State", "DC" for "Washington, D.C.", or "VI" for US Virgin Islands. For areas in which there are prefectures, provinces, or other top-level administrative divisions, the relevant principal subdivision code is returned in accordance with ISO 3166-2.
building: Building|The Building polygon associated with the address.
country: String|This is the 3-character ISO 3166-1 country code for the country in which the streetAddress is known to exist, according to one or more sources in our data set. For example, 'USA' for the United States of America, and 'DEU' for Germany (Deutschland).
entrances: List<Entrance>|When an address is found associated with an Entrance to its designated structure, the geocoder returns an entrances array with the entrances that were found, in no particular order. Only one entrance will exist unless the requested EntranceType is ALL or ALL-PEDESTRIAN.
lat: Double|The latitude (WGS84).
locality: String|This is the "city", or relevant municipality or local administrative area's name in which the street_address was found. For the USA, this will often be synonymous with "city"; though it could be a borough (like Manhattan)) or neighborhood name.
lng: Double|The longitude (WGS84).
neighborhood: String|The neighborhood, or geographically localised community within a larger city, town, suburb or rural area.
postalCode: String|The postal code associated with the response streetAddress according to at least one of our data sources. For the US, this is the 5-digit zipcode (without the plus4 addition).
responseType: ResponseType?|Response types indicate - using an integer value that can be easily checked by the client - information about the kind of response the server sent. See ResponseType for ennumerated reponse types.
streetAddress: String|This is the address (at the street level) of the resolved input. Note: secondary designators (Unit, Apt. Bldg. etc.) are not included, as the highest level of accuracy is at the structure-entrance-level. The streetAddress may include country, and/or adminArea in the address when the responseType is 13.
viewport: LatLngBounds|The bounds for the geographic region such as countries, principal subdivisions within those countries.