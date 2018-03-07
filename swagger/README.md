# Swagger Codegen Assignment: Implemented a API to Identify crime
  prone areas near a GPS location
  
## Usage of Files and Data Structures using rest services hid-sp18-409 
* Pandas (open source, BSD-licensed library providing
  high-performance, easy-to-use data structures and data analysis
  tools for the Python programming language) will be used to
  manipulate the crime dataset available on
  https://catalog.data.gov/dataset/crimes-2001-to-present-398a4
* This crime dataset contains nearly 600,000(1.5GB) crime details
  across USA.
* For the sake of demonstration I have only used 10,000 crime details.
* Based on the GPS location of the user nearby crimes will be
  returned.

## Instructions for docker
* you should install docker.
* change the directory to swagger folder
* Build the project using docker
  * ```docker build -t <your_docker_username>/swagger .```
* Start the container attached to a custom port to which the client
  will forward connections to the container using following command
  * ```docker run -p 5050:8080 <your_docker_username>/swagger```
* Test the service using following get command
  * ```curl
    http://127.0.0.1:5050/v1/crimes?latitude=41.891398861&longitude=-87.744384567```
* Get the container ID using following command
  * ```docker ps```
* Stop the service using following commands
  * ```docker stop <container_ID>``` or ```docker stop $(docker ps -a
    -q -f status=running)```
* Optional starting mechanism (interactive mode)
  * ```docker run --rm -it kadupitiya/swagger bash```
  * ```make start```
  * ```make stop```
	
	
## Executing instructions with ubunu
* you should be running this program in python 3 environment.
* git clone the project.
* change the directory to swagger folder
* create the swagger server with following command
  * ```make service```
* run the swagger server with following command
  * ```make start```
* Install the client program using following command
  * ```make client```
* test the program using following command
  * ```make test```
* stop the service using following command
  * ```make stop```
* clean the server and client codes using following command
  * ```make clean```

## API informations and Results
* End Point : /crimes
* http://localhost:8080/v1/crimes?latitude=41.981398861&longitude=-87.754384567
  * The Crimes endpoint returns information about the crimes
    previously happened at a given location or nearby locations.
  * latitude and longitude should be passed with the request
  * The response includes lists of crimes in the proper display order
  * Nearby distance is defined in the program and currently defaulted
    to 0.1 Miles(528 foot).

### Sample json response for GET request on
    http://localhost:8080/v1/crimes?latitude=41.891398861&longitude=-87.744384567

