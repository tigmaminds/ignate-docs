# Union

## Purpose

The Union Node is used to combine the results of two or more datasets vertically. It is commonly used when appending similar structured datasets.

---

## How It Works

There are two types of union operations:

1. **Union (Distinct)**:

   - Removes duplicate rows by default.
   - Spark internally applies a `distinct()` operation.
   - This may involve a shuffle and impact performance.

2. **Union All**:
   - Appends all rows from both datasets.
   - **Does not remove duplicates.**

### Rules:

- For both Union and Union All:

  - The **order** and **number of columns** must be **exactly the same**.
  - For example:
    - Dataset 1: `name, age, id`
    - Dataset 2: `name, age, id` ✅ Valid
    - Dataset 2: `name, id, age` ❌ Invalid (column order mismatch)
    - Dataset 2: `name, age, id, location` ❌ Invalid (extra column)

- **Union By Name**:

  - Does not require column order to match.
  - Uses column **names** for alignment.
  - More flexible and tolerant of positional mismatch.

  ***

## Use Cases

- Appending data from different sources with the same schema.
- Merging monthly or daily data into a unified dataset.
- Consolidating partitions after transformation.
- Staging data from multiple ingestion points.

---

## Example

### Dataset 1

| name | age | id  |
| ---- | --- | --- |
| Ram  | 23  | 101 |
| Sam  | 24  | 102 |

### Dataset 2

| name | age | id  |
| ---- | --- | --- |
| Ram  | 23  | 101 |
| Tom  | 25  | 103 |

### Union

Removes duplicate row `(Ram, 23, 101)`:

| name | age | id  |
| ---- | --- | --- |
| Ram  | 23  | 101 |
| Sam  | 24  | 102 |
| Tom  | 25  | 103 |

### Union All

Keeps all rows:

| name | age | id  |
| ---- | --- | --- |
| Ram  | 23  | 101 |
| Sam  | 24  | 102 |
| Ram  | 23  | 101 |
| Tom  | 25  | 103 |

---

## Summary

| Feature               | Union                    | Union All | Union By Name |
| --------------------- | ------------------------ | --------- | ------------- |
| Removes Duplicates    | ✅ Yes                   | ❌ No     | Depends       |
| Column Order Required | ✅ Yes                   | ✅ Yes    | ❌ No         |
| Flexible Matching     | ❌ No                    | ❌ No     | ✅ Yes        |
| Performance           | Slower (due to distinct) | Faster    | Depends       |

---

> ✅ Choose Union All when performance matters and duplicates are acceptable. Use Union By Name for schema mismatch tolerance.
