# Union Node

## Purpose

The **Union Node** combines data from **two or more sources vertically** (row-wise). It is primarily used to **append datasets** with similar schemas into a unified structure.

---

## How It Works

The Union Node supports three types of concatenation operations:

### Supported Integration Types

#### 1. **Union (Distinct)**
- Automatically removes duplicate fields based on field names.
- Column **names must match** across sources.
- Ignores the "Remove Duplicates" checkbox (always enabled).
- Useful for ensuring a clean and non-redundant result.

#### 2. **Union All**
- Includes **all fields** from all input sources.
- You may optionally enable **Remove Duplicates**.
  - When enabled, it removes repeated field names.
  - When disabled, all fields (including duplicates) are retained.

#### 3. **Union By Name**
- Matches columns **by name** instead of order.
- Supports different schemas between sources.
- Ignores the "Remove Duplicates" checkbox (not applicable here).
- Best for aligning partially overlapping or misaligned schemas.

---

## Use Cases

- Appending data from multiple ingestion pipelines.
- Merging monthly or partitioned datasets.
- Consolidating outputs from parallel data paths.
- Combining datasets with inconsistent field order (via Union By Name).

---

## Example

### Dataset A

| name | age | id  |
|------|-----|-----|
| Ram  | 23  | 101 |
| Sam  | 24  | 102 |

### Dataset B

| name | age | id  |
|------|-----|-----|
| Ram  | 23  | 101 |
| Tom  | 25  | 103 |

---

### ➕ Union (Distinct)

| name | age | id  |
|------|-----|-----|
| Ram  | 23  | 101 |
| Sam  | 24  | 102 |
| Tom  | 25  | 103 |

---

### ➕ Union All (No deduplication)

| name | age | id  |
|------|-----|-----|
| Ram  | 23  | 101 |
| Sam  | 24  | 102 |
| Ram  | 23  | 101 |
| Tom  | 25  | 103 |

---

### Valid & Invalid Input Example

| Case                                | Valid? | Reason                                  |
| ----------------------------------- | ------ | --------------------------------------- |
| `name, age, id` + `name, age, id`   | ✅     | Same structure                          |
| `name, id, age` + `name, age, id`   | ✅     | Same keys, different order (OK)         |
| `name, age` + `name, age, location` | ❌     | Column mismatch (extra/missing columns) |
| `name, age` + `name, location`      | ✅     | Valid under **Union By Name**           |

---

## Summary

| Feature               | Union (Distinct) | Union All          | Union By Name    |
|----------------------|------------------|--------------------|------------------|
| Removes Duplicates   | ✅ Yes (forced)  | ⚙️ Optional        | ❌ No            |
| Column Order Match   | ❌ Not Required   | ❌ Not Required     | ❌ Not Required  |
| Column Name Match    | ✅ Required       | ✅ Required         | ✅ Required      |
| Flexible Schema      | ❌ No             | ❌ No               | ✅ Yes           |