```json
[
    {
        "arrested": "false",
        "beat_code": "1623",
        "block": "050XX W ARGYLE ST",
        "case_number": "HY198498",
        "community_area_code": "11",
        "crime_code": "0620",
        "crime_id": "10009166",
        "date": "03/25/2015 07:00:00 AM",
        "district_code": "016",
        "domestic": "false",
        "fbi_code": "05",
        "gps_location": "(41.971606007, -87.753880329)",
        "latitude": "41.971606007",
        "location_cat": "APARTMENT",
        "longitude": "-87.753880329",
        "primary_description": "BURGLARY",
        "secondary_description": "UNLAWFUL ENTRY",
        "updated_on": "02/10/2018 03:50:01 PM",
        "ward_code": "45",
        "x_coordinate": "1141823",
        "y_coordinate": "1932776",
        "year": "2015"
    },
    {
        "arrested": "false",
        "beat_code": "1621",
        "block": "060XX N CALDWELL AVE",
        "case_number": "HY195283",
        "community_area_code": "12",
        "crime_code": "1320",
        "crime_id": "10005335",
        "date": "03/11/2015 08:00:00 AM",
        "district_code": "016",
        "domestic": "false",
        "fbi_code": "14",
        "gps_location": "(41.991792049, -87.754907507)",
        "latitude": "41.991792049",
        "location_cat": "STREET",
        "longitude": "-87.754907507",
        "primary_description": "CRIMINAL DAMAGE",
        "secondary_description": "TO VEHICLE",
        "updated_on": "02/10/2018 03:50:01 PM",
        "ward_code": "45",
        "x_coordinate": "1141494",
        "y_coordinate": "1940130",
        "year": "2015"
    },
    {
        "arrested": "false",
        "beat_code": "1623",
        "block": "044XX N MILWAUKEE AVE",
        "case_number": "HY190143",
        "community_area_code": "15",
        "crime_code": "1310",
        "crime_id": "10000180",
        "date": "03/19/2015 04:29:00 AM",
        "district_code": "016",
        "domestic": "false",
        "fbi_code": "14",
        "gps_location": "(41.96085819, -87.754672619)",
        "latitude": "41.96085819",
        "location_cat": "COMMERCIAL / BUSINESS OFFICE",
        "longitude": "-87.754672619",
        "primary_description": "CRIMINAL DAMAGE",
        "secondary_description": "TO PROPERTY",
        "updated_on": "02/10/2018 03:50:01 PM",
        "ward_code": "45",
        "x_coordinate": "1141634",
        "y_coordinate": "1928858",
        "year": "2015"
    },
    {
        "arrested": "false",
        "beat_code": "1623",
        "block": "044XX N MILWAUKEE AVE",
        "case_number": "HY202063",
        "community_area_code": "15",
        "crime_code": "0320",
        "crime_id": "10012406",
        "date": "03/28/2015 07:30:00 PM",
        "district_code": "016",
        "domestic": "false",
        "fbi_code": "03",
        "gps_location": "(41.961001513, -87.754796331)",
        "latitude": "41.961001513",
        "location_cat": "APARTMENT",
        "longitude": "-87.754796331",
        "primary_description": "ROBBERY",
        "secondary_description": "STRONGARM - NO WEAPON",
        "updated_on": "02/10/2018 03:50:01 PM",
        "ward_code": "45",
        "x_coordinate": "1141600",
        "y_coordinate": "1928910",
        "year": "2015"
    },
    {
        "arrested": "true",
        "beat_code": "1623",
        "block": "044XX N MILWAUKEE AVE",
        "case_number": "HY197427",
        "community_area_code": "15",
        "crime_code": "1811",
        "crime_id": "10007602",
        "date": "03/25/2015 01:33:00 AM",
        "district_code": "016",
        "domestic": "false",
        "fbi_code": "18",
        "gps_location": "(41.961029065, -87.754818142)",
        "latitude": "41.961029065",
        "location_cat": "OTHER",
        "longitude": "-87.754818142",
        "primary_description": "NARCOTICS",
        "secondary_description": "POSS: CANNABIS 30GMS OR LESS",
        "updated_on": "02/10/2018 03:50:01 PM",
        "ward_code": "45",
        "x_coordinate": "1141594",
        "y_coordinate": "1928920",
        "year": "2015"
    },
    {
        "arrested": "false",
        "beat_code": "1623",
        "block": "051XX W LAWRENCE AVE",
        "case_number": "HY194086",
        "community_area_code": "11",
        "crime_code": "0820",
        "crime_id": "10004227",
        "date": "03/22/2015 02:00:00 AM",
        "district_code": "016",
        "domestic": "false",
        "fbi_code": "06",
        "gps_location": "(41.967935332, -87.755182208)",
        "latitude": "41.967935332",
        "location_cat": "STREET",
        "longitude": "-87.755182208",
        "primary_description": "THEFT",
        "secondary_description": "$500 AND UNDER",
        "updated_on": "02/10/2018 03:50:01 PM",
        "ward_code": "45",
        "x_coordinate": "1141478",
        "y_coordinate": "1931436",
        "year": "2015"
    },
    {
        "arrested": "true",
        "beat_code": "1624",
        "block": "050XX W MONTROSE AVE",
        "case_number": "HY195394",
        "community_area_code": "15",
        "crime_code": "1811",
        "crime_id": "10005445",
        "date": "03/23/2015 01:06:00 PM",
        "district_code": "016",
        "domestic": "false",
        "fbi_code": "18",
        "gps_location": "(41.960639162, -87.753685563)",
        "latitude": "41.960639162",
        "location_cat": "ALLEY",
        "longitude": "-87.753685563",
        "primary_description": "NARCOTICS",
        "secondary_description": "POSS: CANNABIS 30GMS OR LESS",
        "updated_on": "02/10/2018 03:50:01 PM",
        "ward_code": "45",
        "x_coordinate": "1141903",
        "y_coordinate": "1928780",
        "year": "2015"
    }
]
```
### End Point : /crimes/search
* http://localhost:8080/v1/crimes/search?crime_id=10007143
  * The crimes search endpoint returns information about a particular
    crime for a given crime_id.
  * The response includes a crime object in the proper display order

