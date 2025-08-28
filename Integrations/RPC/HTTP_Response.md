# HttpResponse Node

## Purpose

The **HttpResponse** Node captures and processes HTTP response data from upstream API calls. It's designed to extract, transform, and structure response data for downstream processing in data pipelines.

---

## How It Works

**Input:**  
Receives HTTP response data from upstream nodes.

**Configuration:**
- **Response Processing:** Automatically captures response status, headers, body, and timing.
- **Data Extraction:** Parses JSON, XML, or text responses into structured data.
- **Error Handling:** Captures and formats error responses for debugging.

**Execution:**
- Processes the HTTP response from the upstream node.
- Extracts response metadata (status code, headers, timing).
- Parses response body into structured format.
- Outputs both response data and metadata for downstream use.

---

## Example

**Scenario:** Process user API response data

**Input:**

{
"statusCode": 200,
"response": {
"users": [
{ "id": 1, "name": "Alice", "email": "alice@example.com" },
{ "id": 2, "name": "Bob", "email": "bob@example.com" }
]
},
"responseHeaders": {
"Content-Type": "application/json"
},
"processTime": "150ms"
}


**Output Dataset:**
[
{ "id": 1, "name": "Alice", "email": "alice@example.com" },
{ "id": 2, "name": "Bob", "email": "bob@example.com" }
]


**Additional Metadata (available for downstream nodes):**
- **Status Code:** 200
- **Process Time:** 150ms
- **Response Headers:** Content-Type, etc.

---

## Use Cases

- **API Response Processing:** Extract and structure data from REST API responses.
- **Data Validation:** Check response status codes and handle errors gracefully.
- **Performance Monitoring:** Track API response times and performance metrics.
- **Error Handling:** Capture and format error responses for logging or alerting.
- **Data Transformation:** Convert API responses into the required format for downstream processing.
- **Response Filtering:** Extract specific fields or filter response data based on conditions.

---

| Feature               | Description                                              |
| --------------------- | -------------------------------------------------------- |
| Response Processing   | Automatically handles HTTP responses                     |
| Status Code Tracking  | Captures and validates response status codes             |
| Performance Metrics   | Tracks response time and processing duration             |
| Error Handling        | Formats error responses for debugging                    |
| Data Extraction       | Parses JSON, XML, or text responses                      |
| Metadata Output       | Provides response headers and timing info                |

✅ Best used when processing and validating HTTP responses from API calls, ensuring data quality and handling errors in data pipelines.

