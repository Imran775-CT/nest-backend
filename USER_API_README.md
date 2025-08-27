# User CRUD API Documentation

This NestJS application provides a complete CRUD (Create, Read, Update, Delete) API for managing users.

## API Endpoints

### Base URL: `http://localhost:3000`

### 1. Create User
**POST** `/users`
```json
{
  "email": "john@example.com",
  "firstName": "John",
  "lastName": "Doe"
}
```

**Response:** 201 Created
```json
{
  "id": 1,
  "email": "john@example.com",
  "firstName": "John",
  "lastName": "Doe",
  "isActive": true,
  "createdAt": "2025-08-27T08:19:28.000Z",
  "updatedAt": "2025-08-27T08:19:28.000Z"
}
```

### 2. Get All Users
**GET** `/users`

**Response:** 200 OK
```json
[
  {
    "id": 1,
    "email": "john@example.com",
    "firstName": "John",
    "lastName": "Doe",
    "isActive": true,
    "createdAt": "2025-08-27T08:19:28.000Z",
    "updatedAt": "2025-08-27T08:19:28.000Z"
  }
]
```

### 3. Get User by ID
**GET** `/users/:id`

**Response:** 200 OK
```json
{
  "id": 1,
  "email": "john@example.com",
  "firstName": "John",
  "lastName": "Doe",
  "isActive": true,
  "createdAt": "2025-08-27T08:19:28.000Z",
  "updatedAt": "2025-08-27T08:19:28.000Z"
}
```

### 4. Update User
**PATCH** `/users/:id`
```json
{
  "firstName": "Jane",
  "lastName": "Smith"
}
```

**Response:** 200 OK
```json
{
  "id": 1,
  "email": "john@example.com",
  "firstName": "Jane",
  "lastName": "Smith",
  "isActive": true,
  "createdAt": "2025-08-27T08:19:28.000Z",
  "updatedAt": "2025-08-27T08:19:28.000Z"
}
```

### 5. Delete User
**DELETE** `/users/:id`

**Response:** 204 No Content

## Validation Rules

- **email**: Must be a valid email format
- **firstName**: Must be a string with minimum 2 characters
- **lastName**: Must be a string with minimum 2 characters

## Error Responses

### 400 Bad Request
When validation fails:
```json
{
  "statusCode": 400,
  "message": ["email must be an email", "firstName should not be empty"],
  "error": "Bad Request"
}
```

### 404 Not Found
When user ID doesn't exist:
```json
{
  "statusCode": 404,
  "message": "User with ID 999 not found",
  "error": "Not Found"
}
```

## Testing the API

You can test these endpoints using:
- Postman
- cURL
- Any HTTP client
- Browser developer tools

## Features

- ✅ Input validation using class-validator
- ✅ Proper HTTP status codes
- ✅ Error handling with meaningful messages
- ✅ In-memory data storage (for development)
- ✅ Automatic timestamp management
- ✅ RESTful API design
- ✅ TypeScript support

## Next Steps

To enhance this API, consider adding:
- Database integration (TypeORM, Prisma, etc.)
- Authentication & Authorization
- Password hashing
- Email verification
- Rate limiting
- Logging
- Unit tests
- E2E tests
