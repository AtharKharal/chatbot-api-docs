# Error Codes

The ChatBot.com API uses standard HTTP status codes to indicate success or failure. In addition, structured error responses provide more granular diagnostic information.

## Error Format

All error responses are returned in the following JSON format:

```json
{
  "error": {
    "code": "string",
    "message": "string",
    "status": "integer",
    "details": {
      "field": "string",
      "reason": "string"
    }
  }
}
```

| Field      | Type     | Description                                              |
|------------|----------|----------------------------------------------------------|
| `code`     | string   | Machine-readable error identifier                        |
| `message`  | string   | Human-readable explanation                               |
| `status`   | integer  | HTTP status code                                         |
| `details`  | object   | Additional context, often related to input validation    |

## Common Error Codes

| HTTP Code | Error Code           | Meaning                                                        |
|-----------|----------------------|----------------------------------------------------------------|
| 400       | `invalid_request`     | Malformed or missing parameters                                |
| 401       | `unauthorized`        | Authentication token missing or invalid                        |
| 403       | `forbidden`           | Authenticated but not permitted to access the resource         |
| 404       | `not_found`           | Requested resource does not exist                              |
| 409       | `conflict`            | Resource conflict, e.g. duplicate entries                      |
| 422       | `unprocessable_entity`| Semantically invalid input (e.g., incorrect data format)       |
| 429       | `rate_limited`        | Exceeded API rate limit                                        |
| 500       | `internal_error`      | Unexpected server-side error                                   |
| 503       | `service_unavailable` | API temporarily unavailable due to maintenance or overload     |

## Example: Unauthorized Request

```http
GET /archives HTTP/1.1
Host: api.chatbot.com
Authorization: Bearer invalid_token
```

**Response**

```json
{
  "error": {
    "code": "unauthorized",
    "message": "Invalid or missing authentication token.",
    "status": 401
  }
}
```

## Best Practices for Error Handling

- **Log the `code`** and `status` for programmatic error handling.
- **Display `message`** to end-users for user-friendly error explanations.
- **Retry on 429/503** with exponential backoff.
- **Fail-fast** on 400/422 unless user correction is possible.

---

For full error schema definitions, consult the [OpenAPI Spec](openapi.md).
