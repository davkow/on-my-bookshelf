---
layout: page
---
# `book` resource

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
    "user_id": 2,
    "title": "Gigi",
    "author": "Collette",
    "read_status": "reading",
    "rating": null,
    "book_status": "bookshelf",
    "id": 1 
}
```

| Property name | Type | Required | Description |
| ------------- | ----------- | ----------- | ---|
| `user_id` | integer | yes | ID of the user who owns the book. Derived from the `user_id` of the User object for the owner. |
| `title` | string | yes | Title of the book. |
| `author` | string | yes | Author of the book. |
| `read_status` | string or null | no | Current reading status of the book. Possible values are one of: `read`, `reading`, `toread`, or `null`.  | 
| `rating` | integer or null | no  | Rating given to the book by owner. Possible values can be an integer from `1` through `5`, or `null`. | 
| `book_status` | string | no | Status of the book. Possible values are one of: `bookshelf`, `borrowed`, or `loaned`. |
| `id` | integer | yes | ID of the book. |

## Operations

The `book` resource supports these operations.

### GET (READ)

* [Get all books](books-get-all-books.md)

### POST (CREATE)

* [Create a new book](books-create-a-new-book.md)

### PATCH (UPDATE)

* [Update a book property](books-update-a-book-property.md)

### DELETE

* [Delete a book](books-delete-book.md)