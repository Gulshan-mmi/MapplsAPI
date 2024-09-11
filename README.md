# MapplsApi

`MapplsApi` is a Node.js wrapper for Mappls API services. It provides methods for authentication and interacting with various Mappls API endpoints, such as geocoding, place search, and feedback submission.

## Installation

To use this package, you'll need to have `axios` and `qs` installed. You can add them by running:

# MapplsApi

`MapplsApi` is a Node.js wrapper for Mappls API services. It provides methods for authentication and interacting with various Mappls API endpoints, such as geocoding, place search, and feedback submission.

## Installation

To use this package, you'll need to have `axios` and `qs` installed. You can add them by running:

```bash
npm install axios qs
```

## Initialization

First, create an instance of MapplsApi by providing your Mappls API clientId and clientSecret. Then, you can use the available methods to interact with the Mappls API.

```bash
const MapplsApi = require('./path/to/MapplsApi');

// Initialize MapplsApi instance
const mapplsApi = new MapplsApi('YOUR_CLIENT_ID', 'YOUR_CLIENT_SECRET');
```

## Get Geocode for an Address
To get geocode information for a specific address:
```bash
const queryParams = { address: 'MG Road, Bengaluru' };
mapplsApi.getGeocode(queryParams)
    .then((data) => console.log(data))
    .catch((err) => console.error(err));
```
Output :
```bash
{
    "copResults": {
        "houseNumber": "",
        "houseName": "",
        "poi": "Hyatt Centric MG Road Bangalore",
        "street": "Old Madras Road",
        "subSubLocality": "",
        "subLocality": "Someshwarpura",
        "locality": "Ulsoor",
        "village": "",
        "subDistrict": "Bengaluru North",
        "district": "Bengaluru Urban District",
        "city": "Bengaluru",
        "state": "Karnataka",
        "pincode": "560008",
        "formattedAddress": "Hyatt Centric MG Road Bangalore, Old Madras Road, Someshwarpura, Ulsoor, Bengaluru North, Bengaluru Urban District, Bengaluru, Karnataka, 560008",
        "eLoc": "6ETF6T",
        "geocodeLevel": "city",
        "confidenceScore": 0.8
    }
}
```

