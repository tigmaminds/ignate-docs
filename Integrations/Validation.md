# Validation Node

The **Validation Node** is used to validate data integrity and format compliance before processing. It ensures that data meets specified criteria and provides detailed error reporting for non-compliant records.

---

## Purpose
This node is useful when:
- You need to validate data quality before business logic processing.
- Format compliance checks are required (e.g., email, UUID, phone numbers).
- Data type validation is needed.
- Custom validation rules must be applied to JSON objects.

---

## Validation Methods
The node supports two validation approaches:

### **Schema Tab**
- **JSON Schema**: Write custom validation rules using JSON Schema syntax
- **Advanced Patterns**: Regular expressions and complex validation logic
- **Custom Error Messages**: Define specific error messages for validation failures
- **Direct JSON Editor**: Write validation schemas directly in the JSON editor

### **Validation Tab**
- **Predefined Operations**: Ready-to-use validation rules like `isJSON`
- **Common Validations**: Email format, phone numbers, required fields, data types
- **User-Friendly**: Simple dropdown selections and configurations
- **JSON Query Support**: Use JSON path queries to extract specific values for validation

---

## How It Works
The node requires:
- A **source column** containing the data to validate (e.g., `finalData`, `payload_user_id`)
- A **validation rule** (predefined operation or custom JSON schema)
- An **output column** name for validation results (e.g., `isValid`, `isValidUserId`)

### Schema Tab Example:
Validate user ID format using JSON Schema:
```json
{
  "type": "string",
  "pattern": "^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$",
  "errorMessage": {
    "type": "User ID must be a string",
    "pattern": "User ID must be a valid UUID format"
  }
}
```

### Validation Tab Example:
Use predefined `isJSON` operation with JSON Query `StripePayload` to validate nested JSON structure.

### Result:
Given this dataset:
| payload_user_id | finalData |
|-----------------|-----------|
| abc-123         | {...}     |
| 550e8400-e29b-41d4-a716-446655440000 | {...} |

The output would be:
| payload_user_id | isValidUserId | validationError |
|-----------------|---------------|-----------------|
| abc-123         | false         | User ID must be a valid UUID format |
| 550e8400-e29b-41d4-a716-446655440000 | true | null |

---

## Use Cases
- Validating API payload formats before processing
- Ensuring data quality in ETL pipelines
- Checking required fields and data types
- Validating business rules and constraints
- Format validation for emails, phone numbers, IDs
- JSON structure validation for complex payloads

---

## Summary
- The **Validation Node** ensures data quality through predefined or custom validation rules
- Supports both simple validations (Validation tab) and complex JSON Schema patterns (Schema tab)
- Provides detailed error reporting for failed validations
- Acts as a quality gate before business logic processing
- Offers flexibility through both UI-driven and code-based validation approaches
