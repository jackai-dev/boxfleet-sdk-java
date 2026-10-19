# BoxFleet Java API

<!-- omniwrap-api-reference eyJjb250cmFjdF9maW5nZXJwcmludCI6IjczZGVjMDgzOTQyOGYzOTg1NzhkZmM5ODZmNDc3ODZmNTMwYzZkMWE1Y2VlNjM2MGJmY2UxZDAwN2ViNjY1MzYiLCJvcGVyYXRpb25fY291bnQiOjI1LCJyZW5kZXJlciI6ImphdmEiLCJ2ZXJzaW9uIjoiMS40LjAifQ -->

This generated index is tied to Semantic IR `1.14.0` and contract fingerprint `73dec0839428f398578dfc986f47786f530c6d1a5cee6360bfce1d007eb66536`. Every operation below is rendered from the same semantic contract and artifact-attested public member allocation as the SDK.

SDK maturity: **experimental**  
Artifact evidence: [`omniwrap-artifact.json`](omniwrap-artifact.json) binds this file by SHA-256 and is revalidated by the package gate.

## Client hooks and tracing

`ClientOptions.builder().hooks(RequestHooks)` registers four callbacks. Every attempt starts with `beforeRequest` and ends with exactly one of `onRetry` (another attempt follows), `afterResponse` (the success the call returns) or `onError` (the failure the call reports). Each receives the operation id, the HTTP method, the URL, the request headers, the attempt number (from 1), the time elapsed since the call started and, once the server answered, the HTTP status. No context carries a credential: `Authorization`, `Proxy-Authorization`, `Cookie`, every API-key header and API-key query parameter, and any configured credential value read `[redacted]`. Every context is an immutable `HookContext` record: no hook can change the request.

`ClientOptions.builder().tracer(RequestTracer)` opens one span per call through the tracer interface this SDK defines, named after the operation id, with `http.request.method`, `http.response.status_code` and `http.request.resend_count`. It needs no tracing library; README.md maps it onto the OpenTelemetry API.

## Shared types

- `CapabilitiesResponse`
- `CloudBox`
- `CloudBoxActionRequest`
- `CloudBoxActionResponse`
- `CloudBoxEnvelope`
- `CloudBoxListResponse`
- `CreateCloudBoxRequest`
- `FleetPolicyUpdateRequest`
- `HealthResponse`
- `InspectProjectRequest`
- `JobExecutionResponse`
- `JobListResponse`
- `JobLogsResponse`
- `JobSummary`
- `ModsCatalogResponse`
- `OrganizationFleetResponse`
- `OrganizationMember`
- `OrganizationMembersResponse`
- `ProjectInspectionPlan`
- `ProvidersResponse`
- `SaasPlansResponse`
- `StartAgentJobRequest`
- `StartGithubJobRequest`
- `StartProjectJobRequest`
- `SyncCloudBoxVaultRequest`
- `SyncCloudBoxVaultResponse`
- `UpsertOrganizationMemberRequest`
- `WaitlistListResponse`
- `WaitlistRegisterRequest`
- `WaitlistRegisterResponse`
- `WhiteLabelCloudCatalog`

## Resource `cloud`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJjcmVhdGVDbG91ZEJveCIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJjcmVhdGVDbG91ZEJveCIsInBhdGgiOiIvdjEvY2xvdWQvYm94ZXMiLCJyZXNvdXJjZSI6ImNsb3VkIiwic2VjdGlvbl9zaGEyNTYiOiJhYmEyNjQ1ZTliZmIwZmFiMjZmMTBjMmI2ZTI3YzU5MTE5MTgxY2ViM2NjMTM3MWE0ODk1OTVhZmEwODcxNzAxIiwic2lnbmF0dXJlX3NoYTI1NiI6ImZlNDc2ZWY4N2Q1OGI0OTI3ZTY5ODE2OTc0ZTYwNzMwYjExZDExZDJjM2M0N2NhNWI1ZmM3Mzk3NTJjNWI5YzgifQ -->
### `client.createCloudBox`

Operation ID: `createCloudBox`  
Route: `POST` `/v1/cloud/boxes`  

#### Signature

