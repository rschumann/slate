# Cities

## How obtain all cities

To obtain all cities:

```shell
curl -X GET http://localhost:3000/cities \
-H "SC-API-KEY: Bearer <your-api-key>" \
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
      "id": "7327",
      "type": "cities",
      "attributes": {
        "name": "Tel Aviv",
        "iso": "ISR",
        "lat": null,
        "lng": null,
        "province": null
      },
      "relationships": {
        "country": {
          "data": null
        }
      }
    },
    {
      "id": "7326",
      "type": "cities",
      "attributes": {
        "name": "Washington, DC",
        "iso": "USA",
        "lat": null,
        "lng": null,
        "province": null
      },
      "relationships": {
        "country": {
          "data": null
        }
      }
    },
    {
      "id": "7325",
      "type": "cities",
      "attributes": {
        "name": "Montreal",
        "iso": "CAN",
        "lat": null,
        "lng": null,
        "province": null
      },
      "relationships": {
        "country": {
          "data": null
        }
      }
    },
    {
      "id": "7324",
      "type": "cities",
      "attributes": {
        "name": "Santiago de Chile",
        "iso": "CHL",
        "lat": null,
        "lng": null,
        "province": null
      },
      "relationships": {
        "country": {
          "data": null
        }
      }
    },
    {
      "id": "7323",
      "type": "cities",
      "attributes": {
        "name": "Municipality of Las Condes",
        "iso": "CHL",
        "lat": null,
        "lng": null,
        "province": null
      },
      "relationships": {
        "country": {
          "data": null
        }
      }
    },
    {
      "id": "7322",
      "type": "cities",
      "attributes": {
        "name": "Bulawayo",
        "iso": "ZWE",
        "lat": "-20.16999754",
        "lng": "28.58000199",
        "province": "Bulawayo"
      },
      "relationships": {
        "country": {
          "data": {
            "id": "234",
            "type": "countries"
          }
        }
      }
    },
    {
      "id": "7321",
      "type": "cities",
      "attributes": {
        "name": "Harare",
        "iso": "ZWE",
        "lat": "-17.81778969",
        "lng": "31.04470943",
        "province": "Harare"
      },
      "relationships": {
        "country": {
          "data": {
            "id": "234",
            "type": "countries"
          }
        }
      }
    },
    {
      "id": "7320",
      "type": "cities",
      "attributes": {
        "name": "Chitungwiza",
        "iso": "ZWE",
        "lat": "-18.00000079",
        "lng": "31.10000321",
        "province": "Harare"
      },
      "relationships": {
        "country": {
          "data": {
            "id": "234",
            "type": "countries"
          }
        }
      }
    },
    {
      "id": "7319",
      "type": "cities",
      "attributes": {
        "name": "Kadoma",
        "iso": "ZWE",
        "lat": "-18.33000649",
        "lng": "29.90994665",
        "province": "Mashonaland West"
      },
      "relationships": {
        "country": {
          "data": {
            "id": "234",
            "type": "countries"
          }
        }
      }
    },
    {
      "id": "7318",
      "type": "cities",
      "attributes": {
        "name": "Mutare",
        "iso": "ZWE",
        "lat": "-18.97001911",
        "lng": "32.6500378",
        "province": "Manicaland"
      },
      "relationships": {
        "country": {
          "data": {
            "id": "234",
            "type": "countries"
          }
        }
      }
    }
  ],
  "links": {
    "first": "http://localhost:3000/cities?page%5Bnumber%5D=1",
    "prev": "http://localhost:3000/cities?page%5Bnumber%5D=1",
    "next": "http://localhost:3000/cities?page%5Bnumber%5D=2&page%5Bsize%5D=10",
    "last": "http://localhost:3000/cities?page%5Bnumber%5D=733&page%5Bsize%5D=10",
    "self": "http://localhost:3000/cities?page%5Bnumber%5D=1&page%5Bsize%5D=10"
  }
}
```

### Pagination params

| Field           | Description                | Type
| -------------   |:-------------:| -----:|
| page[size]      | Number elements per page   | Number
| page[number]    | Number of page             | Number

> Return the cities of the page 2 with 5 elements per page

```shell
curl -X GET http://localhost:3000/cities?page[size]=5&page[number]=2
```

### Filter params

Available filters:

| Field         | Description           | Type
| ------------- |:-------------:| -----:|
| sort          | Sort json response by specific attributes (name, created_at, updated_at) | Text
| search        | Search in name | Text
| country       | Search in country | Integer


> To obtain all cities sorted by name:

```shell
curl -X GET http://localhost:3000/cities?sort=name \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

```shell
curl -X GET http://localhost:3000/cities?sort=-name \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

> To search cities sorted by name:

```shell
curl -X GET http://localhost:3000/cities?search=term&sort=name \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

> To filter cities by country sorted by name:

```shell
curl -X GET http://localhost:3000/cities?country=<country-id>&sort=name \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

## How to obtain specific city

To obtain specific city:

```shell
curl -X GET http://localhost:3000/cities/330 \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="success">
Remember — the response is jsonapi format
</aside>


## Creating a City

In order to create a city, you need an authorization token for current admin.

Only admin should be able to create Cities

To create a city, you need to define all of the required fields in the request body. The fields that compose a city are:

| Field               | Description                                                   | Type   | Values                                          | Required |
| ------------------  | -------------------------------------------------------------:| ------:| -----------------------------------------------:|  -------:|
| name                | Name of the city                                              | Text   | Any Text                                        | Yes
| country_id          | Id of country                                                 | Number | 1, 2, 3 ...                                     | No
| province            | City province                                                 | Text   | AnyText                                         | No
| lat                 | Latitude of the city                                          | Text   | Valid latitude                                  | No
| lng                 | Longtitude of the city                                        | Text   | Valid longtitude                                | No
| iso                 | Iso of the country                                            | Text   | Valid iso (ESP)                                 | No

> To create a city, you have to do a POST with the following body:

```shell
curl -X POST http://localhost:3000/cities \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json" -d \
'{__
  "city": {
      "name": "City one",
      "iso": "ESP",
      more attributes...
  }
}'
```
<aside class="notice">
  Remember that create city is an authenticated endpoint!
</aside>


## Updating a City

In order to modify the city, you can PUT/PATCH a request.
It accepts the same parameters as the _create city_ endpoint, and you will need an authentication token.

> An example update request:

```shell
curl -X PATCH http://localhost:3000/cities/<city-id> \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"  -d \
'{__
  "city": {
      "name": "Another name for the city",
      "is_active": true
  }
}'
```

<aside class="notice">
Remember — create city is an authenticated endpoint!
</aside>

## Deleting a City
You can delete a city! Just send a DELETE request to the endpoint:

```shell
curl -X DELETE http://localhost:3000/cities/<city-id> \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="notice">
Remember — create city is an authenticated endpoint!
</aside>
