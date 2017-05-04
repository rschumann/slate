# Users

## Registration

To reginster as an user:

```shell
curl -X POST http://localhost:3000/register \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json" -d \
'{__
  "user": {
      "email": "xyz@email.com",
      "nickname": "Username",
      "password": "password",
      "password_confirmation": "password",
      "name": "Anna Guay"
  }
}'

## Log in

To login as an user:

```shell
curl -X POST http://localhost:3000/login \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json" -d \
'{__
  "auth": {
      "email": "xyz@email.com",
      "password": "password"
  }
}'
```

<aside class="success">
Remember — the response is jsonapi format
</aside>

## Get current user

To obtain current user:

```shell
curl -X GET http://localhost:3000/users/current-user \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="success">
Remember — the response is jsonapi format
</aside>

## Reset user's password

To reset user's password:

```shell
curl -X POST http://localhost:3000/reset-password \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json" -d \
'{__
  "password": {
      "email": "xyz@email.com",
      "reset_url": "http://localhost:5000/password"
  }
}'
```

<aside class="success">
Remember  — the response is jsonapi format
reset_url - url to new password form page
The reset password email will be send to the user. The reset link contains the reset_password_token and the callback url to set new password by user.
Sample link: http://localhost:5000/password?reset_password_token=c2f7bb06-0c16-4365-b184-068105e6e01b
</aside>

## Set new user's password

To set new user's password:

```shell
curl -X POST http://localhost:3000/users/password \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json" -d \
'{__
  "password": {
      "reset_password_token": "f21ef93a-a92f-4a4b-952f-45ffd2043995",
      "password": "password",
      "password_confirmation": "password"
  }
}'
```

<aside class="success">
Remember  — the response is jsonapi format
reset_password_token - token from query param included in the reset password link
The reset password email will be send to the user. The reset link contains the reset_password_token and the callback url to set new password by user.
Sample link: http://localhost:5000/password?reset_password_token=c2f7bb06-0c16-4365-b184-068105e6e01b
</aside>


## Set new current user password

To set new password for current user:

```shell
curl -X PATCH http://localhost:3000/users/current-user/password \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json" -d \
'{__
  "password": {
      "password": "password",
      "password_confirmation": "password"
  }
}'
```

<aside class="success">
Remember  — the response is jsonapi format
Authorization with valid user auth token should be present
</aside>

## How obtain all users

To obtain all users:

```shell
curl -X GET http://localhost:3000/users \
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
      "id": "5",
      "type": "users",
      "attributes": {
        "name": "Web",
        "email": "webuser@example.com",
        "role": "user",
        "country_id": 37,
        "city_id": 7072,
        "nickname": "webuser",
        "institution": null,
        "position": null,
        "twitter_account": null,
        "linkedin_account": null,
        "is_active": true,
        "deactivated_at": null,
        "image": {
          "url": null,
          "thumbnail": {
            "url": null
          },
          "square": {
            "url": null
          }
        }
      }
    },
    {
      "id": "4",
      "type": "users",
      "attributes": {
        "name": "Publisher",
        "email": "publisher@example.com",
        "role": "publisher",
        "country_id": 37,
        "city_id": 7072,
        "nickname": "publisher",
        "institution": null,
        "position": null,
        "twitter_account": null,
        "linkedin_account": null,
        "is_active": true,
        "deactivated_at": null,
        "image": {
          "url": null,
          "thumbnail": {
            "url": null
          },
          "square": {
            "url": null
          }
        }
      }
    },
    {
      "id": "3",
      "type": "users",
      "attributes": {
        "name": "Editor",
        "email": "editor@example.com",
        "role": "editor",
        "country_id": 37,
        "city_id": 7072,
        "nickname": "editor",
        "institution": null,
        "position": null,
        "twitter_account": null,
        "linkedin_account": null,
        "is_active": true,
        "deactivated_at": null,
        "image": {
          "url": null,
          "thumbnail": {
            "url": null
          },
          "square": {
            "url": null
          }
        }
      }
    },
    {
      "id": "2",
      "type": "users",
      "attributes": {
        "name": "Web",
        "email": "user@example.com",
        "role": "user",
        "country_id": 37,
        "city_id": 7072,
        "nickname": "user",
        "institution": null,
        "position": null,
        "twitter_account": null,
        "linkedin_account": null,
        "is_active": true,
        "deactivated_at": null,
        "image": {
          "url": null,
          "thumbnail": {
            "url": null
          },
          "square": {
            "url": null
          }
        }
      }
    },
    {
      "id": "1",
      "type": "users",
      "attributes": {
        "name": "Admin",
        "email": "admin@example.com",
        "role": "admin",
        "country_id": 37,
        "city_id": 7072,
        "nickname": "admin",
        "institution": null,
        "position": null,
        "twitter_account": null,
        "linkedin_account": null,
        "is_active": true,
        "deactivated_at": null,
        "image": {
          "url": null,
          "thumbnail": {
            "url": null
          },
          "square": {
            "url": null
          }
        }
      }
    }
  ],
  "links": {
    "first": "http://localhost:3000/users?page%5Bnumber%5D=1",
    "prev": "http://localhost:3000/users?page%5Bnumber%5D=1",
    "next": "http://localhost:3000/users?page%5Bnumber%5D=1",
    "last": "http://localhost:3000/users?page%5Bnumber%5D=1"
  }
}
```

