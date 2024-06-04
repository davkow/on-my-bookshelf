# Delete a user 

Removes the user you identify in the `user_id` parameter from the user resource, if the user exists.

## URL

```shell
{DELETE} {server_url}/users/{user_id}
```

## Params

| Parameter name | Type   | Description |
| -------------- | ------ | ------------ |
| `user_id`      | integer | The record ID of the user to delete |

## Request headers

| Header name | Description | Required | Values |
| -------------- | ------ | ------------ |------------ |
| Content-Type | The format of the data to be posted. | Optional | application/json. Default value.  |
| Accept | The format of the data to be returned. | Optional | application/json. Default value. |

## Request body
None

## Return body
None

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Action completed successfully |
| 202 | Accepted| Action has been queued |
| 204 | No Content| Action has been performed, but the response does not include an entity |
| 404 | Error | Specified user record not found |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |