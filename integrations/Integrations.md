# Integrations

---

## Purpose

Spark provides extensive integration capabilities to connect and work with a variety of data sources, external services, and tools. These integrations allow seamless data ingestion, transformation, export, and real-time interactions with both internal systems and third-party applications.

---

## How It Works

Spark integrates with other systems through:

- **Connectors**: Built-in or third-party connectors for databases, file systems, and message queues.
- **APIs**: REST or custom APIs to send/receive data.
- **Plugins and Nodes**: Specialized Spark nodes like WebAPI, HTTP Request, etc.
- **Authentication**: Secure communication using OAuth2, API tokens, basic auth, etc.

### Supported Integration Types

- **Databases**: MySQL, PostgreSQL, Oracle, SQL Server via JDBC
- **Cloud Storage**: AWS S3, Azure Blob, GCS
- **Messaging Systems**: Apache Kafka, RabbitMQ
- **APIs**: REST APIs via WebAPI or HTTP Request nodes
- **File Formats**: CSV, JSON, Parquet, Avro
- **BI Tools / Reporting**: Export to databases or APIs for Power BI/Tableau

---

## Use Cases

- Ingesting real-time data from Kafka or APIs
- Pushing cleaned data into data warehouses (e.g., Redshift, BigQuery)
- Automating workflows that depend on external systems
- Triggering jobs via webhook on data arrival
- Sending notifications via Slack, Teams, or email

---

## Example

**Scenario**: Integrate with a REST API to fetch product data, enrich it using Spark, and write the result to a PostgreSQL database.

1. **WebAPI Node**: Calls `https://api.example.com/products`
2. **JSON Extractor**: Extracts relevant fields like `productId`, `price`, `availability`
3. **Transformation**: Apply business logic to enrich or filter data
4. **JDBC Output Node**: Writes final results to PostgreSQL table `products_staging`

```json
{
  "productId": "P001",
  "price": 59.99,
  "availability": "In Stock"
}
```

---

## Summary

| Integration Type | Method Used                 | Example Tool or Node |
| ---------------- | --------------------------- | -------------------- |
| Database         | JDBC                        | PostgreSQL, MySQL    |
| Cloud Storage    | Cloud SDK / File Path       | S3, Azure Blob, GCS  |
| APIs             | WebAPI / HTTP Request Nodes | REST Services        |
| Messaging        | Kafka / RabbitMQ Connector  | Apache Kafka         |
| File Systems     | Direct read/write           | CSV, JSON, Parquet   |
| BI Tools         | API or DB export            | Tableau, Power BI    |

---
