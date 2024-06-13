# Tutorial: Add a new user

This tutorial shows you how to add a new user in the on-my-bookshelf service.

Expect this tutorial to take about 15 minutes to complete.

## Before you start

Make sure to complete the [Prerequisites for using the on-my-bookshelf Service](prereqs.md) on the development system you use for the tutorial.

**Recommendation:** If you are using a fork of the on-my-bookshelf repo, create a new (working) branch to do this tutorial. This will help prevent a mistake from affecting your work in any another branch.   

This tutorial assumes you have set the `server_url` variable in Postman to `http://localhost:3000`. 
If you are **not** using variables in Postman, replace all occurrences of `{server_url}` in these examples with `http://localhost:3000`. For more information on using environments and variables in Postman, see [Using Variables inside Postman](https://blog.postman.com/using-variables-inside-postman-and-collection-runner/).

## Add (enroll) a new user 

You can add a new user in the on-my-bookshelf service. To do this, `POST` a new `user` resource containing the details of the user.

### To add a new user:

1. Ensure your local service is running. If not, start it by navigating to the API directory and running the JSON server with the following command:

    ```shell
    cd <your-github-workspace>/my-bookshelf-service/api
    json-server -w on-my-bookshelf_db-source.json
    ```

1. Open the Postman app on your desktop.
1. Create a new request with the following values:
   * **METHOD**: POST
   * **URL**: `{server_url}/users`
   * **Headers**: `Content-Type`: `application/json`
   * **Request body**: Add values for each property:
   
     **Example**

     ```json 
     {
        "last_name": "Rafferty",
        "first_name": "Terrence",
        "email": "t.rafferty@example.com" 
     }
     ```

1. Click  **Send** to make the request.
1. Watch for the response body, which should look something like the **Example** below. The first and last names are the same as in the **Request body**, and the response includes the newly created `id` of the new user. 

    **Example**

    ```json
    {
        "id": "9340",
        "last_name": "Rafferty",
        "first_name": "Terrence",
        "email": "t.rafferty@example.com"
    }
    ```

This completes the tutorial of adding a new user.  

### Other tutorial topics

- [Tutorial: Search for a user by email, name, or user ID](search-for-a-user-by-email.md)

- [Tutorial: Add a new book](add-a-new-book.md)

- [Tutorial: Get a list of books for a user](get-books-for-a-user.md)
