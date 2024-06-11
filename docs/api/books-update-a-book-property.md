---
layout: page
---

# Update a book property

The Patch request updates a book property, but does not change other parameters in the [`book`](user.md) object.

**Important:** With the on-my-bookshelf service running and the Postman app open, you need to **first** run a GET request with the URL `{sever_url}/users` (or `http://localhost:3000/users`) to locate the unique identifier (`id`) of the book you want to update. Make sure to then include the correct `id` to run a PATCH request to change a book property. 

## URL

```shell
{server_url}/books/{id}
```

## METHOD

PATCH

## Request headers

Must include a `Content-type` header to specify JSON.

| Header name | Description | Required | Value |
| -------------- | ------ | ------------ |------------ |
| Content-type | The format of the data to be posted. | Required | application/json |

## Request body

This table lists the properties you can update.

| Property       | Type    | Required | Description                | 
| -------------- | ------- | -------- | -------------------------- | 
| user_id_owner  | integer | yes      | ID of the user who owns the book |                            
| title          | string  | yes      | Title of the book.         |        
| author         | string  | yes      | Author of the book.        |       
| private | boolean | no | Indicates if the book is private or not. Possible values are `true` or `false`. |
| read_status | string or null | no | Current reading status of the book. Possible values are one of: `read`, `reading`, `toread`, or `null`.  | 
| rating | integer or null | no  | Rating given to the book by owner. Possible values can be an integer from `1` through `5`, or `null`. | 
| book_status | string | no | Status of the book. Possible values are one of: `bookshelf`, `borrowed`, or `loaned`. |
| user_id_borrower | integer or null | no | ID of the user who borrowed the book. Derived from the `user_id` of the User object for the borrower. |
| book_id | integer | yes | ID of the book. |

## Sample request

The PATCH body should look something like this. You can update the value of a property. 

**Example**<br>
This example updates the value of the title from `Gigi` to `The Vagabond`.

```js
{
    "title": "The Vagabond"
}
```

## Return body

Example of the respsonse. The title changed. 

**Example**

```js
[
    {
        "user_id_owner": 2,
        "title": "The Vagabond",
        "author": "Colette",
        "private": "true",
        "read_status": "reading",
        "rating": null,
        "book_status": "bookshelf",
        "user_id_borrower": 3,
        "book_id": 1,
        "id": "8951"

    }
]
```
## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | OK | Standard response for a successful HTTP request. |
| 500 | Internal server Error | Invalid JSON. |
| ECONNREFUSED | N/A | Service is offline. Start the service and try again. |