# Categories

## What is a Category?

A category is a group of categories for specific bussiness area.

## How to obtain all categories

> To obtain all categories:

```shell
curl -X GET http://localhost:3000/categories \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="success">
Remember — the response is jsonapi format and only accesible by admin or publisher user
</aside>

> Example response:

```json
{
  "data": [
    {
      "id": "125",
      "type": "categories",
      "attributes": {
        "name": "Urban energy",
        "description": null,
        "category_type": "Solution"
      },
      "relationships": {
        "parent": {
          "data": null
        },
        "children": {
          "data": [
            {
              "id": "126",
              "type": "categories"
            }
          ]
        }
      }
    },
    {
      "id": "126",
      "type": "categories",
      "attributes": {
        "name": "New efficient constructions",
        "description": null,
        "category_type": "Solution"
      },
      "relationships": {
        "parent": {
          "data": {
            "id": "125",
            "type": "categories"
          }
        },
        "children": {
          "data": [
            {
              "id": "127",
              "type": "categories"
            }
          ]
        }
      }
    },
    {
      "id": "127",
      "type": "categories",
      "attributes": {
        "name": "Whole city approaches",
        "description": null,
        "category_type": "Solution"
      },
      "relationships": {
        "parent": {
          "data": {
            "id": "126",
            "type": "categories"
          }
        },
        "children": {
          "data": []
        }
      }
    },
    {
      "id": "124",
      "type": "categories",
      "attributes": {
        "name": "Campus-level Bike-Share Systems",
        "description": null,
        "category_type": "Solution"
      },
      "relationships": {
        "parent": {
          "data": {
            "id": "119",
            "type": "categories"
          }
        },
        "children": {
          "data": []
        }
      }
    },
    {
      "id": "137",
      "type": "categories",
      "attributes": {
        "name": "Social",
        "description": null,
        "category_type": "Impact"
      },
      "relationships": {
        "parent": {
          "data": null
        },
        "children": {
          "data": [
            {
              "id": "138",
              "type": "categories"
            },
            {
              "id": "139",
              "type": "categories"
            },
            {
              "id": "141",
              "type": "categories"
            },
            {
              "id": "142",
              "type": "categories"
            },
            {
              "id": "144",
              "type": "categories"
            },
            {
              "id": "147",
              "type": "categories"
            }
          ]
        }
      }
    },
    {
      "id": "134",
      "type": "categories",
      "attributes": {
        "name": "Environmental",
        "description": null,
        "category_type": "Impact"
      },
      "relationships": {
        "parent": {
          "data": null
        },
        "children": {
          "data": [
            {
              "id": "135",
              "type": "categories"
            },
            {
              "id": "143",
              "type": "categories"
            },
            {
              "id": "148",
              "type": "categories"
            },
            {
              "id": "149",
              "type": "categories"
            }
          ]
        }
      }
    },
    {
      "id": "122",
      "type": "categories",
      "attributes": {
        "name": "Metropolitan Bike-Share Systems",
        "description": null,
        "category_type": "Solution"
      },
      "relationships": {
        "parent": {
          "data": {
            "id": "119",
            "type": "categories"
          }
        },
        "children": {
          "data": []
        }
      }
    },
    {
      "id": "121",
      "type": "categories",
      "attributes": {
        "name": "City-wide Bike-Share Systems",
        "description": null,
        "category_type": "Solution"
      },
      "relationships": {
        "parent": {
          "data": {
            "id": "119",
            "type": "categories"
          }
        },
        "children": {
          "data": []
        }
      }
    },
    {
      "id": "118",
      "type": "categories",
      "attributes": {
        "name": "Mobility",
        "description": null,
        "category_type": "Solution"
      },
      "relationships": {
        "parent": {
          "data": null
        },
        "children": {
          "data": [
            {
              "id": "119",
              "type": "categories"
            }
          ]
        }
      }
    },
    {
      "id": "119",
      "type": "categories",
      "attributes": {
        "name": "Bike sharing systems",
        "description": null,
        "category_type": "Solution"
      },
      "relationships": {
        "parent": {
          "data": {
            "id": "118",
            "type": "categories"
          }
        },
        "children": {
          "data": [
            {
              "id": "121",
              "type": "categories"
            },
            {
              "id": "122",
              "type": "categories"
            },
            {
              "id": "123",
              "type": "categories"
            },
            {
              "id": "120",
              "type": "categories"
            },
            {
              "id": "124",
              "type": "categories"
            }
          ]
        }
      }
    }
  ],
  "links": {
    "first": "http://localhost:3000/categories?category_type=All&page%5Bnumber%5D=1",
    "prev": "http://localhost:3000/categories?category_type=All&page%5Bnumber%5D=1",
    "next": "http://localhost:3000/categories?page%5Bnumber%5D=2&page%5Bsize%5D=10",
    "last": "http://localhost:3000/categories?page%5Bnumber%5D=15&page%5Bsize%5D=10",
    "self": "http://localhost:3000/categories?page%5Bnumber%5D=1&page%5Bsize%5D=10"
  }
}
```

### Pagination params

| Field           | Description                | Type
| -------------   |:-------------:| -----:|
| page[size]      | Number elements per page   | Number
| page[number]    | Number of page             | Number

> Return the categories of the page 2 with 5 elements per page

```shell
curl -X GET http://localhost:3000/categories?page[size]=5&page[number]=2
```

### Filter params

Available filters:

| Field         | Description           | Type
| ------------- |:-------------:| -----:|
| type          | Filter by specific type (Solution, Bme, Impact, Enabling, Timing)        | Text
| sort          | Sort json response by specific attributes (name, created_at, updated_at) | Text


> To obtain all categories in the parent - children structure:

```shell
curl -X GET http://localhost:3000/categories-tree \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

