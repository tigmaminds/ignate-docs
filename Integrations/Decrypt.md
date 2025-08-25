# Decrypt Node

The **Decrypt Node** is used to decrypt the encrypted data using the same encryption method. It provides the raw original data from the encrypted data from a database or a transmission.

---

## Purpose

This node is useful when:

* Encrypted data must be converted back to its original readable form for processing or display.
* Securely stored or transmitted information needs to be accessed in original form

---

## Decryption Methods

* **Predefined Algorithms**: Choose from algorithms like AES, DES, JWE, Blowfish, etc
* **Key Management**: Configure encryption/decryption keys securely using vault.
* **Customizable Settings**: Define the key and initialization vectors.

---

## How It Works

The node requires:

* The **decoding algorighm** (AES, DES, etc) to decode the data is known prior.
* A **source column** containing the data to decrypt (e.g., `user_id`, `card_number`).
* The **key** to decode the data.
* The **decoded output** is directly obtained in a new column with decoded adjacent name (e.g., `user_id_decrypted`, ``card_number_decrypted`).

---

### Decryption Example:

Decrypt a user email using AES algorithm:
Input:

| user\_mail                                   | secret\_key                                                      |
| -------------------------------------------- | ---------------------------------------------------------------- |
| S/5/ClrNO144f6EgiZQbw28fBDw0IpnGjMld7RM4tX0= | 3f9a7c5b92d14e7fb82ac1e6452fd239e18a29bfc07c6b31862e70dbb9b4a8d4 |

Output:

| user\_mail                                   | user\_mail\_decrypted                                            |
| -------------------------------------------- | ---------------------------------------------------------------- |
| S/5/ClrNO144f6EgiZQbw28fBDw0IpnGjMld7RM4tX0= |  jane@example.com                                                |

---

## Use Cases:

* Decrypting API payloads received from external or internal services.
* Accessing PII (Personally Identifiable Information) stored in encrypted form for processing or reporting.
* Recovering payment details, tokens, or credentials during secure transactions.

---

## Summary

* The Decryption Node restores encrypted information to its original readable form for secure usage.
* Supports predefined algorithms (AES, DES, JWE etc.) with configurable settings.
* Acts as a trusted access layer in workflows by unlocking confidential data only when required.
