# Countries

## How obtain all countries

To obtain all countries:

```shell
curl -X GET http://localhost:3000/countries \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="success">
Remember — the response is jsonapi format
</aside>

> Example response:

```json
{
  "data": [
    {
      "id": "203",
      "type": "countries",
      "attributes": {
        "name": "Singapore",
        "region_name": "South-Eastern Asia",
        "iso": "SGP",
        "region_iso": "SS",
        "country_centroid": {
          "type": "Point",
          "coordinates": [
            1.36667,
            103.8
          ]
        },
        "region_centroid": {
          "type": "Point",
          "coordinates": [
            7.94110667790799,
            109.910978851168
          ]
        },
        "is_active": true
      }
    },
    {
      "id": "28",
      "type": "countries",
      "attributes": {
        "name": "Sweden",
        "region_name": "Northern Europe",
        "iso": "SWE",
        "region_iso": "NE",
        "country_centroid": {
          "type": "Point",
          "coordinates": [
            62,
            15
          ]
        },
        "region_centroid": {
          "type": "Point",
          "coordinates": [
            70.6996532290073,
            -24.4266546450261
          ]
        },
        "is_active": true
      }
    },
    {
      "id": "35",
      "type": "countries",
      "attributes": {
        "name": "Turkey",
        "region_name": "Western Asia",
        "iso": "TUR",
        "region_iso": "WS",
        "country_centroid": {
          "type": "Point",
          "coordinates": [
            39,
            35
          ]
        },
        "region_centroid": {
          "type": "Point",
          "coordinates": [
            28.4515048892831,
            43.3878415812532
          ]
        },
        "is_active": true
      }
    },
    {
      "id": "93",
      "type": "countries",
      "attributes": {
        "name": "India",
        "region_name": "South-Central Asia",
        "iso": "IND",
        "region_iso": "SC",
        "country_centroid": {
          "type": "Point",
          "coordinates": [
            22,
            79
          ]
        },
        "region_centroid": {
          "type": "Point",
          "coordinates": [
            35.3805743715067,
            68.9353807947497
          ]
        },
        "is_active": true
      }
    },
    {
      "id": "37",
      "type": "countries",
      "attributes": {
        "name": "United States",
        "region_name": "North America",
        "iso": "USA",
        "region_iso": "NM",
        "country_centroid": {
          "type": "Point",
          "coordinates": [
            39.76,
            -98.5
          ]
        },
        "region_centroid": {
          "type": "Point",
          "coordinates": [
            55.1397926304534,
            -103.939500476328
          ]
        },
        "is_active": true
      }
    },
    {
      "id": "155",
      "type": "countries",
      "attributes": {
        "name": "Canada",
        "region_name": "North America",
        "iso": "CAN",
        "region_iso": "NM",
        "country_centroid": {
          "type": "Point",
          "coordinates": [
            60.10867,
            -113.64258
          ]
        },
        "region_centroid": {
          "type": "Point",
          "coordinates": [
            55.1397926304534,
            -103.939500476328
          ]
        },
        "is_active": true
      }
    },
    {
      "id": "85",
      "type": "countries",
      "attributes": {
        "name": "Colombia",
        "region_name": "South America",
        "iso": "COL",
        "region_iso": "SM",
        "country_centroid": {
          "type": "Point",
          "coordinates": [
            4,
            -73.25
          ]
        },
        "region_centroid": {
          "type": "Point",
          "coordinates": [
            -15.2231547189536,
            -60.8171054886641
          ]
        },
        "is_active": true
      }
    },
    {
      "id": "196",
      "type": "countries",
      "attributes": {
        "name": "Mexico",
        "region_name": "Central America",
        "iso": "MEX",
        "region_iso": "CM",
        "country_centroid": {
          "type": "Point",
          "coordinates": [
            23,
            -102
          ]
        },
        "region_centroid": {
          "type": "Point",
          "coordinates": [
            21.8133558473591,
            -99.2505808667876
          ]
        },
        "is_active": true
      }
    },
    {
      "id": "78",
      "type": "countries",
      "attributes": {
        "name": "Argentina",
        "region_name": "South America",
        "iso": "ARG",
        "region_iso": "SM",
        "country_centroid": {
          "type": "Point",
          "coordinates": [
            -34,
            -64
          ]
        },
        "region_centroid": {
          "type": "Point",
          "coordinates": [
            -15.2231547189536,
            -60.8171054886641
          ]
        },
        "is_active": true
      }
    },
    {
      "id": "157",
      "type": "countries",
      "attributes": {
        "name": "Chile",
        "region_name": "South America",
        "iso": "CHL",
        "region_iso": "SM",
        "country_centroid": {
          "type": "Point",
          "coordinates": [
            -30,
            -71
          ]
        },
        "region_centroid": {
          "type": "Point",
          "coordinates": [
            -15.2231547189536,
            -60.8171054886641
          ]
        },
        "is_active": true
      }
    }
  ],
  "links": {
    "first": "http://localhost:3000/countries?page%5Bnumber%5D=1",
    "prev": "http://localhost:3000/countries?page%5Bnumber%5D=1",
    "next": "http://localhost:3000/countries?page%5Bnumber%5D=2&page%5Bsize%5D=10",
    "last": "http://localhost:3000/countries?page%5Bnumber%5D=24&page%5Bsize%5D=10",
    "self": "http://localhost:3000/countries?page%5Bnumber%5D=1&page%5Bsize%5D=10"
  }
}
```

### Pagination params

| Field           | Description                | Type
| -------------   |:-------------:| -----:|
| page[size]      | Number elements per page   | Number
| page[number]    | Number of page             | Number

> Return the countries of the page 2 with 5 elements per page

```shell
curl -X GET http://localhost:3000/countries?page[size]=5&page[number]=2
```

### Filter params

Available filters:

| Field         | Description           | Type
| ------------- |:-------------:| -----:|
| sort          | Sort json response by specific attributes (name, created_at, updated_at) | Text


> To obtain all countries sorted by name:

```shell
curl -X GET http://localhost:3000/countries?sort=name \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

