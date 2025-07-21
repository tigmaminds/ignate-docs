# TypeConversion Node

## Purpose
The **TypeConversion** Node allows Spark pipelines to transform data types of columns within datasets. It's used to ensure data consistency, prepare data for downstream processing, and convert between different data formats.

---

## How It Works

**Input:** Dataset with columns of various data types

**Configuration:**
- **Column Selection:** Choose which columns to convert
- **Target Type:** Select the desired output type (e.g., `string`, `integer`, `float`, `boolean`, `date`, `array`, etc.)
- **Conversion Options:** Additional parameters for specific conversions (e.g., date format, array delimiter)

**Execution:**
- Processes each row in the dataset
- Applies type conversion rules to selected columns
- Outputs dataset with converted column types

---

## Example

**Scenario:** Convert user data types for analysis

**Input Dataset:**  
Apply to `JsonTransform`...

**Type Conversions:**
- `user_id`: String → Integer  
- `age`: String → Integer  
- `is_active`: String → Boolean  
- `join_date`: String → Date

**Output Dataset:**
```json
[
  { "user_id": 123, "age": 25, "is_active": true, "join_date": "2023-01-15T00:00:00Z" },
  { "user_id": 456, "age": 30, "is_active": false, "join_date": "2023-02-20T00:00:00Z" }
]
```

---

## Use Cases
- **Data Cleaning:** Converting string numbers to numeric types for calculations
- **API Integration:** Standardizing data types before sending to external APIs
- **Database Operations:** Ensuring proper data types for database storage
- **Analytics Preparation:** Converting data types for statistical analysis
- **Schema Validation:** Enforcing consistent data types across datasets
- **Date Processing:** Converting string dates to proper date objects for time-based analysis

---

## Summary

| Feature             | Description                                                              |
|---------------------|--------------------------------------------------------------------------|
| Supported Types      | String, Integer, Float, Boolean, Date, Array                            |
| Conversion Methods   | Direct casting, parsing, formatting                                     |
| Column Selection     | Multiple columns can be converted simultaneously                        |
| Error Handling       | Invalid conversions are flagged with errors                             |
| Output               | Dataset with converted column types                                     |

> ✅ **Best used when standardizing data types and preparing datasets for downstream processing or analysis.**
