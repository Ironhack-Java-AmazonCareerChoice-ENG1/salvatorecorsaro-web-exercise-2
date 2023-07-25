# WEB EXERCISE 2

Exercise: Create a Digital Library API
Overview

For this exercise, you'll be creating a Digital Library API using Spring Boot and MySQL. This library will store books, allowing users to add, update, retrieve, and remove books.

Imagine a world where physical libraries have become a thing of the past, and our civilization relies solely on digital catalogs. In this dystopian (or utopian, depending on how you see it!) future, YOU have been chosen to lay the foundation of the world's premier digital library!
## Requirements:

Book Entity: Each book should have the following attributes:
        - id: A unique identifier for the book.
        - title: The title of the book.
        - author: The author of the book.
        - isbn: A unique International Standard Book Number.
        - publishedDate: The date the book was published.
        - summary: A brief summary or description of the book.

    Endpoints:
        GET /books: Retrieve a list of all books in the library.
        GET /books/{id}: Retrieve a specific book by its id.
        POST /books: Add a new book to the library. This should reject any books with duplicate isbn numbers.
        PUT /books/{id}: Update an existing book's full details by its id.
        PATCH /books/{id}: Partially update an existing book's details by its id.
        DELETE /books/{id}: Remove a book from the library by its id.

  Database: Use MySQL as the database to store the book records. Make sure to handle database connections properly, managing and pooling resources.

  Error Handling: Properly handle possible errors. This includes invalid data submission, trying to access books that don't exist, or any other potential error.

## Validation Constraints:

- title: Required. Between 3 to 255 characters.
- author: Required. Between 3 to 255 characters.
-  isbn: Required. Should follow the ISBN-13 format (e.g., 978-3-16-148410-0).
- publishedDate: Not in the future. (Optional, but if provided, should be a valid date before the current date.)
- summary: Maximum of 1000 characters.

Implementation:

  Use the @Valid annotation in your controller methods to trigger validation of incoming data.
    Add validation annotations (e.g., @Size, @Pattern, @PastOrPresent) on the attributes of your Book entity.
    Handle MethodArgumentNotValidException in an exception handler to send meaningful error messages to the client.
    

## Instructions:

  1. Setup:
        Initialize a new Spring Boot project using the Spring Initializr or your favorite IDE.
        Add the necessary dependencies: Spring Web, Spring Data JPA, and MySQL Driver.
        Set up the application properties with the appropriate database connection details.

  2. Development:
        Define the Book entity class with the necessary JPA annotations.
        Create a BookRepository interface to manage CRUD operations.
        Develop a BookService class to handle business logic.
        Develop a BookController class to expose the API endpoints.


## Submission:

Once you're done, push your code to a Git repository with the name: [yourname]-spring-web-exercise-2
