# System / API Error

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `cause` | Top-level network cause container when the API error is transport-level rather than an HTTP response. | Optional object; observed 2 of 27 across 1 shape. | false | false |
| `cause.code` | Transport error code exposed on the top-level cause. | Optional string; observed 2 of 27; max length 10; sample `ECONNRESET`. | true | false |
| `cause.errno` | Numeric transport errno exposed on the top-level cause. | Optional number; observed 2 of 27; sample `0`. | true | false |
| `cause.path` | Transport endpoint associated with the top-level cause. | Optional string; observed 2 of 27; max length 47; sample `https://api.anthropic.com/v1/messages?beta=true`. | true | false |
| `cwd` | Working directory context for the API error event. | Required string; observed 27; max length 38; samples include `/Users/wezzard/Projects/product-driver` and `/Users/wezzard/Projects/rubberdux`. | true | false |
| `entrypoint` | Client entry surface that emitted the API error event. | Required string; observed 27; max length 3; constant sample `cli`. | false | false |
| `error` | Provider or transport error container. | Required object; observed 27 across 4 shapes. | false | false |
| `error.cause` | Nested transport cause container inside the error object. | Optional object; observed 2 of 27 across 1 shape. | false | false |
| `error.cause.code` | Transport error code inside the nested error cause. | Optional string; observed 2 of 27; max length 10; sample `ECONNRESET`. | true | false |
| `error.cause.errno` | Numeric transport errno inside the nested error cause. | Optional number; observed 2 of 27; sample `0`. | true | false |
| `error.cause.path` | Transport endpoint inside the nested error cause. | Optional string; observed 2 of 27; max length 47; sample `https://api.anthropic.com/v1/messages?beta=true`. | true | false |
| `error.connection` | Connection detail emitted on overloaded HTTP errors. | Optional null; observed 16 of 27. | false | false |
| `error.error` | Nested provider error envelope for JSON HTTP failures. | Optional object; observed 1 of 27. | false | false |
| `error.error.error` | Nested provider error payload inside the provider envelope. | Optional object; observed 1 of 27. | false | false |
| `error.error.error.message` | Provider error message inside the nested error payload. | Optional string; observed 1 of 27; max length 34; sample `Invalid authentication credentials`. | true | false |
| `error.error.error.type` | Provider error type inside the nested error payload. | Optional string; observed 1 of 27; max length 20; sample `authentication_error`. | true | false |
| `error.error.request_id` | Provider request identifier inside the nested provider envelope. | Optional string; observed 1 of 27; max length 28; sample `req_011CbFZcMfDC526iMxR9cUX9`. | true | false |
| `error.error.type` | Provider envelope type inside the nested provider error. | Optional string; observed 1 of 27; max length 5; sample `error`. | true | false |
| `error.formatted` | Short formatted HTTP error label. | Optional string; observed 16 of 27; max length 14; sample `529 Overloaded`. | true | false |
| `error.headers` | HTTP response headers container when the failure includes response headers. | Optional object; observed 9 of 27 across 2 shapes. | false | false |
| `error.headers.cf-cache-status` | Cloudflare cache status header on the response. | Optional string; observed 1 of 27; max length 7; sample `DYNAMIC`. | false | false |
| `error.headers.cf-ray` | Cloudflare request trace header on the response. | Optional string; observed 9 of 27; max length 20; samples include `9ff2eb505be42ea5-LAX`. | true | false |
| `error.headers.connection` | HTTP connection header on the response. | Optional string; observed 9 of 27; max length 10; sample `keep-alive`. | false | false |
| `error.headers.content-encoding` | HTTP content encoding header on the response. | Optional string; observed 1 of 27; max length 4; sample `gzip`. | false | false |
| `error.headers.content-length` | HTTP content length header on the response. | Optional string; observed 8 of 27; max length 3; sample `155`. | false | false |
| `error.headers.content-security-policy` | HTTP content security policy header on the response. | Optional string; observed 1 of 27; max length 42; sample `default-src 'none'; frame-ancestors 'none'`. | false | false |
| `error.headers.content-type` | HTTP content type header on the response. | Optional string; observed 9 of 27; max length 16; samples include `text/html` and `application/json`. | true | false |
| `error.headers.date` | HTTP date header on the response. | Optional string; observed 9 of 27; max length 29; samples include `Thu, 21 May 2026 10:32:48 GMT`. | false | false |
| `error.headers.request-id` | Provider request identifier emitted as an HTTP response header. | Optional string; observed 1 of 27; max length 28; sample `req_011CbFZcMfDC526iMxR9cUX9`. | true | false |
| `error.headers.server` | HTTP server header on the response. | Optional string; observed 9 of 27; max length 10; sample `cloudflare`. | false | false |
| `error.headers.set-cookie` | Cookie header array container on the response. | Optional array; observed 1 of 27; max items 1. | false | false |
| `error.headers.set-cookie[]` | Cookie header value on the response. | Optional string array item; observed 1 of 27; max length 189. | false | false |
| `error.headers.strict-transport-security` | HTTP strict transport security header on the response. | Optional string; observed 1 of 27; max length 44; sample `max-age=31536000; includeSubDomains; preload`. | false | false |
| `error.headers.transfer-encoding` | HTTP transfer encoding header on the response. | Optional string; observed 1 of 27; max length 7; sample `chunked`. | false | false |
| `error.headers.vary` | HTTP vary header on the response. | Optional string; observed 1 of 27; max length 15; sample `Accept-Encoding`. | false | false |
| `error.headers.x-robots-tag` | HTTP robots header on the response. | Optional string; observed 1 of 27; max length 4; sample `none`. | false | false |
| `error.headers.x-should-retry` | Provider retry guidance header on the response. | Optional string; observed 1 of 27; max length 5; sample `false`. | true | false |
| `error.isNetworkDown` | Network-down flag emitted with overloaded HTTP errors. | Optional bool; observed 16 of 27; constant sample `false`. | true | false |
| `error.message` | Full provider error message string for overloaded HTTP errors. | Optional string; observed 16 of 27; max length 123; samples start with `529 {"type":"error","error":{"type":"overloaded_error"...`. | true | false |
| `error.rateLimits` | Rate-limit detail emitted with overloaded HTTP errors. | Optional null; observed 16 of 27. | false | false |
| `error.requestID` | Provider request identifier using the `requestID` spelling. | Optional null or string; observed 9 of 27; 8 null values and 1 request id string. | true | false |
| `error.requestId` | Provider request identifier using the `requestId` spelling. | Optional string; observed 16 of 27; max length 28; samples use the `req_...` form. | true | false |
| `error.status` | HTTP status code for provider response failures. | Optional number; observed 25 of 27; samples include `529`, `502`, and `401`. | true | true |
| `error.type` | Provider error type when available on the error object. | Optional null or string; observed 11 of 27; 10 null values and sample `authentication_error`. | true | false |
| `gitBranch` | Repository branch context for the API error event. | Required string; observed 27; max length 4; constant sample `main`. | true | false |
| `isSidechain` | Raw transcript sidechain routing flag. | Required bool; observed 27; constant sample `false`. | false | false |
| `level` | System log severity for the API error event. | Required string; observed 27; max length 5; constant sample `error`. | true | false |
| `maxRetries` | Maximum retry count configured for the API request. | Required number; observed 27; constant sample `10`. | true | false |
| `parentUuid` | Parent transcript record identifier. | Required string; observed 27; max length 36. | false | false |
| `retryAttempt` | Current retry attempt for the API request. | Required number; observed 27; samples include `1` through `10`. | true | false |
| `retryInMs` | Delay before the next API retry. | Required number; observed 27; samples include `618.7743497699599` and `37234.60544936182`. | true | false |
| `sessionId` | Transcript session identifier. | Required string; observed 27; max length 36. | false | false |
| `slug` | Optional scan or session slug metadata. | Optional string; observed 11 of 27; max length 44. | false | false |
| `subtype` | Raw subtype discriminator for routing. | Required string; observed 27; max length 9; constant `api_error`. | false | false |
| `timestamp` | Event time for sorting and display in navigation and card chrome. | Required string; observed 27; max length 24. | false | false |
| `type` | Raw type discriminator for routing. | Required string; observed 27; max length 6; constant `system`. | false | false |
| `userType` | Raw transcript user category metadata. | Required string; observed 27; max length 8; constant `external`. | false | false |
| `uuid` | Transcript record identifier. | Required string; observed 27; max length 36. | false | false |
| `version` | Producer version metadata. | Required string; observed 27; max length 7; samples include `2.1.146`, `2.1.148`, and `2.1.177`. | false | false |