```shell
curl -X GET http://localhost:3000/countries?sort=-name \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

## How to obtain specific country

To obtain specific country:

```shell
curl -X GET http://localhost:3000/countries/33 \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="success">
Remember — the response is jsonapi format
</aside>


## Creating a Country

In order to create a country, you need an authorization token for current admin.

Only admin should be able to create Countries

To create a country, you need to define all of the required fields in the request body. The fields that compose a country are:

| Field               | Description                                                   | Type   | Values                                          | Required |
| ------------------  | -------------------------------------------------------------:| ------:| -----------------------------------------------:|  -------:|
| name                | Name of the country                                           | Text   | Any Text                                        | Yes
| region_name         | Name of global region                                         | Text   | Any Text                                        | No
| region_centroid     | JSON data for centroid                                        | JSONB  | ANY JSON                                        | No
| country_centroid    | JSON data for centroid                                        | JSONB  | Any JSON                                        | No
| region_iso          | Ico of global region                                          | Text   | Valid region iso                                | No
| iso                 | Iso of the country                                            | Text   | Valid iso (ESP)                                 | Yes
| is_active           | Activate deactiveta impacts (only accessible by admin and publisher) | Boolean  | default value true                    | No


> To create a country, you have to do a POST with the following body:

```shell
curl -X POST http://localhost:3000/countries \
-H "Authorization: Bearer <your-token>" \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json" -d \
'{__
  "country": {
      "name": "Spain",
      "iso": "ESP",
      more attributes...
  }
}'
```
<aside class="notice">
  Remember that create country is an authenticated endpoint!
</aside>


## Updating a Country

In order to modify the country, you can PUT/PATCH a request.
It accepts the same parameters as the _create country_ endpoint, and you will need an authentication token.

> An example update request:

```shell
curl -X PATCH http://localhost:3000/countries/<country-id> \
-H "Authorization: Bearer <your-token>" \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"  -d \
'{__
  "country": {
      "name": "Another name for the country",
      "is_active": true
  }
}'
```

<aside class="notice">
Remember — create country is an authenticated endpoint!
</aside>

## Deleting a Country
You can delete a country! Just send a DELETE request to the endpoint:

```shell
curl -X DELETE http://localhost:3000/countries/<country-id> \
-H "Authorization: Bearer <your-token>" \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="notice">
Remember — create country is an authenticated endpoint!
</aside>
