# Information Gathering for the Vehicle Inventory API

## 1. Objective

Before writing API documentation, the Technical Writer must understand the API's purpose, supported operations, requirements, and actual behavior.

The developer and API owner are the primary sources for technical details. Do not infer missing details from sample payloads or invent behavior.

## 2. Preparation

Before the developer meeting:

1. Read the Jira documentation task and acceptance criteria.
2. Review available product requirements and design notes.
3. Identify the intended API audience.
4. Review any existing API contract or implementation notes.
5. Prepare questions and record unresolved items.

## 3. Questions for the developer

| Topic | Question | Information to record |
|---|---|---|
| Purpose | What business problem does this API solve? | API purpose and use cases |
| Audience | Which applications or teams consume it? | Intended API consumers |
| Base URL | What are the approved development, test, and production URLs? | Environment URLs |
| Endpoints | Which operations are available? | Paths and HTTP methods |
| Authentication | How does a client obtain and send credentials? | Authentication flow and headers |
| Authorization | What permissions or scopes are needed? | Required permissions |
| Parameters | Which path, query, and header parameters are accepted? | Names, types, required status, constraints |
| Request body | Does the operation accept a body? | Schema and example |
| Response | What does a successful response contain? | Status, schema, example |
| Errors | Which errors can clients receive? | Status codes, error codes, causes |
| Pagination | Is pagination supported? | Page or cursor behavior |
| Filtering | Which filters and sort options are supported? | Query behavior |
| Limits | Are there rate limits or payload limits? | Limits and response headers |
| Versioning | How are breaking changes managed? | Versioning and deprecation policy |
| Compatibility | Are there SDKs or supported client versions? | Compatibility information |
| Security | Is any returned data restricted or sensitive? | Data-handling requirements |

## 4. Example developer conversation

**Technical Writer:** What does the Vehicle Inventory API allow a consumer application to do?

**Developer:** It allows dealership applications to retrieve and search vehicle inventory.

**Technical Writer:** Which operations are included in this release?

**Developer:** For this example, we have list vehicles, retrieve a vehicle by ID, and search vehicles.

**Technical Writer:** What authentication is required?

**Developer:** The example contract uses a Bearer access token. The real token acquisition flow and required permissions must be supplied by the API owner.

**Technical Writer:** Which fields can be used to search?

**Developer:** The sample search uses manufacturer, model, model year, and color. We need to confirm the accepted values and validation rules.

**Technical Writer:** Can you provide a successful response and representative error responses from the test environment?

**Developer:** Yes. I will provide sanitized examples and the approved status codes.

## 5. Information to request from the developer

Request these artifacts where available:

- OpenAPI specification (YAML or JSON).
- API design or engineering specification.
- Approved base URLs for each environment.
- Authentication and authorization instructions.
- Sanitized request and response examples.
- Error catalog and validation rules.
- Postman collection or equivalent test collection.
- Release notes or change summary.
- API owner and technical reviewer.

## 6. Information-gathering record

| Item | Status | Owner / notes |
|---|---|---|
| API purpose | To be confirmed | Product / API owner |
| Endpoint list | Example supplied | Engineering |
| Base URLs | To be supplied | Engineering |
| Authentication flow | To be supplied | Security / Engineering |
| Parameters and constraints | To be confirmed | API owner |
| Response schemas | To be supplied | Engineering |
| Error catalog | To be supplied | Engineering |
| Rate limits and pagination | To be confirmed | API owner |
| Test credentials | To be provided securely | Engineering |

## 7. Exit criteria

Information gathering is complete when:

- The API scope and audience are clear.
- The endpoint list is confirmed.
- The API contract is available.
- Authentication requirements are understood.
- Request and response schemas are available.
- Error behavior and important constraints are confirmed.
- Open questions have owners and resolution dates.

## 8. Important practice

Never put access tokens, passwords, private keys, customer details, or production data in documentation, screenshots, Postman exports, or GitHub commits. Use approved test credentials and sanitized data.
