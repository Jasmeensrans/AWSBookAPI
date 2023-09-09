# Books API

The **Book API** is a serverless API built on AWS infrastructure that allows you to perform CRUD operations on a collection of books stored in a DynamoDB table. This API was created using the AWS console. The purpose of this API is to store different books a user has read, along with a rating for each book. A book object consists of the following 
```
{
  name: string,
  author: string,
  pages: int,
  rating: int, \\ out of 5
  username: string
}
```

## API Base URL

The API is hosted at the following base URL: https://z9ocr7n4rj.execute-api.us-east-2.amazonaws.com/books

## Routes

### Get All Books

Retrieve a list of all books stored in the database.

- **URL:** `/get/books`
- **Method:** `GET`
- **Response:** JSON array containing book objects.

### Get a Book by ID

Retrieve a specific book by providing its unique identifier.

- **URL:** `/get/books/{id}`
- **Method:** `GET`
- **Parameters:**
  - `{id}`: The unique identifier of the book.
- **Response:** JSON object representing the book.

### Create a New Book

Create a new book entry in the database.

- **URL:** `/put/books`
- **Method:** `PUT`
- **Request Body:** JSON object representing the book to be created. Must include fields for name, author, pages, rating, and username.
- **Response:** JSON object confirming the creation of the book.

### Delete a Book

Delete a book from the database using its unique identifier.

- **URL:** `/delete/books/{id}`
- **Method:** `DELETE`
- **Parameters:**
  - `{id}`: The unique identifier of the book to be deleted.
- **Response:** JSON object confirming the deletion.


## Example Usage

Here's an example of how you can use the API with `curl` to create a new book:

```bash
curl -X PUT -H "Content-Type: application/json" -d '{
  "name": "Sample Book",
  "author": "John Doe",
  "pages": 250,
  "rating": 4,
  "username": "johndoe123"
}' https://z9ocr7n4rj.execute-api.us-east-2.amazonaws.com/books/put/books
