# OpenAPI Specification

This API conforms to the [OpenAPI 3.1.0](https://spec.openapis.org/oas/latest.html) specification. The OpenAPI document defines the structure, endpoints, parameters, responses, and data models used by the ChatBot.com API.

## Overview

The full OpenAPI specification for this API is available in JSON and YAML formats:

- [Download OpenAPI (JSON)](../../openapi/chatbot-api.json)
- [Download OpenAPI (YAML)](../../openapi/chatbot-api.yaml)

You can also explore the API interactively using tools like:

- [Swagger UI](https://editor.swagger.io/)
- [ReDoc](https://redocly.github.io/redoc/)

## Versioning

This document reflects **v1.0.0** of the ChatBot.com API. Changes to this specification follow [semantic versioning](https://semver.org/) principles.

- **Major** version: Incompatible API changes
- **Minor** version: Backward-compatible enhancements
- **Patch** version: Backward-compatible bug fixes

## Specification Highlights

- **Base URL:** `https://api.chatbot.com/v1`
- **Authentication:** Bearer token via `Authorization` header
- **Content Type:** All requests and responses use `application/json`
- **Rate Limits:** 1000 requests per minute per authenticated client

## Schema Example

```yaml
openapi: 3.1.0
info:
  title: ChatBot.com API
  version: 1.0.0
  description: API for managing chat archives, users, and entities.
servers:
  - url: https://api.chatbot.com/v1
paths:
  /archives:
    get:
      summary: List chat archives
      responses:
        '200':
          description: List of chat archives
components:
  securitySchemes:
    BearerAuth:
      type: http
      scheme: bearer
      bearerFormat: JWT
security:
  - BearerAuth: []
```

## Tooling Compatibility

This specification is compatible with:

- **Postman** (import as raw JSON or URL)
- **OpenAPI Generator** (generate client SDKs and server stubs)
- **Redoc** (static HTML docs generation)

## Feedback & Contributions

To suggest changes to the OpenAPI spec:

1. Fork the repository.
2. Edit the OpenAPI file in the `openapi/` directory.
3. Open a pull request with rationale.

For technical queries or version pinning issues, contact: `support@chatbot.com`.

