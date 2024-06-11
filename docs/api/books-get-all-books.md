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

None

## Request body

None


## Return body

```js
[   
    {
      "user_id_owner": 2,
      "title": "Gigi",
      "author": "Colette",
      "private": "true",
      "read_status": "reading",
      "rating": null,
      "book_status": "bookshelf",
      "user_id_borrower": 3,
      "book_id": 1
    },
    {
      "user_id_owner": 1,
      "title": "Anna Karenina",
      "author": "Leo Tolstoy",
      "private": "false",
      "read_status": "read",
      "rating": 4,
      "book_status": "loaned",
      "user_id_borrower": 4,
      "book_id": 2
    },
    ...
]
```

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Requested data returned successfully. |
| ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