* Sample json response for GET request on
  http://localhost:8080/v1/crimes/search?crime_id=10007143

```json
{
  "arrested": "false",
  "beat_code": "2522",
  "block": "047XX W ARMITAGE AVE",
  "case_number": "HY196370",
  "community_area_code": "19",
  "crime_code": "0820",
  "crime_id": "10007143",
  "date": "03/22/2015 12:00:00 PM",
  "district_code": "025",
  "domestic": "false",
  "fbi_code": "06",
  "gps_location": "(41.916951295, -87.744546501)",
  "latitude": "41.916951295",
  "location_cat": "STREET",
  "longitude": "-87.744546501",
  "primary_description": "THEFT",
  "secondary_description": "$500 AND UNDER",
  "updated_on": "02/10/2018 03:50:01 PM",
  "ward_code": "31",
  "x_coordinate": "1144498",
  "y_coordinate": "1912877",
  "year": "2015"
}
```

### End Point : /crimes/filter
* http://localhost:8080/v1/crimes?latitude=41.981398861&longitude=-87.754384567&primary_type=NARCOTICS
  * The crimes endpoint returns information about the crimes
    previously happened at a given location or nearby locations
    filtered with crime type.
  * latitude, longitude and primary_type should be passed with the
    request.
  * The response includes lists of crimes in the proper display order
  * Nearby distance is defined in the program and currently defaulted
    to 0.1 Miles(528 foot).
  * Returned list only contained requested type of crimes.

* Sample json response for GET request on
  http://localhost:8080/v1/crimes?latitude=41.981398861&longitude=-87.754384567&primary_type=NARCOTICS

