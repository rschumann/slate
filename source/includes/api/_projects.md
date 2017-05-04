# Projects (StudyCase, BusinessModel)

## What is a Project?

A project is a group of Study cases and business models.

## How to obtain all projects

To obtain all projects (Only accessible by admin and publisher user):

```shell
curl -X GET http://localhost:3000/projects \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
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
      "id": "39",
      "type": "projects",
      "attributes": {
        "name": "Singapore",
        "situation": "Sustainable development remains as a national priority in Singapore given their resource constraints, demands of a growing city, and the global challenge of climate change. Hence, it is necessary for Singapore to play a part in combating climate change and strengthening its position as a global city committed to balancing its development with care for the environment.",
        "solution": "The Building and Construction Authority (BCA) in the city has taking the lead in environmental sustainability by training its workforce, supporting green building advancements, and establishing the BCA Green Mark scheme as the required rating tool of choice in the region.  It also aims to work towards setting industry standards on zero and net positive energy low-rise buildings and low energy high-rise buildings that address high density. Overall, the city’s goal is to make at least 80 percent of the buildings in the city energy efficiency (green) by 2030.\nTo encourage these developments, the BCA has established several incentives schemes that will allow the development of new greener buildings. For example, the Green Mark Gross Floor Area Incentive scheme is applicable to all new and existing private developments that undergo substantial energy efficiency enhancements. In return, it authorizes the developer to utilize additional floor area. In addition, the city has employed other investment incentives for construction of new high-performance buildings.",
        "category_id": 127,
        "country_id": 203,
        "operational_year": "2014-01-01T00:00:00.000Z",
        "project_type": "StudyCase",
        "is_active": true,
        "deactivated_at": null,
        "publish_request": false,
        "published_at": "2017-03-31T07:54:40.174Z"
      },
      "relationships": {
        "country": {
          "data": {
            "id": "203",
            "type": "countries"
          }
        },
        "category": {
          "data": {
            "id": "127",
            "type": "categories"
          }
        },
        "bmes": {
          "data": [
            {
              "id": "140",
              "type": "bmes"
            },
            {
              "id": "138",
              "type": "bmes"
            },
            {
              "id": "75",
              "type": "bmes"
            },
            {
              "id": "175",
              "type": "bmes"
            },
            {
              "id": "117",
              "type": "bmes"
            },
            {
              "id": "110",
              "type": "bmes"
            },
            {
              "id": "108",
              "type": "bmes"
            },
            {
              "id": "105",
              "type": "bmes"
            },
            {
              "id": "104",
              "type": "bmes"
            },
            {
              "id": "103",
              "type": "bmes"
            },
            {
              "id": "102",
              "type": "bmes"
            },
            {
              "id": "101",
              "type": "bmes"
            },
            {
              "id": "99",
              "type": "bmes"
            },
            {
              "id": "172",
              "type": "bmes"
            },
            {
              "id": "94",
              "type": "bmes"
            },
            {
              "id": "93",
              "type": "bmes"
            },
            {
              "id": "90",
              "type": "bmes"
            },
            {
              "id": "89",
              "type": "bmes"
            },
            {
              "id": "87",
              "type": "bmes"
            }
          ]
        },
        "impacts": {
          "data": [
            {
              "id": "100",
              "type": "impacts"
            },
            {
              "id": "101",
              "type": "impacts"
            },
            {
              "id": "102",
              "type": "impacts"
            },
            {
              "id": "103",
              "type": "impacts"
            },
            {
              "id": "104",
              "type": "impacts"
            }
          ]
        },
        "cities": {
          "data": [
            {
              "id": "5469",
              "type": "cities"
            }
          ]
        },
        "users": {
          "data": []
        },
        "photos": {
          "data": []
        },
        "documents": {
          "data": []
        },
        "external_sources": {
          "data": [
            {
              "id": "228",
              "type": "external_sources"
            }
          ]
        },
        "comments": {
          "data": []
        }
      }
    }
  ],
  "links": {
    "first": "http://localhost:3000/projects?page%5Bnumber%5D=1",
    "prev": "http://localhost:3000/projects?page%5Bnumber%5D=1",
    "next": "http://localhost:3000/projects?page%5Bnumber%5D=2&page%5Bsize%5D=1",
    "last": "http://localhost:3000/projects?page%5Bnumber%5D=39&page%5Bsize%5D=1",
    "self": "http://localhost:3000/projects?page%5Bnumber%5D=1&page%5Bsize%5D=1"
  }
}
```

