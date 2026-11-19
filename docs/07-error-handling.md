# Error Handling

## 1. Purpose

Error documentation helps API consumers understand why a request failed and what they can do next.

Document only errors confirmed by the API owner or observed and verified in an approved test environment.

## 2. Common HTTP status codes

The table below gives general HTTP meanings. It does not assert that every endpoint in this example returns every status.

| Status | General meaning | Typical consumer action |
|---|---|---|
| 400 Bad Request | The request is invalid | Check parameter names, formats, and required values |
| 401 Unauthorized | Authentication is missing or invalid | Obtain or refresh credentials using the approved process |
| 403 Forbidden | The caller lacks permission | Request the required access from the API administrator |
| 404 Not Found | The requested resource does not exist or is unavailable to the caller | Check the identifier and resource access |
| 429 Too Many Requests | The request rate limit was exceeded | Follow the documented retry and backoff guidance |
| 500 Internal Server Error | An unexpected server error occurred | Retry only as permitted and contact support with a correlation ID |

## 3. Example error response

This is an illustrative JSON structure. Confirm the actual response schema with the API owner.

```json
{
  "error": "vehicle_not_found",
  "message": "The requested vehicle was not found.",
  "requestId": "example-request-id"
}
```

## 4. Error reference fields

| Field | Type | Description |
|---|---|---|
| error | string | Machine-readable error identifier |
| message | string | Human-readable explanation |
| requestId | string | Example support reference; include only if the API returns it |

## 5. Documentation requirements

For each documented error, collect:

- HTTP status code.
- Machine-readable error code, if provided.
- Response body and field descriptions.
- Conditions that trigger the error.
- Whether the client can retry.
- Recommended corrective action.
- Any correlation or request ID used by support.

## 6. Retry guidance

Do not invent retry behavior. Ask the API owner:

- Which errors are retryable?
- Should clients use exponential backoff?
- Does the server return a Retry-After header?
- Are requests safe to retry?
- Are there idempotency requirements?

## 7. Writer checklist

- Error codes match the API contract.
- Examples are valid JSON.
- Messages do not expose secrets or internal implementation details.
- Troubleshooting steps are actionable.
- Retry guidance has engineering approval.
