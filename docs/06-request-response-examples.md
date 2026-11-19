# Request and Response Examples

## 1. Purpose

This page provides sample HTTP requests and JSON responses for the illustrative Vehicle Inventory API.

Examples help API consumers understand how to construct requests and interpret responses.

> All hostnames, identifiers, data, and API behavior on this page are fictional sample content. Validate examples against the real API contract and a test environment before publication for a live product.

## 2. Request components

An HTTP request may include:

- HTTP method: the operation, such as GET.
- URL: the API host and endpoint path.
- Path parameters: values included in the path.
- Query parameters: filters or options included after the question mark.
- Headers: metadata such as authorization and accepted content type.
- Request body: data sent with operations that accept a body.

## 3. Example: retrieve a vehicle

```http
GET /api/v1/vehicles/10025 HTTP/1.1
Host: dev-api.example.com
Accept: application/json
Authorization: Bearer <ACCESS_TOKEN>
```

The `10025` value is the example vehicle identifier.

## 4. Example: search vehicles

```http
GET /api/v1/vehicles/search?manufacturer=Toyota&model=Camry&year=2025&color=White HTTP/1.1
Host: dev-api.example.com
Accept: application/json
Authorization: Bearer <ACCESS_TOKEN>
```

The query parameters represent the requested manufacturer, model, model year, and color.

## 5. Example success response

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

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

## 6. Field reference

| Field | Type | Example | Description |
|---|---|---|---|
| vehicleId | string | 10025 | Unique vehicle identifier |
| manufacturer | string | Toyota | Vehicle manufacturer |
| model | string | Camry | Vehicle model |
| modelYear | integer | 2025 | Vehicle model year |
| color | string | White | Vehicle exterior color |
| availability | string | Available | Vehicle availability status |

## 7. Example error response

The following is an illustrative not-found response. Confirm the exact error format with the API owner.

```http
HTTP/1.1 404 Not Found
Content-Type: application/json
```

```json
{
  "error": "vehicle_not_found",
  "message": "The requested vehicle was not found."
}
```

## 8. Example quality checks

Before publishing a request or response example, verify:

- The URL and HTTP method match the API contract.
- The example includes all required parameters and headers.
- The JSON is syntactically valid.
- Field names, types, and allowed values match the schema.
- The response status matches the example.
- Sensitive values are replaced with safe placeholders.
- The example has been tested or is clearly labeled as illustrative.
