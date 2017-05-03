# Impacts

## How obtain all impacts

To obtain all impacts:

```shell
curl -X GET http://localhost:3000/impacts \
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
      "id": "104",
      "type": "impacts",
      "attributes": {
        "name": null,
        "description": null,
        "impact_value": "BCA’s seminars and events also enable industry professionals to learn from other organizations’ approaches in driving environmental sustainability, their best practices, and project experiences.",
        "impact_unit": null,
        "is_active": true
      },
      "relationships": {
        "study_case": {
          "data": {
            "id": "39",
            "type": "projects"
          }
        },
        "category": {
          "data": {
            "id": "147",
            "type": "categories"
          }
        }
      }
    },
    {
      "id": "103",
      "type": "impacts",
      "attributes": {
        "name": null,
        "description": null,
        "impact_value": "BCA’s Green Mark Incentive Schemes plays a part in encouraging industry players and professionals along the supply chain to work towards sustainable buildings.",
        "impact_unit": null,
        "is_active": true
      },
      "relationships": {
        "study_case": {
          "data": {
            "id": "39",
            "type": "projects"
          }
        },
        "category": {
          "data": {
            "id": "142",
            "type": "categories"
          }
        }
      }
    },
    {
      "id": "102",
      "type": "impacts",
      "attributes": {
        "name": null,
        "description": null,
        "impact_value": "BCA has conducted more than ten green building roving exhibitions from 2009, taking the green building movement a step further to reach out to the general public.",
        "impact_unit": null,
        "is_active": true
      },
      "relationships": {
        "study_case": {
          "data": {
            "id": "39",
            "type": "projects"
          }
        },
        "category": {
          "data": {
            "id": "147",
            "type": "categories"
          }
        }
      }
    },
    {
      "id": "101",
      "type": "impacts",
      "attributes": {
        "name": null,
        "description": null,
        "impact_value": "Efficiency engagements and incentives have contributed to a pool of eco-conscious building professionals who in turn exercise great influence over the rest of the industry and even over end users.",
        "impact_unit": null,
        "is_active": true
      },
      "relationships": {
        "study_case": {
          "data": {
            "id": "39",
            "type": "projects"
          }
        },
        "category": {
          "data": {
            "id": "142",
            "type": "categories"
          }
        }
      }
    },
    {
      "id": "100",
      "type": "impacts",
      "attributes": {
        "name": null,
        "description": null,
        "impact_value": "Developments targeting beyond Green Mark Platinum standards demonstrate more than 40 percent energy savings as compared to prevailing building efficiency standards.",
        "impact_unit": "Percentage",
        "is_active": true
      },
      "relationships": {
        "study_case": {
          "data": {
            "id": "39",
            "type": "projects"
          }
        },
        "category": {
          "data": {
            "id": "143",
            "type": "categories"
          }
        }
      }
    },
    {
      "id": "99",
      "type": "impacts",
      "attributes": {
        "name": null,
        "description": null,
        "impact_value": "By the end of 2011 there were 179 LEED Certified Buildings in Seattle (30 Certified, 55 Silver, 86 Gold and 8 Platinum).",
        "impact_unit": null,
        "is_active": true
      },
      "relationships": {
        "study_case": {
          "data": {
            "id": "37",
            "type": "projects"
          }
        },
        "category": {
          "data": {
            "id": "128",
            "type": "categories"
          }
        }
      }
    },
    {
      "id": "98",
      "type": "impacts",
      "attributes": {
        "name": null,
        "description": null,
        "impact_value": "179 projects were certified as of December 2011, representing over 58 million square feet.",
        "impact_unit": null,
        "is_active": true
      },
      "relationships": {
        "study_case": {
          "data": {
            "id": "37",
            "type": "projects"
          }
        },
        "category": {
          "data": {
            "id": "128",
            "type": "categories"
          }
        }
      }
    },
    {
      "id": "97",
      "type": "impacts",
      "attributes": {
        "name": null,
        "description": null,
        "impact_value": "Seattle's Sustainable Building policy has fueled private sector growth in the green building industry placing Seattle as one of the leading cities in the US in the number of certified LEED buildings within its City Limits.",
        "impact_unit": null,
        "is_active": true
      },
      "relationships": {
        "study_case": {
          "data": {
            "id": "37",
            "type": "projects"
          }
        },
        "category": {
          "data": {
            "id": "128",
            "type": "categories"
          }
        }
      }
    },
    {
      "id": "96",
      "type": "impacts",
      "attributes": {
        "name": null,
        "description": null,
        "impact_value": "The Green Building Industry is one of the City's strategic economic \"Clusters,\" with $671 million gross revenue per year in Green Building Activity.",
        "impact_unit": null,
        "is_active": true
      },
      "relationships": {
        "study_case": {
          "data": {
            "id": "37",
            "type": "projects"
          }
        },
        "category": {
          "data": {
            "id": "145",
            "type": "categories"
          }
        }
      }
    },
    {
      "id": "95",
      "type": "impacts",
      "attributes": {
        "name": null,
        "description": null,
        "impact_value": "Seattle aims to reach net-zero core greenhouse gas emissions by 2050, with a 91% reduction in building energy emissions, compared with 2008 emission levels.",
        "impact_unit": "Percentage",
        "is_active": true
      },
      "relationships": {
        "study_case": {
          "data": {
            "id": "37",
            "type": "projects"
          }
        },
        "category": {
          "data": {
            "id": "149",
            "type": "categories"
          }
        }
      }
    }
  ],
  "links": {
    "first": "http://localhost:3000/impacts?page%5Bnumber%5D=1",
    "prev": "http://localhost:3000/impacts?page%5Bnumber%5D=1",
    "next": "http://localhost:3000/impacts?page%5Bnumber%5D=2&page%5Bsize%5D=10",
    "last": "http://localhost:3000/impacts?page%5Bnumber%5D=11&page%5Bsize%5D=10",
    "self": "http://localhost:3000/impacts?page%5Bnumber%5D=1&page%5Bsize%5D=10"
  }
}
```

