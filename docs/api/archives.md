# Archives API

The Archives API lets you retrieve historical chat sessions, including their messages, timestamps, and resolution status.

## Endpoint

```
GET /v1/archives
```

## Query Parameters

| Parameter   | Type   | Description                          |
|-------------|--------|--------------------------------------|
| `start`     | string | ISO 8601 start date (e.g. `2024-01-01`) |
| `end`       | string | ISO 8601 end date                    |
| `user_id`   | string | (Optional) Filter by user            |
| `limit`     | int    | Max records to return (default: 100) |

## Example (Python)

````python
import requests

headers = {
    "Authorization": "Bearer YOUR_API_KEY"
}

r = requests.get(
    "https://api.chatbot.com/v1/archives?start=2024-01-01&end=2024-01-31",
    headers=headers
)

print(r.json())
````

## Sample Response

```json
[
  {
    "session_id": "abc123",
    "start_time": "2024-01-01T09:00:00Z",
    "end_time": "2024-01-01T09:05:12Z",
    "status": "resolved"
  }
]
```

## Error Handling

Typical error responses for this endpoint include:

- `400 Bad Request` (invalid date format)
- `401 Unauthorized` (see [Authentication](../getting-started/authentication.md))
- `403 Forbidden` (insufficient permissions)

See full list in the [Error Codes](../reference/errors.md) section.

## Related

- [Authentication](../getting-started/authentication.md)
- [Entities API](./entities.md)
- [Error Codes](../reference/errors.md)