> To obtain solution categories in the parent - children structure:

```shell
curl -X GET http://localhost:3000/categories-tree?type=Solution \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```
> To sort solution categories by name:

```shell
curl -X GET http://localhost:3000/categories-tree?sort=name \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

```shell
curl -X GET http://localhost:3000/categories-tree?sort=-name \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

## How to obtain a specific category

> To obtain the category:

```shell
curl -X GET http://localhost:3000/categories/3 \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```
> Example response:

```json
{
  "data": {
    "id": "3",
    "type": "categories",
    "attributes": {
      "name": "Land",
      "description": null,
      "category_type": "Bme"
    },
    "relationships": {
      "parent": {
        "data": {
          "id": "2",
          "type": "categories"
        }
      },
      "children": {
        "data": []
      }
    }
  },
  "meta": {
    "updated_at": "2017-03-31T07:54:31.458Z",
    "created_at": "2017-03-31T07:54:31.458Z"
  }
}
```

<aside class="success">
Remember — the response is jsonapi format and only accessible by admin or publisher user
</aside>

## How to obtain a category tree

```shell
curl -X GET http://localhost:3000/categories-tree \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```
> Example response:

```json
{
  "data": [
    {
      "id": "125",
      "type": "categories",
      "attributes": {
        "name": "Urban energy",
        "description": null,
        "category_type": "Solution",
        "parent_id": null,
        "children": [
          {
            "id": 126,
            "name": "New efficient constructions",
            "description": null,
            "category_type": "Solution",
            "parent_id": 125,
            "children": [
              {
                "id": 127,
                "name": "Whole city approaches",
                "description": null,
                "category_type": "Solution",
                "parent_id": 126,
                "children": null
              }
            ]
          }
        ]
      }
    },
    {
      "id": "118",
      "type": "categories",
      "attributes": {
        "name": "Mobility",
        "description": null,
        "category_type": "Solution",
        "parent_id": null,
        "children": [
          {
            "id": 119,
            "name": "Bike sharing systems",
            "description": null,
            "category_type": "Solution",
            "parent_id": 118,
            "children": [
              {
                "id": 124,
                "name": "Campus-level Bike-Share Systems",
                "description": null,
                "category_type": "Solution",
                "parent_id": 119,
                "children": null
              },
              {
                "id": 121,
                "name": "City-wide Bike-Share Systems",
                "description": null,
                "category_type": "Solution",
                "parent_id": 119,
                "children": null
              },
              {
                "id": 123,
                "name": "Neighborhood-level Bike-Share Systems",
                "description": null,
                "category_type": "Solution",
                "parent_id": 119,
                "children": null
              },
              {
                "id": 122,
                "name": "Metropolitan Bike-Share Systems",
                "description": null,
                "category_type": "Solution",
                "parent_id": 119,
                "children": null
              },
              {
                "id": 120,
                "name": "District-level Bike-Share Systems",
                "description": null,
                "category_type": "Solution",
                "parent_id": 119,
                "children": null
              }
            ]
          }
        ]
      }
    }
  ],
  "links": {
    "first": "http://localhost:3000/categories?category_type=Tree&page%5Bnumber%5D=1&type=Solution",
    "prev": "http://localhost:3000/categories?category_type=Tree&page%5Bnumber%5D=1&type=Solution",
    "next": "http://localhost:3000/categories?category_type=Tree&page%5Bnumber%5D=1&type=Solution",
    "last": "http://localhost:3000/categories?category_type=Tree&page%5Bnumber%5D=1&type=Solution"
  }
}
```