```java
public CloudBoxEnvelope createCloudBox(CreateCloudBoxRequest body)
public ApiResponse<CloudBoxEnvelope> createCloudBoxWithResponse(CreateCloudBoxRequest body)
public CompletableFuture<ApiResponse<CloudBoxEnvelope>> createCloudBoxWithResponseAsync(CreateCloudBoxRequest body)
public CompletableFuture<CloudBoxEnvelope> createCloudBoxAsync(CreateCloudBoxRequest body)
public CloudBoxEnvelope createCloudBox(CreateCloudBoxRequest body, RequestOptions requestOptions)
public CompletableFuture<CloudBoxEnvelope> createCloudBoxAsync(CreateCloudBoxRequest body, RequestOptions requestOptions)
public ApiResponse<CloudBoxEnvelope> createCloudBoxWithResponse(CreateCloudBoxRequest body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<CloudBoxEnvelope>> createCloudBoxWithResponseAsync(CreateCloudBoxRequest body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `CreateCloudBoxRequest` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `201` | Provisioned white-label box | application/json (CloudBoxEnvelope) |

#### Canonical required-input example

```json
{
  "body": {},
  "content_type": "application/json",
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJjcmVhdGVDbG91ZEJveCJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJnZXRXaGl0ZUxhYmVsQ2xvdWRDYXRhbG9nIiwibWV0aG9kIjoiR0VUIiwib3BlcmF0aW9uX2lkIjoiZ2V0V2hpdGVMYWJlbENsb3VkQ2F0YWxvZyIsInBhdGgiOiIvdjEvY2xvdWQvY2F0YWxvZyIsInJlc291cmNlIjoiY2xvdWQiLCJzZWN0aW9uX3NoYTI1NiI6IjcwMGE3NjNhZGVkODRjNzIwZjg0NDk5ZTVjOWNhMjE5ZTBmZmVmZTE3YTc4YzE4MjEzOWUxOWIxYjBmOGVmMTEiLCJzaWduYXR1cmVfc2hhMjU2IjoiNGY5ZTE1YjYzZGVlYjJmZTUxZTQwOTU0NjY2NmMzYTRkYmI4MjhlYzJhOWQzOThlNmY1MGI1NTQ2MzNjMjljMiJ9 -->
### `client.getWhiteLabelCloudCatalog`

Operation ID: `getWhiteLabelCloudCatalog`  
Route: `GET` `/v1/cloud/catalog`  

#### Signature

```java
public WhiteLabelCloudCatalog getWhiteLabelCloudCatalog()
public ApiResponse<WhiteLabelCloudCatalog> getWhiteLabelCloudCatalogWithResponse()
public CompletableFuture<ApiResponse<WhiteLabelCloudCatalog>> getWhiteLabelCloudCatalogWithResponseAsync()
public CompletableFuture<WhiteLabelCloudCatalog> getWhiteLabelCloudCatalogAsync()
public WhiteLabelCloudCatalog getWhiteLabelCloudCatalog(RequestOptions requestOptions)
public CompletableFuture<WhiteLabelCloudCatalog> getWhiteLabelCloudCatalogAsync(RequestOptions requestOptions)
public ApiResponse<WhiteLabelCloudCatalog> getWhiteLabelCloudCatalogWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<WhiteLabelCloudCatalog>> getWhiteLabelCloudCatalogWithResponseAsync(RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | White-Label Cloud catalog | application/json (WhiteLabelCloudCatalog) |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRXaGl0ZUxhYmVsQ2xvdWRDYXRhbG9nIn0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJsaXN0Q2xvdWRCb3hlcyIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6Imxpc3RDbG91ZEJveGVzIiwicGF0aCI6Ii92MS9jbG91ZC9ib3hlcyIsInJlc291cmNlIjoiY2xvdWQiLCJzZWN0aW9uX3NoYTI1NiI6IjkxODAwZGNmOTYxMjA3NDVhYTVjY2Y5YWZjZGRhNzI3MmQzMmNjYzk4NjE0ZTdlYWViYjA1Y2RjZTdhMGJmYWIiLCJzaWduYXR1cmVfc2hhMjU2IjoiMDk0MmJkOTYwNDc5Yzc3NjcxZTdjNjlkYmI3ZjZjODI5NWM5Nzc1NjgwMTEyMzJmOTE3ZjhmYWM1NjJlYjlhZiJ9 -->
### `client.listCloudBoxes`

Operation ID: `listCloudBoxes`  
Route: `GET` `/v1/cloud/boxes`  

#### Signature

```java
public CloudBoxListResponse listCloudBoxes()
public ApiResponse<CloudBoxListResponse> listCloudBoxesWithResponse()
public CompletableFuture<ApiResponse<CloudBoxListResponse>> listCloudBoxesWithResponseAsync()
public CompletableFuture<CloudBoxListResponse> listCloudBoxesAsync()
public CloudBoxListResponse listCloudBoxes(RequestOptions requestOptions)
public CompletableFuture<CloudBoxListResponse> listCloudBoxesAsync(RequestOptions requestOptions)
public ApiResponse<CloudBoxListResponse> listCloudBoxesWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<CloudBoxListResponse>> listCloudBoxesWithResponseAsync(RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | White-label cloud boxes | application/json (CloudBoxListResponse) |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsaXN0Q2xvdWRCb3hlcyJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJwZXJmb3JtQ2xvdWRCb3hBY3Rpb24iLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoicGVyZm9ybUNsb3VkQm94QWN0aW9uIiwicGF0aCI6Ii92MS9jbG91ZC9ib3hlcy97Ym94SWR9L2FjdGlvbiIsInJlc291cmNlIjoiY2xvdWQiLCJzZWN0aW9uX3NoYTI1NiI6Ijk1MzgwOGYwOGY5Nzc5ZWU1MzZmNjUxNDkxZmU5ZTAxY2RhN2QwNDE0YTAxMTIzM2YzMmUzZGE0ZjNiZDA5ZmIiLCJzaWduYXR1cmVfc2hhMjU2IjoiZDlmYzZkYjA4NTZhZWQ4OTA4YzA4ZjhiZDIwNzdiOTU3ZWVkYTE0NzAzZDQ3MjZhMjJmMmIxZDcwZTU0YmFmZCJ9 -->
### `client.performCloudBoxAction`

Operation ID: `performCloudBoxAction`  
Route: `POST` `/v1/cloud/boxes/{boxId}/action`  

#### Signature

```java
public CloudBoxActionResponse performCloudBoxAction(String boxId, CloudBoxActionRequest body)
public ApiResponse<CloudBoxActionResponse> performCloudBoxActionWithResponse(String boxId, CloudBoxActionRequest body)
public CompletableFuture<ApiResponse<CloudBoxActionResponse>> performCloudBoxActionWithResponseAsync(String boxId, CloudBoxActionRequest body)
public CompletableFuture<CloudBoxActionResponse> performCloudBoxActionAsync(String boxId, CloudBoxActionRequest body)
public CloudBoxActionResponse performCloudBoxAction(String boxId, CloudBoxActionRequest body, RequestOptions requestOptions)
public CompletableFuture<CloudBoxActionResponse> performCloudBoxActionAsync(String boxId, CloudBoxActionRequest body, RequestOptions requestOptions)
public ApiResponse<CloudBoxActionResponse> performCloudBoxActionWithResponse(String boxId, CloudBoxActionRequest body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<CloudBoxActionResponse>> performCloudBoxActionWithResponseAsync(String boxId, CloudBoxActionRequest body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `boxId` | `path` | yes | `string` |  |
| `body` | body | yes | `CloudBoxActionRequest` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Cloud box action result | application/json (CloudBoxActionResponse) |

#### Canonical required-input example

```json
{
  "body": {
    "action": "suspend"
  },
  "content_type": "application/json",
  "parameters": [
    {
      "in": "path",
      "name": "boxId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJwZXJmb3JtQ2xvdWRCb3hBY3Rpb24ifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJzeW5jQ2xvdWRCb3hWYXVsdCIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJzeW5jQ2xvdWRCb3hWYXVsdCIsInBhdGgiOiIvdjEvY2xvdWQvYm94ZXMve2JveElkfS92YXVsdCIsInJlc291cmNlIjoiY2xvdWQiLCJzZWN0aW9uX3NoYTI1NiI6Ijg2ODZkNjNhOWU3NTRmNWY3NzM3NjM5MjZmNTdiNjA3NjA1Yzk0YjM4MTdhNmM2ZDBjY2M0NWYyY2YyYjE5MzMiLCJzaWduYXR1cmVfc2hhMjU2IjoiY2Q2MDcyZjE4NGZmZjJiMjQzNTg4NGRkYjQxZDI4MWYyMGYxYTg2NjQxNjk4N2UzOTljNGY4ZGY4MzhjN2ExNCJ9 -->
### `client.syncCloudBoxVault`

Operation ID: `syncCloudBoxVault`  
Route: `POST` `/v1/cloud/boxes/{boxId}/vault`  

#### Signature

```java
public SyncCloudBoxVaultResponse syncCloudBoxVault(String boxId, SyncCloudBoxVaultRequest body)
public ApiResponse<SyncCloudBoxVaultResponse> syncCloudBoxVaultWithResponse(String boxId, SyncCloudBoxVaultRequest body)
public CompletableFuture<ApiResponse<SyncCloudBoxVaultResponse>> syncCloudBoxVaultWithResponseAsync(String boxId, SyncCloudBoxVaultRequest body)
public CompletableFuture<SyncCloudBoxVaultResponse> syncCloudBoxVaultAsync(String boxId, SyncCloudBoxVaultRequest body)
public SyncCloudBoxVaultResponse syncCloudBoxVault(String boxId, SyncCloudBoxVaultRequest body, RequestOptions requestOptions)
public CompletableFuture<SyncCloudBoxVaultResponse> syncCloudBoxVaultAsync(String boxId, SyncCloudBoxVaultRequest body, RequestOptions requestOptions)
public ApiResponse<SyncCloudBoxVaultResponse> syncCloudBoxVaultWithResponse(String boxId, SyncCloudBoxVaultRequest body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<SyncCloudBoxVaultResponse>> syncCloudBoxVaultWithResponseAsync(String boxId, SyncCloudBoxVaultRequest body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `boxId` | `path` | yes | `string` |  |
| `body` | body | yes | `SyncCloudBoxVaultRequest` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Vault sync receipt (key names only, zero secret values echoed) | application/json (SyncCloudBoxVaultResponse) |

#### Canonical required-input example

```json
{
  "body": {
    "keys": [
      "example"
    ]
  },
  "content_type": "application/json",
  "parameters": [
    {
      "in": "path",
      "name": "boxId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJzeW5jQ2xvdWRCb3hWYXVsdCJ9 -->

## Resource `fleet`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJnZXRPcmdhbml6YXRpb25GbGVldCIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6ImdldE9yZ2FuaXphdGlvbkZsZWV0IiwicGF0aCI6Ii92MS9vcmdhbml6YXRpb25zL3tvcmdJZH0vZmxlZXQiLCJyZXNvdXJjZSI6ImZsZWV0Iiwic2VjdGlvbl9zaGEyNTYiOiIxODllMmNkMzNkZDk0ZjBkZTNmNjg3OGQwZWQ5YmI2MDAyYTBkZWEyNzVhYTY3ZTZhN2E2M2ZjYzY2MGJjMDVkIiwic2lnbmF0dXJlX3NoYTI1NiI6ImRhMDQ2MTliZGI3YzAwZTUzMDIyNDdhN2ZjOTBjMTc2NTQ5YjE3YmJmZmM0YmE3ODk2YjE4ZGNhOTk4NjEwOTIifQ -->
### `client.getOrganizationFleet`

Operation ID: `getOrganizationFleet`  
Route: `GET` `/v1/organizations/{orgId}/fleet`  

#### Signature

```java
public OrganizationFleetResponse getOrganizationFleet(String orgId)
public ApiResponse<OrganizationFleetResponse> getOrganizationFleetWithResponse(String orgId)
public CompletableFuture<ApiResponse<OrganizationFleetResponse>> getOrganizationFleetWithResponseAsync(String orgId)
public CompletableFuture<OrganizationFleetResponse> getOrganizationFleetAsync(String orgId)
public OrganizationFleetResponse getOrganizationFleet(String orgId, RequestOptions requestOptions)
public CompletableFuture<OrganizationFleetResponse> getOrganizationFleetAsync(String orgId, RequestOptions requestOptions)
public ApiResponse<OrganizationFleetResponse> getOrganizationFleetWithResponse(String orgId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<OrganizationFleetResponse>> getOrganizationFleetWithResponseAsync(String orgId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `orgId` | `path` | yes | `string` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Organization fleet park overview | application/json (OrganizationFleetResponse) |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "orgId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRPcmdhbml6YXRpb25GbGVldCJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJsaXN0T3JnYW5pemF0aW9uTWVtYmVycyIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6Imxpc3RPcmdhbml6YXRpb25NZW1iZXJzIiwicGF0aCI6Ii92MS9vcmdhbml6YXRpb25zL3tvcmdJZH0vbWVtYmVycyIsInJlc291cmNlIjoiZmxlZXQiLCJzZWN0aW9uX3NoYTI1NiI6IjcxMDk3NDhlNjViMDUyZDkxMTBlN2RjMjkwZmY1YjgwYjFkODE5Y2E0OWJlMTQzODJiMDkwYTBkNzE1MzQ1YWYiLCJzaWduYXR1cmVfc2hhMjU2IjoiZTU3OGQzNTNhMmE1NTQ2ZmRhNTI1YjI2MmIxNzUzZDE1MDNhZThiYTcxYmE1Yjg4MWM3ODRjMGU1NzE3OTEwMiJ9 -->
### `client.listOrganizationMembers`

Operation ID: `listOrganizationMembers`  
Route: `GET` `/v1/organizations/{orgId}/members`  

#### Signature

```java
public OrganizationMembersResponse listOrganizationMembers(String orgId)
public ApiResponse<OrganizationMembersResponse> listOrganizationMembersWithResponse(String orgId)
public CompletableFuture<ApiResponse<OrganizationMembersResponse>> listOrganizationMembersWithResponseAsync(String orgId)
public CompletableFuture<OrganizationMembersResponse> listOrganizationMembersAsync(String orgId)
public OrganizationMembersResponse listOrganizationMembers(String orgId, RequestOptions requestOptions)
public CompletableFuture<OrganizationMembersResponse> listOrganizationMembersAsync(String orgId, RequestOptions requestOptions)
public ApiResponse<OrganizationMembersResponse> listOrganizationMembersWithResponse(String orgId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<OrganizationMembersResponse>> listOrganizationMembersWithResponseAsync(String orgId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `orgId` | `path` | yes | `string` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Organization members list | application/json (OrganizationMembersResponse) |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "orgId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsaXN0T3JnYW5pemF0aW9uTWVtYmVycyJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJsaXN0U2Fhc1BsYW5zIiwibWV0aG9kIjoiR0VUIiwib3BlcmF0aW9uX2lkIjoibGlzdFNhYXNQbGFucyIsInBhdGgiOiIvdjEvc2Fhcy9wbGFucyIsInJlc291cmNlIjoiZmxlZXQiLCJzZWN0aW9uX3NoYTI1NiI6ImM5ZTVmYTE3NzU0NmIwNzdkNzM1OTgyZjIwYmJjZjliODRhY2I2OWEwZTc2MzcwMmI1OWY5M2RjMWQ4ZDg4OWQiLCJzaWduYXR1cmVfc2hhMjU2IjoiMzA0ZGExNWY1ZDYyMDhjMmRkODI1YmVjNWY3NGZiODU1MjNkYTk1ZmU2MTRhMTA3YTg3ZmZkMjAzMjVhNWNlYSJ9 -->
### `client.listSaasPlans`

Operation ID: `listSaasPlans`  
Route: `GET` `/v1/saas/plans`  

#### Signature

```java
public SaasPlansResponse listSaasPlans()
public ApiResponse<SaasPlansResponse> listSaasPlansWithResponse()
public CompletableFuture<ApiResponse<SaasPlansResponse>> listSaasPlansWithResponseAsync()
public CompletableFuture<SaasPlansResponse> listSaasPlansAsync()
public SaasPlansResponse listSaasPlans(RequestOptions requestOptions)
public CompletableFuture<SaasPlansResponse> listSaasPlansAsync(RequestOptions requestOptions)
public ApiResponse<SaasPlansResponse> listSaasPlansWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<SaasPlansResponse>> listSaasPlansWithResponseAsync(RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | SaaS plan catalog | application/json (SaasPlansResponse) |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsaXN0U2Fhc1BsYW5zIn0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJsaXN0V2FpdGxpc3RJbnZpdGVzIiwibWV0aG9kIjoiR0VUIiwib3BlcmF0aW9uX2lkIjoibGlzdFdhaXRsaXN0SW52aXRlcyIsInBhdGgiOiIvdjEvd2FpdGxpc3QiLCJyZXNvdXJjZSI6ImZsZWV0Iiwic2VjdGlvbl9zaGEyNTYiOiIxYWIyNGVjNTk5NGVkMDhkNTYwZjI1ZjZiMTA5MzEwYzM3NWQ1MmJjYWU3ZWVlYTdlZjg3ZGZjY2YyMmRhZGJiIiwic2lnbmF0dXJlX3NoYTI1NiI6ImExNTliNjFlMjJiOGU1M2VhYTE1MTY0M2EwYjMwOTlkYTI5MjRmNmU0OWJhNzc3MjE2ZmMyNjZhOTcyNjFlMzQifQ -->
### `client.listWaitlistInvites`

Operation ID: `listWaitlistInvites`  
Route: `GET` `/v1/waitlist`  

#### Signature

```java
public WaitlistListResponse listWaitlistInvites()
public ApiResponse<WaitlistListResponse> listWaitlistInvitesWithResponse()
public CompletableFuture<ApiResponse<WaitlistListResponse>> listWaitlistInvitesWithResponseAsync()
public CompletableFuture<WaitlistListResponse> listWaitlistInvitesAsync()
public WaitlistListResponse listWaitlistInvites(RequestOptions requestOptions)
public ApiResponse<WaitlistListResponse> listWaitlistInvitesWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<WaitlistListResponse>> listWaitlistInvitesWithResponseAsync(RequestOptions requestOptions)
public CompletableFuture<WaitlistListResponse> listWaitlistInvitesAsync(RequestOptions requestOptions)
public WaitlistListResponse listWaitlistInvites(Long limit, String format)
public ApiResponse<WaitlistListResponse> listWaitlistInvitesWithResponse(Long limit, String format)
public CompletableFuture<ApiResponse<WaitlistListResponse>> listWaitlistInvitesWithResponseAsync(Long limit, String format)
public CompletableFuture<WaitlistListResponse> listWaitlistInvitesAsync(Long limit, String format)
public WaitlistListResponse listWaitlistInvites(Long limit, String format, RequestOptions requestOptions)
public CompletableFuture<WaitlistListResponse> listWaitlistInvitesAsync(Long limit, String format, RequestOptions requestOptions)
public ApiResponse<WaitlistListResponse> listWaitlistInvitesWithResponse(Long limit, String format, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<WaitlistListResponse>> listWaitlistInvitesWithResponseAsync(Long limit, String format, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `limit` | `query` | no | `integer` |  |
| `format` | `query` | no | `string` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Waitlist invitations list | application/json (WaitlistListResponse) |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsaXN0V2FpdGxpc3RJbnZpdGVzIn0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJyZWdpc3RlcldhaXRsaXN0SW52aXRlIiwibWV0aG9kIjoiUE9TVCIsIm9wZXJhdGlvbl9pZCI6InJlZ2lzdGVyV2FpdGxpc3RJbnZpdGUiLCJwYXRoIjoiL3YxL3dhaXRsaXN0IiwicmVzb3VyY2UiOiJmbGVldCIsInNlY3Rpb25fc2hhMjU2IjoiMmE4OThiNmY2NzlhNGYxNTI0ZjQzOGY4MjRiYzVmOWFkMWIzNWM4M2YwNGI3ODIyMDMwZWM3MzFlMTUxODY5YSIsInNpZ25hdHVyZV9zaGEyNTYiOiIxMWU2Y2IyMjllOGVhNzhiNzU3OWM0MTU5NWM1NGU4YjEyMjcxMDc4MjY3ODMwYTA2NzE0YjJiOGMzYWQxZjFmIn0 -->
### `client.registerWaitlistInvite`

Operation ID: `registerWaitlistInvite`  
Route: `POST` `/v1/waitlist`  

#### Signature

```java
public WaitlistRegisterResponse registerWaitlistInvite(WaitlistRegisterRequest body)
public ApiResponse<WaitlistRegisterResponse> registerWaitlistInviteWithResponse(WaitlistRegisterRequest body)
public CompletableFuture<ApiResponse<WaitlistRegisterResponse>> registerWaitlistInviteWithResponseAsync(WaitlistRegisterRequest body)
public CompletableFuture<WaitlistRegisterResponse> registerWaitlistInviteAsync(WaitlistRegisterRequest body)
public WaitlistRegisterResponse registerWaitlistInvite(WaitlistRegisterRequest body, RequestOptions requestOptions)
public CompletableFuture<WaitlistRegisterResponse> registerWaitlistInviteAsync(WaitlistRegisterRequest body, RequestOptions requestOptions)
public ApiResponse<WaitlistRegisterResponse> registerWaitlistInviteWithResponse(WaitlistRegisterRequest body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<WaitlistRegisterResponse>> registerWaitlistInviteWithResponseAsync(WaitlistRegisterRequest body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `WaitlistRegisterRequest` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `201` | Waitlist registration recorded in boxfleet.waitlist_invites | application/json (WaitlistRegisterResponse) |

#### Canonical required-input example

```json
{
  "body": {
    "email": "example-9266@example.test"
  },
  "content_type": "application/json",
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJyZWdpc3RlcldhaXRsaXN0SW52aXRlIn0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJ1cGRhdGVPcmdhbml6YXRpb25GbGVldFBvbGljeSIsIm1ldGhvZCI6IlBVVCIsIm9wZXJhdGlvbl9pZCI6InVwZGF0ZU9yZ2FuaXphdGlvbkZsZWV0UG9saWN5IiwicGF0aCI6Ii92MS9vcmdhbml6YXRpb25zL3tvcmdJZH0vZmxlZXQvcG9saWN5IiwicmVzb3VyY2UiOiJmbGVldCIsInNlY3Rpb25fc2hhMjU2IjoiZmJiYjMwMTU2NWU1ZmQzM2Y4YTlmZDM0NjQ5N2ZkMTdjMmFlZWJiZjI3ZWM1NDFkOTQwYTNhMzkxNWQ4NTBkNCIsInNpZ25hdHVyZV9zaGEyNTYiOiJjMjAwNWNjNWRhY2M1NmI3ZjgyM2FhYzc0YTNhY2E3NzZjOTU4MTEwOWZiZjJhYTZhZmY5M2QwZGE0ZmZjZDVkIn0 -->
### `client.updateOrganizationFleetPolicy`

Operation ID: `updateOrganizationFleetPolicy`  
Route: `PUT` `/v1/organizations/{orgId}/fleet/policy`  

#### Signature

```java
public OrganizationFleetResponse updateOrganizationFleetPolicy(String orgId, FleetPolicyUpdateRequest body)
public ApiResponse<OrganizationFleetResponse> updateOrganizationFleetPolicyWithResponse(String orgId, FleetPolicyUpdateRequest body)
public CompletableFuture<ApiResponse<OrganizationFleetResponse>> updateOrganizationFleetPolicyWithResponseAsync(String orgId, FleetPolicyUpdateRequest body)
public CompletableFuture<OrganizationFleetResponse> updateOrganizationFleetPolicyAsync(String orgId, FleetPolicyUpdateRequest body)
public OrganizationFleetResponse updateOrganizationFleetPolicy(String orgId, FleetPolicyUpdateRequest body, RequestOptions requestOptions)
public CompletableFuture<OrganizationFleetResponse> updateOrganizationFleetPolicyAsync(String orgId, FleetPolicyUpdateRequest body, RequestOptions requestOptions)
public ApiResponse<OrganizationFleetResponse> updateOrganizationFleetPolicyWithResponse(String orgId, FleetPolicyUpdateRequest body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<OrganizationFleetResponse>> updateOrganizationFleetPolicyWithResponseAsync(String orgId, FleetPolicyUpdateRequest body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `orgId` | `path` | yes | `string` |  |
| `body` | body | yes | `FleetPolicyUpdateRequest` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Updated fleet policy | application/json (OrganizationFleetResponse) |

#### Canonical required-input example

```json
{
  "body": {},
  "content_type": "application/json",
  "parameters": [
    {
      "in": "path",
      "name": "orgId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJ1cGRhdGVPcmdhbml6YXRpb25GbGVldFBvbGljeSJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJ1cHNlcnRPcmdhbml6YXRpb25NZW1iZXIiLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoidXBzZXJ0T3JnYW5pemF0aW9uTWVtYmVyIiwicGF0aCI6Ii92MS9vcmdhbml6YXRpb25zL3tvcmdJZH0vbWVtYmVycyIsInJlc291cmNlIjoiZmxlZXQiLCJzZWN0aW9uX3NoYTI1NiI6ImUyZTMxZTJkZGVhZWQ4MmRiNWUxNmI5NTZmNGQ4ZjFhMzZhNDNjODI0YTExMDY1YjgzOWE0NTIzMTZkYmQ5N2QiLCJzaWduYXR1cmVfc2hhMjU2IjoiZDNjMjIwZTM0YmYwNjljMmNlMGUxZTY3YWVjMjIxNjJmMWEwOWU5MDNjYjcwOTI0ZjJkOTk5ZjhkMjYwOTJiMyJ9 -->
### `client.upsertOrganizationMember`

Operation ID: `upsertOrganizationMember`  
Route: `POST` `/v1/organizations/{orgId}/members`  

#### Signature

```java
public OrganizationMember upsertOrganizationMember(String orgId, UpsertOrganizationMemberRequest body)
public ApiResponse<OrganizationMember> upsertOrganizationMemberWithResponse(String orgId, UpsertOrganizationMemberRequest body)
public CompletableFuture<ApiResponse<OrganizationMember>> upsertOrganizationMemberWithResponseAsync(String orgId, UpsertOrganizationMemberRequest body)
public CompletableFuture<OrganizationMember> upsertOrganizationMemberAsync(String orgId, UpsertOrganizationMemberRequest body)
public OrganizationMember upsertOrganizationMember(String orgId, UpsertOrganizationMemberRequest body, RequestOptions requestOptions)
public CompletableFuture<OrganizationMember> upsertOrganizationMemberAsync(String orgId, UpsertOrganizationMemberRequest body, RequestOptions requestOptions)
public ApiResponse<OrganizationMember> upsertOrganizationMemberWithResponse(String orgId, UpsertOrganizationMemberRequest body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<OrganizationMember>> upsertOrganizationMemberWithResponseAsync(String orgId, UpsertOrganizationMemberRequest body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `orgId` | `path` | yes | `string` |  |
| `body` | body | yes | `UpsertOrganizationMemberRequest` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Upserted organization member | application/json (OrganizationMember) |

#### Canonical required-input example

```json
{
  "body": {
    "email": "example",
    "role": "owner",
    "userId": "example"
  },
  "content_type": "application/json",
  "parameters": [
    {
      "in": "path",
      "name": "orgId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJ1cHNlcnRPcmdhbml6YXRpb25NZW1iZXIifQ -->

## Resource `jobs`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJjYW5jZWxKb2IiLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoiY2FuY2VsSm9iIiwicGF0aCI6Ii92MS9qb2JzL3tqb2JJZH0vY2FuY2VsIiwicmVzb3VyY2UiOiJqb2JzIiwic2VjdGlvbl9zaGEyNTYiOiI1ZGNjZGFhZTBhMTcxYzNkNmZmOTVhNWVhMjM1NTc0ODgxZjY0M2M5Y2NkYTBlNTU0ZDZjY2MwZTNiNzE0N2QyIiwic2lnbmF0dXJlX3NoYTI1NiI6IjBlYTc4OWI2Mzk2NjZiY2E4ZGNiNjdkY2FkZmExMWE5OGY4YzhhZTQ5Y2E1ZDY1NTE3YWJkNWYyZWE5MTg2MGQifQ -->
### `client.cancelJob`

Operation ID: `cancelJob`  
Route: `POST` `/v1/jobs/{jobId}/cancel`  

#### Signature

```java
public JobSummary cancelJob(String jobId)
public ApiResponse<JobSummary> cancelJobWithResponse(String jobId)
public CompletableFuture<ApiResponse<JobSummary>> cancelJobWithResponseAsync(String jobId)
public CompletableFuture<JobSummary> cancelJobAsync(String jobId)
public JobSummary cancelJob(String jobId, RequestOptions requestOptions)
public CompletableFuture<JobSummary> cancelJobAsync(String jobId, RequestOptions requestOptions)
public ApiResponse<JobSummary> cancelJobWithResponse(String jobId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<JobSummary>> cancelJobWithResponseAsync(String jobId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `jobId` | `path` | yes | `string` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Cancellation result | application/json (JobSummary) |

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

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJjYW5jZWxKb2IifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJnZXRKb2JFeGVjdXRpb24iLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJnZXRKb2JFeGVjdXRpb24iLCJwYXRoIjoiL3YxL2pvYnMve2pvYklkfS9leGVjdXRpb24iLCJyZXNvdXJjZSI6ImpvYnMiLCJzZWN0aW9uX3NoYTI1NiI6ImIxYjViNmVmYTJlN2ZkZTc2ZDNiOWRhNGIzMzFkYmE1MWYwMmE0ZjE4MWJhODA0MGQxYTE1ODEyNzIyMDRiYWQiLCJzaWduYXR1cmVfc2hhMjU2IjoiYTBiNGE3OWM0YzE4NTM2OTdiNzJlOTY0ZTA2ZjdlMzFjYjY5OWQwMWIxY2JhMmRjMzM1ZTYwMzYxYzNhZTUyMCJ9 -->
### `client.getJobExecution`

Operation ID: `getJobExecution`  
Route: `GET` `/v1/jobs/{jobId}/execution`  

#### Signature

```java
public JobExecutionResponse getJobExecution(String jobId)
public ApiResponse<JobExecutionResponse> getJobExecutionWithResponse(String jobId)
public CompletableFuture<ApiResponse<JobExecutionResponse>> getJobExecutionWithResponseAsync(String jobId)
public CompletableFuture<JobExecutionResponse> getJobExecutionAsync(String jobId)
public JobExecutionResponse getJobExecution(String jobId, RequestOptions requestOptions)
public CompletableFuture<JobExecutionResponse> getJobExecutionAsync(String jobId, RequestOptions requestOptions)
public ApiResponse<JobExecutionResponse> getJobExecutionWithResponse(String jobId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<JobExecutionResponse>> getJobExecutionWithResponseAsync(String jobId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `jobId` | `path` | yes | `string` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Job execution evidence | application/json (JobExecutionResponse) |

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

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRKb2JFeGVjdXRpb24ifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJnZXRKb2JMb2dzIiwibWV0aG9kIjoiR0VUIiwib3BlcmF0aW9uX2lkIjoiZ2V0Sm9iTG9ncyIsInBhdGgiOiIvdjEvam9icy97am9iSWR9L2xvZ3MiLCJyZXNvdXJjZSI6ImpvYnMiLCJzZWN0aW9uX3NoYTI1NiI6Ijg3OTJlOWVjZWNiZTI4N2IxNDYyODAxZTE5NDM0OGQ0MGQ5YzVkMzQ1MmUwYmE0NGNiODZkNDUxOTQ2MTg4OTQiLCJzaWduYXR1cmVfc2hhMjU2IjoiYTEyNTU2YzJhYWY1MWUyMzUxMzE1MzlkMzdiNjQ5OWZiNGFiNWExNWRmMzc5NTViYTM2NjdlOTEwY2Y3M2JkYyJ9 -->
### `client.getJobLogs`

Operation ID: `getJobLogs`  
Route: `GET` `/v1/jobs/{jobId}/logs`  

#### Signature

```java
public JobLogsResponse getJobLogs(String jobId)
public ApiResponse<JobLogsResponse> getJobLogsWithResponse(String jobId)
public CompletableFuture<ApiResponse<JobLogsResponse>> getJobLogsWithResponseAsync(String jobId)
public CompletableFuture<JobLogsResponse> getJobLogsAsync(String jobId)
public JobLogsResponse getJobLogs(String jobId, RequestOptions requestOptions)
public CompletableFuture<JobLogsResponse> getJobLogsAsync(String jobId, RequestOptions requestOptions)
public ApiResponse<JobLogsResponse> getJobLogsWithResponse(String jobId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<JobLogsResponse>> getJobLogsWithResponseAsync(String jobId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `jobId` | `path` | yes | `string` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Redacted job logs | application/json (JobLogsResponse) |

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

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRKb2JMb2dzIn0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJnZXRKb2JTdGF0dXMiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJnZXRKb2JTdGF0dXMiLCJwYXRoIjoiL3YxL2pvYnMve2pvYklkfSIsInJlc291cmNlIjoiam9icyIsInNlY3Rpb25fc2hhMjU2IjoiZjZhYjUzMzM3YTE0N2ExZmM3ZDQ4NzlhYTA3MmZmYTljYTNkYzAyOTZhZWI1ZmFhOTkwODcyZGYyYjFlYmQyOSIsInNpZ25hdHVyZV9zaGEyNTYiOiJlN2NkMjQwZGUwMDEyOWVhOGZlYTllYTFjMTdkODc1YWIyODZlMWI3ZjI4YzNjYmQzMWVjMzcwZmYxYjlhOGRlIn0 -->
### `client.getJobStatus`

Operation ID: `getJobStatus`  
Route: `GET` `/v1/jobs/{jobId}`  

#### Signature

```java
public JobSummary getJobStatus(String jobId)
public ApiResponse<JobSummary> getJobStatusWithResponse(String jobId)
public CompletableFuture<ApiResponse<JobSummary>> getJobStatusWithResponseAsync(String jobId)
public CompletableFuture<JobSummary> getJobStatusAsync(String jobId)
public JobSummary getJobStatus(String jobId, RequestOptions requestOptions)
public CompletableFuture<JobSummary> getJobStatusAsync(String jobId, RequestOptions requestOptions)
public ApiResponse<JobSummary> getJobStatusWithResponse(String jobId, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<JobSummary>> getJobStatusWithResponseAsync(String jobId, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `jobId` | `path` | yes | `string` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Job status snapshot | application/json (JobSummary) |

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

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRKb2JTdGF0dXMifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJpbnNwZWN0UHJvamVjdCIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJpbnNwZWN0UHJvamVjdCIsInBhdGgiOiIvdjEvaW5zcGVjdCIsInJlc291cmNlIjoiam9icyIsInNlY3Rpb25fc2hhMjU2IjoiNmU3MmFjZmZjMjg4OThmZWI3YzQ0MjM3YjE5OWE4Nzc4NGUzZmM5YjcxMWUzOTYwNTVkNDBkYTEyYjJmMzBhNSIsInNpZ25hdHVyZV9zaGEyNTYiOiIwMDVhNzEzZTllODU5ZmMyZjk4NDJiM2U5ZDU0Zjc0NzY5YzY0OGQzOWNmOThhYjVlZTI1YzY0NDMwNzIyZDJjIn0 -->
### `client.inspectProject`

Operation ID: `inspectProject`  
Route: `POST` `/v1/inspect`  

#### Signature

```java
public ProjectInspectionPlan inspectProject(InspectProjectRequest body)
public ApiResponse<ProjectInspectionPlan> inspectProjectWithResponse(InspectProjectRequest body)
public CompletableFuture<ApiResponse<ProjectInspectionPlan>> inspectProjectWithResponseAsync(InspectProjectRequest body)
public CompletableFuture<ProjectInspectionPlan> inspectProjectAsync(InspectProjectRequest body)
public ProjectInspectionPlan inspectProject(InspectProjectRequest body, RequestOptions requestOptions)
public CompletableFuture<ProjectInspectionPlan> inspectProjectAsync(InspectProjectRequest body, RequestOptions requestOptions)
public ApiResponse<ProjectInspectionPlan> inspectProjectWithResponse(InspectProjectRequest body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<ProjectInspectionPlan>> inspectProjectWithResponseAsync(InspectProjectRequest body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `InspectProjectRequest` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Project inspection plan | application/json (ProjectInspectionPlan) |

#### Canonical required-input example

```json
{
  "body": {
    "projectRoot": "example"
  },
  "content_type": "application/json",
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJpbnNwZWN0UHJvamVjdCJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJsaXN0Sm9icyIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6Imxpc3RKb2JzIiwicGF0aCI6Ii92MS9qb2JzIiwicmVzb3VyY2UiOiJqb2JzIiwic2VjdGlvbl9zaGEyNTYiOiJlYzUxNTAyYTA0YzIyOGFjMjg2MDIyMWQ0N2I2ZDEzZTdjZjQ4OWVmOWRkZDRlMzYxOTQzYjgzOTI0NWVhMzc2Iiwic2lnbmF0dXJlX3NoYTI1NiI6IjZkOWI2NjdhMDc1NDM4YzFiYmM0Y2JjNmI1Y2E2Nzc4NmM3MGYzODljZTRiMjQyZGY1ZDJkNTAxZjJlMDAzMzIifQ -->
### `client.listJobs`

Operation ID: `listJobs`  
Route: `GET` `/v1/jobs`  

#### Signature

```java
public JobListResponse listJobs()
public ApiResponse<JobListResponse> listJobsWithResponse()
public CompletableFuture<ApiResponse<JobListResponse>> listJobsWithResponseAsync()
public CompletableFuture<JobListResponse> listJobsAsync()
public JobListResponse listJobs(RequestOptions requestOptions)
public ApiResponse<JobListResponse> listJobsWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<JobListResponse>> listJobsWithResponseAsync(RequestOptions requestOptions)
public CompletableFuture<JobListResponse> listJobsAsync(RequestOptions requestOptions)
public JobListResponse listJobs(String status, String boxId, Long limit)
public ApiResponse<JobListResponse> listJobsWithResponse(String status, String boxId, Long limit)
public CompletableFuture<ApiResponse<JobListResponse>> listJobsWithResponseAsync(String status, String boxId, Long limit)
public CompletableFuture<JobListResponse> listJobsAsync(String status, String boxId, Long limit)
public JobListResponse listJobs(String status, String boxId, Long limit, RequestOptions requestOptions)
public CompletableFuture<JobListResponse> listJobsAsync(String status, String boxId, Long limit, RequestOptions requestOptions)
public ApiResponse<JobListResponse> listJobsWithResponse(String status, String boxId, Long limit, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<JobListResponse>> listJobsWithResponseAsync(String status, String boxId, Long limit, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `status` | `query` | no | `string` |  |
| `boxId` | `query` | no | `string` |  |
| `limit` | `query` | no | `integer` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Paginated job list | application/json (JobListResponse) |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsaXN0Sm9icyJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJzdGFydEFnZW50Sm9iIiwibWV0aG9kIjoiUE9TVCIsIm9wZXJhdGlvbl9pZCI6InN0YXJ0QWdlbnRKb2IiLCJwYXRoIjoiL3YxL2FnZW50LWpvYnMiLCJyZXNvdXJjZSI6ImpvYnMiLCJzZWN0aW9uX3NoYTI1NiI6IjQzZmY1YTEwOTQ2ODI4YWY5OGUwMzUyMDdhOTJkMDc3OTIxYWU5MGU2N2E4NjNhZmY4MGYyZTVmYzViZGVlMTgiLCJzaWduYXR1cmVfc2hhMjU2IjoiYjU5YTA5OTZiNDg2MzBiNzIxOGY1ODVjNWE1ZGU1Y2Y0OTQxYTZhZTg2ODYzNzViM2U1ODg0MGQ1NWQ2NDlmYSJ9 -->
### `client.startAgentJob`

Operation ID: `startAgentJob`  
Route: `POST` `/v1/agent-jobs`  

#### Signature

```java
public JobSummary startAgentJob(StartAgentJobRequest body)
public ApiResponse<JobSummary> startAgentJobWithResponse(StartAgentJobRequest body)
public CompletableFuture<ApiResponse<JobSummary>> startAgentJobWithResponseAsync(StartAgentJobRequest body)
public CompletableFuture<JobSummary> startAgentJobAsync(StartAgentJobRequest body)
public JobSummary startAgentJob(StartAgentJobRequest body, RequestOptions requestOptions)
public CompletableFuture<JobSummary> startAgentJobAsync(StartAgentJobRequest body, RequestOptions requestOptions)
public ApiResponse<JobSummary> startAgentJobWithResponse(StartAgentJobRequest body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<JobSummary>> startAgentJobWithResponseAsync(StartAgentJobRequest body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `StartAgentJobRequest` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `201` | Autonomous coding job started | application/json (JobSummary) |

#### Canonical required-input example

```json
{
  "body": {
    "projectRoot": "example",
    "task": "example"
  },
  "content_type": "application/json",
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJzdGFydEFnZW50Sm9iIn0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJzdGFydEdpdGh1YkpvYiIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJzdGFydEdpdGh1YkpvYiIsInBhdGgiOiIvdjEvZ2l0aHViLWpvYnMiLCJyZXNvdXJjZSI6ImpvYnMiLCJzZWN0aW9uX3NoYTI1NiI6ImYxMTQwNGY1YjRmYWNhYjE4ZWNlMjgxNmNkYTNlZjY3NmUxMjliMjkxZDZiNTEyM2YwYzQyY2Y5MGE2M2QzMGYiLCJzaWduYXR1cmVfc2hhMjU2IjoiY2E2MTJjOTA2YzVkZmEyMjA0MjczOWIxYjVjNzQwMTY2N2VkNDE5OTE0Y2YyNDJhNjRkMTk4M2RkMzIwMWE5ZCJ9 -->
### `client.startGithubJob`

Operation ID: `startGithubJob`  
Route: `POST` `/v1/github-jobs`  

#### Signature

```java
public JobSummary startGithubJob(StartGithubJobRequest body)
public ApiResponse<JobSummary> startGithubJobWithResponse(StartGithubJobRequest body)
public CompletableFuture<ApiResponse<JobSummary>> startGithubJobWithResponseAsync(StartGithubJobRequest body)
public CompletableFuture<JobSummary> startGithubJobAsync(StartGithubJobRequest body)
public JobSummary startGithubJob(StartGithubJobRequest body, RequestOptions requestOptions)
public CompletableFuture<JobSummary> startGithubJobAsync(StartGithubJobRequest body, RequestOptions requestOptions)
public ApiResponse<JobSummary> startGithubJobWithResponse(StartGithubJobRequest body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<JobSummary>> startGithubJobWithResponseAsync(StartGithubJobRequest body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `StartGithubJobRequest` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `201` | GitHub sandbox job started | application/json (JobSummary) |

#### Canonical required-input example

```json
{
  "body": {
    "repository": "example"
  },
  "content_type": "application/json",
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJzdGFydEdpdGh1YkpvYiJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJzdGFydFByb2plY3RKb2IiLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoic3RhcnRQcm9qZWN0Sm9iIiwicGF0aCI6Ii92MS9qb2JzIiwicmVzb3VyY2UiOiJqb2JzIiwic2VjdGlvbl9zaGEyNTYiOiI2ZGExOGFkN2ZkNjVhODc1OWE1NWE3Yzc3ZmNhNDIzZWQwYzM3ZjA5ODc0NTc1M2ZjN2MyY2UyZTc5NzdhNjFiIiwic2lnbmF0dXJlX3NoYTI1NiI6IjUzN2RiZjMxYmIxMzBkNjMxMmY3NWJkYTYxMjEzZTdhZDI5NzVjYWMxZWZlMWY1NjcyZjE2MTA4ZTIwNWEzNTMifQ -->
### `client.startProjectJob`

Operation ID: `startProjectJob`  
Route: `POST` `/v1/jobs`  

#### Signature

```java
public JobSummary startProjectJob(StartProjectJobRequest body)
public ApiResponse<JobSummary> startProjectJobWithResponse(StartProjectJobRequest body)
public CompletableFuture<ApiResponse<JobSummary>> startProjectJobWithResponseAsync(StartProjectJobRequest body)
public CompletableFuture<JobSummary> startProjectJobAsync(StartProjectJobRequest body)
public JobSummary startProjectJob(StartProjectJobRequest body, RequestOptions requestOptions)
public CompletableFuture<JobSummary> startProjectJobAsync(StartProjectJobRequest body, RequestOptions requestOptions)
public ApiResponse<JobSummary> startProjectJobWithResponse(StartProjectJobRequest body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<JobSummary>> startProjectJobWithResponseAsync(StartProjectJobRequest body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `StartProjectJobRequest` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `201` | Job created and started | application/json (JobSummary) |

#### Canonical required-input example

```json
{
  "body": {
    "projectRoot": "example"
  },
  "content_type": "application/json",
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJzdGFydFByb2plY3RKb2IifQ -->

## Resource `system`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJkZXNjcmliZUFnZW50TW9kcyIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6ImRlc2NyaWJlQWdlbnRNb2RzIiwicGF0aCI6Ii92MS9tb2RzIiwicmVzb3VyY2UiOiJzeXN0ZW0iLCJzZWN0aW9uX3NoYTI1NiI6ImNhMTRkODAxMTQxMzU1NzA0NjI4NTk0ZGI0NjZlY2Q4MDBiZmFlOWU3NzhhMTQ1ZDVmMDMwOThkYjM2ZmRmZmQiLCJzaWduYXR1cmVfc2hhMjU2IjoiYjg0MjgyNmYzN2MyMzNlZjIzNjFjN2Y2MTVjYzIzNGZkNGJjZmI1OTVkYzg2OWIwMmE1NTcwYTMzMmU0OGIzZCJ9 -->
### `client.describeAgentMods`

Operation ID: `describeAgentMods`  
Route: `GET` `/v1/mods`  

#### Signature

```java
public ModsCatalogResponse describeAgentMods()
public ApiResponse<ModsCatalogResponse> describeAgentModsWithResponse()
public CompletableFuture<ApiResponse<ModsCatalogResponse>> describeAgentModsWithResponseAsync()
public CompletableFuture<ModsCatalogResponse> describeAgentModsAsync()
public ModsCatalogResponse describeAgentMods(RequestOptions requestOptions)
public ApiResponse<ModsCatalogResponse> describeAgentModsWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<ModsCatalogResponse>> describeAgentModsWithResponseAsync(RequestOptions requestOptions)
public CompletableFuture<ModsCatalogResponse> describeAgentModsAsync(RequestOptions requestOptions)
public ModsCatalogResponse describeAgentMods(String target)
public ApiResponse<ModsCatalogResponse> describeAgentModsWithResponse(String target)
public CompletableFuture<ApiResponse<ModsCatalogResponse>> describeAgentModsWithResponseAsync(String target)
public CompletableFuture<ModsCatalogResponse> describeAgentModsAsync(String target)
public ModsCatalogResponse describeAgentMods(String target, RequestOptions requestOptions)
public CompletableFuture<ModsCatalogResponse> describeAgentModsAsync(String target, RequestOptions requestOptions)
public ApiResponse<ModsCatalogResponse> describeAgentModsWithResponse(String target, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<ModsCatalogResponse>> describeAgentModsWithResponseAsync(String target, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `target` | `query` | no | `string` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Agent mods catalog | application/json (ModsCatalogResponse) |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJkZXNjcmliZUFnZW50TW9kcyJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJnZXRIZWFsdGgiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJnZXRIZWFsdGgiLCJwYXRoIjoiL2hlYWx0aCIsInJlc291cmNlIjoic3lzdGVtIiwic2VjdGlvbl9zaGEyNTYiOiIzNmJlNTg3ODBjY2M0ZGMzM2E2NjcxODE2YzUxOGQ1YzVmMjFmOGNkYTY1MzkyMWI5MzkzZjM2ZjRlMjhjMThjIiwic2lnbmF0dXJlX3NoYTI1NiI6IjE3MmJhZjFiMmRlZDRkZWI5MGQ2ODA0OTkyNmUwZTZmMmQxOGE0M2JiMTgxYTNmZjUwOTU2ZjFiMzdiZjRlNGYifQ -->
### `client.getHealth`

Operation ID: `getHealth`  
Route: `GET` `/health`  

#### Signature

```java
public HealthResponse getHealth()
public ApiResponse<HealthResponse> getHealthWithResponse()
public CompletableFuture<ApiResponse<HealthResponse>> getHealthWithResponseAsync()
public CompletableFuture<HealthResponse> getHealthAsync()
public HealthResponse getHealth(RequestOptions requestOptions)
public CompletableFuture<HealthResponse> getHealthAsync(RequestOptions requestOptions)
public ApiResponse<HealthResponse> getHealthWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<HealthResponse>> getHealthWithResponseAsync(RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Service health status | application/json (HealthResponse) |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRIZWFsdGgifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJsaXN0Q2FwYWJpbGl0aWVzIiwibWV0aG9kIjoiR0VUIiwib3BlcmF0aW9uX2lkIjoibGlzdENhcGFiaWxpdGllcyIsInBhdGgiOiIvdjEvY2FwYWJpbGl0aWVzIiwicmVzb3VyY2UiOiJzeXN0ZW0iLCJzZWN0aW9uX3NoYTI1NiI6IjI2MjRhMzgxMzBlNjlmMDZhNTk3MjE5MDc5NDRmNzg3ZjQ4NGMwNGIxYWM1ZjZkYTI4MmFjZTcyNDdiMTM1ZjciLCJzaWduYXR1cmVfc2hhMjU2IjoiMzk2OTUxMDdkN2YxMjVmODNkZWQzNDU2MWJkMzBiODdiMGJiMzEyMmZhOTEyYzZjOWU2MmUxZmY0ZWI4ODIxZCJ9 -->
### `client.listCapabilities`

Operation ID: `listCapabilities`  
Route: `GET` `/v1/capabilities`  

#### Signature

```java
public CapabilitiesResponse listCapabilities()
public ApiResponse<CapabilitiesResponse> listCapabilitiesWithResponse()
public CompletableFuture<ApiResponse<CapabilitiesResponse>> listCapabilitiesWithResponseAsync()
public CompletableFuture<CapabilitiesResponse> listCapabilitiesAsync()
public CapabilitiesResponse listCapabilities(RequestOptions requestOptions)
public ApiResponse<CapabilitiesResponse> listCapabilitiesWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<CapabilitiesResponse>> listCapabilitiesWithResponseAsync(RequestOptions requestOptions)
public CompletableFuture<CapabilitiesResponse> listCapabilitiesAsync(RequestOptions requestOptions)
public CapabilitiesResponse listCapabilities(String queryValue, String state)
public ApiResponse<CapabilitiesResponse> listCapabilitiesWithResponse(String queryValue, String state)
public CompletableFuture<ApiResponse<CapabilitiesResponse>> listCapabilitiesWithResponseAsync(String queryValue, String state)
public CompletableFuture<CapabilitiesResponse> listCapabilitiesAsync(String queryValue, String state)
public CapabilitiesResponse listCapabilities(String queryValue, String state, RequestOptions requestOptions)
public CompletableFuture<CapabilitiesResponse> listCapabilitiesAsync(String queryValue, String state, RequestOptions requestOptions)
public ApiResponse<CapabilitiesResponse> listCapabilitiesWithResponse(String queryValue, String state, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<CapabilitiesResponse>> listCapabilitiesWithResponseAsync(String queryValue, String state, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `query` | `query` | no | `string` |  |
| `state` | `query` | no | `string` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Capability catalog and job limits | application/json (CapabilitiesResponse) |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsaXN0Q2FwYWJpbGl0aWVzIn0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJsaXN0UHJvdmlkZXJzIiwibWV0aG9kIjoiR0VUIiwib3BlcmF0aW9uX2lkIjoibGlzdFByb3ZpZGVycyIsInBhdGgiOiIvdjEvcHJvdmlkZXJzIiwicmVzb3VyY2UiOiJzeXN0ZW0iLCJzZWN0aW9uX3NoYTI1NiI6IjZkZTMwZGQ0MDQ5NjE0YjFjZDgyZjczZTAwNzQwN2ZkNzMxOTk1NzlhNTM5MGMwY2M2NzczZGZhMmRmYzUxY2YiLCJzaWduYXR1cmVfc2hhMjU2IjoiM2E4YjNlMDg4NzNhNmM3ZjY3Y2ZhOWVlNmNiMzk1MzliOTU3YmY1ZGFjZDJkYWI5OTgyNzg1YTNmMmZkMjkxOCJ9 -->
### `client.listProviders`

Operation ID: `listProviders`  
Route: `GET` `/v1/providers`  

#### Signature

```java
public ProvidersResponse listProviders()
public ApiResponse<ProvidersResponse> listProvidersWithResponse()
public CompletableFuture<ApiResponse<ProvidersResponse>> listProvidersWithResponseAsync()
public CompletableFuture<ProvidersResponse> listProvidersAsync()
public ProvidersResponse listProviders(RequestOptions requestOptions)
public CompletableFuture<ProvidersResponse> listProvidersAsync(RequestOptions requestOptions)
public ApiResponse<ProvidersResponse> listProvidersWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<ProvidersResponse>> listProvidersWithResponseAsync(RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Provider list with runtime templates | application/json (ProvidersResponse) |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsaXN0UHJvdmlkZXJzIn0 -->

