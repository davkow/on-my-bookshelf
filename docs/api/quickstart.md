---
layout: page
---

# Quickstart

This provides what you need to get started using the on-my-bookshelf service.


## Set up for using the service

If you:

* **Previously used the on-my-bookshelf service:**<br>
You are already enrolled and can continue working with the service. 

* **Are new to the service:**<br>
  There are commonly used tools/appplications you may have already have installed, including GitHub, Postman, node.js, json-server, and Homebrew (macOS only). 
  
  To confirm if you have everything installed, and for the complete step-by-step instructions for set up (on both macOs and Microsoft Windows) see [Prerequisites](../tutorials/prereqs.md).

## Security

* On-my-bookshelf is a simulated API with **Basic Auth** authentication, which requires a **username** and **password**, but it will always pass because there is nothing on the server to check it and fail.
* API requests must provide a **username** and **password** in the HTTP Authorization header, encoded in Base64.

## Make a first API call

After completing set up - ***including*** creating and checking out a test branch of your fork as covered in step 1 of [Test your development system](../tutorials/prereqs.md/#test-your-development-system) - you can try making a first request to to list all the books.

### Steps
1. Open Postman.
1. To create a new request, with **My Workspaces** open, click **New** &gt; **HTTP**.
3. Set the request type to `GET`, and for the URL, type: `http://localhost:3000/books`.
4. Click **Headers** to add a new Header: Key: `Content-Type`, Value: `application/json`.
5. Click **Send**.
6. Check the response. If successful, there is a list of all the books from the on-my-bookshelf service. 

   **Example** The first two books:
   

   ```js
   [   
      {
      "user_id": 2,
      "title": "Gigi",
      "author": "Colette",
      "read_status": "reading",
      "rating": null,
      "book_status": "bookshelf",
      "id": "1"
     },
     {
       "user_id": 1,
       "title": "Anna Karenina",
       "author": "Leo Tolstoy",
       "read_status": "read",
       "rating": 4,
       "book_status": "loaned",
       "id": "2"
     },
     ...
   ]
   ```

## Next steps 

After successful completion of the set up and making a first API call, you are ready to do more things with the service. A good place to start is reading [on-my-bookshelf service API](../index.md), which includes links to tutorials and the API reference docs.