```json
[
  {
    "arrested": "false",
    "beat_code": "1623",
    "block": "050XX W ARGYLE ST",
    "case_number": "HY198498",
    "community_area_code": "11",
    "crime_code": "0620",
    "crime_id": "10009166",
    "date": "03/25/2015 07:00:00 AM",
    "district_code": "016",
    "domestic": "false",
    "fbi_code": "05",
    "gps_location": "(41.971606007, -87.753880329)",
    "latitude": "41.971606007",
    "location_cat": "APARTMENT",
    "longitude": "-87.753880329",
    "primary_description": "BURGLARY",
    "secondary_description": "UNLAWFUL ENTRY",
    "updated_on": "02/10/2018 03:50:01 PM",
    "ward_code": "45",
    "x_coordinate": "1141823",
    "y_coordinate": "1932776",
    "year": "2015"
  },
  {
    "arrested": "false",
    "beat_code": "1621",
    "block": "060XX N CALDWELL AVE",
    "case_number": "HY195283",
    "community_area_code": "12",
    "crime_code": "1320",
    "crime_id": "10005335",
    "date": "03/11/2015 08:00:00 AM",
    "district_code": "016",
    "domestic": "false",
    "fbi_code": "14",
    "gps_location": "(41.991792049, -87.754907507)",
    "latitude": "41.991792049",
    "location_cat": "STREET",
    "longitude": "-87.754907507",
    "primary_description": "CRIMINAL DAMAGE",
    "secondary_description": "TO VEHICLE",
    "updated_on": "02/10/2018 03:50:01 PM",
    "ward_code": "45",
    "x_coordinate": "1141494",
    "y_coordinate": "1940130",
    "year": "2015"
  },
  {
    "arrested": "false",
    "beat_code": "1623",
    "block": "044XX N MILWAUKEE AVE",
    "case_number": "HY190143",
    "community_area_code": "15",
    "crime_code": "1310",
    "crime_id": "10000180",
    "date": "03/19/2015 04:29:00 AM",
    "district_code": "016",
    "domestic": "false",
    "fbi_code": "14",
    "gps_location": "(41.96085819, -87.754672619)",
    "latitude": "41.96085819",
    "location_cat": "COMMERCIAL / BUSINESS OFFICE",
    "longitude": "-87.754672619",
    "primary_description": "CRIMINAL DAMAGE",
    "secondary_description": "TO PROPERTY",
    "updated_on": "02/10/2018 03:50:01 PM",
    "ward_code": "45",
    "x_coordinate": "1141634",
    "y_coordinate": "1928858",
    "year": "2015"
  },
  {
    "arrested": "false",
    "beat_code": "1623",
    "block": "044XX N MILWAUKEE AVE",
    "case_number": "HY202063",
    "community_area_code": "15",
    "crime_code": "0320",
    "crime_id": "10012406",
    "date": "03/28/2015 07:30:00 PM",
    "district_code": "016",
    "domestic": "false",
    "fbi_code": "03",
    "gps_location": "(41.961001513, -87.754796331)",
    "latitude": "41.961001513",
    "location_cat": "APARTMENT",
    "longitude": "-87.754796331",
    "primary_description": "ROBBERY",
    "secondary_description": "STRONGARM - NO WEAPON",
    "updated_on": "02/10/2018 03:50:01 PM",
    "ward_code": "45",
    "x_coordinate": "1141600",
    "y_coordinate": "1928910",
    "year": "2015"
  },
  {
    "arrested": "true",
    "beat_code": "1623",
    "block": "044XX N MILWAUKEE AVE",
    "case_number": "HY197427",
    "community_area_code": "15",
    "crime_code": "1811",
    "crime_id": "10007602",
    "date": "03/25/2015 01:33:00 AM",
    "district_code": "016",
    "domestic": "false",
    "fbi_code": "18",
    "gps_location": "(41.961029065, -87.754818142)",
    "latitude": "41.961029065",
    "location_cat": "OTHER",
    "longitude": "-87.754818142",
    "primary_description": "NARCOTICS",
    "secondary_description": "POSS: CANNABIS 30GMS OR LESS",
    "updated_on": "02/10/2018 03:50:01 PM",
    "ward_code": "45",
    "x_coordinate": "1141594",
    "y_coordinate": "1928920",
    "year": "2015"
  },
  {
    "arrested": "false",
    "beat_code": "1623",
    "block": "051XX W LAWRENCE AVE",
    "case_number": "HY194086",
    "community_area_code": "11",
    "crime_code": "0820",
    "crime_id": "10004227",
    "date": "03/22/2015 02:00:00 AM",
    "district_code": "016",
    "domestic": "false",
    "fbi_code": "06",
    "gps_location": "(41.967935332, -87.755182208)",
    "latitude": "41.967935332",
    "location_cat": "STREET",
    "longitude": "-87.755182208",
    "primary_description": "THEFT",
    "secondary_description": "$500 AND UNDER",
    "updated_on": "02/10/2018 03:50:01 PM",
    "ward_code": "45",
    "x_coordinate": "1141478",
    "y_coordinate": "1931436",
    "year": "2015"
  },
  {
    "arrested": "true",
    "beat_code": "1624",
    "block": "050XX W MONTROSE AVE",
    "case_number": "HY195394",
    "community_area_code": "15",
    "crime_code": "1811",
    "crime_id": "10005445",
    "date": "03/23/2015 01:06:00 PM",
    "district_code": "016",
    "domestic": "false",
    "fbi_code": "18",
    "gps_location": "(41.960639162, -87.753685563)",
    "latitude": "41.960639162",
    "location_cat": "ALLEY",
    "longitude": "-87.753685563",
    "primary_description": "NARCOTICS",
    "secondary_description": "POSS: CANNABIS 30GMS OR LESS",
    "updated_on": "02/10/2018 03:50:01 PM",
    "ward_code": "45",
    "x_coordinate": "1141903",
    "y_coordinate": "1928780",
    "year": "2015"
  }
]

```