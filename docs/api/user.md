---
layout: page
---
# `user` resource

Base endpoint

```shell
{server_url}/users
```

Contains information about the users of the service.

## Resource properties

Sample `user` resource

```js

{
    "last_name": "Leblanc",
    "first_name": "Alix",
    "email": "a.leblanc@example.com",  
    "book_id_borrowed": null,
    "book_id_loaned": 2,
    "user_id": 1,
}
```

| Property name | Type | Required | Description |
| ------------- | ----------- | ----------- | ----- |
| `last_name` | string | yes  | Last name of the user. |
| `first_name` | string | yes | First name of the user. | 
| `email`      | string | yes | Email address of the user. | 
| `book_id_borrowed` | integer or null | no | ID of the book borrowed by the user, if any. Derived from the `book_id` of the Book object for the borrowed book. |
| `book_id_loaned` | integer or null | no | ID of the book loaned by the user, if any. Derived from the `book_id` of the Book object for the loaned book.  |
| `user_id` | integer | yes | ID of the user. |

## Operations

The `user` resource supports these operations.

### GET (READ)

* [Get all users](users-get-all-users.md)

### POST (CREATE)

* [Add a new user](users-add-a-new-user.md)

### PATCH (UPDATE)

* [Update a user property](users-update-a-user-property.md)

### DELETE

* [Delete a user](users-delete-user.md)