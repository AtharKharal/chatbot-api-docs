# Authentication

All requests to the ChatBot.com API must be authenticated using a Bearer token. Unauthorized or improperly authenticated requests will return a `401 Unauthorized` error.

## Base URL

```
https://api.chatbot.com/v1/
```

## Authentication Method

The API uses **Bearer Token Authentication**. You must include your token in the `Authorization` header of each request.

**Header Format:**

```
Authorization: Bearer YOUR_API_TOKEN
```

Tokens can be generated from your [ChatBot.com dashboard](https://app.chatbot.com/settings/api-keys).

---

## Example Usage

### cURL

````bash
curl -X GET https://api.chatbot.com/v1/archives \
  -H "Authorization: Bearer YOUR_API_TOKEN"
````

### Python (requests)

````python
import requests

url = "https://api.chatbot.com/v1/archives"
headers = {
    "Authorization": "Bearer YOUR_API_TOKEN"
}

response = requests.get(url, headers=headers)
print(response.json())
````

### JavaScript (fetch)

````javascript
fetch("https://api.chatbot.com/v1/archives", {
  headers: {
    Authorization: "Bearer YOUR_API_TOKEN"
  }
})
.then(response => response.json())
.then(data => console.log(data));
````

### R (httr)

````r
library(httr)

url <- "https://api.chatbot.com/v1/archives"
res <- GET(url, add_headers(Authorization = "Bearer YOUR_API_TOKEN"))
content(res)
````

---

## Token Management

- **Expiration**: Tokens typically do not expire but can be revoked at any time from the dashboard.
- **Scope**: Each token is associated with the workspace that created it. Tokens cannot access resources outside their originating workspace.
- **Security**: Treat your token like a password. Do not expose it in public repositories or client-side code.

---

## Errors

| HTTP Code | Message             | Description                                      |
|-----------|---------------------|--------------------------------------------------|
| 401       | Unauthorized         | Missing or invalid token                         |
| 403       | Forbidden            | Token lacks necessary permissions                |

---

## Best Practices

- Always use HTTPS to encrypt requests.
- Rotate tokens periodically and remove unused tokens.
- For browser-based applications, use a backend proxy to protect tokens.

---

## Key Rotation

To rotate keys:

1. Generate a new key via the Dashboard.
2. Replace it in your systems.
3. Delete the old key.

## Common Authentication Errors

Refer to the [Error Codes](../reference/errors.md#authentication-errors) page for full explanations of:

- `401 Unauthorized`
- `403 Forbidden`

## Related

- [Entities API](../api/entities.md)
- [Error Codes](../reference/errors.md)

---

## Next Step

Once authenticated, you may proceed to interact with API resources such as:
- [Archives](../api/archives.md)
- [Entities](../api/entities.md)
- [Conversations](../api/conversations.md)
