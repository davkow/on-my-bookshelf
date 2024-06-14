---
layout: page
---

# Update a user property

The Patch request updates a user property, but does not change other parameters in the [`user`](user.md) object.

**Important:** With the on-my-bookshelf service running and the Postman app open, you need to **first** run a GET request with the URL `{sever_url}/users` (or `http://localhost:3000/users`) to locate the unique identifier (`id`) of the user who has the record you want to update. Make sure to then include the correct `id` to run a PATCH request to change a user property. 

## URL

```shell
{server_url}/users/{id}
```

## Method

PATCH

## Request headers

| Header name | Description | Required | Value |
| -------------- | ------ | ------------ |------------ |
| Content-type | The format of the data to be posted. | Required | application/json |
| Basic Auth | A security checkpoint that requires transmission of a username and password with every request. | Required | Basic authentication is a simple authentication scheme that is built into the HTTP protocol. |


## Request body

This table lists the properties you can update.

| Property name      | Type   | Required | Description                | 
| -------------- | ------ | -------- | -------------------------- | 
| `last_name`      | string | yes      | Last name of the user.     |       
| `first_name`     | string | yes      | First name of the user.    |       
| `email`          | string | yes      | Email address of the user. | 
| `book_id_borrowed` | integer or null | no | ID of the book borrowed by the user, if any. Derived from the `book_id` of the Book object for the borrowed book. |
| `book_id_loaned` | integer or null | no | ID of the book loaned by the user, if any. Derived from the `book_id` of the Book object for the loaned book.  |
| `user_id` | integer | yes | ID of the user. |

## Sample request

The PATCH body should look something like this. You can update the value of a property. 

**Example**<br>
This example updates the value of the email address from `a.leblanc@example.com` to `alix.leblanc@example.com`.

```js
{
    "email": "alix.leblanc@example.com"
}
```

## Return body

Example of the respsonse. The email address changed. 

**Example**

```js
[
    {
        "last_name": "Leblanc",
        "first_name": "Alix",
        "email": "alix.leblanc@example.com,"
        "book_id_borrowed": null,
        "book_id_loaned": 2,  
        "user_id": 1,
        "id": "b17d"
    }
]
```
## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | OK | Standard response for a successful HTTP request. |
| 500 | Internal server Error | Invalid JSON. |
| ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

## Related information

* [Security](quickstart.md#security)