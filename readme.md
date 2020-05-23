##distance-between-geocoordinates

This is an npm package that calculates the distance between two geographic coordinates.

##Installation
`npm install --save distance-between-geocoordinates`

##Usage
The function takes as input two **Point** object which consists of a **latitude** and a **longitude** and a units string(**Default Unit is km**).

_The first point may be defined as below_

    point1 = {
      lat: 41.8781,
      lng: 87.6298,
    };

_The second point may be defined as below _

        point2 = {
          lat: 40.0583,
          lng: 74.4057,
        };


To calculate the distance between the two points
  
 const distanceBetweenPoints = require("distance-between-geocoordinates");
  
 result = distanceBetweenPoints(point1, point2);
  
 console.log(`The distance between the points is ${result.distance} ${result.unit}`);
##Result
The result of the function is an object which contains the distance and the units of the distance.

    {
    	distance: 81.04778415589608,
    	unit: 'km'
    }

##Units of the distance
The distance between two points may be obtained in various units of distance.

###km
The default parameter is km and if not unit is passed, the function returns the data in km.

`result = distanceBetweenPoints(point1, point2);`
or
`result = distanceBetweenPoints(point1, point2, "km");`

###mile
`result = distanceBetweenPoints(point1, point2, "mile");`

###yards
`result = distanceBetweenPoints(point1, point2, "yard");`

###foot
`result = distanceBetweenPoints(point1, point2, "foot");`

###Nautical Mile
`result = distanceBetweenPoints(point1, point2, "n-mile");`

###Invalid Units
Invalid units will return the result in km.
`result = distanceBetweenPoints(point1, point2, "abc");`

##Errors Response
An error response is returned if

1. The input coordinates is not a number.
   {
   status: 'Error',
   error: 'Invalid Input. Coordinates Should be a Number.',
   latitude1: 'abc <- Error',
   longitude1: '75.3704 ',
   latitude2: '12.4996 ',
   longitude2: '75.3704 '
   }
   An error is indicated next to the invalid input.

1. The coordinates are in invalid range.
   Latitude should be between -90 to +90
   Longitude should be in the range -180 to +180
   {
   status: 'Error',
   error: 'Latitude or Longitude not in valid Range',
   latitude1: '150 <- Error',
   longitude1: '75.3704 ',
   latitude2: '12.4996 ',
   longitude2: '75.3704 '
   }
