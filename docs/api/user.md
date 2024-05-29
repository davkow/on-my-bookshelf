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
    "book_id_borrowed": null,
    "book_id_loaned": 2,
    "user_id": 1,
}
```

| Property name | Type | Description |
| ------------- | ----------- | ----------- |
| `last_name` | string | The user's last name |
| `first_name` | string | The user's first name |
| `book_id_borrowed` | ***Discuss with SME*** | The book borrowed unique record ID  |
| `book_id_loaned` | number | The book loaned unique record ID |
| `user_id` | number |The user's unique record ID|

## Operations

The `user` resource supports these operations.

## GET (READ)

## POST (CREATE)

## PATCH (UPDATE)

## DELETE
