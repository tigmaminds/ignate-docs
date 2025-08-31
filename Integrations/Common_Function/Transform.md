# Transform Function

The **Transform Function** is used to modify the values of existing columns in a dataset. It applies a specific transformation logic to one or more columns, allowing users to change the format, structure, or content of the data.

---

## Purpose

This function is useful when:
- You want to clean or standardize data.
- Formatting or converting values is required.
- Derived values are needed based on existing ones.

---

## How It Works

The function takes:
- A **column name** to transform.
- A **transformation rule** or logic to apply to each value in that column.

### Example:

To transform a `"name"` column to uppercase:

```json
{
  "column": "name",
  "transformation": "UPPERCASE"
}
```

### Result:

Given the original dataset:

| id | name  |
|----|-------|
| 1  | Alice |
| 2  | Bob   |

The result after applying the transformation would be:

| id | name  |
|----|-------|
| 1  | ALICE |
| 2  | BOB   |

---

## Common Transformations

- **UPPERCASE**: Convert text to uppercase.
- **LOWERCASE**: Convert text to lowercase.
- **TRIM**: Remove leading and trailing spaces.
- **REPLACE**: Replace a substring with another.
- **FORMAT_DATE**: Convert date formats.
- **CONDITIONAL**: Apply rules based on conditions (e.g., "if value > 0 then 'positive'").

---

## Use Cases

- Standardizing text data (e.g., making all names uppercase).
- Cleaning strings (e.g., removing extra spaces).
- Formatting dates or currency values.
- Categorizing values based on conditions.

---

## Summary

- The **Transform Function** modifies existing column values using specified logic.
- Supports a variety of transformations such as case conversion, trimming, replacing, formatting, and conditional logic.
- Helps prepare data for analysis, visualization, or export.
