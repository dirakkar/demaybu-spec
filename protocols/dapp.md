---
description: >-
  The document contains examples, tips, and best practices for explaining the
  operation of decentralized applications and their optimal development.
---

# dApp

## Authentication

Authentication in decentralized applications is accomplished through cryptographic signatures, allowing the avoidance of disclosing critical client data to the server. This method also ensures high data integrity, as users can verify the authenticity of the final data state through cryptographic signatures.

## Lazy execution

Lazy execution is the processing of client requests over a certain period of time. This timeframe, during which requests can be stored or processed, may vary depending on the specific application's needs. Requests stored in the storage can be processed by external services according to their own conditions. The user can utilize these service-executors, in whom they trust to obtain the final state of the data, or in certain cases, determine this state independently.

## Example of architecture

The provided example illustrates the use of smart contracts and the permanent data storage of [Arweave](https://arweave.org) for the creation of decentralized applications.

```mermaid
sequenceDiagram
    actor Client
    participant Node as Arweave Node
    participant Service as Sync Service
    participant Backend
    Client->>Node: Create a new request
    Service->>Node: Get a new requests
    Service->>Backend: Send a new requests
    Client--)Backend: Get the final data state
```
