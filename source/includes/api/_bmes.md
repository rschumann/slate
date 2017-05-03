# Business model elements

## How obtain all business-model-elements

> To obtain all business model elements:

```shell
curl -X GET http://localhost:3000/business-model-elements \
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
      "id": "175",
      "type": "bmes",
      "attributes": {
        "name": "Green Building/ Energy Efficiency Act",
        "description": null
      },
      "relationships": {
        "enablings": {
          "data": []
        },
        "categories": {
          "data": []
        }
      }
    },
    {
      "id": "174",
      "type": "bmes",
      "attributes": {
        "name": "State/Local Government",
        "description": null
      },
      "relationships": {
        "enablings": {
          "data": []
        },
        "categories": {
          "data": []
        }
      }
    },
    {
      "id": "173",
      "type": "bmes",
      "attributes": {
        "name": "Climate-Change Mitigation Plan or Carbon Reduction Goals",
        "description": null
      },
      "relationships": {
        "enablings": {
          "data": []
        },
        "categories": {
          "data": []
        }
      }
    },
    {
      "id": "172",
      "type": "bmes",
      "attributes": {
        "name": "Building Envelope",
        "description": null
      },
      "relationships": {
        "enablings": {
          "data": []
        },
        "categories": {
          "data": []
        }
      }
    },
    {
      "id": "171",
      "type": "bmes",
      "attributes": {
        "name": "Sustainable Landscaping",
        "description": null
      },
      "relationships": {
        "enablings": {
          "data": []
        },
        "categories": {
          "data": []
        }
      }
    },
    {
      "id": "170",
      "type": "bmes",
      "attributes": {
        "name": "Climate-Change Mitigation Programs or Carbon Reduction Goals",
        "description": null
      },
      "relationships": {
        "enablings": {
          "data": []
        },
        "categories": {
          "data": []
        }
      }
    },
    {
      "id": "169",
      "type": "bmes",
      "attributes": {
        "name": "Energy Performance/ Sustainability Certificate or Standards",
        "description": null
      },
      "relationships": {
        "enablings": {
          "data": []
        },
        "categories": {
          "data": []
        }
      }
    },
    {
      "id": "168",
      "type": "bmes",
      "attributes": {
        "name": "Regulations for Energy Declaration and Certification",
        "description": null
      },
      "relationships": {
        "enablings": {
          "data": []
        },
        "categories": {
          "data": []
        }
      }
    },
    {
      "id": "167",
      "type": "bmes",
      "attributes": {
        "name": "Indoor Air Quality Control",
        "description": null
      },
      "relationships": {
        "enablings": {
          "data": []
        },
        "categories": {
          "data": []
        }
      }
    },
    {
      "id": "166",
      "type": "bmes",
      "attributes": {
        "name": "Building Codes/Energy Codes",
        "description": null
      },
      "relationships": {
        "enablings": {
          "data": []
        },
        "categories": {
          "data": []
        }
      }
    }
  ],
  "links": {
    "first": "http://localhost:3000/business-model-elements?page%5Bnumber%5D=1",
    "prev": "http://localhost:3000/business-model-elements?page%5Bnumber%5D=1",
    "next": "http://localhost:3000/business-model-elements?page%5Bnumber%5D=2&page%5Bsize%5D=10",
    "last": "http://localhost:3000/business-model-elements?page%5Bnumber%5D=18&page%5Bsize%5D=10",
    "self": "http://localhost:3000/business-model-elements?page%5Bnumber%5D=1&page%5Bsize%5D=10"
  }
}
```

### Pagination params

| Field           | Description                | Type
| -------------   |:-------------:| -----:|
| page[size]      | Number elements per page   | Number
| page[number]    | Number of page             | Number

> Return the business-model-elements of the page 2 with 5 elements per page

```shell
curl -X GET http://localhost:3000/business-model-elements?page[size]=5&page[number]=2
```

### Filter params

Available filters:

| Field         | Description           | Type
| ------------- |:-------------:| -----:|
| sort          | Sort json response by specific attributes (name, created_at, updated_at) | Text


> To obtain all business model elements sorted by name:

```shell
curl -X GET http://localhost:3000/business-model-elements?sort=name \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

```shell
curl -X GET http://localhost:3000/business-model-elements?sort=-name \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

## How to obtain specific business model

> To obtain specific business model:

```shell
curl -X GET http://localhost:3000/business-model-elements/1 \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="success">
Remember — the response is jsonapi format
</aside>


## Creating an Business model element

In order to create a business model, you need an authorization token for current admin.

Only admin should be able to create Business model elements

To create an business model, you need to define all of the required fields in the request body. The fields that compose a business model are:

| Field               | Description                                                   | Type   | Values                                          | Required |
| ------------------  | -------------------------------------------------------------:| ------:| -----------------------------------------------:|  -------:|
| name                | Name of the business model                                    | Text   | Any Text                                        | Yes
| description         | Business model element description                            | Text   | AnyText                                         | No
| category_ids        | Id of categories (Business model element category)            | Array  | [1, 2, 3 ... ]                                  | No
| project_ids         | Id of projects (Study case)                                   | Array  | [1, 2, 3 ... ]                                  | No
| enabling_ids        | Id of enablings                                               | Array  | [1, 2, 3 ... ]                                  | No

> To create an business model, you have to do a POST with the following body:

```shell
curl -X POST http://localhost:3000/business-model-elements \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json" -d \
'{__
  "business model": {
      "name": "Business model element one",
      "description": "Lorem ipsum...",
      more attributes...
  }
}'
```
<aside class="notice">
  Remember that create business model is an authenticated endpoint!
</aside>


## Updating an Business model element

In order to modify the business model, you can PUT/PATCH a request.
It accepts the same parameters as the _create business model_ endpoint, and you will need an authentication token.

> An example update request:

```shell
curl -X PATCH http://localhost:3000/business-model-elements/<business model-id> \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"  -d \
'{__
  "business model": {
      "name": "Another name for the business model"
  }
}'
```

<aside class="notice">
Remember — create business model is an authenticated endpoint!
</aside>

## Deleting an Business model element
You can delete a business model! Just send a DELETE request to the endpoint:

```shell
curl -X DELETE http://localhost:3000/business-model-elements/<business model-id> \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="notice">
Remember — create business model is an authenticated endpoint!
</aside>
