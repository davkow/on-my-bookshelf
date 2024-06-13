# Delete a book

Removes (deletes) the book you identify in the `book_id` parameter from the book resource, if the book exists.

**Important:** With the on-my-bookshelf service running and the Postman app open, you need to **first** run a GET request with the URL `{sever_url}/users` (or `http://localhost:3000/users`) to locate the unique identifier (`id`) of the book you want to delete. Make sure to then include the correct `id` to run the DELETE request.

## URL

```shell
{server_url}/books/{id}
```

## Method

DELETE

## Parameters

| Property name  | Type    | Description                         |
| -------------- | ------- | ----------------------------------- |
| `book_id`      | integer | The record ID of the book to delete |

## Request headers

| Header name | Description | Required | Values |
| -------------- | ------ | ------------ |------------ |
| Content-Type | The format of the data to be posted. | Optional | application/json. Default value.  |
| Accept | The format of the data to be returned. | Optional | application/json. Default value. |

## Request body
None

## Return body

The response returns a book matching the specified `id`, and deletes the object in the database.


**Example**

```
{
    "user_id_owner": 2,
    "title": "Gigi",
    "author": "Colette",
    "private": "true",
    "read_status": "reading",
    "rating": null,
    "book_status": "bookshelf",
    "user_id_borrower": 3,
    "book_id": 1,
    "id": "0e92"
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