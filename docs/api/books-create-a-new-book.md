---
layout: page
---

# Create a new book

Creates a [`book`](books.md) object in the database. The request body contains the details for the new book. You must specify the required properties for the book. 

## URL

```shell
{server_url}/books
```

## Method

POST

## Request headers

Must include a `Content-type` header to specify JSON.

| Header name | Description | Required | Value |
| -------------- | ------ | ------------ |------------ |
| Content-type | The format of the data to be posted. | Required | application/json |

## Request body

In the request body, specify a JSON representation of the [`book`](books.md) object. This table lists the properties that are required when you create a book. 

| Property          | Type   | Required | Description                | Notes |
| ----------------- | ------ | -------- | -------------------------- | ----- |
| `user_id_owner`   | integer | yes | The ID of the user who owns the book. Derived from the `user_id` of the User object for the owner. |
| `title`           | string | yes | Title of the book. |
| `author` | string | yes | Author of the book. |

## Sample request

The POST body should look something like this. You can change the values of each property.

**Example**

```js
[
    {
        "user_id_owner": "7",
        "title": "The Great Gatsy",
        "author": "F. Scott Fitzgerald"
    }
]
```

## Return body

Example of the respsonse. 

The title and author are same as what was used in the **Request body**. The `id` is automatically generated when the new book object is created. 

**Example**

```js
[
    {
        "id": "92r"
        "user_id_owner": "7",
        "title": "The Great Gatsby",
        "author": "F. Scott Fitzgerald"
    }
]
```
## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 201 | Created | User data created successfully. |
| 500 | Internal server Error | Invalid JSON. |
| ECONNREFUSED | N/A | Service is offline. Start the service and try again. |
