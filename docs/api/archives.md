# Archives API

Access and manage archived conversations and session metadata. Use this endpoint to retrieve historical chat data, filter by date or user, and audit past interactions for analysis or compliance.

## Endpoint Summary

| Method | Endpoint                | Description                          |
|--------|-------------------------|--------------------------------------|
| GET    | `/v1/archives`          | List archived sessions               |
| GET    | `/v1/archives/{id}`     | Retrieve a specific archived session |

---

## GET /v1/archives

Retrieve a paginated list of archived chat sessions.

### Query Parameters

| Name      | Type     | Required | Description                       |
|-----------|----------|----------|-----------------------------------|
| `user_id` | string   | No       | Filter by specific user ID        |
| `from`    | date     | No       | Start date (ISO 8601)             |
| `to`      | date     | No       | End date (ISO 8601)               |
| `limit`   | integer  | No       | Max number of items (default: 50) |

### Response

````json
{
  "data": [
    {
      "id": "archive_7421",
      "user_id": "user_231",
      "created_at": "2024-10-03T14:23:15Z",
      "messages": 19
    },
    {
      "id": "archive_7422",
      "user_id": "user_772",
      "created_at": "2024-10-04T11:01:00Z",
      "messages": 44
    }
  ]
}
