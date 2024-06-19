---
layout: page
---

# Add a new user

Creates a new [`user`](user.md) who is registering with the on-my-bookshelf service.
The request body contains the new user details. 
You must specify the required properties for the user. 

## URL

```shell
{server_url}/users/
```

## Method

POST


## Request headers

| Header name | Description | Required | Value |
| -------------- | ------ | ------------ |------------ |
| Content-type | The format of the data to be posted. | Required | application/json |
| Basic Auth | A security checkpoint that requires transmission of a username and password with every request. | Required | Basic authentication is a simple authentication scheme that is built into the HTTP protocol. |


## Request body

In the request body, specify a JSON representation of the [`user`](user.md) object. This table lists the properties that are required when you create a user. 

| Property name       | Type   | Required | Description                | Notes |
| -------------- | ------ | -------- | -------------------------- | ----- |
| `last_name`      | string | yes      | Last name of the user.     |       | 
| `first_name`     | string | yes      | First name of the user.    |       |
| `email`          | string | yes      | Email address of the user. | A unique email is required |

## Sample request

The POST body should look something like this. You can change the values of each property.

**Example**

```js
{
    "last_name": "Smith",
    "first_name": "John",
    "email": "j.smith@example.com",
}
```

## Return body

Example of the respsonse. 

The `first_name`, `last_name` and `email` were included in the **Request body** to reflect adding a new user. The response includes the `id` of the new user. The `id` is automatically generated when the new user is created.

**Example**

```js
{
    "id": "1d1b"
    "last_name": "Smith",
    "first_name": "John",
    "email": "j.smith@example.com"
}
```
## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 201 | Created | User data created successfully. |
| 500 | Internal server Error | Invalid JSON. |
| ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

## Related information

* [Security](quickstart.md#security)
