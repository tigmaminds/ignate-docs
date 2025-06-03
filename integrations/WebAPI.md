# WebAPI

## Purpose

The WebAPI Node allows Spark pipelines to send data to or fetch data from REST APIs. It's typically used for integrating external web services into data workflows.

---

## How It Works

- **Input**: Can be static or dynamic values used in the API call.
- **Configuration**:
  - Method: GET, POST, PUT, DELETE
  - Headers and Authentication: Add headers (e.g., Authorization tokens)
  - Body: JSON or form-data depending on API spec
- **Execution**:

  - Sends HTTP requests to the specified endpoint.
  - Captures response data for downstream processing.

  ***

## Example

**Scenario**: Fetch user details from a REST API

- **Endpoint**: `https://api.example.com/users/123`
- **Method**: `GET`
- **Headers**:
  - `Authorization`: `Bearer <token>`
- **Output** (JSON):

  ```json
  {
    "id": 123,
    "name": "Alice",
    "email": "alice@example.com"
  }

  ---
  ```

## Use Cases

- Fetching reference or master data from external APIs.
- Pushing processed results to downstream systems via REST.
- Calling external ML scoring endpoints (e.g., model inference APIs).
- Real-time data enrichment using third-party APIs.

---

## Summary

| Feature               | Description                               |
| --------------------- | ----------------------------------------- |
| API Methods Supported | GET, POST, PUT, DELETE                    |
| Input Options         | Dynamic parameters, headers, request body |
| Authentication        | Token-based or header-based               |
| Output                | JSON or text response to be parsed        |

---

> ✅ Best used when integrating external services into Spark workflows.
