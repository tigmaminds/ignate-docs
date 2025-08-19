# Join Node Function

The **Join Node Function** is used to **combine data from multiple sources** by matching records based on specified conditions. This function is essential for data integration, allowing you to merge datasets from different sources into a unified view.

---

## Purpose

This function is helpful when:

- You need to combine data from multiple input sources (CSV, databases, APIs, etc.)
- You want to create relationships between different datasets based on common fields
- You need to perform complex data integration operations
- You want to enrich one dataset with information from another

---

## How It Works

The function takes:

- **Multiple Source Selection**: Choose from available input sources (minimum 2 sources required)
- **Join Configuration**: Define how tables should be joined together
- **Join Types**: Select the type of join operation to perform
- **Join Conditions**: Specify the matching criteria between tables
- **Column Selection**: Choose which columns to include in the output
- **Duplicate Handling**: Option to remove duplicate keys across sources

### Join Types Available:

1. **INNER**: Returns only records that have matching values in both tables
2. **LEFT OUTER**: Returns all records from the left table and matching records from the right table
3. **RIGHT OUTER**: Returns all records from the right table and matching records from the left table
4. **FULL OUTER**: Returns all records from both tables, with NULLs for non-matching records
5. **LEFT SEMI**: Returns records from the left table that have matches in the right table
6. **LEFT ANTI**: Returns records from the left table that do NOT have matches in the right table

### Example:

To join two tables `employees` and `departments` on the `dept_id` field using an INNER join:

```json
{
  "selectedSource": ["employees", "departments"],
  "joinQuery": {
    "from": "employees",
    "joins": [
      {
        "type": "INNER",
        "table": "departments",
        "on": "employees.dept_id=departments.dept_id"
      }
    ],
    "select": ["employees.emp_id", "employees.name", "departments.dept_name"],
    "condition": ""
  },
  "removeDuplicateKeys": true
}
```

### Result:

Given the original datasets:

**Employees Table:**
| emp_id | name    | dept_id |
|--------|---------|---------|
| 1      | Alice   | 101     |
| 2      | Bob     | 102     |

**Departments Table:**
| dept_id | dept_name |
|---------|-----------|
| 101     | HR        |
| 102     | IT        |

The result after applying the INNER join would be:

| emp_id | name  | dept_id | dept_name |
|--------|-------|---------|-----------|
| 1      | Alice | 101     | HR        |
| 2      | Bob   | 102     | IT        |

---

## Key Features

### Source Management
- **Multi-source Selection**: Connect and combine data from multiple input sources
- **Dynamic Schema Detection**: Automatically detects and displays available columns from each source
- **Source Mapping**: Creates normalized table names for consistent referencing

### Join Configuration
- **Flexible Join Types**: Support for all standard SQL join operations
- **Condition Builder**: Specify join conditions using table.column syntax
- **Multiple Joins**: Chain multiple join operations in sequence
- **Where Clause**: Additional filtering conditions after joins

### Data Handling
- **Duplicate Key Removal**: Option to automatically remove duplicate column names across sources
- **Column Prefixing**: Source tables are prefixed to column names for clarity
- **Schema Validation**: Ensures proper join configuration before execution

---

## Use Cases

- **Customer Data Integration**: Combine customer information from CRM, website analytics, and support systems
- **Financial Reporting**: Merge transaction data from multiple bank accounts or payment systems
- **E-commerce Analytics**: Join product catalog with sales data and customer behavior
- **Data Warehousing**: Consolidate data from multiple operational systems
- **Master Data Management**: Create unified views of entities across different systems

---

## Configuration Options

### Required Settings:
- **Selected Sources**: Minimum 2 data sources must be selected
- **From Table**: Primary table to start the join operation
- **Join Operations**: At least one join must be configured with type, table, and condition

### Optional Settings:
- **Remove Duplicate Keys**: Automatically handle column name conflicts
- **Where Conditions**: Additional filtering after joins
- **Column Selection**: Choose specific columns for output

---

## Summary

- The **Join Node** combines data from multiple sources using SQL-like join operations
- Supports all standard join types (INNER, LEFT, RIGHT, FULL, SEMI, ANTI)
- Provides flexible condition building and duplicate key handling
- Essential for data integration and creating unified views from multiple datasets
- Requires proper configuration of join types, tables, and matching conditions

---

## Best Practices

1. **Start with INNER joins** for initial data exploration
2. **Use meaningful join conditions** that reflect actual business relationships
3. **Handle duplicate keys** to avoid column name conflicts
4. **Test with small datasets** before applying to large volumes
5. **Validate join results** to ensure data integrity
