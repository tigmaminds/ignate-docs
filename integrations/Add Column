# Add Column Function

The **Add Column Function** is used to enhance a dataset by adding a **new column with a single constant value** to every row. This function is useful when you want to tag all records with a static label, flag, or default value.

---

## Purpose

This function is helpful when:
- You need to add a default or static field to all entries.
- A constant tag or marker is needed for further filtering or processing.
- You want to ensure a specific field exists in all rows with a predefined value.

---

## How It Works

The function takes:
- A **column name** to be added.
- A **constant value** that will be assigned to every row under that column.

### Example:
To add a column `"source"` with value `"manual"` to all rows:

```json
{
  "new_column": "source",
  "value": "manual"
}
```

### Result:

Given the original dataset:

| id | name  |
|----|-------|
| 1  | Alice |
| 2  | Bob   |

The result after applying the Add Column function would be:

| id | name  | source |
|----|-------|--------|
| 1  | Alice | manual |
| 2  | Bob   | manual |

---

## Use Cases

- **Tagging Source**: e.g., `"source": "imported"`, `"source": "manual"`
- **Marking a Version**: e.g., `"version": "v1.0"`
- **Adding Flags**: e.g., `"reviewed": false`, `"archived": true`

---

## Summary

- The **Add Column Function** adds a new column with the same value in every row.
- Useful for tagging, labeling, or assigning default values.
- Simple and consistent way to enrich a dataset with static context.
