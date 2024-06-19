---
layout: page
---

# Update a book property

The Patch request updates a book property, but does not change other parameters in the [`book`](books.md) object.


## URL

```shell
{server_url}/books/{id}
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

| Property name | Type    | Required | Description                | 
| -------------- | ------- | -------- | -------------------------- |                       
| `title`          | string  | yes      | Title of the book.         |        
| `author`         | string  | yes      | Author of the book.        |       
| `read_status` | string or null | no | Current reading status of the book. Possible values are one of: `read`, `reading`, `toread`, or `null`.  | 
| `rating` | integer or null | no  | Rating given to the book by owner. Possible values can be an integer from `1` through `5`, or `null`. | 
| `book_status` | string | no | Status of the book. Possible values are one of: `bookshelf`, `borrowed`, or `loaned`. |

## Sample request

The PATCH body should look something like this. You can update the value of a property. 

**Example**<br>
This example updates the value of the `"title"` from `Gigi` to `The Vagabond`.

```js
{
    "title": "The Vagabond"
}
```

## Return body

Example of the respsonse. The `"title"` changed to `"The Vagabond"`. 

**Example**

```js
{
    "user_id": 2,
    "title": "The Vagabond",
    "author": "Colette",
    "read_status": "reading",
    "rating": null,
    "book_status": "bookshelf",
    "id": "1"
}
```
## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | OK | Standard response for a successful HTTP request. |
| 404 | Error | Specified user record not found. |
| ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

## Related information

* [Security](quickstart.md#security)