## Search for Places
To perform a text search for places based on a query :
```bash
const searchParams = { query: 'restaurant in Bengaluru' };
mapplsApi.textsearch(searchParams)
    .then((data) => console.log(data))
    .catch((err) => console.error(err));
```
Output : 
```bash
{
    "suggestedLocations": [
        {
            "type": "CITY",
            "placeAddress": "Karnataka",
            "eLoc": "2UQY8X",
            "placeName": "Bengaluru",
            "alternateName": "Bangalore",
            "keywords": [],
            "distance": 0,
            "orderIndex": 1,
            "suggester": "placeName"
        },
        {
            "type": "POI",
            "placeAddress": "28th Km, Mysore Road, Hejjala Post, Near Bidadi, Bengaluru, Ramanagara, Ramanagara District, Karnataka, 562109",
            "eLoc": "C45T73",
            "placeName": "Wonderla Bangalore Park",
            "alternateName": "Wonderla Amusement Park,Wonderla Holidays Pvt Ltd,Wonder La Amusement Park,Wonderla Resort,Wonderla Bengaluru",
            "keywords": [
                "RCNAUS"
            ],
            "distance": 0,
            "orderIndex": 2,
            "suggester": "placeName"
        },
        {
            "type": "POI",
            "placeAddress": "Next To Victoria Hospital Gate, Krishna Rajendra Road, KR Market Area, New Tharagupet, Bengaluru, Karnataka, 560002",
            "eLoc": "BJ8G2W",
            "placeName": "Tippus Fort",
            "alternateName": "Tipu Sultan Fort,Tipus Fort,Bengaluru Fort,KR Market Fort,Bangalore Fort",
            "keywords": [
                "HISFRT"
            ],
            "distance": 0,
            "orderIndex": 3,
            "suggester": "placeName"
        },
        {
            "type": "POI",
            "placeAddress": "Dommasandra Anekal Taluka, Bengaluru, Karnataka, 562125",
            "eLoc": "1VDS97",
            "placeName": "Aruani Grid Track",
            "alternateName": "Aruani Grid",
            "keywords": [
                "RCNSPT"
            ],
            "distance": 0,
            "orderIndex": 4,
            "suggester": "address"
        },
        {
            "type": "POI",
            "placeAddress": "Bannerghatta Road, Bannerghatta, Bengaluru, Karnataka, 560083",
            "eLoc": "TA2S21",
            "placeName": "Bannerghatta National Park",
            "alternateName": "Bannerghatta Biological Park",
            "keywords": [
                "NTCNPK"
            ],
            "distance": 0,
            "orderIndex": 5,
            "suggester": "address"
        },
        {
            "type": "POI",
            "placeAddress": "Tasker Town, Shivaji Nagar, Bengaluru, Karnataka, 560001",
            "eLoc": "BDCD32",
            "placeName": "Commercial Street",
            "alternateName": "",
            "keywords": [
                "MKTMJR"
            ],
            "distance": 0,
            "orderIndex": 6,
            "suggester": "address"
        },
        {
            "type": "POI",
            "placeAddress": "Promenad Road, Cleveland Town, Shivaji Nagar, Bengaluru, Karnataka, 560005",
            "eLoc": "9B8XN2",
            "placeName": "St Francis Xaviers Cathedral",
            "alternateName": "St France Xaviers Cathedral Church",
            "keywords": [
                "PLPCHU"
            ],
            "distance": 0,
            "orderIndex": 7,
            "suggester": "address"
        },
        {
            "type": "LOCALITY",
            "placeAddress": "Bengaluru, Karnataka, 560064",
            "eLoc": "V1G1SD",
            "placeName": "Govindapura Bengaluru",
            "alternateName": "",
            "keywords": [],
            "distance": 0,
            "orderIndex": 8,
            "suggester": "placeName"
        },
        {
            "type": "CITY",
            "placeAddress": "Karnataka",
            "eLoc": "D38B3S",
            "placeName": "Vijayapura Bengaluru Rural",
            "alternateName": "",
            "keywords": [],
            "distance": 0,
            "orderIndex": 9,
            "suggester": "placeName"
        },
        {
            "type": "POI",
            "placeAddress": "Hosakerehalli Main Road, Phase 2, Giri Nagar, Bengaluru, Karnataka, 560085",
            "eLoc": "3T11BC",
            "placeName": "Udupi Restaurant",
            "alternateName": "",
            "keywords": [
                "FODIND"
            ],
            "distance": 0,
            "orderIndex": 10,
            "suggester": "placeName"
        }
    ],
    "userAddedLocations": [
        {
            "eLoc": "EICGJN",
            "orderIndex": 11,
            "placeAddress": "26, DVG Road Basavanagudi Bengaluru Karnataka",
            "placeName": "Nisarga Garden Restaurant",
            "type": ""
        },
        {
            "eLoc": "PKBIJ7",
            "orderIndex": 12,
            "placeAddress": "Puttanna Road Gandhi Bazaar, Basavanagudi Bengaluru Karnataka",
            "placeName": "Nisarga Bar And Restaurant",
            "type": ""
        },
        {
            "eLoc": "9127YY",
            "orderIndex": 13,
            "placeAddress": "Asmath Arcade, Varthur Near Marattahalli, Bengaluru, Karnataka. 33 m from Malgudi Restaurant, Pin-560087",
            "placeName": "Home BLR",
            "type": ""
        }
    ]
}
```

## Submit Feedback
To submit feedback using Mappls API :
```bash
const feedbackParams = {
    typedKeyword: 'restaurant',
    selectedEloc: 'xyz',
    selectedIndex: 1,
    appVersion: '1.0.0'
};
mapplsApi.mapplsFeedback(feedbackParams)
    .then((response) => console.log(response))
    .catch((err) => console.error(err));
```