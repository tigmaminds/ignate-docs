# JSON Transformer Node

## Purpose

The **JSON Transformer** Node enables Spark pipelines to create new columns by mapping and restructuring data into custom JSON objects. It is ideal for preparing, nesting, or flattening data before sending it to APIs, databases, or downstream nodes.

---

## How It Works

**Input:**  
Receives tabular data (rows with columns) from upstream nodes.

**Configuration:**
- **JSON Mapping:** Define a JSON structure where values can reference input columns using `[columnName]` syntax.
- **Output Column Name:** Specify the name for the new column that will contain the generated JSON object.
- **Remove Nulls:** Optionally remove fields with null values from the output JSON.

**Execution:**
- For each row, the node generates a JSON object based on the mapping.
- Column references (e.g., `[user_id]`) are replaced with actual values from the input row.
- The resulting JSON object is stored in the specified output column.

---

## Example

**Scenario:** Nest user details and headers into a single JSON column

**Input Dataset:**
[
{ "user_id": 123, "name": "Alice", "originHeaders": { "Authorization": "Bearer xyz" } }
]

**JSON Mapping:**
{
"id": "[user_id]",
"username": "[name]",
"headers": "[originHeaders]"
}


---

## Use Cases

- **API Integration:** Prepare nested JSON payloads for REST API requests.
- **Data Warehousing:** Store complex objects in a single column for semi-structured databases.
- **Data Restructuring:** Flatten or nest data for downstream processing.
- **Event Streaming:** Format messages for Kafka, Pub/Sub, or other event systems.
- **Custom Output:** Generate custom JSON for reporting or export.

---

| Feature            | Description                                           |
| ------------------ | ----------------------------------------------------- |
| Mapping Syntax     | Use \[columnName] to reference input columns          |
| Output Column      | Custom name for the generated JSON object             |
| Null Handling      | Optionally remove fields with null values             |
| Flexible Structure | Supports flat and nested JSON mappings                |
| Error Handling     | Flags errors for missing or invalid column references |
| Output             | Original data plus new JSON column                    |

✅ Best used for creating custom JSON objects from tabular data, especially when integrating with APIs or storing nested data.
