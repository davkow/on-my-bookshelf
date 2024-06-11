---
layout: page
---

# on-my-bookshelf service API

This is a mock API to simulate the REST interface of an
imaginary service. 

This API can be integrated with applications that allow people to track their books. It can also be used as part of a more social lending library application where you can also track lending and borrowing of books.

## Overview

Get a comprehensive understanding of the service by reading the [Overview](overview.md).

## Get started

Start using the service by completing set up and making a first API call, which are both covered in the [Get started](api/getstarted.md).


## Tutorials

You can learn how to do common tasks with the on-my-bookshelf Service. 

**Before** starting any tutorial, you need to first set up a development system. Complete instructions:<br> 
[Prerequisites for using the on-my-bookshelf Service](tutorials/prereqs.md)

### List of tutorials
- [Get a list of books for a user](tutorials/get-books-for-a-user.md)
- [Add a new book](tutorials/add-a-new-book.md)
- [Add a new user](tutorials/add-a-new-user.md)
- [Search for a user by email, name, or user ID](tutorials/search-for-a-user-by-email.md)

## API reference docs

Detailed descriptions of the service's resources.

The API reference docs refer to a `{server_url}` when they
refer to the URL of a resource. The `{server_url}` value depends on the installation of the service.

When running a local test, the `{server_url}` is
generally `http://localhost:3000`.

* [user resource](api/user.md)
* [books resource](api/books.md)
* [Handling errors](api/error-handling.md)
