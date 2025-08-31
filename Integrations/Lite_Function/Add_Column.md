# Add Column Function

The **Add Column Function** is used to enhance a dataset by adding a **new column with a single constant value** to every row. This function is useful when you want to tag all records with a static label, flag or default value.

---

## Purpose

This function is helpful when:

- You need to add new column with a default or static field to all entries.
- You want to ensure that a specific field exists in all rows with a predefined value.

---

## How It Works

The function takes:

- A **column name** to be added.
- A **operation** to be executed for the new column in each row. The operations are namely:

  1. **Add New Column**: Adds a new column with custom name and value.
  2. **Timestamp**: Adds a new column with current timestamp as the value for each row.
  3. **Filename**: Adds a new column with filename of the propagated input file as the value.
  4. **RAND**: Adds a new column with RAND as the value.
  5. **UUID**: Adds a new column with UUID as the value.
  6. **SeqNumber**: Adds a new column with sequences (default sequence: 0, 1, 2) as the value.
  7. **META.HEADER**: Adds a new column with META.HEADER from the input entries as the value.
  8. **META.CURRENT_ROW**: Adds a new column META.CURRENT_ROW from the input entries as the value.

- A **value** that will be assigned to every row under that column corresponding to the operation chosen. Custom vilues are also available for some operations.
- A **Datatype** that specifies the datatype of the values that the column accomodates.

### Example:

To add a column `"Eligible"` with operation `"Add New Column"`, value `"true"` and Datatype `"boolean"` to all rows:

```json
{
  "new_column": "Eligible",
  "value": "true",
  "dataType": "boolean"
}
```

### Result:

Given the original dataset:

| id  | name  |
| --- | ----- |
| 1   | Alice |
| 2   | Bob   |

The result after applying the Add Column function would be:

| id  | name  | Eligible |
| --- | ----- | -------- |
| 1   | Alice | true     |
| 2   | Bob   | true     |

---

## Use Cases

- **Marking a Version**: e.g., `"version": "v1.0"`
- **Adding Flags**: e.g., `"reviewed": false`, `"archived": true`

---

## Summary

- The **Add Column** node adds a new column with the same or custom values in every row.
- Useful for tagging, labeling, or assigning default values.
- Simple and consistent way to enrich a dataset with static context.