### Pagination params

| Field           | Description                | Type
| -------------   |:-------------:| -----:|
| page[size]      | Number elements per page   | Number
| page[number]    | Number of page             | Number

> Return the users of the page 2 with 5 elements per page

```shell
curl -X GET http://localhost:3000/users?page[size]=5&page[number]=2
```

### Filter params

Available filters:

| Field         | Description           | Type
| ------------- |:-------------:| -----:|
| sort          | Sort json response by specific attributes (name, created_at, updated_at) | Text
| search        | Search in name and nickname | Text


> To obtain all users sorted by name:

```shell
curl -X GET http://localhost:3000/users?sort=name \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

```shell
curl -X GET http://localhost:3000/users?sort=-name \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

> To search users sorted by name:

```shell
curl -X GET http://localhost:3000/users?search=term&sort=-name \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

## How to obtain specific user

To obtain specific user:

```shell
curl -X GET http://localhost:3000/users/1 \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="success">
Remember — the response is jsonapi format
</aside>

## Creating an User

In order to create a user, you need an authorization token for current admin.

Only admin users should be able to create Users

To create a user, you need to define all of the required fields in the request body. The fields that compose a user are:

| Field               | Description                                                   | Type   | Values                                          | Required |
| ------------------  | -------------------------------------------------------------:| ------:| -----------------------------------------------:|  -------:|
| name                | Name of the user                                              | Text   | Any Text                                        | Yes
| email               | Email of the user                                             | Text   | Any valid email                                 | Yes
| password            | Password of the user                                          | Text   | Any valid password                              | Yes
| password_confirmation | Password confirmation of the user password                  | Text   | Any valid password                              | Yes
| nickname            | Username                                                      | Text   | Any Text                                        | Yes
| role                | User role (only accessible by admin)                          | Text   | user, editor. publicher, admin                  | No
| institution         | User institution/company                                      | Text   | AnyText                                         | No
| country_id          | Id of country                                                 | Number | 1, 2, 3 ...                                     | No
| city_id             | City of user                                                  | Number | 1, 2, 3 ...                                     | No
| position            | User position in the company                                  | Text   | AnyText                                         | No
| twitter_account     | Link to user twitter account                                  | Text   | AnyText                                         | No
| linkedin_account    | Link to user linkedin account                                 | Text   | AnyText                                         | No
| image               | base64 image ({"user": { "image": "data:image/jpeg;base64,(/9j/...) }}) | Text    | Valid file base64                 | No
| is_active           | Activate deactiveta users (only accessible by admin and publisher) | Boolean  | default value false                      | No


> To create an user, you have to do a POST with the following body:

```shell
curl -X POST http://localhost:3000/users \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json" -d \
'{__
  "user": {
      "email": "xyz@email.com",
      "nickname": "Username",
      "password": "password",
      "password_confirmation": "password",
      "name": "Anna Guay",
      "country_id": 2,
      "image": "data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAYEBQYFBAYGBQYHBwYIChAKCgkJChQODwwQFxQYGBcUFhYaHSUfGhsjHBYWICwgIyYnKSopGR8tMC0oMCUoKSj/2wBDAQcHBwoIChMKChMoGhYaKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCj/wgARCAEsAZADASIAAhEBAxEB/8QAFQABAQAAAAAAAAAAAAAAAAAAAAX/xAAWAQEBAQAAAAAAAAAAAAAAAAAAAwb/2gAMAwEAAhADEAAAAZ4hsgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAP/8QAFBABAAAAAAAAAAAAAAAAAAAAoP/aAAgBAQABBQJtn//EABQRAQAAAAAAAAAAAAAAAAAAAID/2gAIAQMBAT8Bbf8A/8QAFBEBAAAAAAAAAAAAAAAAAAAAgP/aAAgBAgEBPwFt/wD/xAAUEAEAAAAAAAAAAAAAAAAAAACg/9oACAEBAAY/Am2f/8QAFBABAAAAAAAAAAAAAAAAAAAAoP/aAAgBAQABPyFtn//aAAwDAQACAAMAAAAQ9999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999//8QAFBEBAAAAAAAAAAAAAAAAAAAAgP/aAAgBAwEBPxBt/wD/xAAUEQEAAAAAAAAAAAAAAAAAAACA/9oACAECAQE/EG3/AP/EABQQAQAAAAAAAAAAAAAAAAAAAKD/2gAIAQEAAT8QbZ//2Q==",
      more attributes...
  }
}'
```
<aside class="notice">
  Remember that create user is an authenticated endpoint!
</aside>


## Updating an User

In order to modify the user, you can PUT/PATCH a request.
It accepts the same parameters as the _create user_ endpoint, and you will need an authentication token.

> An example update request:

```shell
curl -X PATCH http://localhost:3000/users/<user-id> \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"  -d \
'{__
  "user": {
      "name": "Another name for the user",
      "is_active": true
  }
}'
```

<aside class="notice">
Remember — create user is an authenticated endpoint!
</aside>

## Deleting an User
You can delete a user! Just send a DELETE request to the endpoint:

```shell
curl -X DELETE http://localhost:3000/users/<user-id> \
-H "Authorization: Bearer <your-token>" \
-H "SC-API-KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="notice">
Remember — create user is an authenticated endpoint!
</aside>
