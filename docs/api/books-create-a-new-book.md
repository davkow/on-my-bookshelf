---
layout: page
---

# Create a new book

Creates a new [`book`](book.md) for a user of the on-my-bookshelf service.
You must specify the required properties for the book. 

## URL

```shell
{POST} {server_url}/books/
```

## Request headers

Must include a `Content-type` header to specify JSON.

| Header name | Description | Required | Value |
| -------------- | ------ | ------------ |------------ |
| Content-type | The format of the data to be posted. | Required | application/json |

## Request body

In the request body, specify a JSON representation of the [`book`](user.md) object. This table lists the properties that are required when you create a book. 

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
        "user_id_owner": "5",
        "title": "Infinite Jest",
        "author": "David Foster Wallace",
    }
]
```

## Return body

Example of the respsonse. 

The `title` and `author` were changed - creating a new book - which is reflected in the response. The `user_id` is automatically generated when a new book is created.

**Example**

```js
[
    {
        "user_id_owner": "7",
        "title": "Fight Club",
        "author": "Chuck Palahniuk",
        "user_id": "15"
    }
]
```
## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 201 | Created | User data created successfully. |
| 500 | Internal server Error | Invalid JSON. |
| ECONNREFUSED | N/A | Service is offline. Start the service and try again. |