<aside class="success">
Remember — the response is jsonapi format
</aside>

## How to obtain all solution categories

> To obtain the solution categories:

```shell
curl -X GET http://localhost:3000/solution-categories \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="success">
Remember — the response is jsonapi format
</aside>

## How to obtain a specific solution category

> To obtain the study case:

```shell
curl -X GET http://localhost:3000/solution-categories/126 \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="success">
Remember — the response is jsonapi format
</aside>

## How to obtain all timing categories

> To obtain the timing categories:

```shell
curl -X GET http://localhost:3000/timing-categories \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="success">
Remember — the response is jsonapi format
</aside>

## How to obtain a specific timing category

> To obtain the timing category:

```shell
curl -X GET http://localhost:3000/timing-categories/22 \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="success">
Remember — the response is jsonapi format
</aside>

## How to obtain all business-model-element categories

> To obtain the business model element categories:

```shell
curl -X GET http://localhost:3000/business-model-element-categories \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="success">
Remember — the response is jsonapi format
</aside>

## How to obtain a specific business-model-element category

> To obtain the business model element category:

```shell
curl -X GET http://localhost:3000/business-model-element-categories/43 \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="success">
Remember — the response is jsonapi format
</aside>

## How to obtain all impact categories

> To obtain the impact categories:

```shell
curl -X GET http://localhost:3000/impact-categories \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="success">
Remember — the response is jsonapi format
</aside>

## How to obtain a specific impact category

> To obtain the impact category:

```shell
curl -X GET http://localhost:3000/impact-categories/139 \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="success">
Remember — the response is jsonapi format
</aside>

## How to obtain all enabling categories

> To obtain the enabling categories:

```shell
curl -X GET http://localhost:3000/enabling-categories \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="success">
Remember — the response is jsonapi format
</aside>

## How to obtain a specific enabling category

> To obtain the enabling category:

```shell
curl -X GET http://localhost:3000/enabling-categories/113 \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="success">
Remember — the response is jsonapi format
</aside>


## Creating a Category

In order to create a category, you need an authorization token for current user.

Only admin users should be able to create Categories

To create a category, you need to define all of the required fields in the request body. The fields that compose a category are:

| Field               | Description                                                   | Type   | Values                                          | Required |
| ------------------  | -------------------------------------------------------:| ------:| -----------------------------------------------:|  -------:|
| name                | Name of the category                                    | Text   | Any Text                                        | Yes
| description         | Enabling description                                    | Text   | AnyText                                         | No
| parent_id           | Id of parent category                                   | Number | 1, 2, 3 ...                                     | No
| category_type       | Type of category                                        | Text   | Available:  (Solution, Bme, Impact, Enabling, Timing)  | Yes

### Business model categories

> To create a Business model element category, you have to do a POST with the following body:

```shell
curl -X POST http://localhost:3000/categories \
-H "Authorization: Bearer <your-token>" \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"  -d \
 '{
   "category": {
      "name":"Test category",
      "category_type":"Bme",
      "description":"Lorem ipsum",
      "parent_id":127
   }
}'
```
<aside class="notice">
  Remember that create category is an authenticated endpoint!
</aside>


## Updating a Category

In order to modify the category, you can PUT/PATCH a request.
It accepts the same parameters as the _create category_ endpoint, and you will need an authentication token.

> An example update request:

```shell
curl -X PATCH http://localhost:3000/categories/<category-id> \
-H "Authorization: Bearer <your-token>" \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"  -d \
'{__
  "category": {
      "name": "Another name for the category"
  }
}'
```

<aside class="notice">
Remember — create category is an authenticated endpoint!
</aside>

## Deleting a Category
You can delete a category! Just send a DELETE request to the endpoint:

```shell
curl -X DELETE http://localhost:3000/categories/<category-id> \
-H "Authorization: Bearer <your-token>" \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="notice">
Remember — create category is an authenticated endpoint!
</aside>
