---
layout: page
---
# `books` resource

Base endpoint

```shell
{server_url}/books
```

Contains information about books stored for the users of the service.

To have a book in the service, the user must be added to
the service first.

## Resource properties

Sample `book` resource

```js

{
    "user_id_owner": 2,
    "title": "Gigi",
    "author": "Collette",
    "private": "true",
    "read_status": "reading",
    "rating": null,
    "book_status": "bookshelf",
    "user_id_borrower": 3,
    "book_id": 1 
}
```

| Property name | Type | Description |
| ------------- | ----------- | ----------- |
| `user_id_owner` | number | The ID of the user resource to which this book is assigned |
| `title` | string | The title of the book |
| `author` | string | The author of the book  |
| `private` | ***Discuss with SME***  | ***Discuss with SME*** |
| `read_status` | string | `reading` (currently reading) or `read` (finished reading)  | 
| `rating` | ***Discuss with SME*** | user rating of the book |
| `book_status` | string | the status of the book: either `loaned` or on `bookshelf` |
| `user_id_borrower` | number | The unique record ID fo the borrower  |
| `book_id` | number | The unique record ID of the book |

## Operations

The `book` resource supports these operations.

## GET (READ)

## POST (CREATE)

## PATCH (UPDATE)

## DELETE
