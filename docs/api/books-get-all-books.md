---
layout: page
---

# Get all books

Returns an array of [`books`](books.md) objects that contain all users that have registered with the service.

## URL

```shell
{server_url}/books
```

## Method

GET

## Paramaters

None

## Request headers

| Header name | Description | Required | Values |
| -------------- | ------ | ------------ |------------ |
| Basic Auth | A security checkpoint that requires transmission of a username and password with every request. | Required | Basic authentication is a simple authentication scheme that is built into the HTTP protocol. |

## Request body

None


## Return body

```js
[   
    {
      "user_id": 2,
      "title": "Gigi",
      "author": "Colette",
      "read_status": "reading",
      "rating": null,
      "book_status": "bookshelf",
      "id": 1
    },
    {
      "user_id": 1,
      "title": "Anna Karenina",
      "author": "Leo Tolstoy",
      "read_status": "read",
      "rating": 4,
      "book_status": "loaned",
      "id": 2
    },
    ...
]
```

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Requested data returned successfully. |
| ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

## Related information

* [Security](quickstart.md#security)