
# Book Management API Documentation

## Overview
The Book Management API is part of a simulated cloud-based SaaS platform for digital publishing. 
It allows authenticated users (e.g., authors, publishers, readers) to manage book entries in a digital catalog. 
The RESTful API supports full CRUD operations and is designed for seamless integration into third-party applications 
or client dashboards. Documentation follows the OpenAPI specification.

## Features
- Add new books to the platform  
- Retrieve a list of all books  
- Fetch details of a specific book by ID  
- Update book information  
- Delete a book entry  
- Designed for multi-tenant SaaS environments  

## Authentication
The API uses API key authentication. Clients must include a valid API key in the header of each request:

```
Authorization: Bearer YOUR_API_KEY
```

## Base URL
```
https://api.cloudbookmanager.com/v1
```

## API Endpoints
| Method | Endpoint         | Description                |
|--------|------------------|----------------------------|
| GET    | /books           | Retrieve all books         |
| GET    | /books/{id}      | Retrieve a book by ID      |
| POST   | /books           | Add a new book             |
| PUT    | /books/{id}      | Update a book              |
| DELETE | /books/{id}      | Delete a book              |

## Sample Request (Add a Book)
```
POST /books
Content-Type: application/json
Authorization: Bearer YOUR_API_KEY

{
  "title": "The Great Gatsby",
  "author": "F. Scott Fitzgerald",
  "year": 1925
}
```

## Sample Response
```
HTTP/1.1 201 Created
Content-Type: application/json

{
  "id": 1,
  "title": "The Great Gatsby",
  "author": "F. Scott Fitzgerald",
  "year": 1925
}
```

## Error Handling
The API returns standard HTTP status codes:
- 200 OK: Request succeeded  
- 201 Created: Resource successfully created  
- 400 Bad Request: Invalid input  
- 401 Unauthorized: Missing or invalid API key  
- 404 Not Found: Book ID does not exist  
