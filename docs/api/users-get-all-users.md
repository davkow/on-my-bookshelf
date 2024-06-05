---
layout: page
---

# Get all users

Returns an array of [`user`](user.md) objects that contain all users that have registered with the service.

## URL

```shell
{server_url}/users
```

## Params

None

## Request headers

None

## Request body

None


## Return body

```js
[
    {
        "last_name": "Leblanc",
        "first_name": "Alix",
        "email": "a.leblanc@example.com",
        "book_id_borrowed": null,
        "book_id_loaned": 2,
        "user_id": 1
    },
    {
        "last_name": "Michaud",
        "first_name": "Genevieve",
        "email": "g.michaud@example.com",
        "book_id_borrowed": 4,
        "book_id_loaned": 3,
        "user_id": 2
    },
    ...
]
```

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | OK | Returns an array of User objects |
| 404 | Not found | The requested resource could not be found. |
| ECONNREFUSED | N/A | Service is offline. Start the service and try again. |
