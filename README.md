# API Documentation

This document provides an overview of the endpoints available in the API.

## Folder Structure

```
app/
├── models/
│   ├── Task.js
│   └── User.js
└── routes/
    ├── auth.js
    └── tasks.js
    └── user.js
util/
└── index.js
└── mongoose.js
└── passport.js
```


## Tasks Endpoints

### Get Task by ID

Returns information about a specific task.

#### Endpoint

```http
GET /api/v1/tasks/:id
```

#### Path Parameters

| Parameter | Description            |
| --------- | ---------------------- |
| id        | The ID of the task.    |

#### Request Body JSON Example

```json
{
  "Text": "Example Task",
  "Done": false,
  "Date": "2024-03-20T12:00:00Z"
}
```

#### Response Body JSON Example

```json
{
  "_id": "609e40dbb49e5e0015dbf4f0",
  "UserId": "123456789",
  "Text": "Example Task",
  "Done": false,
  "Date": "2024-03-20T12:00:00Z"
}
```

### Create Task

Creates a new task.

#### Endpoint

```http
POST /api/v1/tasks/
```

#### Request Body JSON Example

```json
{
  "Text": "New Task",
  "Date": "2024-03-21T10:00:00Z"
}
```

#### Response Body JSON Example

```json
{
  "_id": "609e40dbb49e5e0015dbf4f0",
  "UserId": "123456789",
  "Text": "New Task",
  "Done": false,
  "Date": "2024-03-21T10:00:00Z"
}
```

### Update Task

Updates an existing task.

#### Endpoint

```http
PUT /api/v1/tasks/:id
```

#### Path Parameters

| Parameter | Description            |
| --------- | ---------------------- |
| id        | The ID of the task.    |

#### Request Body JSON Example

```json
{
  "Text": "Updated Task",
  "Done": true
}
```

#### Response Body JSON Example

```json
{
  "_id": "609e40dbb49e5e0015dbf4f0",
  "UserId": "123456789",
  "Text": "Updated Task",
  "Done": true,
  "Date": "2024-03-21T10:00:00Z"
}
```

### Delete Task

Deletes an existing task.

#### Endpoint

```http
DELETE /api/v1/tasks/:id
```

#### Path Parameters

| Parameter | Description            |
| --------- | ---------------------- |
| id        | The ID of the task.    |

#### Response Body JSON Example

```json
"Task deleted successfully"
```

## Authentication Endpoints

### Google Authentication

Initiates authentication via Google OAuth 2.0.

#### Endpoint

```http
GET /api/v1/auth/google
```

#### Response

Redirects to Google OAuth consent screen.

### Google Authentication Callback

Handles the callback from Google OAuth 2.0.

#### Endpoint

```http
GET /api/v1/auth/google/callback
```

#### Response

Redirects to the client application.

### Logout

Logs out the user.

#### Endpoint

```http
GET /api/v1/auth/logout
```

#### Response

Redirects to the client application.

## User Endpoints

### Get Current User

Returns information about the authenticated user.

#### Endpoint

```http
GET /api/v1/user
```

#### Response Body JSON Example

```json
{
  "Id": "123456789",
  "Email": "user@example.com",
  "UserName": "user"
}
```
