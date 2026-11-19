# Vehicle Inventory API – Reference

## 1. Overview

This reference describes three illustrative read operations for a vehicle inventory API.

**Important:** These are example paths and schemas for a learning project. They are not confirmed Tekion endpoints. Confirm all behavior against an actual API contract before using the content in a production integration.

## 2. Base URL

Example development URL:

```text
https://dev-api.example.com
```

The API owner must provide the approved base URL for each environment.

## 3. Authentication

For this example, requests use Bearer token authentication.

Include the token in the HTTP Authorization header:

```http
Authorization: Bearer <ACCESS_TOKEN>
```

Obtain credentials and tokens only through the approved process. Do not put real tokens in source files, documentation examples, or Git commits.

## 4. GET /api/v1/vehicles

**Summary:** Retrieves a list of vehicles.

**Example request**

```http
GET /api/v1/vehicles
Accept: application/json
Authorization: Bearer <ACCESS_TOKEN>
```

**Example cURL**

```bash
curl --request GET \
  --url "https://dev-api.example.com/api/v1/vehicles" \
  --header "Accept: application/json" \
  --header "Authorization: Bearer <ACCESS_TOKEN>"
```

**Example successful response – 200 OK**

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

## 5. GET /api/v1/vehicles/{vehicleId}

**Summary:** Retrieves a vehicle using its unique identifier.

**Path parameter**

| Name | Type | Required | Description |
|---|---|---|---|
| vehicleId | string | Yes | Unique identifier of the vehicle to retrieve |

**Example request**

```http
GET /api/v1/vehicles/10025
```

**Example cURL**

```bash
curl --request GET \
  --url "https://dev-api.example.com/api/v1/vehicles/10025" \
  --header "Accept: application/json" \
  --header "Authorization: Bearer <ACCESS_TOKEN>"
```

**Example successful response – 200 OK**

```json
{
  "vehicleId": "10025",
  "manufacturer": "Toyota",
  "model": "Camry",
  "modelYear": 2025,
  "color": "White",
  "availability": "Available"
}
```

## 6. GET /api/v1/vehicles/search

**Summary:** Searches vehicles using the specified query filters.

**Example query parameters**

| Name | Type | Required in this example | Description |
|---|---|---|---|
| manufacturer | string | No | Filters by manufacturer |
| model | string | No | Filters by model |
| year | integer | No | Filters by model year |
| color | string | No | Filters by exterior color |

The required status, allowed values, case sensitivity, and validation rules must be confirmed by the API owner.

**Example request**

```http
GET /api/v1/vehicles/search?manufacturer=Toyota&model=Camry&year=2025&color=White
```

**Example cURL**

```bash
curl --get \
  --url "https://dev-api.example.com/api/v1/vehicles/search" \
  --header "Accept: application/json" \
  --header "Authorization: Bearer <ACCESS_TOKEN>" \
  --data-urlencode "manufacturer=Toyota" \
  --data-urlencode "model=Camry" \
  --data-urlencode "year=2025" \
  --data-urlencode "color=White"
```

**Example successful response – 200 OK**

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

## 7. Example response fields

| Field | Type | Description |
|---|---|---|
| vehicleId | string | Unique vehicle identifier |
| manufacturer | string | Vehicle manufacturer |
| model | string | Vehicle model |
| modelYear | integer | Vehicle model year |
| color | string | Vehicle exterior color |
| availability | string | Vehicle availability status |

Example availability values shown in this project are Available, Reserved, and Sold. The actual allowed values must be confirmed with the API owner.

## 8. Common HTTP status codes

| Status | General meaning |
|---|---|
| 200 | Request succeeded |
| 400 | Request is invalid |
| 401 | Authentication is missing or invalid |
| 403 | Caller is not permitted to access the resource |
| 404 | Requested resource was not found |
| 429 | Request rate limit was exceeded |
| 500 | Unexpected server error |

The API owner must confirm which status codes each operation actually returns and the error response schema.

## 9. Related documentation

- [Request and response examples](06-request-response-examples.md)
- [Error handling](07-error-handling.md)
- [OpenAPI specification](../openapi/vehicle-inventory.yaml)