## Derived Car Form Content

| Field | Contents |
| --- | --- |
| Cause Code | `{cause.code}` |
| Cause Errno | `{cause.errno}` |
| Cause Path | `{cause.path}` |
| Working Directory | `{cwd}` |
| Error Cause Code | `{error.cause.code}` |
| Error Cause Errno | `{error.cause.errno}` |
| Error Cause Path | `{error.cause.path}` |
| Nested Error Message | `{error.error.error.message}` |
| Nested Error Type | `{error.error.error.type}` |
| Nested Request ID | `{error.error.request_id}` |
| Nested Envelope Type | `{error.error.type}` |
| Formatted Error | `{error.formatted}` |
| CF-Ray | `{error.headers.cf-ray}` |
| Content Type | `{error.headers.content-type}` |
| Header Request ID | `{error.headers.request-id}` |
| Should Retry | `{error.headers.x-should-retry}` |
| Network Down | `{error.isNetworkDown}` |
| Error Message | `{error.message}` |
| Request ID | `{error.requestID}` |
| Request Id | `{error.requestId}` |
| Status | `{error.status}` |
| Error Type | `{error.type}` |
| Git Branch | `{gitBranch}` |
| Level | `{level}` |
| Max Retries | `{maxRetries}` |
| Retry Attempt | `{retryAttempt}` |
| Retry In Ms | `{retryInMs}` |

