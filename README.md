# Library System API Documentation

>## Overview
>The Library System API allows users to manage authors, books, and authentication. It uses the Slim framework and JSON Web Tokens (JWT) for secure communication.

### Features
- User registration and authentication.
- CRUD operations for authors and books.
- Token-based authentication using JWT.
- CORS support for cross-origin requests.


## API Endpoints

### User Management
#### `POST /user/register`
- **Description**: Registers a new user.
- **Payload**: 
  ```json
  {
      "username": "string",
      "password": "string"
  }
  ```
- **Response**:
  - `201 Created` on success.
  - `400 Bad Request` if validation fails.

#### `POST /user/auth`
- **Description**: Authenticates a user and generates a JWT.
- **Payload**:
  ```json
  {
      "username": "string",
      "password": "string"
  }
  ```
- **Response**:
  - `200 OK` with the JWT.
  - `401 Unauthorized` if credentials are invalid.

### Author Management
#### `POST /authors`
- **Description**: Adds a new author.
- **Payload**:
  ```json
  {
      "name": "string",
      "bio": "string"
  }
  ```
- **Response**:
  - `201 Created` on success.
  - `400 Bad Request` if validation fails.
#### `GET /authors/get`
- **Description**: Retrieves a list of all authors.
- **Response**:
  - `200 OK` with an array of authors.

#### `PUT /authors/update/{id}`
- **Description**: Updates details of a specific author.
- **Payload**:
  ```json
  {
      "name": "string",
      "bio": "string"
  }
  ```
- **Response**:
  - `200 OK` on success.
  - `404 Not Found` if the author ID does not exist.

#### `DELETE /authors/delete/{id}`
- **Description**: Deletes a specific author.
- **Response**:
  - `200 OK` on success.
  - `404 Not Found` if the author ID does not exist.

### Book Management
#### `POST /books`
- **Description**: Adds a new book.
- **Payload**:
  ```json
  {
      "title": "string",
      "author_id": "integer",
      "published_date": "string"
  }
  ```
- **Response**:
  - `201 Created` on success.
  - `400 Bad Request` if validation fails.

#### `GET /books/get`
- **Description**: Retrieves a list of all books.
- **Response**:
  - `200 OK` with an array of books.

#### `PUT /books/update/{id}`
- **Description**: Updates details of a specific book.
- **Payload**:
  ```json
  {
      "title": "string",
      "author_id": "integer",
      "published_date": "string"
  }
  ```

- **Response**:
  - `200 OK` on success.
  - `404 Not Found` if the book ID does not exist.

#### `DELETE /books/delete/{id}`
- **Description**: Deletes a specific book.
- **Response**:
  - `200 OK` on success.
  - `404 Not Found` if the book ID does not exist.

### Combined Data
#### `GET /authors_books`
- **Description**: Fetches data combining authors and their books.
- **Response**:
  - `200 OK` with combined data.

## Technical Details
- **Framework**: Slim PHP Framework
- **Database**: MySQL (configured in `index.php`).
- **Authentication**: JWT.

## Setup
1. Clone the repository.
2. Install dependencies:
   ```bash
   composer install
   ```
3. Configure the database connection in `index.php`.
4. Start the server:
   ```bash
   php -S localhost:8080 -t public
   ```
5. Access the API at `http://localhost:8080`.

## Contributing
Feel free to submit issues or create pull requests.

## License
This project is licensed under the MIT License.