### Pagination params

| Field           | Description                | Type
| -------------   |:-------------:| -----:|
| page[size]      | Number elements per page   | Number
| page[number]    | Number of page             | Number

> Return the projects of the page 2 with 5 elements per page

```shell
curl -X GET http://localhost:3000/projects?page[size]=5&page[number]=2
```

### Filter params

Available filters:

| Field         | Description           | Type
| ------------- |:-------------:| -----:|
| sort          | Sort json response by specific attributes (name, created_at, updated_at) | Text
| search        | Search in name and solution | Text


> To obtain all projects sorted by name:

```shell
curl -X GET http://localhost:3000/projects?sort=name \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

```shell
curl -X GET http://localhost:3000/projects?sort=-name \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

> To obtain all study cases sorted by name:

```shell
curl -X GET http://localhost:3000/study-cases?sort=name \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

> To search study cases sorted by name:

```shell
curl -X GET http://localhost:3000/study-cases?search=term&sort=name \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

## How to obtain a specific project

> To obtain the project:

```shell
curl -X GET http://localhost:3000/projects/30 \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

> Example response:

```json
{
  "data": {
    "id": "30",
    "type": "projects",
    "attributes": {
      "name": "Tel-O-Fun",
      "situation": "The City of Tel Aviv was exploring strategies to cut down on automobile usage in the city, reduce air pollution, and encourage physical activity and fitness amongst its residents.",
      "solution": "In 2011, the City of Tel Aviv launched a bike-share program in some districts of the city, deploying 250 bicycles across 35 docking stations. The system was developed in collaboration with the German Railways Deutsche Bahn (DB) that runs bike-share systems in several German cities, and University of Tel Aviv. The system subsequently underwent expansion in phases and in 2015, it was expanded to the neighboring towns of Ramat Gan and Givatayim. The city also undertook construction of dedicated bicycle lanes in the city to complement the bike-share system and promote bicycling as a sustainable transportation alternative.",
      "category_id": 122,
      "country_id": 171,
      "operational_year": "2011-01-01T00:00:00.000Z",
      "project_type": "StudyCase",
      "is_active": true,
      "deactivated_at": null,
      "publish_request": false,
      "published_at": "2017-03-31T07:54:39.990Z"
    },
    "relationships": {
      "country": {
        "data": {
          "id": "171",
          "type": "countries"
        }
      },
      "category": {
        "data": {
          "id": "122",
          "type": "categories"
        }
      },
      "bmes": {
        "data": [
          {
            "id": "79",
            "type": "bmes"
          },
          {
            "id": "67",
            "type": "bmes"
          },
          {
            "id": "66",
            "type": "bmes"
          },
          {
            "id": "156",
            "type": "bmes"
          },
          {
            "id": "147",
            "type": "bmes"
          },
          {
            "id": "33",
            "type": "bmes"
          },
          {
            "id": "19",
            "type": "bmes"
          },
          {
            "id": "10",
            "type": "bmes"
          },
          {
            "id": "7",
            "type": "bmes"
          },
          {
            "id": "1",
            "type": "bmes"
          }
        ]
      },
      "impacts": {
        "data": []
      },
      "cities": {
        "data": [
          {
            "id": "7327",
            "type": "cities"
          }
        ]
      },
      "users": {
        "data": []
      },
      "photos": {
        "data": []
      },
      "documents": {
        "data": []
      },
      "external_sources": {
        "data": [
          {
            "id": "147",
            "type": "external_sources"
          }
        ]
      },
      "comments": {
        "data": []
      }
    }
  },
  "included": [
    {
      "id": "171",
      "type": "countries",
      "attributes": {
        "name": "Israel",
        "region_name": "Western Asia",
        "iso": "ISR",
        "region_iso": "WS",
        "country_centroid": {
          "type": "Point",
          "coordinates": [
            31.5,
            34.75
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
      "id": "79",
      "type": "bmes",
      "attributes": {
        "name": "City Budget",
        "description": "Some cities have covered the capital costs of installing a bike-share system through their budgets. Cities also subsidize operating costs by providing a fixed annual operating subsidy for bike-share systems."
      },
      "relationships": {
        "enablings": {
          "data": [
            {
              "id": "145",
              "type": "enablings"
            },
            {
              "id": "146",
              "type": "enablings"
            },
            {
              "id": "147",
              "type": "enablings"
            }
          ]
        },
        "categories": {
          "data": [
            {
              "id": "20",
              "type": "categories"
            },
            {
              "id": "21",
              "type": "categories"
            },
            {
              "id": "22",
              "type": "categories"
            },
            {
              "id": "48",
              "type": "categories"
            }
          ]
        }
      }
    },
    {
      "id": "67",
      "type": "bmes",
      "attributes": {
        "name": "User Charges",
        "description": "These are the charges paid by users for exceeding the duration of time limit for free usage. In many systems, user charges are incremental. This ensures that bikes are checked out for short trips only."
      },
      "relationships": {
        "enablings": {
          "data": [
            {
              "id": "100",
              "type": "enablings"
            },
            {
              "id": "101",
              "type": "enablings"
            }
          ]
        },
        "categories": {
          "data": [
            {
              "id": "21",
              "type": "categories"
            },
            {
              "id": "42",
              "type": "categories"
            }
          ]
        }
      }
    },
    {
      "id": "66",
      "type": "bmes",
      "attributes": {
        "name": "Membership/Subscription Fees",
        "description": "This is the amount charged to enable users to have access to the bike-share system for a specific time.  Memberships are of two types, short-term (24-hours, 72-hours, 7 days) or long-term (30-days, half-yearly, annual) and usually enable members to take unlimited trips of a specified duration (30, 45 or 60 minutes) during the membership period."
      },
      "relationships": {
        "enablings": {
          "data": [
            {
              "id": "95",
              "type": "enablings"
            },
            {
              "id": "96",
              "type": "enablings"
            },
            {
              "id": "97",
              "type": "enablings"
            },
            {
              "id": "98",
              "type": "enablings"
            },
            {
              "id": "99",
              "type": "enablings"
            }
          ]
        },
        "categories": {
          "data": [
            {
              "id": "21",
              "type": "categories"
            },
            {
              "id": "42",
              "type": "categories"
            }
          ]
        }
      }
    },
    {
      "id": "156",
      "type": "bmes",
      "attributes": {
        "name": "Public-Private Partnership (PPP)",
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
      "id": "147",
      "type": "bmes",
      "attributes": {
        "name": "Build-Operate-Transfer (BOT) Contract",
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
      "id": "33",
      "type": "bmes",
      "attributes": {
        "name": "Redistribution/Rebalancing",
        "description": "Rebalancing bicycles across docking stations is the key process to the success of a bike-share system. During peak hours, users in cities where bike-share is used for commuting, take bikes from residential neighborhoods into office districts (downtown). As a result, stations in residential areas tend to be empty with no bikes available for subsequent riders, whereas stations in office districts (high foot-traffic areas) are full. Similarly, in areas with steep topography, uphill stations tend to be empty and ones located downhill tend to be full as users avoid wheeling bicycles on steep inclines. In order to maintain the supply of bicycles in places with high demand, bike-share systems deploy vehicles to collect bikes from high-volume stations and redistribute them to low-volume stations. Bicycles have RFID tags, which emit a signal when they get docked. The bike-share staff receives this data from all stations across the system and uses it to ascertain volumes at various stations in real-time. This data is used to plan and prioritize bicycle pick-up and drop-off locations. Rebalancing is also dne through differential pricing or incentives such as giving additional free ride-times for individuals docking bicycles in low-demand areas or up-hill neighborhoods. Maintaining the volume of bikes in stations with high demand and facilitating easy return of bikes in stations located in popular destinations is extremely crucial to the success of a bike-share system."
      },
      "relationships": {
        "enablings": {
          "data": []
        },
        "categories": {
          "data": [
            {
              "id": "4",
              "type": "categories"
            },
            {
              "id": "14",
              "type": "categories"
            }
          ]
        }
      }
    },
    {
      "id": "19",
      "type": "bmes",
      "attributes": {
        "name": "Road Safety",
        "description": "Road safety is an important consideration, especially in cities where bicycling is still at a nascent stage. Cities often draw up and implement a bicycling plan that mandates investment in constructing infrastructure such as dedicated bike-lanes to complement the bike-share system. Several cities have modified traffic regulations to factor in bicyclists, published road safety manuals for bicyclists, held training and awareness campaigns for both bicyclists and motorists, made helmets mandatory, and distributed them free-of-charge or at subsidized costs to promote safe bicycling."
      },
      "relationships": {
        "enablings": {
          "data": []
        },
        "categories": {
          "data": [
            {
              "id": "4",
              "type": "categories"
            },
            {
              "id": "8",
              "type": "categories"
            }
          ]
        }
      }
    },
    {
      "id": "10",
      "type": "bmes",
      "attributes": {
        "name": "Bicycles",
        "description": "The bicycles are one of the primary components of a bike-share system, and have to be designed carefully to promote a modern image, as well as to be able to withstand heavy use and exposure to all possible weather conditions. \nBikes have a step-through frame to ensure that they are compatible with most user groups, and clothing types. Sturdy, puncture-resistant tires are commonly used, and most bikes have front and rear drum brakes preferably with internal wires, and chain guards making them easy to maintain. Bicycles for bike-share systems are designed to be heavier than standard bikes to make them sturdier, and deter theft. They are also built out of unique parts that can only be opened with proprietary tools. Seat posts are designed to be easily adjustable to enable users to adjust seat height quickly, and most bikes come with three-speed internal hub gears, which are especially useful in cities with an uneven terrain. Bike lights are mandatory in most cities at night, so bikes are designed with front and rear LED lights usually powered by a hub dynamo. Reflectors are provided on wheels, pedals, etc. to improve visibility in the dark. The frame is also usually a bright color and reflective to provide good visibility to motorists in all conditions. Bicycles usually have baskets with straps in the front or rear to enable riders to secure their small personal belongings like handbags, backpacks, etc., and front and rear mudguards to protect clothing from dirt and mud splashes. The baskets and mudguards should ideally have a provision for the installation of advertisements, which enables a program to obtain revenue through private sponsorships.\nBicycles in 3rd and 4th Generation systems have an automated docking mechanism which enables users to check out and return bikes to automated docks using cards or special codes sent to their smartphones. This mechanism comes with a GPS, and RFID tag, which carries the bike’s unique identification number, and is read when the cycle is docked at a station. This helps operators maintain real-time data on bike availability at stations, as well as trip lengths, origins, and destinations. Several systems integrate technology that enables users to track their heart-rate, calories burned, etc. while riding the bike."
      },
      "relationships": {
        "enablings": {
          "data": []
        },
        "categories": {
          "data": [
            {
              "id": "4",
              "type": "categories"
            },
            {
              "id": "6",
              "type": "categories"
            }
          ]
        }
      }
    },
    {
      "id": "7",
      "type": "bmes",
      "attributes": {
        "name": "Dedicated Bicycle Lanes",
        "description": "Several cities invest in developing bicycle infrastructure that enhances safety of bicyclists on urban roads, and encourages more people to ride bicycles, to complement a bike-share system. Dedicated bicycle lanes are one such investment. These could be exclusive bicycling lanes designated by a white strip, bicycle symbols, or paint, to differentiate them from vehicular lanes. They could also be designated through a slight grade separation, physical barriers separating them from the motorized traffic, or a strip of landscaping. Bicycle lanes can also be in the form of urban trails running through parks, landscaped areas, and natural areas. Cities across the world are actively engaged in creating a network of dedicated bicycle lanes, comprising of urban lanes and bicycle trails through targeted initiatives such as Bicycle Master Plans."
      },
      "relationships": {
        "enablings": {
          "data": []
        },
        "categories": {
          "data": [
            {
              "id": "4",
              "type": "categories"
            },
            {
              "id": "5",
              "type": "categories"
            }
          ]
        }
      }
    },
    {
      "id": "1",
      "type": "bmes",
      "attributes": {
        "name": "Sidewalks/Plazas",
        "description": "A majority of cities locate bike-share stations on side-walks and plazas outside transit and commercial hubs, and public spaces such as parks, highstreets, tourist attractions, and so on that have high foot traffic. Station locations are decided through a rigorous analysis during the scoping and planning phase. Several cities undertake intensive public engagement to determine the optimum locations for stations in various urban neighborhoods."
      },
      "relationships": {
        "enablings": {
          "data": []
        },
        "categories": {
          "data": [
            {
              "id": "3",
              "type": "categories"
            },
            {
              "id": "4",
              "type": "categories"
            }
          ]
        }
      }
    },
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
      "id": "147",
      "type": "external_sources",
      "attributes": {
        "name": "Tel-O-Fun: Homepage",
        "description": null,
        "web_url": "https://www.tel-o-fun.co.il/en/HomePage.aspx",
        "source_type": "Website",
        "author": "Tel-O-Fun",
        "publication_year": null,
        "institution": "Tel-O-Fun",
        "is_active": true
      },
      "relationships": {
        "attacheable": {
          "data": {
            "id": "30",
            "type": "projects"
          }
        }
      }
    }
  ],
  "meta": {
    "updated_at": "2017-03-31T07:54:46.976Z",
    "created_at": "2017-03-31T07:54:39.989Z"
  }
}
```

<aside class="success">
Remember — the response is jsonapi format and only accessible by admin or publisher user
</aside>

## How to obtain all study cases

To obtain all study cases:

```shell
curl -X GET http://localhost:3000/study-cases \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="success">
Remember — the response is jsonapi format
</aside>

## How to obtain a specific study case

To obtain the study case:

```shell
curl -X GET http://localhost:3000/study-cases/39 \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="success">
Remember — the response is jsonapi format
</aside>

## How to obtain all business models

To obtain all business models:

The admin and publisher user can access all business models.

The editor and user can access owned business models.

```shell
curl -X GET http://localhost:3000/business-models \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="success">
Remember — the response is jsonapi format
</aside>

## How to obtain a specific business model

To obtain the business model:

```shell
curl -X GET http://localhost:3000/business-models/:id \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="success">
Remember — the response is jsonapi format
</aside>

## Creating a Project

In order to create a project, you need an authorization token for current user.

Only admin users should be able to create Study cases

To create a project, you need to define all of the required fields in the request body. The fields that compose a project are:

| Field               | Description                                                   | Type   | Values                                          | Required |
| ------------------  | -------------------------------------------------------------:| ------:| -----------------------------------------------:|  -------:|
| name                | Name of the project                                           | Text   | Any Text                                        | Yes
| situation           | Description field of the project                              | Text   | Any Text                                        | No
| project_type        | Project type                                                  | Text   | BusinessModel, StudyCase                        | Yes
| solution            | Description field of the project                              | Text   | AnyText                                         | No
| category_id         | Id of solution (solution-category)                            | Number | 1, 2, 3 ...                                     | No
| country_id          | Id of country                                                 | Number | 1, 2, 3 ...                                     | No
| operational_year    | Date of operational year                                      | Date   | Date time                                       | No
| city_ids            | Cities of project                                             | Array  | Any list of cities ids                          | No
| bme_ids             | Business model elements of project                            | Array  | Any list of bme's ids                           | No
| external_source_ids | External sources of project                                   | Array  | Any list of sources ids                         | No
| impact_ids          | Impacts of project                                            | Array  | Any list of impacts ids                         | No
| user_ids            | Users of project (only accessible by admin)                   | Array  | Any list of users ids                           | No
| is_active           | Activate deactiveta projects (only accessible by admin and publisher) | Boolean  | default value false                    | No

### Business model projects

> To create a Business model, you have to do a POST with the following body:

```shell
curl -X POST http://localhost:3000/projects \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"  -d \
 '{
   "project": {
      "name":"Test project",
      "project_type":"BusinessModel",
      "situation":"Lorem ipsum",
      "solution":"Lorem ipsum",
      "category_id":127,
      "city_ids": [5],
      more attributes...
   }
}'
```

> To create a Study case, you have to do a POST with the following body. Only admin can create a new study case. Editor can make a reques to convert a existing bussines model into a study case:

```shell
curl -X POST http://localhost:3000/projects \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"  -d \
 '{
   "project": {
      "name":"Test project",
      "project_type":"StudyCase",
      "situation":"Lorem ipsum",
      "solution":"Lorem ipsum",
      "category_id":127,
      "city_ids": [5],
      more attributes...
   }
}'
```
<aside class="notice">
	Remember that create project is an authenticated endpoint!
</aside>


## Updating a Project

In order to modify the project, you can PUT/PATCH a request.
It accepts the same parameters as the _create project_ endpoint, and you will need an authentication token.

> An example update request:

```shell
curl -X PATCH http://localhost:3000/projects/<project-id> \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"  -d \
'{__
	"project": {
      "name": "Another name for the project",
      "is_active": true
	}
}'
```

<aside class="notice">
Remember — create project is an authenticated endpoint!
</aside>

## Deleting a Project
You can delete a project! Just send a DELETE request to the endpoint:

```shell
curl -X DELETE http://localhost:3000/projects/<project-id> \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="notice">
Remember — create project is an authenticated endpoint!
</aside>
