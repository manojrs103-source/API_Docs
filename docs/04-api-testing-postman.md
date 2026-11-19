# API Testing Using Postman

## 1. Purpose

Postman can be used to send API requests and inspect responses. A Technical Writer may use it to validate documentation examples in an authorized test environment.

Testing must use an approved test URL, test account, and sanitized test data supplied by the API team.

> The hostname and API paths in this portfolio are illustrative. They will not work unless an API implementation is deployed at an approved host.

## 2. Prerequisites

Obtain from the developer or API owner:

- Approved test base URL.
- Test credentials or token, shared through a secure channel.
- A valid sample vehicle ID.
- Expected test data and response behavior.
- Permission to access the test environment.

Do not store actual credentials in this repository or in exported Postman collections.

## 3. Create a request

1. Open Postman.
2. Create a new HTTP request.
3. Select the GET method.
4. Enter the approved request URL.
5. Configure authorization as instructed by the API owner.
6. Add required headers.
7. Click Send.
8. Inspect the status code, headers, and response body.

## 4. Example: Retrieve all vehicles

Method:

```http
GET
```

Example URL:

```text
https://dev-api.example.com/api/v1/vehicles
```

Example headers:

| Header | Example value | Purpose |
|---|---|---|
| Authorization | Bearer <TEST_TOKEN> | Supplies the access token |
| Accept | application/json | Requests a JSON response |

The placeholder `<TEST_TOKEN>` is not a real credential. Use a secure Postman variable for an approved test token.

## 5. Example successful response

The following is sample data for documentation practice, not a verified live response.

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

## 6. What the Technical Writer validates

- Does the request use the correct method and path?
- Are required headers present?
- Does the API return the expected status code?
- Does the response match the documented schema?
- Are field names and data types correct?
- Are null, empty, and optional values handled as documented?
- Are error responses represented accurately?
- Do examples contain only sanitized data?

## 7. Record test results

| Test | Expected result | Actual result | Status |
|---|---|---|---|
| Valid request | Success response | To be tested | Not run |
| Missing token | Authentication error | To be tested | Not run |
| Invalid vehicle ID | Not-found response, if defined by contract | To be tested | Not run |
| Unsupported parameter | Validation behavior from contract | To be tested | Not run |

Do not mark a test as passed until it has been executed against the approved environment.

## 8. Troubleshooting

If a request fails, check:

1. The base URL and path.
2. The selected HTTP method.
3. The token and its permissions.
4. Required headers and parameter values.
5. Network access to the test environment.
6. The API service status.

Ask the developer to investigate server-side failures. Do not infer undocumented behavior from a single failed request.
