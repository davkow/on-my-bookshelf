---
layout: page
---

# Get all users

Returns an array of [`user`](user.md) objects that contain all users that have registered with the service.

## URL

```shell
{server_url}/users
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
        "last_name": "Leblanc",
        "first_name": "Alix",
        "email": "a.leblanc@example.com",
        "user_id": 1
    },
    {
        "last_name": "Michaud",
        "first_name": "Genevieve",
        "email": "g.michaud@example.com",
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

## Related information

* [Security](quickstart.md#security)