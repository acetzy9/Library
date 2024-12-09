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
