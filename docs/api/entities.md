# Entities API

The Entities API enables CRUD operations on core business objects such as users, agents, bots, and custom data records. Use it to manage and inspect the domain-level entities that participate in conversations.

## Endpoint Summary

| Method | Endpoint              | Description               |
|--------|-----------------------|---------------------------|
| GET    | `/v1/entities`        | List all entities         |
| POST   | `/v1/entities`        | Create a new entity       |
| GET    | `/v1/entities/{id}`   | Retrieve a specific entity |
| PATCH  | `/v1/entities/{id}`   | Update an entity          |
| DELETE | `/v1/entities/{id}`   | Delete an entity          |

---

## GET /v1/entities

Retrieve a list of all registered entities in the system.

### Query Parameters

| Name         | Type     | Required | Description                       |
|--------------|----------|----------|-----------------------------------|
| `type`       | string   | No       | Filter by type (e.g., `user`)     |
| `limit`      | integer  | No       | Items per page (default: 25)      |

### Response

````json
{
  "data": [
    {
      "id": "ent_001",
      "type": "user",
      "name": "Ali",
      "metadata": {
        "email": "ali@example.com",
        "subscription": "pro"
      }
    },
    {
      "id": "ent_002",
      "type": "bot",
      "name": "SupportBot",
      "metadata": {}
    }
  ]
}
