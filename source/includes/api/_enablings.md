# Enablings

## How obtain all enablings

To obtain all enablings:

```shell
curl -X GET http://localhost:3000/enablings \
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
      "id": "204",
      "type": "enablings",
      "attributes": {
        "name": "Availability of funding and technical capacity to implement such initiatives and programs.",
        "description": null,
        "assessment_value": "Success"
      },
      "relationships": {
        "category": {
          "data": {
            "id": "56",
            "type": "categories"
          }
        },
        "bmes": {
          "data": [
            {
              "id": "140",
              "type": "bmes"
            }
          ]
        }
      }
    },
    {
      "id": "203",
      "type": "enablings",
      "attributes": {
        "name": "Needs to ensure that there are adequate setbacks from adjacent properties.",
        "description": null,
        "assessment_value": "Success"
      },
      "relationships": {
        "category": {
          "data": {
            "id": "60",
            "type": "categories"
          }
        },
        "bmes": {
          "data": [
            {
              "id": "139",
              "type": "bmes"
            }
          ]
        }
      }
    },
    {
      "id": "202",
      "type": "enablings",
      "attributes": {
        "name": "Requires an amendment to the Zoning Code and/or Building Regulations, which could be a protracted process.",
        "description": null,
        "assessment_value": "Barrier"
      },
      "relationships": {
        "category": {
          "data": {
            "id": "84",
            "type": "categories"
          }
        },
        "bmes": {
          "data": [
            {
              "id": "139",
              "type": "bmes"
            }
          ]
        }
      }
    },
    {
      "id": "201",
      "type": "enablings",
      "attributes": {
        "name": "Structuring bonuses and certification requirements that are aligned with each other, and are attractive to developers.",
        "description": null,
        "assessment_value": "Success"
      },
      "relationships": {
        "category": {
          "data": {
            "id": "60",
            "type": "categories"
          }
        },
        "bmes": {
          "data": [
            {
              "id": "138",
              "type": "bmes"
            }
          ]
        }
      }
    },
    {
      "id": "200",
      "type": "enablings",
      "attributes": {
        "name": "Rebates structured such that they are attractive to consumers and encourage resource conservation.",
        "description": null,
        "assessment_value": "Success"
      },
      "relationships": {
        "category": {
          "data": {
            "id": "81",
            "type": "categories"
          }
        },
        "bmes": {
          "data": [
            {
              "id": "136",
              "type": "bmes"
            }
          ]
        }
      }
    },
    {
      "id": "199",
      "type": "enablings",
      "attributes": {
        "name": "Publicly-owned utility companies.",
        "description": null,
        "assessment_value": "Success"
      },
      "relationships": {
        "category": {
          "data": {
            "id": "82",
            "type": "categories"
          }
        },
        "bmes": {
          "data": [
            {
              "id": "136",
              "type": "bmes"
            }
          ]
        }
      }
    },
    {
      "id": "198",
      "type": "enablings",
      "attributes": {
        "name": "Structuring fee reductions such that they are attractive to developers.",
        "description": null,
        "assessment_value": "Success"
      },
      "relationships": {
        "category": {
          "data": {
            "id": "81",
            "type": "categories"
          }
        },
        "bmes": {
          "data": [
            {
              "id": "135",
              "type": "bmes"
            }
          ]
        }
      }
    },
    {
      "id": "197",
      "type": "enablings",
      "attributes": {
        "name": "Usually disbursed at the national-level.",
        "description": null,
        "assessment_value": "Barrier"
      },
      "relationships": {
        "category": {
          "data": {
            "id": "83",
            "type": "categories"
          }
        },
        "bmes": {
          "data": [
            {
              "id": "134",
              "type": "bmes"
            }
          ]
        }
      }
    },
    {
      "id": "136",
      "type": "enablings",
      "attributes": {
        "name": "Use up public funds, which could be prioritized for other purposes.",
        "description": null,
        "assessment_value": "Barrier"
      },
      "relationships": {
        "category": {
          "data": {
            "id": "81",
            "type": "categories"
          }
        },
        "bmes": {
          "data": [
            {
              "id": "75",
              "type": "bmes"
            }
          ]
        }
      }
    },
    {
      "id": "134",
      "type": "enablings",
      "attributes": {
        "name": "Could be limited in size and used only for specific aspects (e.g. capital expenses).",
        "description": null,
        "assessment_value": "Barrier"
      },
      "relationships": {
        "category": {
          "data": {
            "id": "65",
            "type": "categories"
          }
        },
        "bmes": {
          "data": [
            {
              "id": "134",
              "type": "bmes"
            }
          ]
        }
      }
    }
  ],
  "links": {
    "first": "http://localhost:3000/enablings?page%5Bnumber%5D=1",
    "prev": "http://localhost:3000/enablings?page%5Bnumber%5D=1",
    "next": "http://localhost:3000/enablings?page%5Bnumber%5D=2&page%5Bsize%5D=10",
    "last": "http://localhost:3000/enablings?page%5Bnumber%5D=21&page%5Bsize%5D=10",
    "self": "http://localhost:3000/enablings?page%5Bnumber%5D=1&page%5Bsize%5D=10"
  }
}
```

