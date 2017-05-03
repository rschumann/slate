# Comments

## How obtain all comments

To obtain all comments:

```shell
curl -X GET http://localhost:3000/comments \
-H "Authorization: Bearer <your-token>" \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="success">
Remember — the response is jsonapi format
</aside>

### Pagination params

| Field           | Description                | Type
| -------------   |:-------------:| -----:|
| page[size]      | Number elements per page   | Number
| page[number]    | Number of page             | Number

> Return the comments of the page 2 with 5 elements per page

```shell
curl -X GET http://localhost:3000/comments?page[size]=5&page[number]=2
```

### Filter params

Available filters:

| Field         | Description           | Type
| ------------- |:-------------:| -----:|
| sort          | Sort json response by specific attributes (created_at, updated_at) | Text


> To obtain all comments sorted by created_at:

```shell
curl -X GET http://localhost:3000/comments?sort=created_at \
-H "Authorization: Bearer <your-token>" \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

```shell
curl -X GET http://localhost:3000/comments?sort=-created_at \
-H "Authorization: Bearer <your-token>" \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

## Creating an Comment

In order to create a comment, you need an authorization token for current user.

To create an comment, you need to define all of the required fields in the request body. The fields that compose a comment are:

| Field               | Description                                                   | Type   | Values                                          | Required |
| ------------------  | -------------------------------------------------------------:| ------:| -----------------------------------------------:|  -------:|
| body                | Comment text                                                    | Text   | AnyText                                         | Yes
| commentable_id      | Id of commentable                                               | Number | 1, 2, 3 ...                                     | Yes
| commentable_type    | Type of commentable (now available for Project)                 | Text   | 'Project'                                       | Yes
| is_active           | Activate deactiveta comments (only accessible by admin and publisher) | Boolean  | default value true                      | No


> To create an comment, you have to do a POST with the following body:

```shell
curl -X POST http://localhost:3000/comments \
-H "Authorization: Bearer <your-token>" \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json" -d \
'{__
  "comment": {
      "body": "Lorem ipsum...",
      "commentable_id": 2,
      "commentable_type": "Project"
  }
}'
```

<aside class="notice">
  Remember that create comment is an authenticated endpoint!
</aside>


## Updating an Comment

In order to modify the comment, you can PUT/PATCH a request.
It accepts the same parameters as the _create comment_ endpoint, and you will need an authentication token.

> An example update request:

```shell
curl -X PATCH http://localhost:3000/comments/<comment-id> \
-H "Authorization: Bearer <your-token>" \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"  -d \
'{__
  "comment": {
      "is_active": false
  }
}'
```

<aside class="notice">
Remember — create comment is an authenticated endpoint!
</aside>

## Deleting an Comment
You can delete a comment! Just send a DELETE request to the endpoint:

```shell
curl -X DELETE http://localhost:3000/comments/<comment-id> \
-H "Authorization: Bearer <your-token>" \
-H "SC_API_KEY: Bearer <your-api-key>" \
-H "Content-Type: application/json"
```

<aside class="notice">
Remember — create comment is an authenticated endpoint!
</aside>
