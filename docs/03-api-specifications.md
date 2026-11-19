# API Specifications

## 1. What is an API specification?

An API specification is a structured description of an API's contract. It defines how a consumer can interact with an API, including paths, methods, parameters, request bodies, responses, and security requirements.

OpenAPI is a widely used format for describing HTTP APIs in YAML or JSON.

## 2. What the Technical Writer receives

The developer may provide:

- An OpenAPI YAML or JSON file.
- An API design document.
- Endpoint details in an engineering ticket.
- A Postman collection.
- Sample requests and responses.

The OpenAPI file is often the most useful starting point because it provides a structured API contract.

## 3. Example endpoint inventory

The following endpoint list is illustrative and must be confirmed by the API owner.

| Method | Path | Purpose |
|---|---|---|
| GET | `/api/v1/vehicles` | Retrieve a list of vehicles |
| GET | `/api/v1/vehicles/{vehicleId}` | Retrieve one vehicle |
| GET | `/api/v1/vehicles/search` | Search vehicles using filters |

## 4. OpenAPI example

The repository includes a starter specification at [vehicle-inventory.yaml](../openapi/vehicle-inventory.yaml).

A shortened example:

```yaml
openapi: 3.0.3
info:
  title: Vehicle Inventory API
  version: 1.0.0
paths:
  /api/v1/vehicles:
    get:
      summary: Retrieve vehicles
      responses:
        '200':
          description: A list of vehicles
```

## 5. How the Technical Writer reviews the specification

Check the following:

| Area | Review question |
|---|---|
| API metadata | Are the title, version, and description accurate? |
| Servers | Are environment URLs approved and correct? |
| Paths | Does every documented endpoint exist in the contract? |
| Methods | Is the HTTP method correct? |
| Parameters | Are names, types, required status, and constraints clear? |
| Security | Is the security scheme described correctly? |
| Request body | Is the schema and content type defined where applicable? |
| Responses | Are success and error responses documented? |
| Examples | Do examples match the schemas? |
| Reuse | Are shared schemas and parameters referenced consistently? |

## 6. Questions and discrepancies

Record discrepancies rather than silently correcting the API contract.

Examples:

- An endpoint appears in the engineering ticket but not in the OpenAPI file.
- A response example contains a field missing from the schema.
- A parameter is marked optional in one place and required in another.
- An error code is mentioned in a support note but not defined in the contract.

Raise these items with the API owner and update documentation only after the behavior is confirmed.

## 7. Validation

Use an OpenAPI editor or validator approved by the team to check YAML/JSON syntax and specification structure. A syntactically valid specification does not, by itself, prove that the running API behaves as described.

## 8. Deliverable

The Technical Writer should have:

- A reviewed API contract.
- A confirmed endpoint inventory.
- A list of unresolved technical questions.
- Accurate details to use in the API reference.