### Pagination params

| Field           | Description                | Type
| -------------   |:-------------:| -----:|
| page[size]      | Number elements per page   | Number
| page[number]    | Number of page             | Number

> Return the enablings of the page 2 with 5 elements per page

```shell
curl -X GET http://localhost:3000/enablings?page[size]=5&page[number]=2
```

### Filter params

Available filters:

| Field         | Description           | Type
| ------------- |:-------------:| -----:|
| sort          | Sort json response by specific attributes (name, created_at, updated_at) | Text


> To obtain all enablings sorted by name:

```shell
curl -X GET http://localhost:3000/enablings?sort=name \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

```shell
curl -X GET http://localhost:3000/enablings?sort=-name \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

## How to obtain specific enabling

To obtain specific enabling:

```shell
curl -X GET http://localhost:3000/enablings/1 \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="success">
Remember — the response is jsonapi format
</aside>


## Creating an Enabling

In order to create a enabling, you need an authorization token for current admin.

Only admin should be able to create Enablings

To create an enabling, you need to define all of the required fields in the request body. The fields that compose a enabling are:

| Field               | Description                                                   | Type   | Values                                          | Required |
| ------------------  | -------------------------------------------------------------:| ------:| -----------------------------------------------:|  -------:|
| name                | Name of the enabling                                              | Text   | Any Text                                        | Yes
| description         | Enabling description                                              | Text   | AnyText                                         | No
| category_id         | Id of category (Enabling category)                                | Number | 1, 2, 3 ...                                     | No
| assessment_value    | Enabling value                                                    | Text   | Available:  Success, Barrier                    | No
| bme_ids             | Id of business model elements                                     | Array  | [1, 2, 3 ... ]                                  | No

> To create an enabling, you have to do a POST with the following body:

```shell
curl -X POST http://localhost:3000/enablings \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json" -d \
'{__
  "enabling": {
      "name": "Enabling one",
      "description": "Lorem ipsum...",
      "assessment_value": "Success",
      more attributes...
  }
}'
```

<aside class="notice">
  Remember that create enabling is an authenticated endpoint!
</aside>


## Updating an Enabling

In order to modify the enabling, you can PUT/PATCH a request.
It accepts the same parameters as the _create enabling_ endpoint, and you will need an authentication token.

> An example update request:

```shell
curl -X PATCH http://localhost:3000/enablings/<enabling-id> \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"  -d \
'{__
  "enabling": {
      "name": "Another name for the enabling"
  }
}'
```

<aside class="notice">
Remember — create enabling is an authenticated endpoint!
</aside>

## Deleting an Enabling
You can delete a enabling! Just send a DELETE request to the endpoint:

```shell
curl -X DELETE http://localhost:3000/enablings/<enabling-id> \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="notice">
Remember — create enabling is an authenticated endpoint!
</aside>
