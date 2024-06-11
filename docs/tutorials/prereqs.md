# Prerequisites for using the on-my-bookshelf Service

## General

* Development system (Mac, PC, or Linux) running a current or Long-term support (LTS) version of the OS.
* [GitHub account](https://github.com)
* [Postman (The Postman app) ](https://www.postman.com/downloads/)<br>
  **Note**: Do not install **Postman on the web**. It will not work when running the on-my-bookshelf service on a development system with a ``http://localhost`` hostname.
* **Optional**: [GitHub Desktop](https://desktop.github.com)

## Specific to using the Service

* Fork of the [`on-my-bookshelf`](https://github.com/davkow/on-my-bookshelf) repository (repo).<br>
Instructions: [Forking a repository](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo#forking-a-repository)

* Current copy of the database file: `on-my-bookshelf_db-source.json`. It is available *after* syncing your fork. Location: `on-my-bookshelf` (repo) &gt; `api` folder/directory. 

* Current/LTS version of [node.js](https://nodejs.org/en)

* **MacOS only**: Install [Homebrew](https://brew.sh/):
  1. Open Terminal.
  2. Paste code and press enter, and then follow the instructions.
     
     ```
     /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
     ```
* Current version of [json-server](https://www.npmjs.com/package/json-server). 

   **MacOS only**: 
   Steps from the Terminal:
  
   1. ``brew install git node json-server``
   2. ``sudo npm install -g json-server``

## Test your development system
1. Create and checkout a test branch of your fork of the ``on-my-bookshelf`` repo. 

   &lt;`your GitHub repo workspace`&gt; is the directory that contains your fork of the `on-my-bookshelf` repo.

    ```shell
    cd <your GitHub repo workspace>
    ls
    # (see the on-my-bookshelf directory in the list)
    cd on-my-bookshelf
    git checkout -b tutorial-test
    cd api
    json-server -w on-my-bookshelf_db-source.json
    ```

    If your development system is installed correctly, you should see
    the service start and display the URL of the service: `http://localhost:3000`.

1. Make a test call to the service using curl.

    ```shell
    curl http://localhost:3000/users
    ```
   **Note:** [curl](https://curl.se/) is installed by default on the macOS and [Microsoft Windows 10 & 11](https://curl.se/windows/microsoft.html). 


1. If the service is running correctly, you should see a list of users from the service, such as in this example.

    ```js
    [
        {
            "last_name": "Leblanc",
            "first_name": "Alix",
            "email": "a.leblanc@example.com",
            "book_id_borrowed": null,
            "book_id_loaned": 2,
            "user_id": 1
        },
        {
            "last_name": "Michaud",
            "first_name": "Genevieve",
            "email": "g.michaud@example.com",
            "book_id_borrowed": 4,
            "book_id_loaned": 3,
            "user_id": 2
        },
        ...
    ```

If you do not see the list of users, or receive an error in any step
of the procedure, investigate and correct the error before continuing.
Some common situations that cause errors include:

1. You mistyped a command.
2. You are not in the correct directory.
3. A required software component did not install correctly.
4. A required software component is not up to date.


