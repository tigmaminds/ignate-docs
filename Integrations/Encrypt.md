# Encrypt Node

The **Encrypt Node** is used to protect sensitive data by applying encryption operations. It ensures that confidential information such as user IDs, payment details, or personal identifiers are securely handled before storage or transmission.

---

## Purpose

This node is useful when:

* Sensitive information must be encrypted before being stored in a database or log.
* Secure exchange of information between systems must be ensured.

---

## Encryption Methods

* **Predefined Algorithms**: Choose from algorithms like AES, RSA, SHA (hashing), or Base64.
* **Key Management**: Configure encryption/decryption keys securely.
* **Modes & Padding**: Select block cipher modes (e.g., CBC, GCM) and padding schemes.
* **Customizable Settings**: Define key length, encoding (hex, base64), and initialization vectors.

---

## How It Works

The node requires:

* A **source column** containing the data to encrypt/decrypt (e.g., `user_id`, `card_number`).
* An **operation type** (Encrypt or Decrypt).
* A **key** or configuration settings (depending on chosen algorithm).
* An **output column** for results (e.g., `encryptedUserId`, ``encryptedCard`).

### Encryption Example:

Encrypt a user ID using AES-256 with Base64 output:
Input:

| user\_id                             | card\_number     |
| ------------------------------------ | ---------------- |
| 550e8400-e29b-41d4-a716-446655440000 | 4111111111111111 |

Output:

| user\_id                             | encryptedUserId         | encryptedCard        |
| ------------------------------------ | ----------------------- | -------------------- |
| 550e8400-e29b-41d4-a716-446655440000 | U2FsdGVkX1+3n92abcxyz== | YWJjMTIzQGVuY3J5cHQ= |

---

## Use Cases

* Encrypting API payloads before sending across services.
* Protecting PII (Personally Identifiable Information) in logs and databases.
* Securely transmitting payment details, tokens, or credentials.
* Ensuring data security compliance in ETL pipelines.

---

## Summary

* The **Encryption Node** safeguards sensitive information through **encryption and decryption** operations.
* Supports **predefined algorithms** (AES, RSA, SHA, Base64) and flexible configuration.
* Provides both **UI-driven setup** (tabs & dropdowns) and advanced custom key management.
* Acts as a **security layer** in workflows by protecting confidential data.
* Ensures compliance with industry security standards and best practices.


