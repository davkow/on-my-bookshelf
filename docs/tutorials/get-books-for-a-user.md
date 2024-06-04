---
layout: page
---

# Tutorial: Get books for a user

This tutorial shows you how to get a list of books associated with a specific user in the on-my-bookshelf service.

Expect this tutorial to take about 10 minutes to complete.

## Before you start

Make sure to complete the [Prerequisites for using the on-my-bookshelf Service](prereqs.md) on the development system you use for the tutorial.

## Retrieve books for a specific user

Retrieving tasks for a specific user from the service requires sending a `GET` request to the appropriate endpoint with the ID of a user.

To retreive books for a specific user:

1. Ensure your local service is running. If not, start it by navigating to the API directory and running the JSON server with the following command:

    ```shell
    cd <your-github-workspace>/my-bookshelf-service/api
    json-server -w on-my-bookshelf_db-source.json
    ```

1. Open the Postman app on your desktop.
1. Create a new request with the following values:
    - **METHOD**: GET
    - **URL**: `{{server_url}}/books?user_id_owner=<1>`<br>
        Replace `<>` with the ID of the user of the books you want to retrieve.<br> 
        **Example**: For the user ``"user_id_owner": 1``, the URL is: `{{server_url}}/books?user_id_owner=1`
    - **Headers**:
        - `Content-Type: application/json`

1. Click  **Send** to make the request.
1. Review the response body, which should contain an array of books associated with the specified user. Each book object should include many details, including `title` and `author`. 

    **Example**

    ```json
    [
        {
        "user_id_owner": 1,
        "title": "Anna Karenina",
        "author": "Leo Tolstory",
        "private": "false",
        "read_status": "read",
        "rating": 4,
        "book_status": "loaned",
        "user_id_borrower": 4,
        "book_id": 2,
        "id": "81c1"
       },

       {
       "user_id_owner": 1,
       "title": "The Years",
       "author": "Annie Ernaux",
       "private": "false",
       "read_status": "reading",
       "rating": null,
       "book_status": "bookshelf",
       "user_id_borrower": null,
       "book_id": 3,
       "id": "da2d"
       }
    ]
    ```

## Next steps

After doing this tutorial in Postman, you might like to repeat it in your favorite programming language. To do this, adapt the values from the tutorial to the properties and arguments that the language uses to
make REST API calls.