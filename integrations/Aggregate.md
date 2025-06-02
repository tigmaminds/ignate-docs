# Aggregate Function

The **Aggregate Function** is used to perform calculations across a set of values and return a single summarized result for each group or for the entire dataset. It helps in summarizing data for reporting, analysis, or validation.

---

## Purpose

This function is useful when:
- You want to get a summary of the data.
- Calculations like totals, averages, or counts are needed.
- Group-wise analysis or aggregation is required.

---

## Supported Aggregations

The function can support various aggregation types such as:

- **COUNT**: Counts the number of records.
- **SUM**: Adds up the values of a numeric column.
- **AVG**: Computes the average of a numeric column.
- **MIN**: Finds the minimum value.
- **MAX**: Finds the maximum value.

---

## How It Works

The function requires:
- A **target column** to perform the aggregation on (except for `COUNT`, which can work on all records).
- An optional **group by** column to perform the aggregation within groups.

### Example:
Aggregate data to find the average age per department:

```json
{
  "operation": "AVG",
  "target_column": "age",
  "group_by": "department"
}
```

### Result:

Given this dataset:

| name  | department | age |
|-------|------------|-----|
| Alice | HR         | 30  |
| Bob   | HR         | 40  |
| Carol | IT         | 25  |

The output would be:

| department | avg_age |
|------------|---------|
| HR         | 35.0    |
| IT         | 25.0    |

---

## Use Cases

- Counting records by category.
- Finding the total sales per region.
- Calculating the average rating per product.
- Determining the highest or lowest score in a group.

---

## Summary

- The **Aggregate Function** summarizes data using operations like COUNT, SUM, AVG, MIN, and MAX.
- Can be applied globally or within groups defined by one or more columns.
- Useful for insights, summaries, dashboards, and data validations.
