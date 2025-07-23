
# HttpRequest Node

## Purpose
The HttpRequest Node enables Spark pipelines to make HTTP requests to external APIs and web services. It's designed to fetch data from REST endpoints, send data to external services, and integrate with web-based APIs as part of data workflows.

## How It Works

**Input:** Receives data from upstream nodes that can be used as parameters, headers, or request body

**Configuration:**  
- **HTTP Method:** GET, POST, PUT, DELETE, PATCH  
- **URL:** Target endpoint URL (can be dynamic using input data)  
- **Headers:** Custom headers including authentication tokens  
- **Request Body:** JSON, form-data, or raw data payload  
- **Authentication:** Bearer tokens, API keys, or custom auth headers

**Execution:**  
- Constructs HTTP request using configuration and input data  
- Sends request to specified endpoint  
- Captures response data, status codes, and timing information  
- Outputs response data for downstream processing

## Example

**Scenario:** Fetch user data from external API  

**Input Data:**

```
[
  { "user_id": 123, "api_token": "abc123" },
  { "user_id": 456, "api_token": "def456" }
]
```

**Configuration:**  
- **Method:** GET  
- **URL:** https://api.example.com/users/[user_id]  
- **Headers:**  
  - Authorization: Bearer [api_token]  
  - Content-Type: application/json  

**Output (for each user):**

```
[
  {
    "user_id": 123,
    "api_token": "abc123",
    "statusCode": 200,
    "response": { "id": 123, "name": "Alice", "email": "alice@example.com" },
    "processTime": "150ms",
    "error": null
  }
]
```

## Use Cases
- **Data Enrichment:** Fetch additional data from external APIs to enrich existing datasets  
- **Real-time Integration:** Connect to live APIs for real-time data updates  
- **Microservice Communication:** Interact with internal microservices in data pipelines  
- **Third-party API Integration:** Connect to external services (payment gateways, social media APIs, etc.)  
- **Data Synchronization:** Sync data between different systems via REST APIs  
- **API Testing:** Validate API endpoints and response formats in data workflows  

## Summary

| Feature              | Description |
|----------------------|-------------|
| **HTTP Methods**     | GET, POST, PUT, DELETE, PATCH |
| **Dynamic URLs**     | Support for parameterized URLs using input data |
| **Authentication**   | Bearer tokens, API keys, custom headers |
| **Request Body**     | JSON, form-data, raw data support |
| **Error Handling**   | Captures and formats HTTP errors |
| **Performance Tracking** | Measures request/response timing |
| **Response Processing** | Outputs structured response data |

> ✅ **Best used when integrating external APIs and web services into data pipelines, enabling real-time data exchange and system integration.**
