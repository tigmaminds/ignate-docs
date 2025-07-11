# Filter Function

The **Filter Function** is used to refine a dataset by applying two types of filters:

- **Row Filter**
- **Column Filter**

These filters allow users to extract relevant information based on specific criteria or selection preferences.

## 1. Row Filter

The **Row Filter** is responsible for filtering records (rows) from the dataset based on certain input conditions.

### Example:
If the input condition is:
```json
{ "status": "active" }
```
Then only rows where the `status` column has the value `"active"` will be included in the output.

### Use Case:
Useful for narrowing down the data to only include rows that meet specific criteria such as date ranges, statuses, user IDs, etc.

## 2. Column Filter

The **Column Filter** determines which columns should be included in the final output.

### Example:
If the column filter input is:
```json
["name", "email", "status"]
```
Then only these columns will appear in the output data, and all other columns will be excluded.

### Use Case:
This is useful when you want to hide irrelevant or sensitive data and only show the fields required for a particular view or report.

---

## Combined Example

Given the dataset:

| id | name  | email           | status  |
|----|-------|------------------|---------|
| 1  | Alice | alice@mail.com  | active  |
| 2  | Bob   | bob@mail.com    | inactive|

With:
- Row Filter: `{ "status": "active" }`
- Column Filter: `[ "name", "email" ]`

The result would be:

| name  | email          |
|-------|----------------|
| Alice | alice@mail.com |

---

## Summary

- **Row Filter**: Filters rows based on condition values.
- **Column Filter**: Selects specific columns to include in the output.
- These filters can be used independently or together to customize the resulting dataset effectively.
