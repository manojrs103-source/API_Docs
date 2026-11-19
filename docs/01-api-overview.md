# Vehicle Inventory API – Overview

## 1. Purpose

This project demonstrates how a Technical Writer can plan, gather information for, test, write, review, publish, and maintain API documentation.

The example uses a fictional automotive dealership inventory service. It is intended as a learning and portfolio exercise, not as documentation for a verified Tekion API.

## 2. Business scenario

ABC Motors is a car dealership. A customer visits the showroom and asks for a 2025 white Toyota Camry.

A dealership employee opens the dealership's inventory application and searches for the vehicle. The employee is an end user; they do not write API requests.

Behind the scenes:

1. The employee enters search criteria in the application.
2. The application sends an HTTP request to an inventory API.
3. The API service processes the request and obtains matching inventory records from its data source.
4. The service returns a response, represented here as JSON.
5. The application displays the matching vehicles to the employee.

## 3. What is the API's role?

An API provides a defined way for one software system to request information or functionality from another system.

In this example, the inventory API exposes operations that an authorized application can call to retrieve vehicle inventory data.

## 4. Example API capabilities

| Operation | Example method and path | Purpose |
|---|---|---|
| List vehicles | `GET /api/v1/vehicles` | Retrieve a list of vehicles |
| Get vehicle by ID | `GET /api/v1/vehicles/{vehicleId}` | Retrieve one vehicle |
| Search vehicles | `GET /api/v1/vehicles/search` | Filter inventory using search criteria |

These paths are examples only. An actual API consumer must use the endpoint details published by the API owner.

## 5. Example request flow

An illustrative search request:

```http
GET /api/v1/vehicles/search?manufacturer=Toyota&model=Camry&year=2025&color=White
Accept: application/json
Authorization: Bearer <ACCESS_TOKEN>
```

An illustrative response:

```json
{
  "vehicles": [
    {
      "vehicleId": "10025",
      "manufacturer": "Toyota",
      "model": "Camry",
      "modelYear": 2025,
      "color": "White",
      "availability": "Available"
    }
  ]
}
```

The values and response structure are fictional examples. The real contract, supported filters, and status codes must be confirmed with the API owner.

## 6. Who does what?

### Dealership employee

Uses the dealership application to search inventory, view vehicle details, and support the customer.

### Application

Provides the user interface and sends API requests when the employee performs an action.

### Developer

Designs, builds, tests, and maintains the API or the application integration. The developer confirms the API contract and technical behavior.

### Technical Writer

Works with product and engineering teams to gather accurate information, create developer-focused documentation, validate examples, coordinate technical review, publish content, and maintain it as the API changes.

## 7. Scope of this documentation project

This portfolio project covers:

- API overview and business scenario.
- Information gathering and questions for developers.
- Review of an OpenAPI specification.
- API testing workflow using Postman.
- Endpoint reference documentation.
- Request and response examples.
- Error handling.
- Developer review and approval.
- Publishing workflow.
- Documentation maintenance.

## 8. Important assumptions and limitations

- This is a fictional example created for learning.
- It is not a real Tekion API specification.
- The sample host `dev-api.example.com` is a placeholder and is not expected to resolve.
- Sample vehicle IDs, fields, values, and error responses are illustrative.
- No live API has been deployed or tested as part of this repository.
- Before documenting a real API, confirm all details against its approved contract and test environment.

## 9. Next steps

Continue with:

1. [Information Gathering](02-information-gathering.md)
2. [API Specifications](03-api-specifications.md)
3. [API Testing Using Postman](04-api-testing-postman.md)
4. [API Reference](05-api-reference.md)