### Pagination params

| Field           | Description                | Type
| -------------   |:-------------:| -----:|
| page[size]      | Number elements per page   | Number
| page[number]    | Number of page             | Number

> Return the impacts of the page 2 with 5 elements per page

```shell
curl -X GET http://localhost:3000/impacts?page[size]=5&page[number]=2
```

### Filter params

Available filters:

| Field         | Description           | Type
| ------------- |:-------------:| -----:|
| sort          | Sort json response by specific attributes (name, created_at, updated_at) | Text


> To obtain all impacts sorted by name:

```shell
curl -X GET http://localhost:3000/impacts?sort=name \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

```shell
curl -X GET http://localhost:3000/impacts?sort=-name \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

## How to obtain specific impact

To obtain specific impact:

```shell
curl -X GET http://localhost:3000/impacts/1 \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="success">
Remember — the response is jsonapi format
</aside>


## Creating an Impact

In order to create a impact, you need an authorization token for current admin.

Only admin should be able to create Impacts

To create an impact, you need to define all of the required fields in the request body. The fields that compose a impact are:

| Field               | Description                                                   | Type   | Values                                          | Required |
| ------------------  | -------------------------------------------------------------:| ------:| -----------------------------------------------:|  -------:|
| name                | Name of the impact                                              | Text   | Any Text                                        | Yes
| description         | Impact description                                              | Text   | AnyText                                         | No
| category_id         | Id of category (Impact category)                                | Number | 1, 2, 3 ...                                     | No
| impact_value        | Impact value                                                    | Text   | AnyText                                         | Yes
| impact_unit         | Unit for the impact value                                       | Text   | AnyText                                         | No
| project_id          | Id of the project                                               | Number | 1, 2, 3 ...                                     | No
| is_active           | Activate deactiveta impacts (only accessible by admin and publisher) | Boolean  | default value false                    | No


> To create an impact, you have to do a POST with the following body:

```shell
curl -X POST http://localhost:3000/impacts \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json" -d \
'{__
  "impact": {
      "name": "Impact one",
      "description": "Lorem ipsum...",
      "impact_vale": "QWERTY",
      more attributes...
  }
}'
```
<aside class="notice">
  Remember that create impact is an authenticated endpoint!
</aside>


## Updating an Impact

In order to modify the impact, you can PUT/PATCH a request.
It accepts the same parameters as the _create impact_ endpoint, and you will need an authentication token.

> An example update request:

```shell
curl -X PATCH http://localhost:3000/impacts/<impact-id> \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"  -d \
'{__
  "impact": {
      "name": "Another name for the impact",
      "is_active": true
  }
}'
```

<aside class="notice">
Remember — create impact is an authenticated endpoint!
</aside>

## Deleting an Impact
You can delete a impact! Just send a DELETE request to the endpoint:

```shell
curl -X DELETE http://localhost:3000/impacts/<impact-id> \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="notice">
Remember — create impact is an authenticated endpoint!
</aside>
