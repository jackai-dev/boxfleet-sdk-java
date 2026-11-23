# BoxFleet hosted control plane (boxfleet.io) Java API

<!-- omniwrap-api-reference eyJjb250cmFjdF9maW5nZXJwcmludCI6ImUzZmQ0Yzc0NGFlODkzM2MwZTBiZDBjMjFhNjkyODk3Nzk1YTE0NjU3ZTU3N2ZiODIxMDg1MDBkMzlmMmFjOGQiLCJvcGVyYXRpb25fY291bnQiOjU2LCJyZW5kZXJlciI6ImphdmEiLCJ2ZXJzaW9uIjoiMS41LjAifQ -->

This generated index is tied to Semantic IR `1.14.0` and contract fingerprint `e3fd4c744ae8933c0e0bd0c21a692897795a14657e577fb82108500d39f2ac8d`. Every operation below is rendered from the same semantic contract and artifact-attested public member allocation as the SDK.

SDK maturity: **experimental**  
Artifact evidence: [`omniwrap-artifact.json`](omniwrap-artifact.json) binds this file by SHA-256 and is revalidated by the package gate.

## Client hooks and tracing

`ClientOptions.builder().hooks(RequestHooks)` registers four callbacks. Every attempt starts with `beforeRequest` and ends with exactly one of `onRetry` (another attempt follows), `afterResponse` (the success the call returns) or `onError` (the failure the call reports). Each receives the operation id, the HTTP method, the URL, the request headers, the attempt number (from 1), the time elapsed since the call started and, once the server answered, the HTTP status. No context carries a credential: `Authorization`, `Proxy-Authorization`, `Cookie`, every API-key header and API-key query parameter, and any configured credential value read `[redacted]`. Every context is an immutable `HookContext` record: no hook can change the request.

`ClientOptions.builder().tracer(RequestTracer)` opens one span per call through the tracer interface this SDK defines, named after the operation id, with `http.request.method`, `http.response.status_code` and `http.request.resend_count`. It needs no tracing library; README.md maps it onto the OpenTelemetry API.

## Shared types

- `HostedPersistentBoxClose`
- `HostedPersistentBoxRead`
- `HostedPersistentUsageMeter`
- `HostedPersistentUsageRead`
- `ObservedBox`

## Resource `accounts()`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJhY2NvdW50cygpLmdldENvbmZpZyIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6ImdldEFjY291bnRzQ29uZmlnIiwicGF0aCI6Ii92MS9hY2NvdW50cy9jb25maWciLCJyZXNvdXJjZSI6ImFjY291bnRzKCkiLCJzZWN0aW9uX3NoYTI1NiI6ImU5ZTIwMDA1M2ZkY2QwZTFlZmQ2MjViOTM1ODJkNWI5MDNhYzU4YmQwMThjN2U2ZThiZTRiY2Q0ZjdhYzYwMjciLCJzaWduYXR1cmVfc2hhMjU2IjoiODFhODE1NjBjM2VkYjBmZTI4YzVkYTQyZTk0YzhhMmJkN2NmZWNiM2E4NWQ2ZGUzNjY5MjA2YzNlZDk5ZTU2MSJ9 -->
### `client.accounts().getConfig`

Operation ID: `getAccountsConfig`  
Route: `GET` `/v1/accounts/config`  
Equivalent member: `client.getAccountsConfig`  

#### Signature

