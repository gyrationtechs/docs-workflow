# API Guide

This guide provides detailed information about the Task Management API endpoints and how to use them effectively.

## Introduction

The API is designed to be simple and easy to use. It provides a RESTful interface for managing tasks and projects. The API can be accessed via HTTP requests and returns JSON responses.

## Endpoints Overview

The API consists of several endpoints that are used for different purposes:

- `/tasks` - Used for task management operations
- `/projects` - Used for project management operations  
- `/users` - Used for user management operations
- `/teams` - Used for team management operations

## Task Endpoints

### Get All Tasks

This endpoint is used to retrieve all tasks. The tasks are returned in a paginated format.

**Endpoint:** `GET /tasks`

**Parameters:**
- `page` (optional): The page number to retrieve
- `limit` (optional): The number of tasks per page
- `status` (optional): Filter tasks by status

**Example Request:**
```bash
curl -X GET "https://api.taskmanager.com/v1/tasks?page=1&limit=10" \
  -H "Authorization: Bearer YOUR_API_KEY"
```

**Example Response:**
```json
{
  "data": [
    {
      "id": "123",
      "title": "Complete documentation",
      "description": "Write API documentation",
      "status": "in_progress",
      "priority": "high",
      "created_at": "2024-01-15T10:30:00Z"
    }
  ],
  "pagination": {
    "page": 1,
    "limit": 10,
    "total": 50
  }
}
```

### Create Task

This endpoint is used to create a new task. The task will be created with the provided information.

**Endpoint:** `POST /tasks`

**Request Body:**
```json
{
  "title": "New task title",
  "description": "Task description",
  "priority": "medium",
  "due_date": "2024-02-15"
}
```

**Example Request:**
```bash
curl -X POST "https://api.taskmanager.com/v1/tasks" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "title": "New task",
    "description": "Task description",
    "priority": "medium"
  }'
```

## Project Endpoints

### Get Projects

This endpoint retrieves all projects. Projects are returned in a list format.

**Endpoint:** `GET /projects`

**Example Request:**
```bash
curl -X GET "https://api.taskmanager.com/v1/projects" \
  -H "Authorization: Bearer YOUR_API_KEY"
```

## Error Codes

The API uses various error codes to indicate different types of errors:

- `400` - Bad Request: The request was malformed
- `401` - Unauthorized: Authentication is required
- `403` - Forbidden: Access is denied
- `404` - Not Found: The resource was not found
- `429` - Too Many Requests: Rate limit exceeded
- `500` - Internal Server Error: Something went wrong on the server

## Best Practices

When using the API, it is recommended to:

1. Always include proper error handling in your code
2. Use pagination when retrieving large datasets
3. Implement retry logic for failed requests
4. Cache responses when appropriate
5. Monitor your API usage to stay within rate limits

## SDK Examples

Here are some examples of how to use the API with different programming languages:

### JavaScript Example
```javascript
const response = await fetch('https://api.taskmanager.com/v1/tasks', {
  method: 'POST',
  headers: {
    'Authorization': 'Bearer YOUR_API_KEY',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    title: 'New task',
    description: 'Task description'
  })
});
```

### Python Example
```python
import requests

response = requests.post(
    'https://api.taskmanager.com/v1/tasks',
    headers={
        'Authorization': 'Bearer YOUR_API_KEY',
        'Content-Type': 'application/json'
    },
    json={
        'title': 'New task',
        'description': 'Task description'
    }
)
```

## Conclusion

This API guide provides the basic information needed to get started with the Task Management API. For more detailed information, please refer to the API reference documentation. 