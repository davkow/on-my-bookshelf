# Delete a user 

Removes (deletes) the user you identify in the `id` parameter from the user resource, if the user exists.

## URL

```shell
{server_url}/users/{id}
```

## Method

DELETE

## Parameters

| Property name | Type   | Description |
| -------------- | ------ | ------------ |
| `id`      | integer | The record ID of the user to delete |

## Request headers

| Header name | Description | Required | Values |
| -------------- | ------ | ------------ |------------ |
| Content-Type | The format of the data to be posted. | Optional | application/json. Default value. |
| Basic Auth | A security checkpoint that requires transmission of a username and password with every request. | Required | Basic authentication is a simple authentication scheme that is built into the HTTP protocol. |
| Accept | The format of the data to be returned. | Optional | application/json. Default value. |

## Request body
None

## Return body

The response returns a user matching the specified `id`, and deletes the object in the database.

```
{
    "last_name": "Leblanc",
    "first_name": "Alix",
    "email": "a.leblanc@example.com",
    "id": "1"
}
```
## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Action completed successfully |
| 202 | Accepted| Action has been queued |
| 204 | No Content| Action has been performed, but the response does not include an entity |
| 404 | Error | Specified user record not found |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

## Related information

* [Security](quickstart.md#security)
