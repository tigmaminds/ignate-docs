# JSON Extractor

## Purpose

The JSON Extractor Node is used to parse and extract specific values from JSON content within a dataset. It helps transform nested JSON structures into structured tabular formats.

---

## How It Works

- **Input**: Accepts a JSON string (e.g., from API response or a column).
- **Field Mapping**: Define JSON paths to extract specific fields.
- **Supports Nested Keys**: Easily extract values from deep hierarchies using dot notation (e.g., `data.user.name`).
- **Array Handling**: Can extract from JSON arrays with indexing or iteration logic.

---

## Use Cases

- Parsing API responses or logs stored in JSON format.
- Flattening complex nested JSON structures for analysis.
- Extracting metadata from JSON columns in data lakes.
- Converting JSON logs to structured records.

---

## Example

**Input JSON**:

```json
{
  "user": {
    "id": 123,
    "name": "Alice",
    "contacts": {
      "email": "alice@example.com",
      "phone": "+1234567890"
    }
  }
}
```

---

### Extraction Paths

| JSON Path             | Extracted Value   |
| --------------------- | ----------------- |
| `user.id`             | 123               |
| `user.name`           | Alice             |
| `user.contacts.email` | alice@example.com |

---

### Output Table

| user.id | user.name | user.contacts.email |
| ------- | --------- | ------------------- |
| 123     | Alice     | alice@example.com   |

---

## Summary

| Feature             | Description                      |
| ------------------- | -------------------------------- |
| Input Format        | JSON string                      |
| Field Extraction    | Via JSON path expressions        |
| Nested JSON Support | Yes                              |
| Array Support       | Yes (partial or full extraction) |

---

> ✅ Ideal for cleaning and structuring unstructured JSON data before further transformations.