```java
public Void getConfig()
public CompletableFuture<Void> getConfigAsync()
public ApiResponse<Void> getConfigWithResponse()
public CompletableFuture<ApiResponse<Void>> getConfigWithResponseAsync()
public Void getConfig(RequestOptions requestOptions)
public CompletableFuture<Void> getConfigAsync(RequestOptions requestOptions)
public ApiResponse<Void> getConfigWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> getConfigWithResponseAsync(RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | OK | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.accounts().getConfig();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRBY2NvdW50c0NvbmZpZyJ9 -->

## Resource `admin()`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJhZG1pbigpLmNvbnRyb2xVc2VyIiwibWV0aG9kIjoiUE9TVCIsIm9wZXJhdGlvbl9pZCI6ImNvbnRyb2xVc2VyIiwicGF0aCI6Ii92MS9hZG1pbi91c2VycyIsInJlc291cmNlIjoiYWRtaW4oKSIsInNlY3Rpb25fc2hhMjU2IjoiODA2NzM0Y2U5MzU4MGQzODcxZDgyYzE1Y2Q4MWU3MzU1NWY2ZTM4ZTg3ZDczMmZjMjVhMjNlOTI0ZTY5OGMwYiIsInNpZ25hdHVyZV9zaGEyNTYiOiJiMzBiOWZkZjUzNzkyNTY0NmM1YzVmZDI1Y2FiMWU3MGEyNGE4M2QwZDBiYzQxNmMzZWU1YjIyMzY0NmZkYTQ3In0 -->
### `client.admin().controlUser`

Operation ID: `controlUser`  
Route: `POST` `/v1/admin/users`  
Equivalent member: `client.controlUser`  

#### Signature

```java
public Void controlUser(Map<String, Object> body)
public CompletableFuture<Void> controlUserAsync(Map<String, Object> body)
public ApiResponse<Void> controlUserWithResponse(Map<String, Object> body)
public CompletableFuture<ApiResponse<Void>> controlUserWithResponseAsync(Map<String, Object> body)
public Void controlUser(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Void> controlUserAsync(Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Void> controlUserWithResponse(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> controlUserWithResponseAsync(Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Applied | none |
| `401` | Admin token required | none |
| `409` | Managed account authority required; use the returned JackAISaaS accountUrl or portalUrl. | none |

#### Canonical required-input example

```json
{
  "body": {},
  "content_type": "application/json",
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.admin().controlUser(/* body */ {});
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJjb250cm9sVXNlciJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJhZG1pbigpLmdldENvbnNvbGUiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJnZXRBZG1pbkNvbnNvbGUiLCJwYXRoIjoiL3YxL2FkbWluL2NvbnNvbGUiLCJyZXNvdXJjZSI6ImFkbWluKCkiLCJzZWN0aW9uX3NoYTI1NiI6IjAwMmJiMzRmOTA4YzJiYjlhNWMwNjY4ZjhlOTk4M2I0YTFjNjMwYWQwYTk4MzEyYTYyOGE1ODU0Y2NkYTk1MjgiLCJzaWduYXR1cmVfc2hhMjU2IjoiNDk0MTZjYzk1OTBlNTUzMTU4YzAzNTY0Y2Q3YWIzYjEzYThmMTI5ZWIyNWYyYzA5MGQyYTczNGQxYjhkZTlhNiJ9 -->
### `client.admin().getConsole`

Operation ID: `getAdminConsole`  
Route: `GET` `/v1/admin/console`  
Equivalent member: `client.getAdminConsole`  

#### Signature

```java
public Void getConsole()
public CompletableFuture<Void> getConsoleAsync()
public ApiResponse<Void> getConsoleWithResponse()
public CompletableFuture<ApiResponse<Void>> getConsoleWithResponseAsync()
public Void getConsole(RequestOptions requestOptions)
public CompletableFuture<Void> getConsoleAsync(RequestOptions requestOptions)
public ApiResponse<Void> getConsoleWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> getConsoleWithResponseAsync(RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Console | none |
| `401` | Admin token required | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.admin().getConsole();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRBZG1pbkNvbnNvbGUifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJhZG1pbigpLmdldFBsYW5zIiwibWV0aG9kIjoiR0VUIiwib3BlcmF0aW9uX2lkIjoiZ2V0QWRtaW5QbGFucyIsInBhdGgiOiIvdjEvYWRtaW4vcGxhbnMiLCJyZXNvdXJjZSI6ImFkbWluKCkiLCJzZWN0aW9uX3NoYTI1NiI6IjA5ODMxNjZkMDllZWMzNjM3NjEwOTMxNzJmNmQwNjE3N2U4ZTBmMDQ3ZmVlMzBkNTRiZGYwMzQ3ZTdlODU1ODgiLCJzaWduYXR1cmVfc2hhMjU2IjoiMjYzMjFlNGZjMWE4MGExOWVmYjZiNWRlOTNhMDNjMWVlNjZiY2RkMWJhMjYwODkxODY1MmRkZjk1ZjUwNGEyMCJ9 -->
### `client.admin().getPlans`

Operation ID: `getAdminPlans`  
Route: `GET` `/v1/admin/plans`  
Equivalent member: `client.getAdminPlans`  

#### Signature

```java
public Void getPlans()
public CompletableFuture<Void> getPlansAsync()
public ApiResponse<Void> getPlansWithResponse()
public CompletableFuture<ApiResponse<Void>> getPlansWithResponseAsync()
public Void getPlans(RequestOptions requestOptions)
public CompletableFuture<Void> getPlansAsync(RequestOptions requestOptions)
public ApiResponse<Void> getPlansWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> getPlansWithResponseAsync(RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Plans | none |
| `401` | Admin token required | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.admin().getPlans();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRBZG1pblBsYW5zIn0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJhZG1pbigpLmxpc3RVc2VycyIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6Imxpc3RVc2VycyIsInBhdGgiOiIvdjEvYWRtaW4vdXNlcnMiLCJyZXNvdXJjZSI6ImFkbWluKCkiLCJzZWN0aW9uX3NoYTI1NiI6IjNmMDVmMTY3NDA0NTQzOWY5OTdmYTM1OWQ3NGRjZDkyZGY3MTVhYWU0ZGI5MzQ5ZTViOGU4OTZjY2QwZDZmZjciLCJzaWduYXR1cmVfc2hhMjU2IjoiNDc5YzJlMDRkNDViYTNiNDFiZTNmZWZlY2Q5NjIxNTk2YmQwNjRlMDgwODI4MzBmYmQwOTAwYWQxNDhmMmExNCJ9 -->
### `client.admin().listUsers`

Operation ID: `listUsers`  
Route: `GET` `/v1/admin/users`  
Equivalent member: `client.listUsers`  

#### Signature

```java
public Void listUsers()
public CompletableFuture<Void> listUsersAsync()
public ApiResponse<Void> listUsersWithResponse()
public CompletableFuture<ApiResponse<Void>> listUsersWithResponseAsync()
public Void listUsers(RequestOptions requestOptions)
public CompletableFuture<Void> listUsersAsync(RequestOptions requestOptions)
public ApiResponse<Void> listUsersWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> listUsersWithResponseAsync(RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Users | none |
| `401` | Admin token required | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.admin().listUsers();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsaXN0VXNlcnMifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJhZG1pbigpLnJlYWRUZWxlbWV0cnkiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJyZWFkVGVsZW1ldHJ5IiwicGF0aCI6Ii92MS9hZG1pbi90ZWxlbWV0cnkiLCJyZXNvdXJjZSI6ImFkbWluKCkiLCJzZWN0aW9uX3NoYTI1NiI6ImZjOTQ1MzhjMzQwOGQzN2JjZDM0YTg3NGRhZjVmODk1MTgyMWVjYzhhZmM5ODAwNTdmZWRkZWZmNjQ5NTNkNzMiLCJzaWduYXR1cmVfc2hhMjU2IjoiMzcyZmY5MjQ1ZjFlZGJlYWFkM2NkNzU0ZTI4NmQyZmZjNzVjN2JiODZlNDBiNWEzZDcwZDVkOGY3YThkZDViYiJ9 -->
### `client.admin().readTelemetry`

Operation ID: `readTelemetry`  
Route: `GET` `/v1/admin/telemetry`  
Equivalent member: `client.readTelemetry`  

#### Signature

```java
public Void readTelemetry()
public CompletableFuture<Void> readTelemetryAsync()
public ApiResponse<Void> readTelemetryWithResponse()
public CompletableFuture<ApiResponse<Void>> readTelemetryWithResponseAsync()
public Void readTelemetry(RequestOptions requestOptions)
public CompletableFuture<Void> readTelemetryAsync(RequestOptions requestOptions)
public ApiResponse<Void> readTelemetryWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> readTelemetryWithResponseAsync(RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Events | none |
| `401` | Admin token required | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.admin().readTelemetry();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJyZWFkVGVsZW1ldHJ5In0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJhZG1pbigpLnVwZGF0ZVBsYW4iLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoidXBkYXRlUGxhbiIsInBhdGgiOiIvdjEvYWRtaW4vcGxhbnMiLCJyZXNvdXJjZSI6ImFkbWluKCkiLCJzZWN0aW9uX3NoYTI1NiI6ImMwNmVjZmVmNzU3MDYyZDBiMjk1ZDRjMmNjNWVkZjUwZjFiOGJmZTcyYTBlMDYxZGY4MTI1MTg4NGIxZTc5MTEiLCJzaWduYXR1cmVfc2hhMjU2IjoiNjQ4Zjg4ZDMxNDc0NDdkZjZjNjM2ZjMyZjU1MmFlOWY4YzYwM2NlOTc4MGI5Zjc2NWI3ZDk5YmFkZDZhOTJmYiJ9 -->
### `client.admin().updatePlan`

Operation ID: `updatePlan`  
Route: `POST` `/v1/admin/plans`  
Equivalent member: `client.updatePlan`  

#### Signature

```java
public Void updatePlan(Map<String, Object> body)
public CompletableFuture<Void> updatePlanAsync(Map<String, Object> body)
public ApiResponse<Void> updatePlanWithResponse(Map<String, Object> body)
public CompletableFuture<ApiResponse<Void>> updatePlanWithResponseAsync(Map<String, Object> body)
public Void updatePlan(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Void> updatePlanAsync(Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Void> updatePlanWithResponse(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> updatePlanWithResponseAsync(Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Updated | none |
| `401` | Admin token required | none |
| `409` | Managed account authority required; use the returned JackAISaaS accountUrl or portalUrl. | none |

#### Canonical required-input example

```json
{
  "body": {},
  "content_type": "application/json",
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.admin().updatePlan(/* body */ {});
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJ1cGRhdGVQbGFuIn0 -->

## Resource `auth()`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJhdXRoKCkuZ2V0R2F0ZSIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6ImdldEF1dGhHYXRlIiwicGF0aCI6Ii92MS9hdXRoL2dhdGUiLCJyZXNvdXJjZSI6ImF1dGgoKSIsInNlY3Rpb25fc2hhMjU2IjoiZThlZTIyNzBhMTU5MDg0NzgzMWMwYTFkZTBhOWI5ZTc3YjI0ZGYzZTlkMzA5YTk0YjJkZGQ5MDA2ZTFjMzI5NSIsInNpZ25hdHVyZV9zaGEyNTYiOiJmMmQ4MTA1ZDE1Njg2Njg1Yjk1YTI1MmQ1YjNiOGY0NmY3ZGRiYTJjN2Y1M2RiY2IxZTQ0ODIzODI3ODE0OTZmIn0 -->
### `client.auth().getGate`

Operation ID: `getAuthGate`  
Route: `GET` `/v1/auth/gate`  
Equivalent member: `client.getAuthGate`  

#### Signature

```java
public Void getGate()
public CompletableFuture<Void> getGateAsync()
public ApiResponse<Void> getGateWithResponse()
public CompletableFuture<ApiResponse<Void>> getGateWithResponseAsync()
public Void getGate(RequestOptions requestOptions)
public CompletableFuture<Void> getGateAsync(RequestOptions requestOptions)
public ApiResponse<Void> getGateWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> getGateWithResponseAsync(RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | OK | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.auth().getGate();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRBdXRoR2F0ZSJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJhdXRoKCkucmVnaXN0ZXIiLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoicmVnaXN0ZXIiLCJwYXRoIjoiL3YxL2F1dGgvcmVnaXN0ZXIiLCJyZXNvdXJjZSI6ImF1dGgoKSIsInNlY3Rpb25fc2hhMjU2IjoiM2M5MjA0MzRhNzA2ZGU5YzE4ZTU3NDFmNWEzNjBmZDFmMGQxZWNjMGI0Y2IwMjUzYjE5ODEzMzFlOWNjMmEyOCIsInNpZ25hdHVyZV9zaGEyNTYiOiI1Nzc1MzQ1NWI5ZGYwNzNjOGM4MzAxNTViYWMxOGU4MDk3OWMyMWQxZGMzMmYyYzcwZjY2ZGJiNDM5MTk3YWRhIn0 -->
### `client.auth().register`

Operation ID: `register`  
Route: `POST` `/v1/auth/register`  
Equivalent member: `client.register`  

#### Signature

```java
public Void register(Map<String, Object> body)
public CompletableFuture<Void> registerAsync(Map<String, Object> body)
public ApiResponse<Void> registerWithResponse(Map<String, Object> body)
public CompletableFuture<ApiResponse<Void>> registerWithResponseAsync(Map<String, Object> body)
public Void register(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Void> registerAsync(Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Void> registerWithResponse(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> registerWithResponseAsync(Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `201` | License issued | none |
| `202` | Verification code sent (or withheld by the resend cooldown) | none |
| `400` | Invalid or expired code | none |
| `403` | Not invited or refused | none |
| `409` | Managed account authority required; use the returned JackAISaaS accountUrl or portalUrl. | none |
| `429` | Rate limited | none |
| `503` | Registration not configured | none |

#### Canonical required-input example

```json
{
  "body": {},
  "content_type": "application/json",
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.auth().register(/* body */ {});
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJyZWdpc3RlciJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJhdXRoKCkudXBkYXRlR2F0ZSIsIm1ldGhvZCI6IlBVVCIsIm9wZXJhdGlvbl9pZCI6InVwZGF0ZUF1dGhHYXRlIiwicGF0aCI6Ii92MS9hdXRoL2dhdGUiLCJyZXNvdXJjZSI6ImF1dGgoKSIsInNlY3Rpb25fc2hhMjU2IjoiZjY5YmE3ZWY1M2VmYzQ5NTk1ZWJmYWYwN2VlMjA4YTA3NDU2MjU3OTMzYWQ1MDRhNmUzZmIxYWUyYmIzYWE1MyIsInNpZ25hdHVyZV9zaGEyNTYiOiJkMDg2YzdlNjdhYTYzYjk2NWIzYWQ5YzlmNjk3MzNmZjQ5MWY1ZTBjNTZjMjJkM2I1YWEzM2QxOTZmOTczMzRkIn0 -->
### `client.auth().updateGate`

Operation ID: `updateAuthGate`  
Route: `PUT` `/v1/auth/gate`  
Equivalent member: `client.updateAuthGate`  

#### Signature

```java
public Void updateGate(Map<String, Object> body)
public CompletableFuture<Void> updateGateAsync(Map<String, Object> body)
public ApiResponse<Void> updateGateWithResponse(Map<String, Object> body)
public CompletableFuture<ApiResponse<Void>> updateGateWithResponseAsync(Map<String, Object> body)
public Void updateGate(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Void> updateGateAsync(Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Void> updateGateWithResponse(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> updateGateWithResponseAsync(Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Updated | none |
| `401` | Admin token required | none |
| `409` | Managed account authority required; use the returned JackAISaaS accountUrl or portalUrl. | none |

#### Canonical required-input example

```json
{
  "body": {},
  "content_type": "application/json",
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.auth().updateGate(/* body */ {});
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJ1cGRhdGVBdXRoR2F0ZSJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJhdXRoKCkudmVyaWZ5TGljZW5zZSIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJ2ZXJpZnlMaWNlbnNlIiwicGF0aCI6Ii92MS9hdXRoL3ZlcmlmeSIsInJlc291cmNlIjoiYXV0aCgpIiwic2VjdGlvbl9zaGEyNTYiOiI1ODlkZGNmZjM0YWFlYWRmOTJlZGY5ODY1NGNlMDIyODljYzBhMDU5MTAwMDk3NzhkZWJiZjQzZTQ5NTMxMjMxIiwic2lnbmF0dXJlX3NoYTI1NiI6ImUyYTk2MmQyOThhYjYyNjMxZmU1N2I3YjM0MzdkZmI2MGJkY2Y3ZDlmODZiNWU0ZjE1ZGJmOGFhYTg4NjQyNWIifQ -->
### `client.auth().verifyLicense`

Operation ID: `verifyLicense`  
Route: `POST` `/v1/auth/verify`  
Equivalent member: `client.verifyLicense`  

#### Signature

```java
public Void verifyLicense(Map<String, Object> body)
public CompletableFuture<Void> verifyLicenseAsync(Map<String, Object> body)
public ApiResponse<Void> verifyLicenseWithResponse(Map<String, Object> body)
public CompletableFuture<ApiResponse<Void>> verifyLicenseWithResponseAsync(Map<String, Object> body)
public Void verifyLicense(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Void> verifyLicenseAsync(Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Void> verifyLicenseWithResponse(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> verifyLicenseWithResponseAsync(Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Valid | none |
| `401` | Invalid license | none |
| `403` | Refused | none |
| `409` | Managed account authority required; use the returned JackAISaaS accountUrl or portalUrl. | none |
| `503` | Verification not configured | none |

#### Canonical required-input example

```json
{
  "body": {},
  "content_type": "application/json",
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.auth().verifyLicense(/* body */ {});
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJ2ZXJpZnlMaWNlbnNlIn0 -->

## Resource `billing()`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJiaWxsaW5nKCkuc3RyaXBlV2ViaG9vayIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJzdHJpcGVXZWJob29rIiwicGF0aCI6Ii92MS9iaWxsaW5nL3N0cmlwZS93ZWJob29rIiwicmVzb3VyY2UiOiJiaWxsaW5nKCkiLCJzZWN0aW9uX3NoYTI1NiI6ImU0ZTY5ZWRkYzUzODNlODE3NjUxYzJmNDM1MTM2NDc2MWZkNjFjNTk3ZWI2NmRkMDNlMmQ1NDFmMmMyZDIxZjciLCJzaWduYXR1cmVfc2hhMjU2IjoiZjNkMDY0NWUxYjZiZjE4NDJhNTc5MTM2OGFkNzBjYzk1ODQxOGI1YWM4MzQ2MjJmNjU3MWEyMDNkYjE1NzVjMyJ9 -->
### `client.billing().stripeWebhook`

Operation ID: `stripeWebhook`  
Route: `POST` `/v1/billing/stripe/webhook`  
Equivalent member: `client.stripeWebhook`  

#### Signature

```java
public Void stripeWebhook()
public CompletableFuture<Void> stripeWebhookAsync()
public ApiResponse<Void> stripeWebhookWithResponse()
public CompletableFuture<ApiResponse<Void>> stripeWebhookWithResponseAsync()
public Void stripeWebhook(RequestOptions requestOptions)
public CompletableFuture<Void> stripeWebhookAsync(RequestOptions requestOptions)
public ApiResponse<Void> stripeWebhookWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> stripeWebhookWithResponseAsync(RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Received | none |
| `400` | Invalid signature or payload | none |
| `409` | Managed account authority required; use the returned JackAISaaS accountUrl or portalUrl. | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.billing().stripeWebhook();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJzdHJpcGVXZWJob29rIn0 -->

## Resource `health()`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJoZWFsdGgoKS5nZXQiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJnZXRIZWFsdGgiLCJwYXRoIjoiL2hlYWx0aCIsInJlc291cmNlIjoiaGVhbHRoKCkiLCJzZWN0aW9uX3NoYTI1NiI6ImM1ZTU4ZTllZmJkMGM4ZTAzZWU5YjEzYTc0NGEzZGRlOWZhN2ExMzFiOGI1M2U1MjIzOGE2N2Q4OWZiMGZjZTIiLCJzaWduYXR1cmVfc2hhMjU2IjoiMThhYWE1YWUzNWEwMzY5YTMxYmJlYzBhOTZjOTAwZDBhMDgxODIzYTFkNTA1NmNjYzZkOTMyMTdhN2NlY2JmOCJ9 -->
### `client.health().get`

Operation ID: `getHealth`  
Route: `GET` `/health`  
Equivalent member: `client.getHealth`  

#### Signature

```java
public Void get()
public CompletableFuture<Void> getAsync()
public ApiResponse<Void> getWithResponse()
public CompletableFuture<ApiResponse<Void>> getWithResponseAsync()
public Void get(RequestOptions requestOptions)
public CompletableFuture<Void> getAsync(RequestOptions requestOptions)
public ApiResponse<Void> getWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> getWithResponseAsync(RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | OK | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.health().get();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRIZWFsdGgifQ -->

## Resource `jobs()`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJqb2JzKCkuY2FuY2VsIiwibWV0aG9kIjoiUE9TVCIsIm9wZXJhdGlvbl9pZCI6ImNhbmNlbEpvYiIsInBhdGgiOiIvdjEvam9icy97am9iSWR9L2NhbmNlbCIsInJlc291cmNlIjoiam9icygpIiwic2VjdGlvbl9zaGEyNTYiOiI3OTM5MjhiZjNmZDRjYzdkYzZkZjJkYzM0ZjdlODZlNGE4OGU2ZTRmZTAzMzlhMmU0NDRlODc1ZTA2MzZkZjMzIiwic2lnbmF0dXJlX3NoYTI1NiI6ImFiMTc4M2YzNDJkMjJmYzg4NTgxNDlmNGExYjdlNmQ2ZjgxN2M4MzUwNjIwZGViOTA2NWI2MTViNzJlZDJmMDEifQ -->
### `client.jobs().cancel`

Operation ID: `cancelJob`  
Route: `POST` `/v1/jobs/{jobId}/cancel`  
Equivalent member: `client.cancelJob`  

#### Signature

```java
public Void cancel(String jobId)
public CompletableFuture<Void> cancelAsync(String jobId)
public ApiResponse<Void> cancelWithResponse(String jobId)
public CompletableFuture<ApiResponse<Void>> cancelWithResponseAsync(String jobId)
public Void cancel(String jobId, RequestOptions requestOptions)
public CompletableFuture<Void> cancelAsync(String jobId, RequestOptions requestOptions)
public ApiResponse<Void> cancelWithResponse(String jobId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> cancelWithResponseAsync(String jobId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `jobId` | `path` | yes | `string` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | OK | none |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "jobId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.jobs().cancel(/* jobId */ "example");
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJjYW5jZWxKb2IifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJqb2JzKCkuZ2V0IiwibWV0aG9kIjoiR0VUIiwib3BlcmF0aW9uX2lkIjoiZ2V0Sm9iIiwicGF0aCI6Ii92MS9qb2JzL3tqb2JJZH0iLCJyZXNvdXJjZSI6ImpvYnMoKSIsInNlY3Rpb25fc2hhMjU2IjoiMWRkNTVkN2UxZjA4MGY2ZWU1MGNjMmRmMTk5YjliNzc2YTFiOGE3ZGVmM2Y2NjY0NmIzNGMyNGYzMjkxMzFjOCIsInNpZ25hdHVyZV9zaGEyNTYiOiI0MTc1MTQ4NWQyZGE4Zjk0NDNmM2QxOThhNzU3ZmIwMTUwNWU0MmQwODEzNTRkNzVkOTYzM2MzNThhNDUzMWVjIn0 -->
### `client.jobs().get`

Operation ID: `getJob`  
Route: `GET` `/v1/jobs/{jobId}`  
Equivalent member: `client.getJob`  

#### Signature

```java
public Void get(String jobId)
public CompletableFuture<Void> getAsync(String jobId)
public ApiResponse<Void> getWithResponse(String jobId)
public CompletableFuture<ApiResponse<Void>> getWithResponseAsync(String jobId)
public Void get(String jobId, RequestOptions requestOptions)
public CompletableFuture<Void> getAsync(String jobId, RequestOptions requestOptions)
public ApiResponse<Void> getWithResponse(String jobId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> getWithResponseAsync(String jobId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `jobId` | `path` | yes | `string` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | OK | none |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "jobId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.jobs().get(/* jobId */ "example");
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRKb2IifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJqb2JzKCkubGlzdEV2ZW50cyIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6Imxpc3RKb2JFdmVudHMiLCJwYXRoIjoiL3YxL2pvYnMve2pvYklkfS9ldmVudHMiLCJyZXNvdXJjZSI6ImpvYnMoKSIsInNlY3Rpb25fc2hhMjU2IjoiOTdmZGJhZWNiMzNjODMyZjYwYmQ5NDY5NjJmOTIwMWMxOTU0NzI2NzQ1NmM2ZWQwMGYzMjBjNzgwOTczYTlmMiIsInNpZ25hdHVyZV9zaGEyNTYiOiIzZDIyODA5ZTNiOTE1YjUxOWJmNjhmMDhmZmUyYjYxOTExYjQyZmI2MDA4NDA0ZjU5OGNhNWJhZjJhN2FiMTEzIn0 -->
### `client.jobs().listEvents`

Operation ID: `listJobEvents`  
Route: `GET` `/v1/jobs/{jobId}/events`  
Equivalent member: `client.listJobEvents`  

#### Signature

```java
public Void listEvents(String jobId)
public CompletableFuture<Void> listEventsAsync(String jobId)
public ApiResponse<Void> listEventsWithResponse(String jobId)
public CompletableFuture<ApiResponse<Void>> listEventsWithResponseAsync(String jobId)
public Void listEvents(String jobId, RequestOptions requestOptions)
public CompletableFuture<Void> listEventsAsync(String jobId, RequestOptions requestOptions)
public ApiResponse<Void> listEventsWithResponse(String jobId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> listEventsWithResponseAsync(String jobId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `jobId` | `path` | yes | `string` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | OK | none |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "jobId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.jobs().listEvents(/* jobId */ "example");
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsaXN0Sm9iRXZlbnRzIn0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJqb2JzKCkubGlzdCIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6Imxpc3RKb2JzIiwicGF0aCI6Ii92MS9qb2JzIiwicmVzb3VyY2UiOiJqb2JzKCkiLCJzZWN0aW9uX3NoYTI1NiI6ImM2NmZkZGM2MjY3NWVmMDQ3YzllMThmOGZmNmY1NjA1MGU1ZjNlN2I2NzQ3YWJhMjllZDllODU4YWJlMGIwYTEiLCJzaWduYXR1cmVfc2hhMjU2IjoiZTE0ZjU5YjkxMGNlNzM5OGRjNWIwZmMzZjE2MzhmNjc3ZTI3NzY5ZTQwNzk3NTUxMjk0YjljYmM1MDc2NWRlYyJ9 -->
### `client.jobs().list`

Operation ID: `listJobs`  
Route: `GET` `/v1/jobs`  
Equivalent member: `client.listJobs`  

#### Signature

```java
public Void list()
public CompletableFuture<Void> listAsync()
public ApiResponse<Void> listWithResponse()
public CompletableFuture<ApiResponse<Void>> listWithResponseAsync()
public Void list(RequestOptions requestOptions)
public CompletableFuture<Void> listAsync(RequestOptions requestOptions)
public ApiResponse<Void> listWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> listWithResponseAsync(RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Jobs | none |
| `401` | Session required | none |
| `503` | Storage not configured | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.jobs().list();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsaXN0Sm9icyJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJqb2JzKCkuc3VibWl0IiwibWV0aG9kIjoiUE9TVCIsIm9wZXJhdGlvbl9pZCI6InN1Ym1pdEpvYiIsInBhdGgiOiIvdjEvam9icyIsInJlc291cmNlIjoiam9icygpIiwic2VjdGlvbl9zaGEyNTYiOiJkZTI1MzNlNzBhY2Q5NTQ5MmQ4NjY1NDYyMDcxN2Q3YWY5ZjhjODJmNDVhYWU1NzAxYWNiMDNjMjIyN2UxY2JiIiwic2lnbmF0dXJlX3NoYTI1NiI6IjdlMDYyZmYyOTViMmFhMTA2YTc3OGZiYTQ2ZTRmYjA2MjFkNmMwMmQ0NTZiMThkNjI5Njg2NmFhNmVjZjg0NWYifQ -->
### `client.jobs().submit`

Operation ID: `submitJob`  
Route: `POST` `/v1/jobs`  
Equivalent member: `client.submitJob`  

#### Signature

```java
public Void submit(Map<String, Object> body)
public CompletableFuture<Void> submitAsync(Map<String, Object> body)
public ApiResponse<Void> submitWithResponse(Map<String, Object> body)
public CompletableFuture<ApiResponse<Void>> submitWithResponseAsync(Map<String, Object> body)
public Void submit(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Void> submitAsync(Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Void> submitWithResponse(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> submitWithResponseAsync(Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Replayed | none |
| `201` | Created | none |
| `401` | Session required | none |
| `503` | Storage not configured | none |

#### Canonical required-input example

```json
{
  "body": {},
  "content_type": "application/json",
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.jobs().submit(/* body */ {});
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJzdWJtaXRKb2IifQ -->

## Resource `organizations()`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkuY2xvc2VQZXJzaXN0ZW50Qm94IiwibWV0aG9kIjoiUE9TVCIsIm9wZXJhdGlvbl9pZCI6ImNsb3NlUGVyc2lzdGVudEJveCIsInBhdGgiOiIvdjEvb3JnYW5pemF0aW9ucy97b3JnYW5pemF0aW9uSWR9L3BlcnNpc3RlbnQtYm94ZXMve2JveElkfS9jbG9zZSIsInJlc291cmNlIjoib3JnYW5pemF0aW9ucygpIiwic2VjdGlvbl9zaGEyNTYiOiJhZDZhMmZlYmFmMTAwZDQ4YTlkNWI0MWNiYmQyNWUxMTcwZjRkNTFhMGZkNzEyNGFmMmE3MGM0MTc1YjliZDRiIiwic2lnbmF0dXJlX3NoYTI1NiI6IjAzMDI4NzQyNzY1NjZkOWIxZTA3YTc0NmMxNjE2ZTYzZWIzNTdiNjUxYTEyMGY1MjRhMDk2ZDUyNmEzMTlkMmYifQ -->
### `client.organizations().closePersistentBox`

Operation ID: `closePersistentBox`  
Route: `POST` `/v1/organizations/{organizationId}/persistent-boxes/{boxId}/close`  
Equivalent member: `client.closePersistentBox`  

#### Signature

```java
public HostedPersistentBoxClose closePersistentBox(String organizationId, String boxId)
public CompletableFuture<HostedPersistentBoxClose> closePersistentBoxAsync(String organizationId, String boxId)
public ApiResponse<HostedPersistentBoxClose> closePersistentBoxWithResponse(String organizationId, String boxId)
public CompletableFuture<ApiResponse<HostedPersistentBoxClose>> closePersistentBoxWithResponseAsync(String organizationId, String boxId)
public HostedPersistentBoxClose closePersistentBox(String organizationId, String boxId, RequestOptions requestOptions)
public CompletableFuture<HostedPersistentBoxClose> closePersistentBoxAsync(String organizationId, String boxId, RequestOptions requestOptions)
public ApiResponse<HostedPersistentBoxClose> closePersistentBoxWithResponse(String organizationId, String boxId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<HostedPersistentBoxClose>> closePersistentBoxWithResponseAsync(String organizationId, String boxId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |
| `boxId` | `path` | yes | `string&lt;uuid&gt;` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Closure is recorded; repeat requests return the same result without deleting again. | application/json (HostedPersistentBoxClose) |
| `202` | Closure is unconfirmed. Lost, late, negative or mismatched acknowledgements and failed receipt persistence retain reservations. Repeat requests never dispatch another deletion; operator reconciliation is required. | application/json (HostedPersistentBoxClose) |
| `400` | Invalid UUID, body or query parameters. | none |
| `401` | Missing or rejected product session. | none |
| `403` | Current authority denied cleanup or the organization/product/environment differs. | none |
| `404` | No durable box in this exact target scope. | none |
| `409` | Unconfirmed or changed provider allocation requires operator reconciliation. | none |
| `503` | Authority or storage unavailable, or no matching operator provider adapter. Missing configuration refuses before any close intention or deletion. | none |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    },
    {
      "in": "path",
      "name": "boxId",
      "value": "00000000-0000-0000-c54d-988d0e4e7e77"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().closePersistentBox(/* organizationId */ "example", /* boxId */ "00000000-0000-0000-c54d-988d0e4e7e77");
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJjbG9zZVBlcnNpc3RlbnRCb3gifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkuY3JlYXRlQmlsbGluZ1BvcnRhbCIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJjcmVhdGVCaWxsaW5nUG9ydGFsIiwicGF0aCI6Ii92MS9vcmdhbml6YXRpb25zL3tvcmdhbml6YXRpb25JZH0vYmlsbGluZy9wb3J0YWwiLCJyZXNvdXJjZSI6Im9yZ2FuaXphdGlvbnMoKSIsInNlY3Rpb25fc2hhMjU2IjoiNjVkZDZhMjRiNTI1ZDRiOGI5ZjNhNzM0NzFjMmQ3ODZmMWNhMzU0MDM0OTkzNGNhYThlMzY0Yjg0ZWVhMmFlMiIsInNpZ25hdHVyZV9zaGEyNTYiOiIwNDExMjdjOTU1NjUwYmFhZTRkODMxYTVkMzMyN2MwOTc4OWU1ZTM3YjAwYzk4MWZhNzFiMWNhY2E1NTc3OTY1In0 -->
### `client.organizations().createBillingPortal`

Operation ID: `createBillingPortal`  
Route: `POST` `/v1/organizations/{organizationId}/billing/portal`  
Equivalent member: `client.createBillingPortal`  

#### Signature

```java
public Void createBillingPortal(String organizationId)
public CompletableFuture<Void> createBillingPortalAsync(String organizationId)
public ApiResponse<Void> createBillingPortalWithResponse(String organizationId)
public CompletableFuture<ApiResponse<Void>> createBillingPortalWithResponseAsync(String organizationId)
public Void createBillingPortal(String organizationId, RequestOptions requestOptions)
public CompletableFuture<Void> createBillingPortalAsync(String organizationId, RequestOptions requestOptions)
public ApiResponse<Void> createBillingPortalWithResponse(String organizationId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> createBillingPortalWithResponseAsync(String organizationId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `201` | portalUrl | none |
| `404` | No Stripe customer yet | none |
| `409` | Managed account authority required; use the returned JackAISaaS accountUrl or portalUrl. | none |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().createBillingPortal(/* organizationId */ "example");
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJjcmVhdGVCaWxsaW5nUG9ydGFsIn0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkuY3JlYXRlQm94IiwibWV0aG9kIjoiUE9TVCIsIm9wZXJhdGlvbl9pZCI6ImNyZWF0ZUJveCIsInBhdGgiOiIvdjEvb3JnYW5pemF0aW9ucy97b3JnYW5pemF0aW9uSWR9L2JveGVzIiwicmVzb3VyY2UiOiJvcmdhbml6YXRpb25zKCkiLCJzZWN0aW9uX3NoYTI1NiI6IjkwMjJjNGU3ZTQwNTUxMjBiMDJlOTdjZGRiZjhmMGVjZjIzNTEyZjRkZDY3MWRhODdkM2QyMTIyYTQxOGY3OTgiLCJzaWduYXR1cmVfc2hhMjU2IjoiMWFlMjA4ODEyZDNjNjczOWRkNDJlNWY2YzFmM2UwNjQ1N2I4NDQ2OGY3ZjQyM2M3NWZjNmZiODNjZTM4OTQ3MiJ9 -->
### `client.organizations().createBox`

Operation ID: `createBox`  
Route: `POST` `/v1/organizations/{organizationId}/boxes`  
Equivalent member: `client.createBox`  

#### Signature

```java
public Void createBox(String organizationId, Map<String, Object> body)
public CompletableFuture<Void> createBoxAsync(String organizationId, Map<String, Object> body)
public ApiResponse<Void> createBoxWithResponse(String organizationId, Map<String, Object> body)
public CompletableFuture<ApiResponse<Void>> createBoxWithResponseAsync(String organizationId, Map<String, Object> body)
public Void createBox(String organizationId, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Void> createBoxAsync(String organizationId, Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Void> createBoxWithResponse(String organizationId, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> createBoxWithResponseAsync(String organizationId, Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `201` | Box running at the provider | none |
| `402` | Concurrent-box limit reached | none |
| `502` | The provider refused; recorded as failed | none |
| `503` | No provider or no storage | none |

#### Canonical required-input example

```json
{
  "body": {},
  "content_type": "application/json",
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().createBox(/* organizationId */ "example", /* body */ {});
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJjcmVhdGVCb3gifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkuY3JlYXRlQ2hlY2tvdXQiLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoiY3JlYXRlQ2hlY2tvdXQiLCJwYXRoIjoiL3YxL29yZ2FuaXphdGlvbnMve29yZ2FuaXphdGlvbklkfS9iaWxsaW5nL2NoZWNrb3V0IiwicmVzb3VyY2UiOiJvcmdhbml6YXRpb25zKCkiLCJzZWN0aW9uX3NoYTI1NiI6IjdmZmUwZDQ3ZWQ0MWU3MmE2MDNkMmQ2MGNiMmJmMjRhYWY5ZjkxNzNkNDkwZjNiNTllZGI1MDBiNjQ5N2YzYmUiLCJzaWduYXR1cmVfc2hhMjU2IjoiY2E0MWRlYmQ0ZDhlNmQ0YmRjNDQzMmQyOTczMTdiN2I4YjdmZTQ3NDI5Yjg4OTMyNTllMGU0NDBkMTAwODJiMCJ9 -->
### `client.organizations().createCheckout`

Operation ID: `createCheckout`  
Route: `POST` `/v1/organizations/{organizationId}/billing/checkout`  
Equivalent member: `client.createCheckout`  

#### Signature

```java
public Void createCheckout(String organizationId, Map<String, Object> body)
public CompletableFuture<Void> createCheckoutAsync(String organizationId, Map<String, Object> body)
public ApiResponse<Void> createCheckoutWithResponse(String organizationId, Map<String, Object> body)
public CompletableFuture<ApiResponse<Void>> createCheckoutWithResponseAsync(String organizationId, Map<String, Object> body)
public Void createCheckout(String organizationId, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Void> createCheckoutAsync(String organizationId, Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Void> createCheckoutWithResponse(String organizationId, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> createCheckoutWithResponseAsync(String organizationId, Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `201` | checkoutUrl of the Stripe Checkout Session | none |
| `409` | Managed account authority required; use the returned JackAISaaS accountUrl or portalUrl. Autonomous mode: Plan not on sale or subscription exists | none |

#### Canonical required-input example

```json
{
  "body": {
    "planKey": "pro"
  },
  "content_type": "application/json",
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().createCheckout(/* organizationId */ "example", /* body */ {"planKey": "pro"});
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJjcmVhdGVDaGVja291dCJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkuZ2V0QmlsbGluZyIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6ImdldEJpbGxpbmciLCJwYXRoIjoiL3YxL29yZ2FuaXphdGlvbnMve29yZ2FuaXphdGlvbklkfS9iaWxsaW5nIiwicmVzb3VyY2UiOiJvcmdhbml6YXRpb25zKCkiLCJzZWN0aW9uX3NoYTI1NiI6ImQ3OWM2MGFjYmNjZWY2YTU3MmQ3NzRiYWE4N2U5Zjk5OThhNDBjNmUyMGRiYTJhY2EwYjg5NWFlZDVmM2QxODUiLCJzaWduYXR1cmVfc2hhMjU2IjoiNjEwNmE1ODkxMWFjNzI2YmE2NTIxNmEzYzhjZGMyY2QwNzlmNDkzOTY2ZGM0YzZiNDU0ZWE0MWQ4YmZiNGQzNiJ9 -->
### `client.organizations().getBilling`

Operation ID: `getBilling`  
Route: `GET` `/v1/organizations/{organizationId}/billing`  
Equivalent member: `client.getBilling`  

#### Signature

```java
public Void getBilling(String organizationId)
public CompletableFuture<Void> getBillingAsync(String organizationId)
public ApiResponse<Void> getBillingWithResponse(String organizationId)
public CompletableFuture<ApiResponse<Void>> getBillingWithResponseAsync(String organizationId)
public Void getBilling(String organizationId, RequestOptions requestOptions)
public CompletableFuture<Void> getBillingAsync(String organizationId, RequestOptions requestOptions)
public ApiResponse<Void> getBillingWithResponse(String organizationId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> getBillingWithResponseAsync(String organizationId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Billing status | none |
| `409` | Managed account authority required; use the returned JackAISaaS accountUrl or portalUrl. | none |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().getBilling(/* organizationId */ "example");
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRCaWxsaW5nIn0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkuZ2V0Qm94IiwibWV0aG9kIjoiR0VUIiwib3BlcmF0aW9uX2lkIjoiZ2V0Qm94IiwicGF0aCI6Ii92MS9vcmdhbml6YXRpb25zL3tvcmdhbml6YXRpb25JZH0vYm94ZXMve2JveElkfSIsInJlc291cmNlIjoib3JnYW5pemF0aW9ucygpIiwic2VjdGlvbl9zaGEyNTYiOiI0ZjEwMTU3M2Q4NjMwZjJhYTg4Y2EyMmZlZDE3NGVmM2UwNjJhN2I2MWNiM2FiODY0NDk4NDBhODg0MzA2MjRiIiwic2lnbmF0dXJlX3NoYTI1NiI6IjE1MGU1Y2RjY2ViMTEwNmU4NDQ5NzlmZWY4ODYxM2E3MzQxOTVjM2M4ZjA4MTIxMTRmOWYyYjJlOTU1YjJiYjAifQ -->
### `client.organizations().getBox`

Operation ID: `getBox`  
Route: `GET` `/v1/organizations/{organizationId}/boxes/{boxId}`  
Equivalent member: `client.getBox`  

#### Signature

```java
public Void getBox(String organizationId, String boxId)
public CompletableFuture<Void> getBoxAsync(String organizationId, String boxId)
public ApiResponse<Void> getBoxWithResponse(String organizationId, String boxId)
public CompletableFuture<ApiResponse<Void>> getBoxWithResponseAsync(String organizationId, String boxId)
public Void getBox(String organizationId, String boxId, RequestOptions requestOptions)
public CompletableFuture<Void> getBoxAsync(String organizationId, String boxId, RequestOptions requestOptions)
public ApiResponse<Void> getBoxWithResponse(String organizationId, String boxId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> getBoxWithResponseAsync(String organizationId, String boxId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |
| `boxId` | `path` | yes | `string&lt;uuid&gt;` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Stored box | none |
| `404` | Unknown box | none |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    },
    {
      "in": "path",
      "name": "boxId",
      "value": "00000000-0000-0000-d32a-0e84cb70d88a"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().getBox(/* organizationId */ "example", /* boxId */ "00000000-0000-0000-d32a-0e84cb70d88a");
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRCb3gifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkuZ2V0RW50aXRsZW1lbnRzIiwibWV0aG9kIjoiR0VUIiwib3BlcmF0aW9uX2lkIjoiZ2V0RW50aXRsZW1lbnRzIiwicGF0aCI6Ii92MS9vcmdhbml6YXRpb25zL3tvcmdhbml6YXRpb25JZH0vZW50aXRsZW1lbnRzIiwicmVzb3VyY2UiOiJvcmdhbml6YXRpb25zKCkiLCJzZWN0aW9uX3NoYTI1NiI6ImVlNmQ3ZDE4ZTE1ZjVmOGI4MjZlZmRhNTk1ODIxZGIxYzY1YjAwZjAwYWM5NmJiZmM0MzJjMzkxNzE2ZjFjZmYiLCJzaWduYXR1cmVfc2hhMjU2IjoiMzIxMWVhYzhjYTg5YjEwNWM1NTU0YjIyMTY0YmM0MGJjM2I3NzU3ZjBkYTliYmMzNDNmMTEyZmNkZWQxNGU2YSJ9 -->
### `client.organizations().getEntitlements`

Operation ID: `getEntitlements`  
Route: `GET` `/v1/organizations/{organizationId}/entitlements`  
Equivalent member: `client.getEntitlements`  

#### Signature

```java
public Void getEntitlements(String organizationId)
public CompletableFuture<Void> getEntitlementsAsync(String organizationId)
public ApiResponse<Void> getEntitlementsWithResponse(String organizationId)
public CompletableFuture<ApiResponse<Void>> getEntitlementsWithResponseAsync(String organizationId)
public Void getEntitlements(String organizationId, RequestOptions requestOptions)
public CompletableFuture<Void> getEntitlementsAsync(String organizationId, RequestOptions requestOptions)
public ApiResponse<Void> getEntitlementsWithResponse(String organizationId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> getEntitlementsWithResponseAsync(String organizationId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Entitlements and usage | none |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().getEntitlements(/* organizationId */ "example");
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRFbnRpdGxlbWVudHMifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkuZ2V0RmxlZXQiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJnZXRGbGVldCIsInBhdGgiOiIvdjEvb3JnYW5pemF0aW9ucy97b3JnYW5pemF0aW9uSWR9L2ZsZWV0IiwicmVzb3VyY2UiOiJvcmdhbml6YXRpb25zKCkiLCJzZWN0aW9uX3NoYTI1NiI6ImVhY2FjM2ZjN2Y5MzJlY2FmZTIxYzIyODVhZTk5MTI1MDAxNzg3ZDEyZjQyMmQxODY4ODQwODNkZWMxY2UxYTEiLCJzaWduYXR1cmVfc2hhMjU2IjoiOTRkMjc2ZDU5OTQyN2QwMzA2NWY1MGE3MDMwZDUxMjUzMDVlYzgyYWNlOWYxM2RiY2ZlNjdmMGI1NDhmMzM5YiJ9 -->
### `client.organizations().getFleet`

Operation ID: `getFleet`  
Route: `GET` `/v1/organizations/{organizationId}/fleet`  
Equivalent member: `client.getFleet`  

#### Signature

```java
public Void getFleet(String organizationId)
public CompletableFuture<Void> getFleetAsync(String organizationId)
public ApiResponse<Void> getFleetWithResponse(String organizationId)
public CompletableFuture<ApiResponse<Void>> getFleetWithResponseAsync(String organizationId)
public Void getFleet(String organizationId, RequestOptions requestOptions)
public CompletableFuture<Void> getFleetAsync(String organizationId, RequestOptions requestOptions)
public ApiResponse<Void> getFleetWithResponse(String organizationId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> getFleetWithResponseAsync(String organizationId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Stored fleet | none |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().getFleet(/* organizationId */ "example");
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRGbGVldCJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkuZ2V0RmxlZXRQb2xpY3kiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJnZXRGbGVldFBvbGljeSIsInBhdGgiOiIvdjEvb3JnYW5pemF0aW9ucy97b3JnYW5pemF0aW9uSWR9L2ZsZWV0L3BvbGljeSIsInJlc291cmNlIjoib3JnYW5pemF0aW9ucygpIiwic2VjdGlvbl9zaGEyNTYiOiIzMDBlYzhkZGY1OGM5ZWQ1NzA4MDEwODMyODQ0NGMyMjFjZTU2MGUwYjllODNhZjFmMWUzNTY3YzJkZjVhMzk4Iiwic2lnbmF0dXJlX3NoYTI1NiI6IjI4OTQ1ZDEyNjA0M2YwMmMyYmE4NzQxNmNhOWQ1ZDMwNzhhZWNkY2ZlZDZlOGNhNDQ1N2YzZTcxNWMyZGVmNWUifQ -->
### `client.organizations().getFleetPolicy`

Operation ID: `getFleetPolicy`  
Route: `GET` `/v1/organizations/{organizationId}/fleet/policy`  
Equivalent member: `client.getFleetPolicy`  

#### Signature

```java
public Void getFleetPolicy(String organizationId)
public CompletableFuture<Void> getFleetPolicyAsync(String organizationId)
public ApiResponse<Void> getFleetPolicyWithResponse(String organizationId)
public CompletableFuture<ApiResponse<Void>> getFleetPolicyWithResponseAsync(String organizationId)
public Void getFleetPolicy(String organizationId, RequestOptions requestOptions)
public CompletableFuture<Void> getFleetPolicyAsync(String organizationId, RequestOptions requestOptions)
public ApiResponse<Void> getFleetPolicyWithResponse(String organizationId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> getFleetPolicyWithResponseAsync(String organizationId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Effective policy | none |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().getFleetPolicy(/* organizationId */ "example");
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRGbGVldFBvbGljeSJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkuZ2V0UGVyc2lzdGVudEJveCIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6ImdldFBlcnNpc3RlbnRCb3giLCJwYXRoIjoiL3YxL29yZ2FuaXphdGlvbnMve29yZ2FuaXphdGlvbklkfS9wZXJzaXN0ZW50LWJveGVzL3tib3hJZH0iLCJyZXNvdXJjZSI6Im9yZ2FuaXphdGlvbnMoKSIsInNlY3Rpb25fc2hhMjU2IjoiMDQwNTE3ZTExY2IwYzJkYzMxYmFlYWMyOGVjZTUyMjRlMDhlMjRhOTM0MTJlY2FjMmQ1NDc4ZjVkYmFhM2Q1YyIsInNpZ25hdHVyZV9zaGEyNTYiOiJiZjlmYTg1MGU3YTRhNmU1ZGQyMDg1ODllMGYwNGE3OWUzNTNiOTgzOTdlMDE2YmUwNzJmY2ZlZGQ5ZjRmNjU2In0 -->
### `client.organizations().getPersistentBox`

Operation ID: `getPersistentBox`  
Route: `GET` `/v1/organizations/{organizationId}/persistent-boxes/{boxId}`  
Equivalent member: `client.getPersistentBox`  

#### Signature

```java
public Map<String, Object> getPersistentBox(String organizationId, String boxId)
public CompletableFuture<Map<String, Object>> getPersistentBoxAsync(String organizationId, String boxId)
public ApiResponse<Map<String, Object>> getPersistentBoxWithResponse(String organizationId, String boxId)
public CompletableFuture<ApiResponse<Map<String, Object>>> getPersistentBoxWithResponseAsync(String organizationId, String boxId)
public Map<String, Object> getPersistentBox(String organizationId, String boxId, RequestOptions requestOptions)
public CompletableFuture<Map<String, Object>> getPersistentBoxAsync(String organizationId, String boxId, RequestOptions requestOptions)
public ApiResponse<Map<String, Object>> getPersistentBoxWithResponse(String organizationId, String boxId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Map<String, Object>>> getPersistentBoxWithResponseAsync(String organizationId, String boxId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |
| `boxId` | `path` | yes | `string&lt;uuid&gt;` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Private stored record and reserved budget; runtime status is not-metered. | application/json (object) |
| `400` | Invalid UUID or query parameters. | none |
| `401` | Missing or rejected product session. | none |
| `403` | Current authority denied access or the organization/product/environment differs. | none |
| `404` | No durable box in this exact target scope. | none |
| `503` | Authority or durable record storage unavailable. | none |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    },
    {
      "in": "path",
      "name": "boxId",
      "value": "00000000-0000-0000-098c-d4f2b24057fb"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().getPersistentBox(/* organizationId */ "example", /* boxId */ "00000000-0000-0000-098c-d4f2b24057fb");
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRQZXJzaXN0ZW50Qm94In0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkuZ2V0UGVyc2lzdGVudEJveFByb3ZpZGVyVXNhZ2UiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJnZXRQZXJzaXN0ZW50Qm94UHJvdmlkZXJVc2FnZSIsInBhdGgiOiIvdjEvb3JnYW5pemF0aW9ucy97b3JnYW5pemF0aW9uSWR9L3BlcnNpc3RlbnQtYm94ZXMve2JveElkfS91c2FnZSIsInJlc291cmNlIjoib3JnYW5pemF0aW9ucygpIiwic2VjdGlvbl9zaGEyNTYiOiI3NDFkNDI3OGM2M2FjMmFkMTIwNDVjZjM5YjdmYjJlMzQyMjY4ODU3YjY0YWFjMjQ3NTY3ZGMzOTI1YzI3MzQwIiwic2lnbmF0dXJlX3NoYTI1NiI6ImJmODUyOTk0ZjRhZTQyODg1ZmI0NmE3NWRhM2VjNzVkZjgwMzEyNjkxZjRhOGJiOTc3ZThkNmVkNmViMTA3YmIifQ -->
### `client.organizations().getPersistentBoxProviderUsage`

Operation ID: `getPersistentBoxProviderUsage`  
Route: `GET` `/v1/organizations/{organizationId}/persistent-boxes/{boxId}/usage`  
Equivalent member: `client.getPersistentBoxProviderUsage`  

#### Signature

```java
public Map<String, Object> getPersistentBoxProviderUsage(String organizationId, String boxId, String from, String to)
public CompletableFuture<Map<String, Object>> getPersistentBoxProviderUsageAsync(String organizationId, String boxId, String from, String to)
public ApiResponse<Map<String, Object>> getPersistentBoxProviderUsageWithResponse(String organizationId, String boxId, String from, String to)
public CompletableFuture<ApiResponse<Map<String, Object>>> getPersistentBoxProviderUsageWithResponseAsync(String organizationId, String boxId, String from, String to)
public Map<String, Object> getPersistentBoxProviderUsage(String organizationId, String boxId, String from, String to, RequestOptions requestOptions)
public CompletableFuture<Map<String, Object>> getPersistentBoxProviderUsageAsync(String organizationId, String boxId, String from, String to, RequestOptions requestOptions)
public ApiResponse<Map<String, Object>> getPersistentBoxProviderUsageWithResponse(String organizationId, String boxId, String from, String to, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Map<String, Object>>> getPersistentBoxProviderUsageWithResponseAsync(String organizationId, String boxId, String from, String to, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |
| `boxId` | `path` | yes | `string&lt;uuid&gt;` |  |
| `from` | `query` | yes | `string&lt;date-time&gt;` |  |
| `to` | `query` | yes | `string&lt;date-time&gt;` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Private provider evidence summary with explicit interval coverage. | application/json (object) |
| `400` | Invalid box ID or bounded UTC window. | none |
| `401` | Missing or rejected product session. | none |
| `403` | Current authority denied access or target scope differs. | none |
| `404` | No durable box in this exact target scope. | none |
| `413` | Stored evidence exceeds the per-read record bound; select a smaller window. | none |
| `503` | Authority or usage storage unavailable. | none |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    },
    {
      "in": "path",
      "name": "boxId",
      "value": "00000000-0000-0000-0848-7a89fcbe4ab4"
    },
    {
      "in": "query",
      "name": "from",
      "value": "2026-01-01T00:00:00Z"
    },
    {
      "in": "query",
      "name": "to",
      "value": "2026-01-01T00:00:27Z"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().getPersistentBoxProviderUsage(/* organizationId */ "example", /* boxId */ "00000000-0000-0000-0848-7a89fcbe4ab4", /* from */ "2026-01-01T00:00:00Z", /* to */ "2026-01-01T00:00:27Z");
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRQZXJzaXN0ZW50Qm94UHJvdmlkZXJVc2FnZSJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkubGlzdEJveGVzIiwibWV0aG9kIjoiR0VUIiwib3BlcmF0aW9uX2lkIjoibGlzdEJveGVzIiwicGF0aCI6Ii92MS9vcmdhbml6YXRpb25zL3tvcmdhbml6YXRpb25JZH0vYm94ZXMiLCJyZXNvdXJjZSI6Im9yZ2FuaXphdGlvbnMoKSIsInNlY3Rpb25fc2hhMjU2IjoiYWNlMDRmZmZjOGU0YjkxNjc0ZGU1OTU5YjU4MGNhMjQ2MmE4MDdkMmQ2ZjFkNzVkYTFjYzUxMDJkMzU1YTI3YSIsInNpZ25hdHVyZV9zaGEyNTYiOiJlMDFhMWRlNmJlMWM0OTM2ZGI1ZTAwMzg2Y2NjMTJlNTY5YWE5YzIxMWZiOTFiZGI3OGM5MTQzNjc1ZmZlMjUxIn0 -->
### `client.organizations().listBoxes`

Operation ID: `listBoxes`  
Route: `GET` `/v1/organizations/{organizationId}/boxes`  
Equivalent member: `client.listBoxes`  

#### Signature

```java
public Void listBoxes(String organizationId)
public CompletableFuture<Void> listBoxesAsync(String organizationId)
public ApiResponse<Void> listBoxesWithResponse(String organizationId)
public CompletableFuture<ApiResponse<Void>> listBoxesWithResponseAsync(String organizationId)
public Void listBoxes(String organizationId, RequestOptions requestOptions)
public CompletableFuture<Void> listBoxesAsync(String organizationId, RequestOptions requestOptions)
public ApiResponse<Void> listBoxesWithResponse(String organizationId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> listBoxesWithResponseAsync(String organizationId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Stored boxes with their provider state | none |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().listBoxes(/* organizationId */ "example");
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsaXN0Qm94ZXMifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkubGlzdEludm9pY2VzIiwibWV0aG9kIjoiR0VUIiwib3BlcmF0aW9uX2lkIjoibGlzdEludm9pY2VzIiwicGF0aCI6Ii92MS9vcmdhbml6YXRpb25zL3tvcmdhbml6YXRpb25JZH0vYmlsbGluZy9pbnZvaWNlcyIsInJlc291cmNlIjoib3JnYW5pemF0aW9ucygpIiwic2VjdGlvbl9zaGEyNTYiOiJmN2ZmYjdjNWE1NDQ4NWI0Y2U3ZDg4ZGM5MmM1OGI5YTA4OGM4NTIyYmI1N2ZhYmMwMjliZDYzMDBhMDAwNjg1Iiwic2lnbmF0dXJlX3NoYTI1NiI6IjMzOTk2YjI4ODAzOTA4MmI2MzFhMjE4NzRjYThjZjk0ZjZhZTI1OTAyOTA3MGZkZWJiYjVjODhmZDJlMjkwMWEifQ -->
### `client.organizations().listInvoices`

Operation ID: `listInvoices`  
Route: `GET` `/v1/organizations/{organizationId}/billing/invoices`  
Equivalent member: `client.listInvoices`  

#### Signature

```java
public Void listInvoices(String organizationId)
public CompletableFuture<Void> listInvoicesAsync(String organizationId)
public ApiResponse<Void> listInvoicesWithResponse(String organizationId)
public CompletableFuture<ApiResponse<Void>> listInvoicesWithResponseAsync(String organizationId)
public Void listInvoices(String organizationId, RequestOptions requestOptions)
public CompletableFuture<Void> listInvoicesAsync(String organizationId, RequestOptions requestOptions)
public ApiResponse<Void> listInvoicesWithResponse(String organizationId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> listInvoicesWithResponseAsync(String organizationId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Invoices | none |
| `409` | Managed account authority required; use the returned JackAISaaS accountUrl or portalUrl. | none |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().listInvoices(/* organizationId */ "example");
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsaXN0SW52b2ljZXMifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkubGlzdE1lbWJlcnMiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJsaXN0TWVtYmVycyIsInBhdGgiOiIvdjEvb3JnYW5pemF0aW9ucy97b3JnYW5pemF0aW9uSWR9L21lbWJlcnMiLCJyZXNvdXJjZSI6Im9yZ2FuaXphdGlvbnMoKSIsInNlY3Rpb25fc2hhMjU2IjoiNGQ1ZDY1NWRlZGFjMmRhYmFjYWI5N2YyOGYwNWQxYTYxZDRiNDM0YjYwYzhhYjFiNzA4NTBhZWY1OWNkYmJjYyIsInNpZ25hdHVyZV9zaGEyNTYiOiI4MzMxNGM5ZjkxNDExZWQ3YTZiYjQxNjE2MTllNDc2MGMzZTE5NzlkNTBmMzA5MTNjZGFlZWQ5NDFiZWIzYmI5In0 -->
### `client.organizations().listMembers`

Operation ID: `listMembers`  
Route: `GET` `/v1/organizations/{organizationId}/members`  
Equivalent member: `client.listMembers`  

#### Signature

```java
public Void listMembers(String organizationId)
public CompletableFuture<Void> listMembersAsync(String organizationId)
public ApiResponse<Void> listMembersWithResponse(String organizationId)
public CompletableFuture<ApiResponse<Void>> listMembersWithResponseAsync(String organizationId)
public Void listMembers(String organizationId, RequestOptions requestOptions)
public CompletableFuture<Void> listMembersAsync(String organizationId, RequestOptions requestOptions)
public ApiResponse<Void> listMembersWithResponse(String organizationId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> listMembersWithResponseAsync(String organizationId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Stored members and the plan seat limit | none |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().listMembers(/* organizationId */ "example");
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsaXN0TWVtYmVycyJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkubGlzdE9ic2VydmVkQm94ZXMiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJsaXN0T2JzZXJ2ZWRCb3hlcyIsInBhdGgiOiIvdjEvb3JnYW5pemF0aW9ucy97b3JnYW5pemF0aW9uSWR9L29ic2VydmVkLWJveGVzIiwicmVzb3VyY2UiOiJvcmdhbml6YXRpb25zKCkiLCJzZWN0aW9uX3NoYTI1NiI6Ijc3NTkyYmRjOTg5MGRkOTNmYmQ5M2I3YzZiODI5ZDk0OTU0YzEyZDliNzgzYmNkMTQ5MmY5N2FkYmI4ZDQ2OGEiLCJzaWduYXR1cmVfc2hhMjU2IjoiNzAyYTM3Y2E0ZDdhZDJhNzkxYTIzZjJlZWRlZDM0ODE4N2U0ZGY1ZjAwZjg4ZTU4NTViMTEzNGVhZGU4NmNlNCJ9 -->
### `client.organizations().listObservedBoxes`

Operation ID: `listObservedBoxes`  
Route: `GET` `/v1/organizations/{organizationId}/observed-boxes`  
Equivalent member: `client.listObservedBoxes`  

#### Signature

```java
public Map<String, Object> listObservedBoxes(String organizationId)
public CompletableFuture<Map<String, Object>> listObservedBoxesAsync(String organizationId)
public ApiResponse<Map<String, Object>> listObservedBoxesWithResponse(String organizationId)
public CompletableFuture<ApiResponse<Map<String, Object>>> listObservedBoxesWithResponseAsync(String organizationId)
public Map<String, Object> listObservedBoxes(String organizationId, RequestOptions requestOptions)
public CompletableFuture<Map<String, Object>> listObservedBoxesAsync(String organizationId, RequestOptions requestOptions)
public ApiResponse<Map<String, Object>> listObservedBoxesWithResponse(String organizationId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Map<String, Object>>> listObservedBoxesWithResponseAsync(String organizationId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Up to 100 non-expired client snapshots, private and not cacheable. | application/json (object) |
| `401` | No valid product session. | none |
| `403` | Organization or scope denied. | none |
| `503` | Inventory storage unavailable. | none |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().listObservedBoxes(/* organizationId */ "example");
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsaXN0T2JzZXJ2ZWRCb3hlcyJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkubGlzdFBlcnNpc3RlbnRCb3hPZmZlcnMiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJsaXN0UGVyc2lzdGVudEJveE9mZmVycyIsInBhdGgiOiIvdjEvb3JnYW5pemF0aW9ucy97b3JnYW5pemF0aW9uSWR9L3BlcnNpc3RlbnQtYm94ZXMvb2ZmZXJzIiwicmVzb3VyY2UiOiJvcmdhbml6YXRpb25zKCkiLCJzZWN0aW9uX3NoYTI1NiI6ImRhOGFiMjFjNWY1Nzg3YTEwNGIyN2I5MTI4NzMyMWE0OWRlMzVjOWExYzUzODAzZTQ0MjY0ODMwNzU0ZGNjZjQiLCJzaWduYXR1cmVfc2hhMjU2IjoiNjRlNmVkODUyNDM0MmM2ZjM3MmI1ZWY2ZTliNjVlNjEwMGM4YzQ5Yjk1YWRkNDYzZGRlYjQ5NGQ2NmZmZDc2MyJ9 -->
### `client.organizations().listPersistentBoxOffers`

Operation ID: `listPersistentBoxOffers`  
Route: `GET` `/v1/organizations/{organizationId}/persistent-boxes/offers`  
Equivalent member: `client.listPersistentBoxOffers`  

#### Signature

```java
public Map<String, Object> listPersistentBoxOffers(String organizationId)
public CompletableFuture<Map<String, Object>> listPersistentBoxOffersAsync(String organizationId)
public ApiResponse<Map<String, Object>> listPersistentBoxOffersWithResponse(String organizationId)
public CompletableFuture<ApiResponse<Map<String, Object>>> listPersistentBoxOffersWithResponseAsync(String organizationId)
public Map<String, Object> listPersistentBoxOffers(String organizationId, RequestOptions requestOptions)
public CompletableFuture<Map<String, Object>> listPersistentBoxOffersAsync(String organizationId, RequestOptions requestOptions)
public ApiResponse<Map<String, Object>> listPersistentBoxOffersWithResponse(String organizationId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Map<String, Object>>> listPersistentBoxOffersWithResponseAsync(String organizationId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Private configured offers. | application/json (object) |
| `401` | Product session required. | none |
| `403` | Current read authority denied. | none |
| `503` | Storage or operator offer configuration unavailable. | none |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().listPersistentBoxOffers(/* organizationId */ "example");
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsaXN0UGVyc2lzdGVudEJveE9mZmVycyJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkubGlzdFBlcnNpc3RlbnRCb3hlcyIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6Imxpc3RQZXJzaXN0ZW50Qm94ZXMiLCJwYXRoIjoiL3YxL29yZ2FuaXphdGlvbnMve29yZ2FuaXphdGlvbklkfS9wZXJzaXN0ZW50LWJveGVzIiwicmVzb3VyY2UiOiJvcmdhbml6YXRpb25zKCkiLCJzZWN0aW9uX3NoYTI1NiI6IjQwYTc0MmFlNjJjNGY4MzM3ZDhmZmE3ZjYwMDc2OTQxMDAyNjQ5MGEzZjA2YjY3MmQ4YmZiODJlNmEwOTBlOWIiLCJzaWduYXR1cmVfc2hhMjU2IjoiMWIxNzY4NGNlZmRiNjE2OTcwYTU1MDNjYjA4YmNhZmU5NGI1YmE4MTRlODBmYzYwMDBiOWI4MzZmNzg0N2UwZCJ9 -->
### `client.organizations().listPersistentBoxes`

Operation ID: `listPersistentBoxes`  
Route: `GET` `/v1/organizations/{organizationId}/persistent-boxes`  
Equivalent member: `client.listPersistentBoxes`  

#### Signature

```java
public Map<String, Object> listPersistentBoxes(String organizationId)
public CompletableFuture<Map<String, Object>> listPersistentBoxesAsync(String organizationId)
public ApiResponse<Map<String, Object>> listPersistentBoxesWithResponse(String organizationId)
public CompletableFuture<ApiResponse<Map<String, Object>>> listPersistentBoxesWithResponseAsync(String organizationId)
public Map<String, Object> listPersistentBoxes(String organizationId, RequestOptions requestOptions)
public CompletableFuture<Map<String, Object>> listPersistentBoxesAsync(String organizationId, RequestOptions requestOptions)
public ApiResponse<Map<String, Object>> listPersistentBoxesWithResponse(String organizationId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Map<String, Object>>> listPersistentBoxesWithResponseAsync(String organizationId, RequestOptions requestOptions)
public Map<String, Object> listPersistentBoxes(String organizationId, Long limit)
public CompletableFuture<Map<String, Object>> listPersistentBoxesAsync(String organizationId, Long limit)
public ApiResponse<Map<String, Object>> listPersistentBoxesWithResponse(String organizationId, Long limit)
public CompletableFuture<ApiResponse<Map<String, Object>>> listPersistentBoxesWithResponseAsync(String organizationId, Long limit)
public Map<String, Object> listPersistentBoxes(String organizationId, Long limit, RequestOptions requestOptions)
public CompletableFuture<Map<String, Object>> listPersistentBoxesAsync(String organizationId, Long limit, RequestOptions requestOptions)
public ApiResponse<Map<String, Object>> listPersistentBoxesWithResponse(String organizationId, Long limit, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Map<String, Object>>> listPersistentBoxesWithResponseAsync(String organizationId, Long limit, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |
| `limit` | `query` | no | `integer` | Maximum recent records; duplicates and other query parameters are rejected. |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Bounded stored records, private and not cacheable. limitReached indicates the requested bound was filled, not an exact total or proof that more records exist. | application/json (object) |
| `400` | Invalid query parameters. | none |
| `401` | Missing or rejected product session. | none |
| `403` | Current authority denied access or the organization/product/environment differs. | none |
| `503` | Authority or durable record storage unavailable. | none |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().listPersistentBoxes(/* organizationId */ "example", /* optional: limit */);
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsaXN0UGVyc2lzdGVudEJveGVzIn0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkucHJvdmlzaW9uUGVyc2lzdGVudEJveCIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJwcm92aXNpb25QZXJzaXN0ZW50Qm94IiwicGF0aCI6Ii92MS9vcmdhbml6YXRpb25zL3tvcmdhbml6YXRpb25JZH0vcGVyc2lzdGVudC1ib3hlcyIsInJlc291cmNlIjoib3JnYW5pemF0aW9ucygpIiwic2VjdGlvbl9zaGEyNTYiOiJlMDdiNGRjOGIxM2U1Yjk1NzA3ZTZhODAwYTU0ODNkZmJhZTAxZDcxN2ZiZThlZjdmN2EzOTliOWI4YzdhMDRiIiwic2lnbmF0dXJlX3NoYTI1NiI6IjIxM2RlYTczZjY2NTJjMTBiYjZiNTIwYjQxNzY4M2E3YTNjODk3Y2NiOWM5NzdjYzNjZWY3NjI3NTRhYWU0NzgifQ -->
### `client.organizations().provisionPersistentBox`

Operation ID: `provisionPersistentBox`  
Route: `POST` `/v1/organizations/{organizationId}/persistent-boxes`  
Equivalent member: `client.provisionPersistentBox`  

#### Signature

```java
public Void provisionPersistentBox(String organizationId, Map<String, Object> body)
public CompletableFuture<Void> provisionPersistentBoxAsync(String organizationId, Map<String, Object> body)
public ApiResponse<Void> provisionPersistentBoxWithResponse(String organizationId, Map<String, Object> body)
public CompletableFuture<ApiResponse<Void>> provisionPersistentBoxWithResponseAsync(String organizationId, Map<String, Object> body)
public Void provisionPersistentBox(String organizationId, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Void> provisionPersistentBoxAsync(String organizationId, Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Void> provisionPersistentBoxWithResponse(String organizationId, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> provisionPersistentBoxWithResponseAsync(String organizationId, Map<String, Object> body, RequestOptions requestOptions)
public Void provisionPersistentBox(String organizationId, String idempotencyKey, Map<String, Object> body)
public CompletableFuture<Void> provisionPersistentBoxAsync(String organizationId, String idempotencyKey, Map<String, Object> body)
public ApiResponse<Void> provisionPersistentBoxWithResponse(String organizationId, String idempotencyKey, Map<String, Object> body)
public CompletableFuture<ApiResponse<Void>> provisionPersistentBoxWithResponseAsync(String organizationId, String idempotencyKey, Map<String, Object> body)
public Void provisionPersistentBox(String organizationId, String idempotencyKey, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Void> provisionPersistentBoxAsync(String organizationId, String idempotencyKey, Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Void> provisionPersistentBoxWithResponse(String organizationId, String idempotencyKey, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> provisionPersistentBoxWithResponseAsync(String organizationId, String idempotencyKey, Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |
| `Idempotency-Key` | `header` | no | `string` |  |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Previously recorded running or closed allocation; replayed is true. | none |
| `201` | Provider allocation confirmed and recorded as running. Runtime remains reserved, not measured. | application/json (object) |
| `202` | The reservation is held and the allocation remains unconfirmed. Repeated requests never dispatch create again; operator reconciliation is required. | none |
| `400` | Invalid body, unsupported fields, query parameters or idempotency key. | none |
| `401` | Missing or rejected product session. | none |
| `402` | Missing durable entitlement, bounded allowance or available capacity. | none |
| `403` | Current authority denied the operation or target scope. | none |
| `409` | Idempotency conflict, unresolved prior budget or UTC month boundary. | none |
| `413` | Request body exceeds 4 KiB. | none |
| `503` | Authority, storage, operator offer or independent runtime enforcement unavailable. Missing configuration is refused before reservation. | none |

#### Canonical required-input example

```json
{
  "body": {
    "offer": "example",
    "reserveMinutes": 1
  },
  "content_type": "application/json",
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().provisionPersistentBox(/* organizationId */ "example", /* body */ {"offer": "example", "reserveMinutes": 1}, /* optional: Idempotency-Key */);
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJwcm92aXNpb25QZXJzaXN0ZW50Qm94In0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkucHV0RmxlZXRQb2xpY3kiLCJtZXRob2QiOiJQVVQiLCJvcGVyYXRpb25faWQiOiJwdXRGbGVldFBvbGljeSIsInBhdGgiOiIvdjEvb3JnYW5pemF0aW9ucy97b3JnYW5pemF0aW9uSWR9L2ZsZWV0L3BvbGljeSIsInJlc291cmNlIjoib3JnYW5pemF0aW9ucygpIiwic2VjdGlvbl9zaGEyNTYiOiJmNmEzNDA5OTg0OGM3NTExMTdlOTVlNzgzMzFmZmY0YzUzZmI0MTNkNWZkN2EwNGQ5NWZhOTYwYWQyMzZiYzdmIiwic2lnbmF0dXJlX3NoYTI1NiI6ImFlNWIxM2I4Mzc4Y2U1ZWNiYTU4YjU1MzI3NzI2NmQ1OGQ1MmFlYTM4NTQ3MmNiYmQ3ZTI3NDE4MjFjYWQxNDQifQ -->
### `client.organizations().putFleetPolicy`

Operation ID: `putFleetPolicy`  
Route: `PUT` `/v1/organizations/{organizationId}/fleet/policy`  
Equivalent member: `client.putFleetPolicy`  

#### Signature

```java
public Void putFleetPolicy(String organizationId, Map<String, Object> body)
public CompletableFuture<Void> putFleetPolicyAsync(String organizationId, Map<String, Object> body)
public ApiResponse<Void> putFleetPolicyWithResponse(String organizationId, Map<String, Object> body)
public CompletableFuture<ApiResponse<Void>> putFleetPolicyWithResponseAsync(String organizationId, Map<String, Object> body)
public Void putFleetPolicy(String organizationId, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Void> putFleetPolicyAsync(String organizationId, Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Void> putFleetPolicyWithResponse(String organizationId, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> putFleetPolicyWithResponseAsync(String organizationId, Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Stored policy | none |
| `400` | Invalid or unenforced field | none |

#### Canonical required-input example

```json
{
  "body": {},
  "content_type": "application/json",
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().putFleetPolicy(/* organizationId */ "example", /* body */ {});
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJwdXRGbGVldFBvbGljeSJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkucmVjb25jaWxlUGVyc2lzdGVudEJveCIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJyZWNvbmNpbGVQZXJzaXN0ZW50Qm94IiwicGF0aCI6Ii92MS9vcmdhbml6YXRpb25zL3tvcmdhbml6YXRpb25JZH0vcGVyc2lzdGVudC1ib3hlcy97Ym94SWR9L3JlY29uY2lsZSIsInJlc291cmNlIjoib3JnYW5pemF0aW9ucygpIiwic2VjdGlvbl9zaGEyNTYiOiI2MWJlM2E0ODkwZTc5YjE1ZTY5M2YzMjg5YjRlM2JkMTlkZWI0NWE3ZDk3N2QyZTBiNjZlYzExNDJiYzc1YTU5Iiwic2lnbmF0dXJlX3NoYTI1NiI6IjMyYjAyYzRiZTA1MmJhNGEwOTlmNzE0YTg5ODA0Mzk3ZmExMmExNTY2NjIzODRhNGEzNDE5ZjY2ZmM3YWFlYjMifQ -->
### `client.organizations().reconcilePersistentBox`

Operation ID: `reconcilePersistentBox`  
Route: `POST` `/v1/organizations/{organizationId}/persistent-boxes/{boxId}/reconcile`  
Equivalent member: `client.reconcilePersistentBox`  

#### Signature

```java
public Map<String, Object> reconcilePersistentBox(String organizationId, String boxId, Map<String, Object> body)
public CompletableFuture<Map<String, Object>> reconcilePersistentBoxAsync(String organizationId, String boxId, Map<String, Object> body)
public ApiResponse<Map<String, Object>> reconcilePersistentBoxWithResponse(String organizationId, String boxId, Map<String, Object> body)
public CompletableFuture<ApiResponse<Map<String, Object>>> reconcilePersistentBoxWithResponseAsync(String organizationId, String boxId, Map<String, Object> body)
public Map<String, Object> reconcilePersistentBox(String organizationId, String boxId, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Map<String, Object>> reconcilePersistentBoxAsync(String organizationId, String boxId, Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Map<String, Object>> reconcilePersistentBoxWithResponse(String organizationId, String boxId, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Map<String, Object>>> reconcilePersistentBoxWithResponseAsync(String organizationId, String boxId, Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |
| `boxId` | `path` | yes | `string&lt;uuid&gt;` |  |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Confirmed operation or replayed receipt. | application/json (object) |
| `202` | Operation remains unconfirmed; reconcile its operation ID without repeating the mutation. | application/json (object) |
| `400` | Invalid bounded lifecycle request. | none |
| `401` | Product session required. | none |
| `402` | Durable feature or quota denied. | none |
| `403` | Fresh operation authority denied. | none |
| `404` | Box or operation missing in the exact organization and deployment. | none |
| `409` | Conflicting operation, unresolved evidence or unavailable runtime budget. | none |
| `503` | Authority, storage or matching operator adapter unavailable. | none |

#### Canonical required-input example

```json
{
  "body": {
    "operationId": "00000000-0000-0000-f735-3d332872b96e"
  },
  "content_type": "application/json",
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    },
    {
      "in": "path",
      "name": "boxId",
      "value": "00000000-0000-0000-a264-3ce9cdfbbeff"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().reconcilePersistentBox(/* organizationId */ "example", /* boxId */ "00000000-0000-0000-a264-3ce9cdfbbeff", /* body */ {"operationId": "00000000-0000-0000-f735-3d332872b96e"});
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJyZWNvbmNpbGVQZXJzaXN0ZW50Qm94In0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkucmVtb3ZlTWVtYmVyIiwibWV0aG9kIjoiREVMRVRFIiwib3BlcmF0aW9uX2lkIjoicmVtb3ZlTWVtYmVyIiwicGF0aCI6Ii92MS9vcmdhbml6YXRpb25zL3tvcmdhbml6YXRpb25JZH0vbWVtYmVycy97dXNlcklkfSIsInJlc291cmNlIjoib3JnYW5pemF0aW9ucygpIiwic2VjdGlvbl9zaGEyNTYiOiI0NjE0YjY1MGJmN2Y0YmQyZjc2YjliMDQ2OWFiZWE3NjU4Y2MwOTI5ZmFkMGM0NTFmMTBiNWI0NTI3OWQ4Zjg0Iiwic2lnbmF0dXJlX3NoYTI1NiI6IjBhZjI2ODc0NDIxNmU2ZmQ2MjY1YmJmODJlZTM3NTY3ZDQ1MGRhNTRhM2NlNDFjNDE5ZmNmMGVhYzAyNGFmYjkifQ -->
### `client.organizations().removeMember`

Operation ID: `removeMember`  
Route: `DELETE` `/v1/organizations/{organizationId}/members/{userId}`  
Equivalent member: `client.removeMember`  

#### Signature

```java
public Void removeMember(String organizationId, String userId)
public CompletableFuture<Void> removeMemberAsync(String organizationId, String userId)
public ApiResponse<Void> removeMemberWithResponse(String organizationId, String userId)
public CompletableFuture<ApiResponse<Void>> removeMemberWithResponseAsync(String organizationId, String userId)
public Void removeMember(String organizationId, String userId, RequestOptions requestOptions)
public CompletableFuture<Void> removeMemberAsync(String organizationId, String userId, RequestOptions requestOptions)
public ApiResponse<Void> removeMemberWithResponse(String organizationId, String userId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> removeMemberWithResponseAsync(String organizationId, String userId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |
| `userId` | `path` | yes | `string` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Removed | none |
| `404` | Unknown member | none |
| `409` | Managed account authority required; use the returned JackAISaaS accountUrl or portalUrl. | none |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    },
    {
      "in": "path",
      "name": "userId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().removeMember(/* organizationId */ "example", /* userId */ "example");
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJyZW1vdmVNZW1iZXIifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkuc3RhcnRQZXJzaXN0ZW50Qm94IiwibWV0aG9kIjoiUE9TVCIsIm9wZXJhdGlvbl9pZCI6InN0YXJ0UGVyc2lzdGVudEJveCIsInBhdGgiOiIvdjEvb3JnYW5pemF0aW9ucy97b3JnYW5pemF0aW9uSWR9L3BlcnNpc3RlbnQtYm94ZXMve2JveElkfS9zdGFydCIsInJlc291cmNlIjoib3JnYW5pemF0aW9ucygpIiwic2VjdGlvbl9zaGEyNTYiOiJlYzZlMGUwYThhZDE0YzAyMDQ3MDlmMDhjMDdmMjhjODYzZGQ5YjQ3NjIzYWVhNmYxOGJjYzJhMWU1NDU5NGVlIiwic2lnbmF0dXJlX3NoYTI1NiI6Ijk5ZGZlOGVmYzdkNDExOTRmOGYwMDFkZTk0YjQwYTAyNGRmNTAxNmU3MzQ0OGFkYTg1NGY0OTc1MjEwNWJkNzAifQ -->
### `client.organizations().startPersistentBox`

Operation ID: `startPersistentBox`  
Route: `POST` `/v1/organizations/{organizationId}/persistent-boxes/{boxId}/start`  
Equivalent member: `client.startPersistentBox`  

#### Signature

```java
public Map<String, Object> startPersistentBox(String organizationId, String boxId, Map<String, Object> body)
public CompletableFuture<Map<String, Object>> startPersistentBoxAsync(String organizationId, String boxId, Map<String, Object> body)
public ApiResponse<Map<String, Object>> startPersistentBoxWithResponse(String organizationId, String boxId, Map<String, Object> body)
public CompletableFuture<ApiResponse<Map<String, Object>>> startPersistentBoxWithResponseAsync(String organizationId, String boxId, Map<String, Object> body)
public Map<String, Object> startPersistentBox(String organizationId, String boxId, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Map<String, Object>> startPersistentBoxAsync(String organizationId, String boxId, Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Map<String, Object>> startPersistentBoxWithResponse(String organizationId, String boxId, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Map<String, Object>>> startPersistentBoxWithResponseAsync(String organizationId, String boxId, Map<String, Object> body, RequestOptions requestOptions)
public Map<String, Object> startPersistentBox(String organizationId, String boxId, String idempotencyKey, Map<String, Object> body)
public CompletableFuture<Map<String, Object>> startPersistentBoxAsync(String organizationId, String boxId, String idempotencyKey, Map<String, Object> body)
public ApiResponse<Map<String, Object>> startPersistentBoxWithResponse(String organizationId, String boxId, String idempotencyKey, Map<String, Object> body)
public CompletableFuture<ApiResponse<Map<String, Object>>> startPersistentBoxWithResponseAsync(String organizationId, String boxId, String idempotencyKey, Map<String, Object> body)
public Map<String, Object> startPersistentBox(String organizationId, String boxId, String idempotencyKey, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Map<String, Object>> startPersistentBoxAsync(String organizationId, String boxId, String idempotencyKey, Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Map<String, Object>> startPersistentBoxWithResponse(String organizationId, String boxId, String idempotencyKey, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Map<String, Object>>> startPersistentBoxWithResponseAsync(String organizationId, String boxId, String idempotencyKey, Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |
| `boxId` | `path` | yes | `string&lt;uuid&gt;` |  |
| `Idempotency-Key` | `header` | no | `string` |  |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Confirmed operation or replayed receipt. | application/json (object) |
| `202` | Operation remains unconfirmed; reconcile its operation ID without repeating the mutation. | application/json (object) |
| `400` | Invalid bounded lifecycle request. | none |
| `401` | Product session required. | none |
| `402` | Durable feature or quota denied. | none |
| `403` | Fresh operation authority denied. | none |
| `404` | Box or operation missing in the exact organization and deployment. | none |
| `409` | Conflicting operation, unresolved evidence or unavailable runtime budget. | none |
| `503` | Authority, storage or matching operator adapter unavailable. | none |

#### Canonical required-input example

```json
{
  "body": {
    "reserveMinutes": 1
  },
  "content_type": "application/json",
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    },
    {
      "in": "path",
      "name": "boxId",
      "value": "00000000-0000-0000-d7e8-d81c5e30ed9a"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().startPersistentBox(/* organizationId */ "example", /* boxId */ "00000000-0000-0000-d7e8-d81c5e30ed9a", /* body */ {"reserveMinutes": 1}, /* optional: Idempotency-Key */);
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJzdGFydFBlcnNpc3RlbnRCb3gifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkuc3RvcEJveCIsIm1ldGhvZCI6IkRFTEVURSIsIm9wZXJhdGlvbl9pZCI6InN0b3BCb3giLCJwYXRoIjoiL3YxL29yZ2FuaXphdGlvbnMve29yZ2FuaXphdGlvbklkfS9ib3hlcy97Ym94SWR9IiwicmVzb3VyY2UiOiJvcmdhbml6YXRpb25zKCkiLCJzZWN0aW9uX3NoYTI1NiI6ImQwN2FjNzM3Y2RiMDI2MDkxOGU2Nzg5YzNkOTcxMTYyNzFlZGE0YmY3NTY5ZDk0ZDJlN2ZjODgyY2M3Yzg0YzYiLCJzaWduYXR1cmVfc2hhMjU2IjoiMzgyNmUwNDBhMTIyODE3MGIwNzQ4YzY5MWM4ODk0YTlmNmRiMmZjZWI0OTg3NGE2ZTg4NmU3YzcxM2NhMDI3ZiJ9 -->
### `client.organizations().stopBox`

Operation ID: `stopBox`  
Route: `DELETE` `/v1/organizations/{organizationId}/boxes/{boxId}`  
Equivalent member: `client.stopBox`  

#### Signature

```java
public Void stopBox(String organizationId, String boxId)
public CompletableFuture<Void> stopBoxAsync(String organizationId, String boxId)
public ApiResponse<Void> stopBoxWithResponse(String organizationId, String boxId)
public CompletableFuture<ApiResponse<Void>> stopBoxWithResponseAsync(String organizationId, String boxId)
public Void stopBox(String organizationId, String boxId, RequestOptions requestOptions)
public CompletableFuture<Void> stopBoxAsync(String organizationId, String boxId, RequestOptions requestOptions)
public ApiResponse<Void> stopBoxWithResponse(String organizationId, String boxId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> stopBoxWithResponseAsync(String organizationId, String boxId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |
| `boxId` | `path` | yes | `string&lt;uuid&gt;` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Stopped | none |
| `502` | The provider refused; state unchanged | none |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    },
    {
      "in": "path",
      "name": "boxId",
      "value": "00000000-0000-0000-265e-7c895c60153e"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().stopBox(/* organizationId */ "example", /* boxId */ "00000000-0000-0000-265e-7c895c60153e");
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJzdG9wQm94In0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkuc3RvcFBlcnNpc3RlbnRCb3giLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoic3RvcFBlcnNpc3RlbnRCb3giLCJwYXRoIjoiL3YxL29yZ2FuaXphdGlvbnMve29yZ2FuaXphdGlvbklkfS9wZXJzaXN0ZW50LWJveGVzL3tib3hJZH0vc3RvcCIsInJlc291cmNlIjoib3JnYW5pemF0aW9ucygpIiwic2VjdGlvbl9zaGEyNTYiOiJiMmQ3MjJmNTA0MTkxYWRhNzAxYTk5OGM5MWI0YWY4NGE5MWE5OGQ3OGRiY2ViZjZkNDhlNjQ0ZGU4OTI2NjlmIiwic2lnbmF0dXJlX3NoYTI1NiI6ImQ3MDI2OWMwYjYxZDQxMjcxZDIyOTJkNTU3M2Y2MTNmYmMwMzNkM2E0ODIzYzU4YzAyZjFiYWU3Y2NmYWEyZGEifQ -->
### `client.organizations().stopPersistentBox`

Operation ID: `stopPersistentBox`  
Route: `POST` `/v1/organizations/{organizationId}/persistent-boxes/{boxId}/stop`  
Equivalent member: `client.stopPersistentBox`  

#### Signature

```java
public Map<String, Object> stopPersistentBox(String organizationId, String boxId, Map<String, Object> body)
public CompletableFuture<Map<String, Object>> stopPersistentBoxAsync(String organizationId, String boxId, Map<String, Object> body)
public ApiResponse<Map<String, Object>> stopPersistentBoxWithResponse(String organizationId, String boxId, Map<String, Object> body)
public CompletableFuture<ApiResponse<Map<String, Object>>> stopPersistentBoxWithResponseAsync(String organizationId, String boxId, Map<String, Object> body)
public Map<String, Object> stopPersistentBox(String organizationId, String boxId, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Map<String, Object>> stopPersistentBoxAsync(String organizationId, String boxId, Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Map<String, Object>> stopPersistentBoxWithResponse(String organizationId, String boxId, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Map<String, Object>>> stopPersistentBoxWithResponseAsync(String organizationId, String boxId, Map<String, Object> body, RequestOptions requestOptions)
public Map<String, Object> stopPersistentBox(String organizationId, String boxId, String idempotencyKey, Map<String, Object> body)
public CompletableFuture<Map<String, Object>> stopPersistentBoxAsync(String organizationId, String boxId, String idempotencyKey, Map<String, Object> body)
public ApiResponse<Map<String, Object>> stopPersistentBoxWithResponse(String organizationId, String boxId, String idempotencyKey, Map<String, Object> body)
public CompletableFuture<ApiResponse<Map<String, Object>>> stopPersistentBoxWithResponseAsync(String organizationId, String boxId, String idempotencyKey, Map<String, Object> body)
public Map<String, Object> stopPersistentBox(String organizationId, String boxId, String idempotencyKey, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Map<String, Object>> stopPersistentBoxAsync(String organizationId, String boxId, String idempotencyKey, Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Map<String, Object>> stopPersistentBoxWithResponse(String organizationId, String boxId, String idempotencyKey, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Map<String, Object>>> stopPersistentBoxWithResponseAsync(String organizationId, String boxId, String idempotencyKey, Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |
| `boxId` | `path` | yes | `string&lt;uuid&gt;` |  |
| `Idempotency-Key` | `header` | no | `string` |  |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Confirmed operation or replayed receipt. | application/json (object) |
| `202` | Operation remains unconfirmed; reconcile its operation ID without repeating the mutation. | application/json (object) |
| `400` | Invalid bounded lifecycle request. | none |
| `401` | Product session required. | none |
| `402` | Durable feature or quota denied. | none |
| `403` | Fresh operation authority denied. | none |
| `404` | Box or operation missing in the exact organization and deployment. | none |
| `409` | Conflicting operation, unresolved evidence or unavailable runtime budget. | none |
| `503` | Authority, storage or matching operator adapter unavailable. | none |

#### Canonical required-input example

```json
{
  "body": {},
  "content_type": "application/json",
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    },
    {
      "in": "path",
      "name": "boxId",
      "value": "00000000-0000-0000-978f-a93165cf6579"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().stopPersistentBox(/* organizationId */ "example", /* boxId */ "00000000-0000-0000-978f-a93165cf6579", /* body */ {}, /* optional: Idempotency-Key */);
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJzdG9wUGVyc2lzdGVudEJveCJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkuc3luY09ic2VydmVkQm94ZXMiLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoic3luY09ic2VydmVkQm94ZXMiLCJwYXRoIjoiL3YxL29yZ2FuaXphdGlvbnMve29yZ2FuaXphdGlvbklkfS9vYnNlcnZlZC1ib3hlcy9zeW5jIiwicmVzb3VyY2UiOiJvcmdhbml6YXRpb25zKCkiLCJzZWN0aW9uX3NoYTI1NiI6IjFjODAzOGZkNjc1OWY1ZjUzYzRkNTYxZmYyMTYwZDYyOGFmYzMyZjE4Y2I2OGI4Y2UyMjU5YmRlMWFmMzJiOWEiLCJzaWduYXR1cmVfc2hhMjU2IjoiZjNlZmJmMTBlY2FhZWM1NjI2YjA0OThhNmI3NTc2NzliNDg3YmY2NDZmMjk2MDNmNGYxY2U3YmJjYTE4NTA4YSJ9 -->
### `client.organizations().syncObservedBoxes`

Operation ID: `syncObservedBoxes`  
Route: `POST` `/v1/organizations/{organizationId}/observed-boxes/sync`  
Equivalent member: `client.syncObservedBoxes`  

#### Signature

```java
public Map<String, Object> syncObservedBoxes(String organizationId, Map<String, Object> body)
public CompletableFuture<Map<String, Object>> syncObservedBoxesAsync(String organizationId, Map<String, Object> body)
public ApiResponse<Map<String, Object>> syncObservedBoxesWithResponse(String organizationId, Map<String, Object> body)
public CompletableFuture<ApiResponse<Map<String, Object>>> syncObservedBoxesWithResponseAsync(String organizationId, Map<String, Object> body)
public Map<String, Object> syncObservedBoxes(String organizationId, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Map<String, Object>> syncObservedBoxesAsync(String organizationId, Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Map<String, Object>> syncObservedBoxesWithResponse(String organizationId, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Map<String, Object>>> syncObservedBoxesWithResponseAsync(String organizationId, Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Snapshot accepted; private and not cacheable. | application/json (object) |
| `400` | Invalid observation snapshot. | none |
| `401` | No valid product session. | none |
| `403` | Organization or scope denied. | none |
| `413` | Snapshot exceeds 64 KiB. | none |
| `503` | Inventory storage unavailable. | none |

#### Canonical required-input example

```json
{
  "body": {
    "boxes": [
      {
        "boxId": "example",
        "kind": "provider-list",
        "provider": "example",
        "state": "running"
      }
    ],
    "sourceId": "00000000-0000-0000-ae61-93cfab8e5e4b"
  },
  "content_type": "application/json",
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().syncObservedBoxes(/* organizationId */ "example", /* body */ {"boxes": [{"boxId": "example", "kind": "provider-list", "provider": "example", "state": "running"}], "sourceId": "00000000-0000-0000-ae61-93cfab8e5e4b"});
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJzeW5jT2JzZXJ2ZWRCb3hlcyJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJvcmdhbml6YXRpb25zKCkudXBzZXJ0TWVtYmVyIiwibWV0aG9kIjoiUE9TVCIsIm9wZXJhdGlvbl9pZCI6InVwc2VydE1lbWJlciIsInBhdGgiOiIvdjEvb3JnYW5pemF0aW9ucy97b3JnYW5pemF0aW9uSWR9L21lbWJlcnMiLCJyZXNvdXJjZSI6Im9yZ2FuaXphdGlvbnMoKSIsInNlY3Rpb25fc2hhMjU2IjoiYjg1MTg2YTE0YzFlZmYxMGQxZTdiZTA3YTQwY2M3MWYwNGYxZTY4OWMzNzY2ZjU0YTAyMTFhMjQ4YzkwZGFkNCIsInNpZ25hdHVyZV9zaGEyNTYiOiI4NGQyZTI4ZjZiNTkyNjk0ZjIxMTkxY2RlNWMwNThmODc0ZTUzY2RlN2NiYjQ0NzBhYWY2NzI3ZDA3N2JhMDE1In0 -->
### `client.organizations().upsertMember`

Operation ID: `upsertMember`  
Route: `POST` `/v1/organizations/{organizationId}/members`  
Equivalent member: `client.upsertMember`  

#### Signature

```java
public Void upsertMember(String organizationId, Map<String, Object> body)
public CompletableFuture<Void> upsertMemberAsync(String organizationId, Map<String, Object> body)
public ApiResponse<Void> upsertMemberWithResponse(String organizationId, Map<String, Object> body)
public CompletableFuture<ApiResponse<Void>> upsertMemberWithResponseAsync(String organizationId, Map<String, Object> body)
public Void upsertMember(String organizationId, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Void> upsertMemberAsync(String organizationId, Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Void> upsertMemberWithResponse(String organizationId, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> upsertMemberWithResponseAsync(String organizationId, Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `organizationId` | `path` | yes | `string` |  |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Member updated | none |
| `201` | Member added | none |
| `402` | Seat limit reached or entitlement missing | none |
| `409` | Managed account authority required; use the returned JackAISaaS accountUrl or portalUrl. | none |

#### Canonical required-input example

```json
{
  "body": {
    "email": "example-f35c@example.test",
    "role": "owner"
  },
  "content_type": "application/json",
  "parameters": [
    {
      "in": "path",
      "name": "organizationId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.organizations().upsertMember(/* organizationId */ "example", /* body */ {"email": "example-f35c@example.test", "role": "owner"});
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJ1cHNlcnRNZW1iZXIifQ -->

## Resource `plans()`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJwbGFucygpLmdldCIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6ImdldFBsYW5zIiwicGF0aCI6Ii92MS9wbGFucyIsInJlc291cmNlIjoicGxhbnMoKSIsInNlY3Rpb25fc2hhMjU2IjoiYTEwNDM1Mzg0MGQyYzcxMmIzZTQyOTljMmIzMTc4OWU3ZmU3NmNkOTMzMTEzNzY2NjY4ZjliOWEyN2QzMTg1MSIsInNpZ25hdHVyZV9zaGEyNTYiOiIxOGFhYTVhZTM1YTAzNjlhMzFiYmVjMGE5NmM5MDBkMGEwODE4MjNhMWQ1MDU2Y2NjNmQ5MzIxN2E3Y2VjYmY4In0 -->
### `client.plans().get`

Operation ID: `getPlans`  
Route: `GET` `/v1/plans`  
Equivalent member: `client.getPlans`  

#### Signature

```java
public Void get()
public CompletableFuture<Void> getAsync()
public ApiResponse<Void> getWithResponse()
public CompletableFuture<ApiResponse<Void>> getWithResponseAsync()
public Void get(RequestOptions requestOptions)
public CompletableFuture<Void> getAsync(RequestOptions requestOptions)
public ApiResponse<Void> getWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> getWithResponseAsync(RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | OK | none |
| `409` | Managed account authority required; use the returned JackAISaaS accountUrl or portalUrl. | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.plans().get();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRQbGFucyJ9 -->

## Resource `telemetry()`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJ0ZWxlbWV0cnkoKS5pbmdlc3QiLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoiaW5nZXN0VGVsZW1ldHJ5IiwicGF0aCI6Ii92MS90ZWxlbWV0cnkvaW5nZXN0IiwicmVzb3VyY2UiOiJ0ZWxlbWV0cnkoKSIsInNlY3Rpb25fc2hhMjU2IjoiNmIwNGViZjYxMGRlMjU0NTUzZGY3NGI4YjRjNDYzNzA2ZGY5NGUyZGU0ZjdkMjkzOGM2NmY3MjliNjdkMWU4YyIsInNpZ25hdHVyZV9zaGEyNTYiOiI1ZTMyYWNjNDM3NDM3ZWM0YzM0NzkzNTEzN2VhYzFlZWUwMjZhZmYwMTNmZTAxMDE4NjNmMGIyNWNhMjM5NmU1In0 -->
### `client.telemetry().ingest`

Operation ID: `ingestTelemetry`  
Route: `POST` `/v1/telemetry/ingest`  
Equivalent member: `client.ingestTelemetry`  

#### Signature

```java
public Void ingest(Map<String, Object> body)
public CompletableFuture<Void> ingestAsync(Map<String, Object> body)
public ApiResponse<Void> ingestWithResponse(Map<String, Object> body)
public CompletableFuture<ApiResponse<Void>> ingestWithResponseAsync(Map<String, Object> body)
public Void ingest(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Void> ingestAsync(Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Void> ingestWithResponse(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> ingestWithResponseAsync(Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `201` | Stored | none |
| `400` | Invalid event | none |
| `401` | License required | none |
| `409` | Managed account authority required; use the returned JackAISaaS accountUrl or portalUrl. | none |
| `413` | Body too large | none |
| `503` | Ingestion not configured | none |

#### Canonical required-input example

```json
{
  "body": {},
  "content_type": "application/json",
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.telemetry().ingest(/* body */ {});
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJpbmdlc3RUZWxlbWV0cnkifQ -->

## Resource `waitlist()`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJ3YWl0bGlzdCgpLmxpc3QiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJsaXN0V2FpdGxpc3QiLCJwYXRoIjoiL3YxL3dhaXRsaXN0IiwicmVzb3VyY2UiOiJ3YWl0bGlzdCgpIiwic2VjdGlvbl9zaGEyNTYiOiI5Yjk4NDAxMWNiZTFhMGYzOTNiNzAzYjYyY2M2YTY2NGQ1OWI4OTE2MGM1M2Q2YWFhNzg4ZWNmMTMxOWQ1NGMxIiwic2lnbmF0dXJlX3NoYTI1NiI6ImUxNGY1OWI5MTBjZTczOThkYzViMGZjM2YxNjM4ZjY3N2UyNzc2OWU0MDc5NzU1MTI5NGI5Y2JjNTA3NjVkZWMifQ -->
### `client.waitlist().list`

Operation ID: `listWaitlist`  
Route: `GET` `/v1/waitlist`  
Equivalent member: `client.listWaitlist`  

#### Signature

```java
public Void list()
public CompletableFuture<Void> listAsync()
public ApiResponse<Void> listWithResponse()
public CompletableFuture<ApiResponse<Void>> listWithResponseAsync()
public Void list(RequestOptions requestOptions)
public CompletableFuture<Void> listAsync(RequestOptions requestOptions)
public ApiResponse<Void> listWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> listWithResponseAsync(RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Requests | none |
| `401` | Admin token required | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.waitlist().list();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsaXN0V2FpdGxpc3QifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJ3YWl0bGlzdCgpLnJlcXVlc3RBY2Nlc3MiLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoicmVxdWVzdEFjY2VzcyIsInBhdGgiOiIvdjEvd2FpdGxpc3QiLCJyZXNvdXJjZSI6IndhaXRsaXN0KCkiLCJzZWN0aW9uX3NoYTI1NiI6IjkwNGU5ZDYyMGFiOGU0NDZiNmMyOWI5ZGQ1MTYyN2Q5YjQ1MDdlNTI2ODM1ZTdlMzg2MDZkNTk3NTMyNWEzMzMiLCJzaWduYXR1cmVfc2hhMjU2IjoiMjVhNGQxYTY5NjMxMWYzZjZhNGRlM2NhNDRmYTJjNTU2YmJiYzdmODdhZTY3NDVlM2MxNWFkYTRhMDExZTRkNiJ9 -->
### `client.waitlist().requestAccess`

Operation ID: `requestAccess`  
Route: `POST` `/v1/waitlist`  
Equivalent member: `client.requestAccess`  

#### Signature

```java
public Void requestAccess(Map<String, Object> body)
public CompletableFuture<Void> requestAccessAsync(Map<String, Object> body)
public ApiResponse<Void> requestAccessWithResponse(Map<String, Object> body)
public CompletableFuture<ApiResponse<Void>> requestAccessWithResponseAsync(Map<String, Object> body)
public Void requestAccess(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Void> requestAccessAsync(Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Void> requestAccessWithResponse(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> requestAccessWithResponseAsync(Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `202` | Received | none |
| `400` | Invalid email | none |
| `413` | Body too large | none |
| `429` | Rate limited | none |

#### Canonical required-input example

```json
{
  "body": {},
  "content_type": "application/json",
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.waitlist().requestAccess(/* body */ {});
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJyZXF1ZXN0QWNjZXNzIn0 -->

## Resource `workspaces()`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJ3b3Jrc3BhY2VzKCkuY2xvc2VIb3N0ZWQiLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoiY2xvc2VIb3N0ZWRXb3Jrc3BhY2UiLCJwYXRoIjoiL3YxL3dvcmtzcGFjZXMve3dvcmtzcGFjZUlkfS9jbG9zZSIsInJlc291cmNlIjoid29ya3NwYWNlcygpIiwic2VjdGlvbl9zaGEyNTYiOiJlOGJhMDNmODM2MmU3MGI1ZWIyMGY0YTEzZDNiMDNkZmY1ZTVmNWM5YmM1YTgyODcyNDE4MWU4NDkzYzFkNjY0Iiwic2lnbmF0dXJlX3NoYTI1NiI6IjBjNTRlMWU4ZGY0MDIzY2JkNjU3MzgxMGU3NWZiMTA2MDAyYjJiZGQ3MDc2OTU3OTEzMDgxZWZmZjk2YzRhYzEifQ -->
### `client.workspaces().closeHosted`

Operation ID: `closeHostedWorkspace`  
Route: `POST` `/v1/workspaces/{workspaceId}/close`  
Equivalent member: `client.closeHostedWorkspace`  

#### Signature

```java
public Void closeHosted(String workspaceId)
public CompletableFuture<Void> closeHostedAsync(String workspaceId)
public ApiResponse<Void> closeHostedWithResponse(String workspaceId)
public CompletableFuture<ApiResponse<Void>> closeHostedWithResponseAsync(String workspaceId)
public Void closeHosted(String workspaceId, RequestOptions requestOptions)
public CompletableFuture<Void> closeHostedAsync(String workspaceId, RequestOptions requestOptions)
public ApiResponse<Void> closeHostedWithResponse(String workspaceId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> closeHostedWithResponseAsync(String workspaceId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `workspaceId` | `path` | yes | `string&lt;uuid&gt;` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Authorized workspace state or result | none |
| `400` | Invalid bounded request | none |
| `401` | Product session rejected | none |
| `402` | Hub entitlement or atomic quota denied | none |
| `403` | Operation or fleet policy denied | none |
| `404` | Resource not found in the authorized tenant and product environment | none |
| `409` | Idempotency conflict, incompatible state or cleanup unconfirmed | none |
| `503` | Operator provider, template, storage or authority unavailable | none |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "workspaceId",
      "value": "00000000-0000-0000-6658-e129a559a4dd"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.workspaces().closeHosted(/* workspaceId */ "00000000-0000-0000-6658-e129a559a4dd");
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJjbG9zZUhvc3RlZFdvcmtzcGFjZSJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJ3b3Jrc3BhY2VzKCkuZ2V0SG9zdGVkIiwibWV0aG9kIjoiR0VUIiwib3BlcmF0aW9uX2lkIjoiZ2V0SG9zdGVkV29ya3NwYWNlIiwicGF0aCI6Ii92MS93b3Jrc3BhY2VzL3t3b3Jrc3BhY2VJZH0iLCJyZXNvdXJjZSI6IndvcmtzcGFjZXMoKSIsInNlY3Rpb25fc2hhMjU2IjoiYzdmMTc3ZjM3YzhhNWY1YjM3MGI3N2M3ZjIyMjJkYWQzMDRjOWQ5YzgzMDY0YTgxYTFiZGJkY2QyNmExM2YzZSIsInNpZ25hdHVyZV9zaGEyNTYiOiIzMTNiZTNlYzM1MjMyODc4Nzc4NGNmNjBjM2VmOGM1OTRhZmM3YTdjMmFlMDkyM2I1ZjhlOWJmZjQ3Yzc5Y2I5In0 -->
### `client.workspaces().getHosted`

Operation ID: `getHostedWorkspace`  
Route: `GET` `/v1/workspaces/{workspaceId}`  
Equivalent member: `client.getHostedWorkspace`  

#### Signature

```java
public Void getHosted(String workspaceId)
public CompletableFuture<Void> getHostedAsync(String workspaceId)
public ApiResponse<Void> getHostedWithResponse(String workspaceId)
public CompletableFuture<ApiResponse<Void>> getHostedWithResponseAsync(String workspaceId)
public Void getHosted(String workspaceId, RequestOptions requestOptions)
public CompletableFuture<Void> getHostedAsync(String workspaceId, RequestOptions requestOptions)
public ApiResponse<Void> getHostedWithResponse(String workspaceId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> getHostedWithResponseAsync(String workspaceId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `workspaceId` | `path` | yes | `string&lt;uuid&gt;` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Authorized workspace state or result | none |
| `400` | Invalid bounded request | none |
| `401` | Product session rejected | none |
| `402` | Hub entitlement or atomic quota denied | none |
| `403` | Operation or fleet policy denied | none |
| `404` | Resource not found in the authorized tenant and product environment | none |
| `409` | Idempotency conflict, incompatible state or cleanup unconfirmed | none |
| `503` | Operator provider, template, storage or authority unavailable | none |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "workspaceId",
      "value": "00000000-0000-0000-dd2f-cd2edd1eeb24"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.workspaces().getHosted(/* workspaceId */ "00000000-0000-0000-dd2f-cd2edd1eeb24");
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRIb3N0ZWRXb3Jrc3BhY2UifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJ3b3Jrc3BhY2VzKCkuZ2V0SG9zdGVkT3BlcmF0aW9uIiwibWV0aG9kIjoiR0VUIiwib3BlcmF0aW9uX2lkIjoiZ2V0SG9zdGVkV29ya3NwYWNlT3BlcmF0aW9uIiwicGF0aCI6Ii92MS93b3Jrc3BhY2VzL3t3b3Jrc3BhY2VJZH0vb3BlcmF0aW9ucy97b3BlcmF0aW9uSWR9IiwicmVzb3VyY2UiOiJ3b3Jrc3BhY2VzKCkiLCJzZWN0aW9uX3NoYTI1NiI6IjViYjIwYjg5MThlMzQxNGVmYmRhNTkyMDYzNmM4ODNjMDM5ZDQwOGQwZTgzZjZjNDgwY2YzMWQ2NTk1YjhkZjIiLCJzaWduYXR1cmVfc2hhMjU2IjoiM2Y4YTEyZDhjZDNkNmE5ZDUwNDc5Njc5MzZkMGI0MTQyZDA0ZjBhMGQyNTcwNTNkNTQyMzk4NTBmNmI4N2RjYSJ9 -->
### `client.workspaces().getHostedOperation`

Operation ID: `getHostedWorkspaceOperation`  
Route: `GET` `/v1/workspaces/{workspaceId}/operations/{operationId}`  
Equivalent member: `client.getHostedWorkspaceOperation`  

#### Signature

```java
public Void getHostedOperation(String workspaceId, String operationId)
public CompletableFuture<Void> getHostedOperationAsync(String workspaceId, String operationId)
public ApiResponse<Void> getHostedOperationWithResponse(String workspaceId, String operationId)
public CompletableFuture<ApiResponse<Void>> getHostedOperationWithResponseAsync(String workspaceId, String operationId)
public Void getHostedOperation(String workspaceId, String operationId, RequestOptions requestOptions)
public CompletableFuture<Void> getHostedOperationAsync(String workspaceId, String operationId, RequestOptions requestOptions)
public ApiResponse<Void> getHostedOperationWithResponse(String workspaceId, String operationId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> getHostedOperationWithResponseAsync(String workspaceId, String operationId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `workspaceId` | `path` | yes | `string&lt;uuid&gt;` |  |
| `operationId` | `path` | yes | `string&lt;uuid&gt;` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Authorized workspace state or result | none |
| `400` | Invalid bounded request | none |
| `401` | Product session rejected | none |
| `402` | Hub entitlement or atomic quota denied | none |
| `403` | Operation or fleet policy denied | none |
| `404` | Resource not found in the authorized tenant and product environment | none |
| `409` | Idempotency conflict, incompatible state or cleanup unconfirmed | none |
| `503` | Operator provider, template, storage or authority unavailable | none |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "workspaceId",
      "value": "00000000-0000-0000-7261-284a8b699ebd"
    },
    {
      "in": "path",
      "name": "operationId",
      "value": "00000000-0000-0000-5ba1-19fa55640b6d"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.workspaces().getHostedOperation(/* workspaceId */ "00000000-0000-0000-7261-284a8b699ebd", /* operationId */ "00000000-0000-0000-5ba1-19fa55640b6d");
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRIb3N0ZWRXb3Jrc3BhY2VPcGVyYXRpb24ifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJ3b3Jrc3BhY2VzKCkuZ2V0SG9zdGVkU291cmNlIiwibWV0aG9kIjoiR0VUIiwib3BlcmF0aW9uX2lkIjoiZ2V0SG9zdGVkV29ya3NwYWNlU291cmNlIiwicGF0aCI6Ii92MS93b3Jrc3BhY2VzL3t3b3Jrc3BhY2VJZH0vc291cmNlIiwicmVzb3VyY2UiOiJ3b3Jrc3BhY2VzKCkiLCJzZWN0aW9uX3NoYTI1NiI6IjJhNGY5OGY5ZjA0YTZjMGViMjQ2N2MyNTNjYzI4NTNhZjViM2ZjZDY1NzAwZWNmZWYxZDgxOTRhYWFjYzg1NDgiLCJzaWduYXR1cmVfc2hhMjU2IjoiODRlNWRkODFhZjkzOWNiYjBkNjU3MTdjZjllYWIxMWJlOTgwMzgyZTYzZDNlODVhZjBhMDgyOTQyNDNkY2RmYyJ9 -->
### `client.workspaces().getHostedSource`

Operation ID: `getHostedWorkspaceSource`  
Route: `GET` `/v1/workspaces/{workspaceId}/source`  
Equivalent member: `client.getHostedWorkspaceSource`  

#### Signature

```java
public Void getHostedSource(String workspaceId)
public CompletableFuture<Void> getHostedSourceAsync(String workspaceId)
public ApiResponse<Void> getHostedSourceWithResponse(String workspaceId)
public CompletableFuture<ApiResponse<Void>> getHostedSourceWithResponseAsync(String workspaceId)
public Void getHostedSource(String workspaceId, RequestOptions requestOptions)
public CompletableFuture<Void> getHostedSourceAsync(String workspaceId, RequestOptions requestOptions)
public ApiResponse<Void> getHostedSourceWithResponse(String workspaceId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> getHostedSourceWithResponseAsync(String workspaceId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `workspaceId` | `path` | yes | `string&lt;uuid&gt;` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Authorized workspace state or result | none |
| `400` | Invalid bounded request | none |
| `401` | Product session rejected | none |
| `402` | Hub entitlement or atomic quota denied | none |
| `403` | Operation or fleet policy denied | none |
| `404` | Resource not found in the authorized tenant and product environment | none |
| `409` | Idempotency conflict, incompatible state or cleanup unconfirmed | none |
| `503` | Operator provider, template, storage or authority unavailable | none |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "workspaceId",
      "value": "00000000-0000-0000-43c8-d895a22336ed"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.workspaces().getHostedSource(/* workspaceId */ "00000000-0000-0000-43c8-d895a22336ed");
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRIb3N0ZWRXb3Jrc3BhY2VTb3VyY2UifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJ3b3Jrc3BhY2VzKCkubGlzdEhvc3RlZCIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6Imxpc3RIb3N0ZWRXb3Jrc3BhY2VzIiwicGF0aCI6Ii92MS93b3Jrc3BhY2VzIiwicmVzb3VyY2UiOiJ3b3Jrc3BhY2VzKCkiLCJzZWN0aW9uX3NoYTI1NiI6IjVmYTZhZmEwODM1NWRmNjE5Y2ZkYmZkMTQ5MzNlNjZkNGMwM2FjNDgwM2UyODVlMTNlNjY1NTdlNTc2OTA5OTciLCJzaWduYXR1cmVfc2hhMjU2IjoiOGZlOWZkZGVkNzgzNmNmMGY3NGM3MzAyZDRmYzMyOWVjNWU2ZjNkY2VmMTdhZThiYWVkNDgxMTRhMTA0NWQ4MiJ9 -->
### `client.workspaces().listHosted`

Operation ID: `listHostedWorkspaces`  
Route: `GET` `/v1/workspaces`  
Equivalent member: `client.listHostedWorkspaces`  

#### Signature

```java
public Void listHosted()
public CompletableFuture<Void> listHostedAsync()
public ApiResponse<Void> listHostedWithResponse()
public CompletableFuture<ApiResponse<Void>> listHostedWithResponseAsync()
public Void listHosted(RequestOptions requestOptions)
public CompletableFuture<Void> listHostedAsync(RequestOptions requestOptions)
public ApiResponse<Void> listHostedWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> listHostedWithResponseAsync(RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Authorized workspace state or result | none |
| `400` | Invalid bounded request | none |
| `401` | Product session rejected | none |
| `402` | Hub entitlement or atomic quota denied | none |
| `403` | Operation or fleet policy denied | none |
| `404` | Resource not found in the authorized tenant and product environment | none |
| `409` | Idempotency conflict, incompatible state or cleanup unconfirmed | none |
| `503` | Operator provider, template, storage or authority unavailable | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.workspaces().listHosted();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsaXN0SG9zdGVkV29ya3NwYWNlcyJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJ3b3Jrc3BhY2VzKCkub3Blbkhvc3RlZCIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJvcGVuSG9zdGVkV29ya3NwYWNlIiwicGF0aCI6Ii92MS93b3Jrc3BhY2VzIiwicmVzb3VyY2UiOiJ3b3Jrc3BhY2VzKCkiLCJzZWN0aW9uX3NoYTI1NiI6IjUxNmI0OGZlZDdkMmI5ZTVjMmNlZjJiOTkwNzk4M2UzNjA4MDVjOWQ0ODVmOWUwM2JhNjJmYmI3MTM5YWRhODgiLCJzaWduYXR1cmVfc2hhMjU2IjoiNDQxZDMwN2NlZTM2MGVjOTM1OGI3MGEyMzUyZTY4ZDU3MTY2MzdlYzdiYTlmM2NmNGYxOWVkYmQ1OTI2NjI0ZCJ9 -->
### `client.workspaces().openHosted`

Operation ID: `openHostedWorkspace`  
Route: `POST` `/v1/workspaces`  
Equivalent member: `client.openHostedWorkspace`  

#### Signature

```java
public Void openHosted(Map<String, Object> body)
public CompletableFuture<Void> openHostedAsync(Map<String, Object> body)
public ApiResponse<Void> openHostedWithResponse(Map<String, Object> body)
public CompletableFuture<ApiResponse<Void>> openHostedWithResponseAsync(Map<String, Object> body)
public Void openHosted(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Void> openHostedAsync(Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Void> openHostedWithResponse(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> openHostedWithResponseAsync(Map<String, Object> body, RequestOptions requestOptions)
public Void openHosted(String idempotencyKey, Map<String, Object> body)
public CompletableFuture<Void> openHostedAsync(String idempotencyKey, Map<String, Object> body)
public ApiResponse<Void> openHostedWithResponse(String idempotencyKey, Map<String, Object> body)
public CompletableFuture<ApiResponse<Void>> openHostedWithResponseAsync(String idempotencyKey, Map<String, Object> body)
public Void openHosted(String idempotencyKey, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Void> openHostedAsync(String idempotencyKey, Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Void> openHostedWithResponse(String idempotencyKey, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> openHostedWithResponseAsync(String idempotencyKey, Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `Idempotency-Key` | `header` | no | `string` | Required here or in the idempotencyKey body field. Replays never allocate or execute again. |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Authorized workspace state or result | none |
| `201` | Prepared workspace; source and provider allocation recorded durably | none |
| `400` | Invalid bounded request | none |
| `401` | Product session rejected | none |
| `402` | Hub entitlement or atomic quota denied | none |
| `403` | Operation or fleet policy denied | none |
| `404` | Resource not found in the authorized tenant and product environment | none |
| `409` | Idempotency conflict, incompatible state or cleanup unconfirmed | none |
| `503` | Operator provider, template, storage or authority unavailable | none |

#### Canonical required-input example

```json
{
  "body": {},
  "content_type": "application/json",
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.workspaces().openHosted(/* body */ {}, /* optional: Idempotency-Key */);
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJvcGVuSG9zdGVkV29ya3NwYWNlIn0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJ3b3Jrc3BhY2VzKCkucmVjb3Zlckhvc3RlZCIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJyZWNvdmVySG9zdGVkV29ya3NwYWNlIiwicGF0aCI6Ii92MS93b3Jrc3BhY2VzL3t3b3Jrc3BhY2VJZH0vcmVjb3ZlciIsInJlc291cmNlIjoid29ya3NwYWNlcygpIiwic2VjdGlvbl9zaGEyNTYiOiI0YzJlYzU1MDg3NWFmOTBkMzM4YmEwZjhjNGFhODhiMThjNWRiMTIzOTM5YzAxM2E0MTk2NzMxMTU3MjAxN2ExIiwic2lnbmF0dXJlX3NoYTI1NiI6Ijc5N2VkZmM0MjZjNWM1Y2IzNGM5Y2FmMjJjMzIwNjA1NTM4YjI4YTY5OTBiNGIxYjY4Y2E3N2Y2NjlmM2YyY2EifQ -->
### `client.workspaces().recoverHosted`

Operation ID: `recoverHostedWorkspace`  
Route: `POST` `/v1/workspaces/{workspaceId}/recover`  
Equivalent member: `client.recoverHostedWorkspace`  

#### Signature

```java
public Void recoverHosted(String workspaceId, Map<String, Object> body)
public CompletableFuture<Void> recoverHostedAsync(String workspaceId, Map<String, Object> body)
public ApiResponse<Void> recoverHostedWithResponse(String workspaceId, Map<String, Object> body)
public CompletableFuture<ApiResponse<Void>> recoverHostedWithResponseAsync(String workspaceId, Map<String, Object> body)
public Void recoverHosted(String workspaceId, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Void> recoverHostedAsync(String workspaceId, Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Void> recoverHostedWithResponse(String workspaceId, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> recoverHostedWithResponseAsync(String workspaceId, Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `workspaceId` | `path` | yes | `string&lt;uuid&gt;` |  |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Authorized workspace state or result | none |
| `202` | No verified terminal receipt yet; workspace remains unavailable for new commands | none |
| `400` | Invalid bounded request | none |
| `401` | Product session rejected | none |
| `402` | Hub entitlement or atomic quota denied | none |
| `403` | Operation or fleet policy denied | none |
| `404` | Resource not found in the authorized tenant and product environment | none |
| `409` | Idempotency conflict, incompatible state or cleanup unconfirmed | none |
| `503` | Operator provider, template, storage or authority unavailable | none |

#### Canonical required-input example

```json
{
  "body": {
    "operationId": "00000000-0000-0000-d4ac-b0b84827b6d9"
  },
  "content_type": "application/json",
  "parameters": [
    {
      "in": "path",
      "name": "workspaceId",
      "value": "00000000-0000-0000-973a-c9ae0260973d"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.workspaces().recoverHosted(/* workspaceId */ "00000000-0000-0000-973a-c9ae0260973d", /* body */ {"operationId": "00000000-0000-0000-d4ac-b0b84827b6d9"});
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJyZWNvdmVySG9zdGVkV29ya3NwYWNlIn0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJ3b3Jrc3BhY2VzKCkucnVuSG9zdGVkIiwibWV0aG9kIjoiUE9TVCIsIm9wZXJhdGlvbl9pZCI6InJ1bkhvc3RlZFdvcmtzcGFjZSIsInBhdGgiOiIvdjEvd29ya3NwYWNlcy97d29ya3NwYWNlSWR9L3J1biIsInJlc291cmNlIjoid29ya3NwYWNlcygpIiwic2VjdGlvbl9zaGEyNTYiOiJiMTIwNGE0ZTJkMTJiOTA4YTRlNTUyOTU4NGM2MTI1YTdkOGQ4NmVhODE5YzU1ZWQ4NDZlMWNhNGUyNTQxZTEyIiwic2lnbmF0dXJlX3NoYTI1NiI6Ijg5NmUwYzQ5NmE0YTNlYjAwMzFiNTkyMTk4MWRjNTAzYzExOGIxOTA2OTI1ZDU2ZDdjYzdhMWY3ZjU4MDhjOTkifQ -->
### `client.workspaces().runHosted`

Operation ID: `runHostedWorkspace`  
Route: `POST` `/v1/workspaces/{workspaceId}/run`  
Equivalent member: `client.runHostedWorkspace`  

#### Signature

```java
public Void runHosted(String workspaceId, Map<String, Object> body)
public CompletableFuture<Void> runHostedAsync(String workspaceId, Map<String, Object> body)
public ApiResponse<Void> runHostedWithResponse(String workspaceId, Map<String, Object> body)
public CompletableFuture<ApiResponse<Void>> runHostedWithResponseAsync(String workspaceId, Map<String, Object> body)
public Void runHosted(String workspaceId, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Void> runHostedAsync(String workspaceId, Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Void> runHostedWithResponse(String workspaceId, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> runHostedWithResponseAsync(String workspaceId, Map<String, Object> body, RequestOptions requestOptions)
public Void runHosted(String workspaceId, String idempotencyKey, Map<String, Object> body)
public CompletableFuture<Void> runHostedAsync(String workspaceId, String idempotencyKey, Map<String, Object> body)
public ApiResponse<Void> runHostedWithResponse(String workspaceId, String idempotencyKey, Map<String, Object> body)
public CompletableFuture<ApiResponse<Void>> runHostedWithResponseAsync(String workspaceId, String idempotencyKey, Map<String, Object> body)
public Void runHosted(String workspaceId, String idempotencyKey, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Void> runHostedAsync(String workspaceId, String idempotencyKey, Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Void> runHostedWithResponse(String workspaceId, String idempotencyKey, Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> runHostedWithResponseAsync(String workspaceId, String idempotencyKey, Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `workspaceId` | `path` | yes | `string&lt;uuid&gt;` |  |
| `Idempotency-Key` | `header` | no | `string` | Required here or in the idempotencyKey body field. Replays never allocate or execute again. |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Authorized workspace state or result | none |
| `202` | Running or uncertain operation; inspect or explicitly recover, never resend with a new key | none |
| `400` | Invalid bounded request | none |
| `401` | Product session rejected | none |
| `402` | Hub entitlement or atomic quota denied | none |
| `403` | Operation or fleet policy denied | none |
| `404` | Resource not found in the authorized tenant and product environment | none |
| `409` | Idempotency conflict, incompatible state or cleanup unconfirmed | none |
| `503` | Operator provider, template, storage or authority unavailable | none |

#### Canonical required-input example

```json
{
  "body": {
    "command": "example"
  },
  "content_type": "application/json",
  "parameters": [
    {
      "in": "path",
      "name": "workspaceId",
      "value": "00000000-0000-0000-4862-6c003dd1756b"
    }
  ]
}
```

#### SDK call example

Example status: `generated`  
```java
var result = client.workspaces().runHosted(/* workspaceId */ "00000000-0000-0000-4862-6c003dd1756b", /* body */ {"command": "example"}, /* optional: Idempotency-Key */);
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJydW5Ib3N0ZWRXb3Jrc3BhY2UifQ -->

