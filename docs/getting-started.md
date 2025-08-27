# Getting Started with Task Management API

Welcome to the Task Management API documentation. This guide will help you get started with integrating our API into your applications.

## Overview

The Task Management API provides a comprehensive solution for managing tasks, projects, and team collaboration. Our RESTful API follows industry best practices and provides consistent responses across all endpoints.

## Authentication

All API requests require authentication using API keys. Include your API key in the request header:

```bash
Authorization: Bearer YOUR_API_KEY
```

## Base URL

All API endpoints are relative to the base URL:

```
https://api.taskmanager.com/v1
```

## Rate Limiting

The API implements rate limiting to ensure fair usage:

- **Free tier**: 1,000 requests per hour
- **Pro tier**: 10,000 requests per hour
- **Enterprise tier**: 100,000 requests per hour

Rate limit headers are included in all responses:

- `X-RateLimit-Limit`: Maximum requests per hour
- `X-RateLimit-Remaining`: Remaining requests in the current hour
- `X-RateLimit-Reset`: Time when the rate limit resets (Unix timestamp)

## Error Handling

The API uses standard HTTP status codes and returns detailed error messages in JSON format:

```json
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Invalid request parameters",
    "details": {
      "field": "title",
      "issue": "Title is required"
    }
  }
}
```

## SDKs and Libraries

We provide official sdks for popular programming languages:

- **JavaScript/Node.js**: `npm install @taskmanager/api`
- **Python**: `pip install taskmanager-api`
- **Ruby**: `gem install taskmanager-api`
- **PHP**: `composer require taskmanager/api`

## Quick Start Example

Here's a simple example of creating a task using cURL:

```bash
curl -X POST https://api.taskmanager.com/v1/tasks \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "title": "Complete project documentation",
    "description": "Write comprehensive API documentation",
    "priority": "high",
    "due_date": "2024-02-15"
  }'
```

## Next Steps

- Read the [API Guide](api-guide.md) for detailed endpoint documentation
- Explore our [API Reference](https://docs.taskmanager.com/api) for interactive examples
- Join our [Developer Community](https://community.taskmanager.com) for support and discussions

## Support

If you need help or have questions:

- **Documentation**: [docs.taskmanager.com](https://docs.taskmanager.com)
- **API Status**: [status.taskmanager.com](https://status.taskmanager.com)
- **Support Email**: api-support@taskmanager.com
- **Community Forum**: [community.taskmanager.com](https://community.taskmanager.com) 