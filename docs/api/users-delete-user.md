# Delete a user 

Removes (deletes) the user you identify in the `user_id` parameter from the user resource, if the user exists.

Important: With the on-my-bookshelf service running and the Postman app open, you need to first run a GET request with the URL {sever_url}/users (or http://localhost:3000/users) to locate the unique identifier (`id`) of the user you want to delete. Make sure to then include the correct `id` to run the DELETE request.

## URL

```shell
{server_url}/users/{id}
```

## Method

DELETE

## Parameters

| Property name | Type   | Description |
| -------------- | ------ | ------------ |
| `user_id`      | integer | The record ID of the user to delete |

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
    "book_id_borrowed": null,
    "book_id_loaned": 2,
    "user_id": 1,
    "id": "750b"
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
