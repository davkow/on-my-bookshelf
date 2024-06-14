# Tutorial: Search for a user by email, name, or user ID

This tutorial shows you how to search for (get) a user by email, name, or user ID in the on-my-bookshelf service.

Expect this tutorial to take about 15 minutes to complete.

## Before you start

Make sure to complete the [Prerequisites for using the on-my-bookshelf Service](prereqs.md) on the development system you use for the tutorial.

**Recommendation:** If you are using a fork of the on-my-bookshelf repo, create a new (working) branch to do this tutorial. This will help prevent a mistake from affecting your work in any another branch.   

This tutorial assumes you have set the `server_url` variable in Postman to `http://localhost:3000`. 
If you are **not** using variables in Postman, replace all occurrences of \{\{server_url\}\} in these examples with `http://localhost:3000`. For more information on using environments and variables in Postman, see [Using Variables inside Postman](https://blog.postman.com/using-variables-inside-postman-and-collection-runner/).

## Search for a user by email, name, or user ID

To search for a user by email, name, or user ID from the service requires sending a `GET` request to the appropriate endpoint.

### To search for a user by email:

1. Ensure your local service is running. If not, start it by navigating to the API directory and running the JSON server with the following command:

    ```shell
    cd <your-github-workspace>/my-bookshelf-service/api
    json-server -w on-my-bookshelf_db-source.json
    ```

1. Open the Postman app on your desktop.
1. Create a new request with the following values:
   * **METHOD**: GET
   * **URL**: `{server_url}/users?email=<  >`
     
     Replace `<  >` with the email of the user.
    
     **Example**: For the email for the user Alix Leblanc, the URL is: 
     
     `{server_url}/users?email=a.leblanc@example.com`
   * **Headers**: Key: `Content-Type`, Value: `application/json`

     **Note:** The email address is case sensitive.

1. Click  **Send** to make the request.
1. Review the response body, which should contain: 

    **Example**

    ```json
    [
        {
        "last_name": "Leblanc",
        "first_name": "Alix",
        "email": "a.leblanc@example.com",
        "book_id_borrowed": null,
        "book_id_loaned": 2,
        "user_id": 1,
        "id": "b17d"
        }

    ]
    ```

   **Note:** If no user matches the search criteria, the service will return an empty array ([]), indicating that there are no users with the specified email address.

This completes the tutorial of searching for a user by email.  

### To search for a user by name or user ID

Follow the steps above for [To search for a user by email](#to-search-for-a-user-by-email), except modify the URL:

- URL: Search for a user by last name: `{{server_url}}/users?last_name=<  >`<br>

  **Example:** `{{server_url}}/users?last_name=Leblanc`

- URL: Search for a user by first name: `{{server_url}}/users?first_name=<  >`<br>

  **Example:** `{{server_url}}/users?first_name=Alix`

- URL: Search for a user by user ID: `{{server_url}}/users?user_id=<>`<br>

  **Example** `{{server_url}}/users?user_id=1`

**Note:** The last name and first name are case sensitive.

### Other tutorial topics

- [Tutorial: Get a list of books for a user](get-books-for-a-user.md)

- [Tutorial: Add a new user](add-a-new-user.md)

- [Tutorial: Add a new book](add-a-new-book.md)