## Message Navigation Item Design

Use `System / API Error` as the two-level category. Line 1 keeps the category and subtype on the left and the formatted event time on the right. Line 2 uses the status-first summary, then falls back to transport cause fields when `error.status` is absent.

```text
System / API Error .................................................... {time}
{error.status or cause.code or error.cause.code} | {error.formatted or error.type or error.error.error.message or error.message} | retry {retryAttempt}/{maxRetries}
```

## Message Card Design

Render the card with the system-slate tone and full first-level and second-level badges. The content form starts with the provider or transport failure, follows with retry fields, and keeps response headers in a grouped table. The `error.headers.set-cookie[]` array is displayed as a nested table when present.

```text
+------------------------------------------------------------------------------------------------+
| Title Bar                                                                                      |
| o  [System] [API Error]  {time}  agent/path                                  [Raw] [Copy JSON] |
+------------------------------------------------------------------------------------------------+
| Content Form                                                                                   |
|                                                                                                |
| API Error                                                                                      |
| +----------------------+-------------------------------------------------------------------+   |
| | Level                | {level}                                                           |   |
| | Status               | {error.status}                                                    |   |
| | Formatted Error      | {error.formatted}                                                 |   |
| | Error Type           | {error.type}                                                      |   |
| | Error Message        | {error.message}                                                   |   |
| | Request Id           | {error.requestId}                                                 |   |
| | Request ID           | {error.requestID}                                                 |   |
| +----------------------+-------------------------------------------------------------------+   |
|                                                                                                |
| Nested Provider Error                                                                          |
| +----------------------+-------------------------------------------------------------------+   |
| | Nested Error Type    | {error.error.error.type}                                          |   |
| | Nested Error Message | {error.error.error.message}                                       |   |
| | Nested Request ID    | {error.error.request_id}                                          |   |
| | Nested Envelope Type | {error.error.type}                                                |   |
| +----------------------+-------------------------------------------------------------------+   |
|                                                                                                |
| Transport Cause                                                                                |
| +----------------------+-------------------------------------------------------------------+   |
| | Cause Code           | {cause.code}                                                      |   |
| | Cause Errno          | {cause.errno}                                                     |   |
| | Cause Path           | {cause.path}                                                      |   |
| | Error Cause Code     | {error.cause.code}                                                |   |
| | Error Cause Errno    | {error.cause.errno}                                               |   |
| | Error Cause Path     | {error.cause.path}                                                |   |
| | Network Down         | {error.isNetworkDown}                                             |   |
| +----------------------+-------------------------------------------------------------------+   |
|                                                                                                |
| Retry                                                                                          |
| +----------------------+-------------------------------------------------------------------+   |
| | Retry Attempt        | {retryAttempt}                                                    |   |
| | Max Retries          | {maxRetries}                                                      |   |
| | Retry In Ms          | {retryInMs}                                                       |   |
| | Should Retry         | {error.headers.x-should-retry}                                    |   |
| +----------------------+-------------------------------------------------------------------+   |
|                                                                                                |
| Response Headers                                                                               |
| +------------------------------+------------------------------------------------------------+        |
| | CF-Ray                       | {error.headers.cf-ray}                                    |        |
| | Content Type                 | {error.headers.content-type}                              |        |
| | Header Request ID            | {error.headers.request-id}                                |        |
| | Cache Status                 | {error.headers.cf-cache-status}                           |        |
| | Connection                   | {error.headers.connection}                                |        |
| | Content Encoding             | {error.headers.content-encoding}                          |        |
| | Content Length               | {error.headers.content-length}                            |        |
| | Content Security Policy      | {error.headers.content-security-policy}                   |        |
| | Date                         | {error.headers.date}                                      |        |
| | Server                       | {error.headers.server}                                    |        |
| | Strict Transport Security    | {error.headers.strict-transport-security}                 |        |
| | Transfer Encoding            | {error.headers.transfer-encoding}                         |        |
| | Vary                         | {error.headers.vary}                                      |        |
| | X-Robots-Tag                 | {error.headers.x-robots-tag}                              |        |
| | Set-Cookie                   | +----+---------------------------------------------------+ |        |
| |                              | | #  | {error.headers.set-cookie[]}                    | |        |
| |                              | +----+---------------------------------------------------+ |        |
| +------------------------------+------------------------------------------------------------+        |
|                                                                                                |
| Workspace Context                                                                              |
| +----------------------+-------------------------------------------------------------------+   |
| | Working Directory    | {cwd}                                                             |   |
| | Git Branch           | {gitBranch}                                                       |   |
| +----------------------+-------------------------------------------------------------------+   |
+------------------------------------------------------------------------------------------------+
```
