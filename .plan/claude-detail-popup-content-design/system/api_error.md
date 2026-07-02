# Detail Popup Content Design - System / API Error

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Cause | `cause` | Structural container for top-level transport failure details; child fields carry Content values. | Object observed on connection-reset shapes. | false |
| Cause Code | `cause.code` | Shows the top-level transport failure code when the API error is caused by a connection failure. | String; observed value `ECONNRESET`. | true |
| Cause Errno | `cause.errno` | Supports the top-level transport failure code with the numeric errno value. | Number; observed value `0`. | true |
| Cause Path | `cause.path` | Captures the API endpoint trace associated with the top-level transport failure. | String URL; observed Anthropic messages endpoint. | false |
| CWD | `cwd` | Records the working directory for transcript context. | String filesystem paths; observed across all shapes. | false |
| Entrypoint | `entrypoint` | Records the launcher that emitted the message. | String; observed value `cli`. | false |
| Error | `error` | Structural container for API client error details; child fields carry Content values. | Object observed across all shapes. | false |
| Error Cause | `error.cause` | Structural container for nested transport failure details. | Object observed on connection-reset shapes. | false |
| Error Cause Code | `error.cause.code` | Shows the nested transport failure code when the API client wraps the cause under `error`. | String; observed value `ECONNRESET`. | true |
| Error Cause Errno | `error.cause.errno` | Supports the nested transport failure code with the numeric errno value. | Number; observed value `0`. | true |
| Error Cause Path | `error.cause.path` | Captures the API endpoint trace associated with the nested transport failure. | String URL; observed Anthropic messages endpoint. | false |
| Error Connection | `error.connection` | Captures connection payload data when supplied by the API client. | Null in observed messages. | false |
| Error Error | `error.error` | Structural container for a provider error envelope nested under the client error. | Object observed on authentication-error shape. | false |
| Error Error Error | `error.error.error` | Structural container for the provider-supplied nested error body. | Object observed on authentication-error shape. | false |
| Error Error Error Message | `error.error.error.message` | Shows the provider-supplied error message inside a nested API error envelope. | String; observed value `Invalid authentication credentials`. | true |
| Error Error Error Type | `error.error.error.type` | Shows the provider-supplied nested error kind. | String; observed value `authentication_error`. | true |
| Error Error Request ID | `error.error.request_id` | Provides the provider request identifier from the nested error envelope. | String request id. | false |
| Error Error Type | `error.error.type` | Captures the outer nested error envelope type. | String; observed value `error`. | false |
| Error Formatted | `error.formatted` | Shows the compact API error summary produced by the client. | String; observed value `529 Overloaded`. | true |
| Error Headers | `error.headers` | Structural container for HTTP response headers. | Object observed on HTTP response error shapes. | false |
| Error Headers Cf Cache Status | `error.headers.cf-cache-status` | Captures Cloudflare cache header data. | String; observed value `DYNAMIC`. | false |
| Error Headers Cf Ray | `error.headers.cf-ray` | Captures Cloudflare trace header data. | String ray ids. | false |
| Error Headers Connection | `error.headers.connection` | Captures HTTP connection header data. | String; observed value `keep-alive`. | false |
| Error Headers Content Encoding | `error.headers.content-encoding` | Captures HTTP response encoding header data. | String; observed value `gzip`. | false |
| Error Headers Content Length | `error.headers.content-length` | Captures HTTP response length header data. | String; observed value `155`. | false |
| Error Headers Content Security Policy | `error.headers.content-security-policy` | Captures HTTP security policy header data. | String CSP value. | false |
| Error Headers Content Type | `error.headers.content-type` | Captures HTTP response content type header data. | String; observed values include `text/html` and `application/json`. | false |
| Error Headers Date | `error.headers.date` | Captures HTTP response date header data. | String HTTP dates. | false |
| Error Headers Request ID | `error.headers.request-id` | Captures request id header data for provider correlation. | String request id. | false |
| Error Headers Server | `error.headers.server` | Captures server header data. | String; observed value `cloudflare`. | false |
| Error Headers Set Cookie | `error.headers.set-cookie` | Structural array container for cookie header values. | Array; observed max item count `1`. | false |
| Error Headers Set Cookie Items | `error.headers.set-cookie[]` | Captures individual cookie header values. | String cookie header item. | false |
| Error Headers Strict Transport Security | `error.headers.strict-transport-security` | Captures HTTP transport security header data. | String HSTS value. | false |
| Error Headers Transfer Encoding | `error.headers.transfer-encoding` | Captures HTTP transfer encoding header data. | String; observed value `chunked`. | false |
| Error Headers Vary | `error.headers.vary` | Captures HTTP vary header data. | String; observed value `Accept-Encoding`. | false |
| Error Headers X Robots Tag | `error.headers.x-robots-tag` | Captures robots header data. | String; observed value `none`. | false |
| Error Headers X Should Retry | `error.headers.x-should-retry` | Shows provider retry guidance when a response includes it. | String boolean; observed value `false`. | true |
| Error Is Network Down | `error.isNetworkDown` | Shows whether the client classified the failure as a network-down condition. | Boolean; observed value `false`. | true |
| Error Message | `error.message` | Shows the full API error message returned through the client. | String containing status, provider error payload, and request id. | true |
| Error Rate Limits | `error.rateLimits` | Captures rate limit payload data when supplied by the API client. | Null in observed messages. | false |
| Error Request ID | `error.requestID` | Provides the API request identifier from client error payloads using `requestID`. | Null or string request id. | false |
| Error Request ID | `error.requestId` | Provides the API request identifier from client error payloads using `requestId`. | String request ids. | false |
| Error Status | `error.status` | Shows the HTTP or provider status associated with the API failure. | Number; observed values include `401`, `502`, and `529`. | true |
| Error Type | `error.type` | Shows the provider error type when supplied at the client error level. | Null or string; observed value includes `authentication_error`. | true |
| Git Branch | `gitBranch` | Records repository branch context. | String; observed value `main`. | false |
| Is Sidechain | `isSidechain` | Records transcript sidechain routing state. | Boolean; observed value `false`. | false |
| Level | `level` | Records log severity for the system event. | String; observed value `error`. | false |
| Max Retries | `maxRetries` | Shows the retry ceiling applied to the API request. | Number; observed value `10`. | true |
| Parent UUID | `parentUuid` | Links this system event to its parent transcript event. | String UUIDs. | false |
| Retry Attempt | `retryAttempt` | Shows which retry attempt produced this API error event. | Number; observed values include `1` through `10`. | true |
| Retry In Ms | `retryInMs` | Shows the delay before the next retry. | Number milliseconds. | true |
| Session ID | `sessionId` | Links the event to the transcript session. | String UUIDs. | false |
| Slug | `slug` | Records transcript slug routing data. | String slugs. | false |
| Subtype | `subtype` | Supports message routing and titlebar identity. | String; observed value `api_error`. | false |
| Timestamp | `timestamp` | Records event time for transcript ordering. | ISO timestamp strings. | false |
| Type | `type` | Supports message routing and titlebar identity. | String; observed value `system`. | false |
| User Type | `userType` | Records transcript user classification. | String; observed value `external`. | false |
| UUID | `uuid` | Identifies this transcript event. | String UUIDs. | false |
| Version | `version` | Records emitting client version. | String versions; observed values include `2.1.146`, `2.1.148`, and `2.1.177`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Cause Code | `cause.code` | Use the recorded `cause.code` value when present; show `Not provided` when absent. | Render inside the `Cause` group under `Code` as compact code text. |
| Cause Errno | `cause.errno` | Use the recorded `cause.errno` value when present; show `Not provided` when absent. | Render inside the `Cause` group under `Errno` as a numeric scalar. |
| Error Cause Code | `error.cause.code` | Use the recorded `error.cause.code` value when present; show `Not provided` when absent. | Render inside the `Error Cause` group under `Code` as compact code text. |
| Error Cause Errno | `error.cause.errno` | Use the recorded `error.cause.errno` value when present; show `Not provided` when absent. | Render inside the `Error Cause` group under `Errno` as a numeric scalar. |
| Error Error Error Message | `error.error.error.message` | Use the recorded `error.error.error.message` value when present; show `Not provided` when absent. | Render inside the `Error Error Error` group under `Message` as wrapped text. |
| Error Error Error Type | `error.error.error.type` | Use the recorded `error.error.error.type` value when present; show `Not provided` when absent. | Render inside the `Error Error Error` group under `Type` as compact code text. |
| Error Formatted | `error.formatted` | Use the recorded `error.formatted` value when present; show `Not provided` when absent. | Render as the primary compact error summary row. |
| Error Headers X Should Retry | `error.headers.x-should-retry` | Use the recorded `error.headers.x-should-retry` value when present; show `Not provided` when absent. | Render inside the `Error Headers` group under `X Should Retry` as a boolean-like scalar. |
| Error Is Network Down | `error.isNetworkDown` | Use the recorded `error.isNetworkDown` value when present; show `Not provided` when absent. | Render as a boolean scalar row. |
| Error Message | `error.message` | Use the recorded `error.message` value when present; show `Not provided` when absent. | Render as wrapped multiline text with preserved JSON-like content and overflow expansion. |
| Error Status | `error.status` | Use the recorded `error.status` value when present; show `Not provided` when absent. | Render as a numeric status value. |
| Error Type | `error.type` | Use the recorded `error.type` value when present; show `Not provided` when absent. | Render as compact code text. |
| Max Retries | `maxRetries` | Use the recorded `maxRetries` value when present; show `Not provided` when absent. | Render as a numeric scalar row. |
| Retry Attempt | `retryAttempt` | Use the recorded `retryAttempt` value when present; show `Not provided` when absent. | Render as a numeric scalar row. |
| Retry In Ms | `retryInMs` | Use the recorded `retryInMs` value when present; show `Not provided` when absent. | Render as milliseconds with a compact numeric value. |

## Card Design

```text
+--------------------------------------------------------------------------------+
| [System] [API Error]                                               [pin] [x]   |
+--------------------------------------------------------------------------------+
|                           Content | Metadata | Raw                             |
+--------------------------------------------------------------------------------+
| Error Formatted             <error.formatted>                                  |
| Error Status                <error.status>                                     |
| Error Type                  <error.type>                                       |
| Error Is Network Down       <error.isNetworkDown>                              |
| Error Message                                                                  |
|   <error.message>                                                              |
|                                                                                |
| Cause                                                                          |
|   | Code                 | Errno                                            | |
|   | <cause.code>         | <cause.errno>                                    | |
| Error Cause                                                                    |
|   | Code                 | Errno                                            | |
|   | <error.cause.code>   | <error.cause.errno>                              | |
| Error Error Error                                                              |
|   | Message                                  | Type                         | |
|   | <error.error.error.message>              | <error.error.error.type>     | |
| Error Headers                                                                  |
|   | X Should Retry                                                           | |
|   | <error.headers.x-should-retry>                                           | |
| Max Retries                 <maxRetries>                                       |
| Retry Attempt               <retryAttempt>                                     |
| Retry In Ms                 <retryInMs>                                        |
+--------------------------------------------------------------------------------+
```
