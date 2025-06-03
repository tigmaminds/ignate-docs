# HTTP Request

## Purpose

The HTTP Request Node is used to make configurable HTTP calls within Spark pipelines. It is ideal for interacting with web services or sending notifications.

---

## How It Works

- **Supports RESTful communication**: Works with GET, POST, PUT, DELETE.
- **Custom Headers**: Add headers like `Content-Type`, `Authorization`.
- **Payload Handling**: Can send plain text or structured JSON.
- **Timeouts and Error Handling**: Configure retries, timeouts, and error propagation.

---

## Use Cases

- Sending alerts (e.g., Slack or webhook notifications).
- Posting processed data to web servers.
- Interacting with external services like APIs or microservices.
- Triggering downstream jobs via webhooks.

---

## Example

**Scenario**: Send a POST request to notify job completion

- **Endpoint**: `https://hooks.example.com/notify`
- **Method**: `POST`
- **Headers**:
  - `Content-Type`: `application/json`
- **Payload**:

  ```json
  {
    "jobId": "load_2025_06_03",
    "status": "success",
    "timestamp": "2025-06-03T09:00:00Z"
  }
  ```

---

## Summary

| Feature              | Description                           |
| -------------------- | ------------------------------------- |
| Methods Supported    | GET, POST, PUT, DELETE                |
| Payload Format       | JSON, text, form-data                 |
| Response Handling    | Returned as string/JSON to downstream |
| Retry/Timeout Config | Yes                                   |

---

> ⚠️ Use with proper error handling to avoid pipeline breaks.
