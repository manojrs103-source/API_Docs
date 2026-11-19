# Vehicle Inventory API Documentation

A practical API documentation portfolio project based on an illustrative automotive dealership inventory workflow.

> **Important:** This is a learning and portfolio example. The endpoints, hostnames, payloads, and behaviors in this repository are illustrative and are not verified Tekion production APIs.

## Scenario

ABC Motors uses an automotive retail application. A dealership employee searches its inventory for a 2025 white Toyota Camry. The application sends a request to an inventory API, the backend retrieves matching records, and the application displays the results.

The dealership employee is the end user. The application calls the API automatically; the employee does not write API requests. Developers build or integrate applications that call the API.

## Documentation workflow

1. Receive a documentation task and understand its scope.
2. Meet with the developer and gather API requirements.
3. Review the API contract (for example, an OpenAPI specification).
4. Test requests and responses in a non-production environment with approved credentials.
5. Write endpoint reference documentation and examples.
6. Ask the developer to review technical accuracy.
7. Publish the approved documentation.
8. Maintain the documentation when the API changes.

## Example endpoints

| Method | Endpoint | Purpose |
|---|---|---|
| GET | `/api/v1/vehicles` | Retrieve vehicles |
| GET | `/api/v1/vehicles/{vehicleId}` | Retrieve one vehicle |
| GET | `/api/v1/vehicles/search` | Search vehicles |

These endpoints are illustrative and must be confirmed against an actual API contract before use.

## Documentation pages

- [API overview](docs/01-api-overview.md)
- [Information gathering](docs/02-information-gathering.md)
- [API specifications](docs/03-api-specifications.md)
- [API testing with Postman](docs/04-api-testing-postman.md)
- [API reference](docs/05-api-reference.md)
- [Request and response examples](docs/06-request-response-examples.md)
- [Error handling](docs/07-error-handling.md)
- [Developer review](docs/08-developer-review.md)
- [Publishing](docs/09-publishing.md)
- [Maintenance](docs/10-maintenance.md)
- [Illustrative OpenAPI file](openapi/vehicle-inventory.yaml)

## Roles

### Developer
Designs and implements the API, defines the contract, tests behavior, and confirms technical details.

### Technical Writer
Gathers information, reviews the contract, tests examples, writes clear documentation, coordinates review, publishes, and maintains content.

## Tools used in this example

- Jira: task tracking
- Confluence: collaboration and internal knowledge sharing
- OpenAPI / Swagger: API contract and reference
- Postman: request and response testing
- Markdown: documentation authoring
- GitHub: version control and publishing workflow

## Accuracy and security notes

- Replace example hostnames with approved environment URLs.
- Never commit real API keys, access tokens, passwords, customer data, or other secrets.
- Use only authorized test credentials and test data.
- Confirm all methods, parameters, response fields, status codes, and error behavior with the API owner.
