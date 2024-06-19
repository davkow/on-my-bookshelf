---
layout: page
---

# Update a user property

The Patch request updates a user property, but does not change other parameters in the [`user`](user.md) object.

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
{
    "last_name": "Leblanc",
    "first_name": "Alix",
    "email": "alix.leblanc@example.com,"
    "id": "1"
}
```
## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | OK | Standard response for a successful HTTP request. |
| 400 | Error | Specified user record not found. |
| ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

## Related information

* [Security](quickstart.md#security)