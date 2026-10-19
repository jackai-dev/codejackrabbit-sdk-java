# CodeJackRabbit Java API

<!-- omniwrap-api-reference eyJjb250cmFjdF9maW5nZXJwcmludCI6ImZlMGYyMjU1OGZiNDM0MTEwODJkZjVlMDc2MmEyM2U5ZWFmOTBhOWM3MTNmZTRlZTljZmQyNzM3OTIyMjgwM2QiLCJvcGVyYXRpb25fY291bnQiOjIyLCJyZW5kZXJlciI6ImphdmEiLCJ2ZXJzaW9uIjoiMS40LjAifQ -->

This generated index is tied to Semantic IR `1.14.0` and contract fingerprint `fe0f22558fb43411082df5e0762a23e9eaf90a9c713fe4ee9cfd27379222803d`. Every operation below is rendered from the same semantic contract and artifact-attested public member allocation as the SDK.

SDK maturity: **experimental**  
Artifact evidence: [`omniwrap-artifact.json`](omniwrap-artifact.json) binds this file by SHA-256 and is revalidated by the package gate.

## Client hooks and tracing

`ClientOptions.builder().hooks(RequestHooks)` registers four callbacks. Every attempt starts with `beforeRequest` and ends with exactly one of `onRetry` (another attempt follows), `afterResponse` (the success the call returns) or `onError` (the failure the call reports). Each receives the operation id, the HTTP method, the URL, the request headers, the attempt number (from 1), the time elapsed since the call started and, once the server answered, the HTTP status. No context carries a credential: `Authorization`, `Proxy-Authorization`, `Cookie`, every API-key header and API-key query parameter, and any configured credential value read `[redacted]`. Every context is an immutable `HookContext` record: no hook can change the request.

`ClientOptions.builder().tracer(RequestTracer)` opens one span per call through the tracer interface this SDK defines, named after the operation id, with `http.request.method`, `http.response.status_code` and `http.request.resend_count`. It needs no tracing library; README.md maps it onto the OpenTelemetry API.

## Shared types

- `ComplianceGateRequest`
- `FileChange`
- `ReviewRequest`
- `WaitlistRequest`

## Resource `analysis`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJhbmFseXplQ29udHJhY3REcmlmdCIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJhbmFseXplQ29udHJhY3REcmlmdCIsInBhdGgiOiIvdjEvYW5hbHlzaXMvY29udHJhY3QtZHJpZnQiLCJyZXNvdXJjZSI6ImFuYWx5c2lzIiwic2VjdGlvbl9zaGEyNTYiOiI5NmM3ZjlkOWNkNGZkZTQ0NTI0MjYzYTg2YWRiYjZmOTUzNWQ5NDdiY2ZkNTFlNzY0MzA0MjJhZTNlYjI1YWJhIiwic2lnbmF0dXJlX3NoYTI1NiI6Ijc3M2ZhOWVjMjU3MGUwMzY1YzhlZmNiYmFjMzk3YTU0M2E0Mzc0ZjE3ZTdlOWM1NTU2NzU0MjNiYjk2MjcwZGQifQ -->
### `client.analyzeContractDrift`

Operation ID: `analyzeContractDrift`  
Route: `POST` `/v1/analysis/contract-drift`  

#### Signature

```java
public Void analyzeContractDrift(ReviewRequest body)
public ApiResponse<Void> analyzeContractDriftWithResponse(ReviewRequest body)
public CompletableFuture<ApiResponse<Void>> analyzeContractDriftWithResponseAsync(ReviewRequest body)
public CompletableFuture<Void> analyzeContractDriftAsync(ReviewRequest body)
public Void analyzeContractDrift(ReviewRequest body, RequestOptions requestOptions)
public CompletableFuture<Void> analyzeContractDriftAsync(ReviewRequest body, RequestOptions requestOptions)
public ApiResponse<Void> analyzeContractDriftWithResponse(ReviewRequest body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> analyzeContractDriftWithResponseAsync(ReviewRequest body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `ReviewRequest` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Contract drift report and SemVer recommendation | none |

#### Canonical required-input example

```json
{
  "body": {
    "files": [
      {
        "filename": "example"
      }
    ]
  },
  "content_type": "application/json",
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJhbmFseXplQ29udHJhY3REcmlmdCJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJhbmFseXplUGVyZkZpbk9wcyIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJhbmFseXplUGVyZkZpbk9wcyIsInBhdGgiOiIvdjEvYW5hbHlzaXMvcGVyZi1maW5vcHMiLCJyZXNvdXJjZSI6ImFuYWx5c2lzIiwic2VjdGlvbl9zaGEyNTYiOiIzMjM3YTgxZjc2NWU4NGUzYmI1N2E1MjcyMDkyOGJjYTUxMWRjODAzN2IxZjZkMTE1ZDZlZTY3MmRlMDQwNDdmIiwic2lnbmF0dXJlX3NoYTI1NiI6IjQ0Njg0MzhmNThkNmQxM2FiZDUyOWJjMTc3OTYxN2U2ZTI0ODYxYWJjOWNkMWE2Y2VhMTJkOWRmMjYyZDhkZjEifQ -->
### `client.analyzePerfFinOps`

Operation ID: `analyzePerfFinOps`  
Route: `POST` `/v1/analysis/perf-finops`  

#### Signature

```java
public Void analyzePerfFinOps(ReviewRequest body)
public ApiResponse<Void> analyzePerfFinOpsWithResponse(ReviewRequest body)
public CompletableFuture<ApiResponse<Void>> analyzePerfFinOpsWithResponseAsync(ReviewRequest body)
public CompletableFuture<Void> analyzePerfFinOpsAsync(ReviewRequest body)
public Void analyzePerfFinOps(ReviewRequest body, RequestOptions requestOptions)
public CompletableFuture<Void> analyzePerfFinOpsAsync(ReviewRequest body, RequestOptions requestOptions)
public ApiResponse<Void> analyzePerfFinOpsWithResponse(ReviewRequest body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> analyzePerfFinOpsWithResponseAsync(ReviewRequest body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `ReviewRequest` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Performance and FinOps audit report | none |

#### Canonical required-input example

```json
{
  "body": {
    "files": [
      {
        "filename": "example"
      }
    ]
  },
  "content_type": "application/json",
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJhbmFseXplUGVyZkZpbk9wcyJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJwbGFuU3RhY2tlZFByU3BsaXQiLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoicGxhblN0YWNrZWRQclNwbGl0IiwicGF0aCI6Ii92MS9hbmFseXNpcy9zcGxpdC1wciIsInJlc291cmNlIjoiYW5hbHlzaXMiLCJzZWN0aW9uX3NoYTI1NiI6ImQ0MmIxNDdhMDQ0YzM1MDRkMDc2MGZlYzJhNGIwZDU4ZjE1ZDI3NTg4NmY2YWYwMzUzNjIzYTJmN2M5Mjk3YzYiLCJzaWduYXR1cmVfc2hhMjU2IjoiYjMyZjZkMDA4YzAwNzgyOTljODBjN2VlMjIwMTQyOGUzYjA4OTkyMTkyOGNlNzk3ZTljNzIyN2RjZjEwZjAyNSJ9 -->
### `client.planStackedPrSplit`

Operation ID: `planStackedPrSplit`  
Route: `POST` `/v1/analysis/split-pr`  

#### Signature

```java
public Void planStackedPrSplit(ReviewRequest body)
public ApiResponse<Void> planStackedPrSplitWithResponse(ReviewRequest body)
public CompletableFuture<ApiResponse<Void>> planStackedPrSplitWithResponseAsync(ReviewRequest body)
public CompletableFuture<Void> planStackedPrSplitAsync(ReviewRequest body)
public Void planStackedPrSplit(ReviewRequest body, RequestOptions requestOptions)
public CompletableFuture<Void> planStackedPrSplitAsync(ReviewRequest body, RequestOptions requestOptions)
public ApiResponse<Void> planStackedPrSplitWithResponse(ReviewRequest body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> planStackedPrSplitWithResponseAsync(ReviewRequest body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `ReviewRequest` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Ordered stacked PR plan and git commands | none |

#### Canonical required-input example

```json
{
  "body": {
    "files": [
      {
        "filename": "example"
      }
    ]
  },
  "content_type": "application/json",
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJwbGFuU3RhY2tlZFByU3BsaXQifQ -->

## Resource `analytics`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJnZXRBbmFseXRpY3NSb2kiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJnZXRBbmFseXRpY3NSb2kiLCJwYXRoIjoiL3YxL2FuYWx5dGljcy9yb2kiLCJyZXNvdXJjZSI6ImFuYWx5dGljcyIsInNlY3Rpb25fc2hhMjU2IjoiNTBmNWI0NTdmZDJiNDdmZWRlM2EzZWNhMDNlZWI1MWE0YmIzZDY0NWI2OTZmMzQzMDc5MTk1ZmNlNTA3NTc0OSIsInNpZ25hdHVyZV9zaGEyNTYiOiIzNWI4MTVlOTZiZjYyMTNmYWUwZmU2YjBhNGE2MjJiMzhmNWU1ZDVkN2VjN2Y1YzVkOWVkMGNmMTlhNDMyYTgwIn0 -->
### `client.getAnalyticsRoi`

Operation ID: `getAnalyticsRoi`  
Route: `GET` `/v1/analytics/roi`  

#### Signature

```java
public Void getAnalyticsRoi()
public ApiResponse<Void> getAnalyticsRoiWithResponse()
public CompletableFuture<ApiResponse<Void>> getAnalyticsRoiWithResponseAsync()
public CompletableFuture<Void> getAnalyticsRoiAsync()
public Void getAnalyticsRoi(RequestOptions requestOptions)
public CompletableFuture<Void> getAnalyticsRoiAsync(RequestOptions requestOptions)
public ApiResponse<Void> getAnalyticsRoiWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> getAnalyticsRoiWithResponseAsync(RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | ROI telemetry summary | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRBbmFseXRpY3NSb2kifQ -->

## Resource `capabilities`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJnZXRDYXBhYmlsaXRpZXMiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJnZXRDYXBhYmlsaXRpZXMiLCJwYXRoIjoiL3YxL2NhcGFiaWxpdGllcyIsInJlc291cmNlIjoiY2FwYWJpbGl0aWVzIiwic2VjdGlvbl9zaGEyNTYiOiIxMDkwNjIyYjVlYmE4Mjk5YjI1M2I4ZDI0Y2Y4MDRiMDI1ZTNmMTJjZmZjN2FhNGFkYmMzNzg1ZTYyYWZhMjRhIiwic2lnbmF0dXJlX3NoYTI1NiI6ImI1ZGQ0N2E4N2NiMzM4NWQ2MDA2ODc0NGU0MWIwMzYxNTkxNWViZDkxZWMxZmU1NjNhNWNmYjU5ZGU5OWVkYTMifQ -->
### `client.getCapabilities`

Operation ID: `getCapabilities`  
Route: `GET` `/v1/capabilities`  

#### Signature

```java
public Void getCapabilities()
public ApiResponse<Void> getCapabilitiesWithResponse()
public CompletableFuture<ApiResponse<Void>> getCapabilitiesWithResponseAsync()
public CompletableFuture<Void> getCapabilitiesAsync()
public Void getCapabilities(RequestOptions requestOptions)
public CompletableFuture<Void> getCapabilitiesAsync(RequestOptions requestOptions)
public ApiResponse<Void> getCapabilitiesWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> getCapabilitiesWithResponseAsync(RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Capabilities catalog | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRDYXBhYmlsaXRpZXMifQ -->

## Resource `compliance`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJldmFsdWF0ZUNvbXBsaWFuY2VHYXRlIiwibWV0aG9kIjoiUE9TVCIsIm9wZXJhdGlvbl9pZCI6ImV2YWx1YXRlQ29tcGxpYW5jZUdhdGUiLCJwYXRoIjoiL3YxL2NvbXBsaWFuY2UvZ2F0ZSIsInJlc291cmNlIjoiY29tcGxpYW5jZSIsInNlY3Rpb25fc2hhMjU2IjoiZTQyMzA5YzNhMDczYTZjMjBkMzU4YjE3ZGNlZTBjNTczNTM3MDNmNzU5ODViODBkNGI5NzY3NTg3NDIyMWVhOCIsInNpZ25hdHVyZV9zaGEyNTYiOiIyZTMxNjhlYjBjOGE4MjVlOTY2NWY3ZGEwNGE2ODVkNmY2ZmViMmEyZDg0MTk1NjEzMjg1NmM5ZDliNWNjZTAyIn0 -->
### `client.evaluateComplianceGate`

Operation ID: `evaluateComplianceGate`  
Route: `POST` `/v1/compliance/gate`  

#### Signature

```java
public Void evaluateComplianceGate(ComplianceGateRequest body)
public ApiResponse<Void> evaluateComplianceGateWithResponse(ComplianceGateRequest body)
public CompletableFuture<ApiResponse<Void>> evaluateComplianceGateWithResponseAsync(ComplianceGateRequest body)
public CompletableFuture<Void> evaluateComplianceGateAsync(ComplianceGateRequest body)
public Void evaluateComplianceGate(ComplianceGateRequest body, RequestOptions requestOptions)
public CompletableFuture<Void> evaluateComplianceGateAsync(ComplianceGateRequest body, RequestOptions requestOptions)
public ApiResponse<Void> evaluateComplianceGateWithResponse(ComplianceGateRequest body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> evaluateComplianceGateWithResponseAsync(ComplianceGateRequest body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `ComplianceGateRequest` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Compliance gate verdict and SHA-256 attestation | none |

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

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJldmFsdWF0ZUNvbXBsaWFuY2VHYXRlIn0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJleHBvcnRTYXJpZiIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJleHBvcnRTYXJpZiIsInBhdGgiOiIvdjEvY29tcGxpYW5jZS9zYXJpZiIsInJlc291cmNlIjoiY29tcGxpYW5jZSIsInNlY3Rpb25fc2hhMjU2IjoiYjc5NTZjY2QxNmZkYzFlMDY1NzIyZjI1MWNiMDhkNzZiMGFlMGI3OGYwZWI5OTMwNTg1OWNmNDNmZDlhMDM1NyIsInNpZ25hdHVyZV9zaGEyNTYiOiIyYzkwODAwMjc2YWQwNmJlMTkzYjg4NmEzMGU0NGZmY2RiMGIzMDNmNmYzZDdiMTFmOTY2ZTIyMGQ4OGU3NTI4In0 -->
### `client.exportSarif`

Operation ID: `exportSarif`  
Route: `POST` `/v1/compliance/sarif`  

#### Signature

```java
public Void exportSarif(Map<String, Object> body)
public ApiResponse<Void> exportSarifWithResponse(Map<String, Object> body)
public CompletableFuture<ApiResponse<Void>> exportSarifWithResponseAsync(Map<String, Object> body)
public CompletableFuture<Void> exportSarifAsync(Map<String, Object> body)
public Void exportSarif(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Void> exportSarifAsync(Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Void> exportSarifWithResponse(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> exportSarifWithResponseAsync(Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | SARIF 2.1.0 JSON document | none |

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

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJleHBvcnRTYXJpZiJ9 -->

## Resource `health`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJnZXRIZWFsdGgiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJnZXRIZWFsdGgiLCJwYXRoIjoiL2hlYWx0aCIsInJlc291cmNlIjoiaGVhbHRoIiwic2VjdGlvbl9zaGEyNTYiOiIzODQ2NzA4NzNmN2FhYzYzODhiMzQzODFhOTNkMGE4ODM3YjUzMmY2MDQ3ODk0OWQwOGQ1ZTVkZGZhOWMwYjM3Iiwic2lnbmF0dXJlX3NoYTI1NiI6IjM3N2JkOTY1NGM0YmU1YzZkMDg5Yjg3Y2M0NzM4NTNlNjA0ZGEzMmRjYmYwNzgwNjEyNTI0NzYwMDc1OWVlMjUifQ -->
### `client.getHealth`

Operation ID: `getHealth`  
Route: `GET` `/health`  

#### Signature

```java
public Void getHealth()
public ApiResponse<Void> getHealthWithResponse()
public CompletableFuture<ApiResponse<Void>> getHealthWithResponseAsync()
public CompletableFuture<Void> getHealthAsync()
public Void getHealth(RequestOptions requestOptions)
public CompletableFuture<Void> getHealthAsync(RequestOptions requestOptions)
public ApiResponse<Void> getHealthWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> getHealthWithResponseAsync(RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Server health status | none |

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

## Resource `reviews`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJidWlsZEF1dG9maXhCdW5kbGUiLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoiYnVpbGRBdXRvZml4QnVuZGxlIiwicGF0aCI6Ii92MS9yZXZpZXdzL2F1dG9maXgiLCJyZXNvdXJjZSI6InJldmlld3MiLCJzZWN0aW9uX3NoYTI1NiI6ImZiZDExMWJjODkxODg3ZTBhZWQxOTM5MGI3NmRmMDUxMTYyMDljMTE1ODM2NzFlYTFiZWFmYzkwZDJjM2MxYTEiLCJzaWduYXR1cmVfc2hhMjU2IjoiMDgxZWU5ZGJkYTdhZGQ4MjM2MWZiMzQzNDQyYThkOTAxNTk5OTYxMTg1MjcxMmEyY2Q2ZTNmNWU0ODJhOTMzNSJ9 -->
### `client.buildAutofixBundle`

Operation ID: `buildAutofixBundle`  
Route: `POST` `/v1/reviews/autofix`  

#### Signature

```java
public Void buildAutofixBundle(ReviewRequest body)
public ApiResponse<Void> buildAutofixBundleWithResponse(ReviewRequest body)
public CompletableFuture<ApiResponse<Void>> buildAutofixBundleWithResponseAsync(ReviewRequest body)
public CompletableFuture<Void> buildAutofixBundleAsync(ReviewRequest body)
public Void buildAutofixBundle(ReviewRequest body, RequestOptions requestOptions)
public CompletableFuture<Void> buildAutofixBundleAsync(ReviewRequest body, RequestOptions requestOptions)
public ApiResponse<Void> buildAutofixBundleWithResponse(ReviewRequest body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> buildAutofixBundleWithResponseAsync(ReviewRequest body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `ReviewRequest` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Remediation patch bundle | none |

#### Canonical required-input example

```json
{
  "body": {
    "files": [
      {
        "filename": "example"
      }
    ]
  },
  "content_type": "application/json",
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJidWlsZEF1dG9maXhCdW5kbGUifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJjb21wdXRlUmlza1JhZGFyIiwibWV0aG9kIjoiUE9TVCIsIm9wZXJhdGlvbl9pZCI6ImNvbXB1dGVSaXNrUmFkYXIiLCJwYXRoIjoiL3YxL3Jldmlld3Mvcmlzay1yYWRhciIsInJlc291cmNlIjoicmV2aWV3cyIsInNlY3Rpb25fc2hhMjU2IjoiMjFiOWNlOTZlOTNiYzE5YWE4YzBhZmUzZGU1ZTEzM2NiNTBlY2M4OWE3Zjk0NWRhMzYxNTJhOTQ0N2ZhNDRmZSIsInNpZ25hdHVyZV9zaGEyNTYiOiIyMTNmOWEyOGVkOWRmYjlmYmUzMWI0N2Q4MzNiOWY3NTBkOGRhMjcxMTZjMDg5YTJiMGMwMDc4MzY5MjA1ZGNiIn0 -->
### `client.computeRiskRadar`

Operation ID: `computeRiskRadar`  
Route: `POST` `/v1/reviews/risk-radar`  

#### Signature

```java
public Void computeRiskRadar(ReviewRequest body)
public ApiResponse<Void> computeRiskRadarWithResponse(ReviewRequest body)
public CompletableFuture<ApiResponse<Void>> computeRiskRadarWithResponseAsync(ReviewRequest body)
public CompletableFuture<Void> computeRiskRadarAsync(ReviewRequest body)
public Void computeRiskRadar(ReviewRequest body, RequestOptions requestOptions)
public CompletableFuture<Void> computeRiskRadarAsync(ReviewRequest body, RequestOptions requestOptions)
public ApiResponse<Void> computeRiskRadarWithResponse(ReviewRequest body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> computeRiskRadarWithResponseAsync(ReviewRequest body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `ReviewRequest` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | 6-axis Risk Radar telemetry | none |

#### Canonical required-input example

```json
{
  "body": {
    "files": [
      {
        "filename": "example"
      }
    ]
  },
  "content_type": "application/json",
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJjb21wdXRlUmlza1JhZGFyIn0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJjcmVhdGVSZXZpZXciLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoiY3JlYXRlUmV2aWV3IiwicGF0aCI6Ii92MS9yZXZpZXdzIiwicmVzb3VyY2UiOiJyZXZpZXdzIiwic2VjdGlvbl9zaGEyNTYiOiI5NDc3NWYzYjkyNGVjNTlkMDk4Njk1MjMwYTE5ZDY1NDljOGI1ZjYyMGM0NzA4YzVmNmQ1MGM2ODdlZDk5MjJlIiwic2lnbmF0dXJlX3NoYTI1NiI6IjNlZDQ3NzgxOGQyZDM1YmZlMTQ0YWIzYjI1YWEzODEwMGJjZDhlMGRlNzM2YTExMTc2ZDgxN2MyYmVmMTI0MmQifQ -->
### `client.createReview`

Operation ID: `createReview`  
Route: `POST` `/v1/reviews`  

#### Signature

```java
public Void createReview(ReviewRequest body)
public ApiResponse<Void> createReviewWithResponse(ReviewRequest body)
public CompletableFuture<ApiResponse<Void>> createReviewWithResponseAsync(ReviewRequest body)
public CompletableFuture<Void> createReviewAsync(ReviewRequest body)
public Void createReview(ReviewRequest body, RequestOptions requestOptions)
public CompletableFuture<Void> createReviewAsync(ReviewRequest body, RequestOptions requestOptions)
public ApiResponse<Void> createReviewWithResponse(ReviewRequest body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> createReviewWithResponseAsync(ReviewRequest body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `ReviewRequest` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Completed review result with findings, blast radius, and change stack | none |

#### Canonical required-input example

```json
{
  "body": {
    "files": [
      {
        "filename": "example"
      }
    ]
  },
  "content_type": "application/json",
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJjcmVhdGVSZXZpZXcifQ -->

## Resource `saas`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJmaW5hbGl6ZU1ldGVyaW5nUXVvdGEiLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoiZmluYWxpemVNZXRlcmluZ1F1b3RhIiwicGF0aCI6Ii92MS9zYWFzL21ldGVyaW5nL2ZpbmFsaXplIiwicmVzb3VyY2UiOiJzYWFzIiwic2VjdGlvbl9zaGEyNTYiOiI5YjUxOTQ2MDNlNGMyNTY2NzQxYjMwNDMxMTc2MTg2NjcwYmM0NjA2OWQ0Yzc4YWNiZmNiYTE2YzUxYjRjY2JjIiwic2lnbmF0dXJlX3NoYTI1NiI6IjBhM2YxNTNjOWRkYjMwM2JjZjZmODdkZWQ1NWJmM2NlNzlmNzc0MTE4Y2Y5MzBhYTI0OWM0Y2I5ZjFiZGFkOWMifQ -->
### `client.finalizeMeteringQuota`

Operation ID: `finalizeMeteringQuota`  
Route: `POST` `/v1/saas/metering/finalize`  

#### Signature

```java
public Void finalizeMeteringQuota(Map<String, Object> body)
public ApiResponse<Void> finalizeMeteringQuotaWithResponse(Map<String, Object> body)
public CompletableFuture<ApiResponse<Void>> finalizeMeteringQuotaWithResponseAsync(Map<String, Object> body)
public CompletableFuture<Void> finalizeMeteringQuotaAsync(Map<String, Object> body)
public Void finalizeMeteringQuota(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Void> finalizeMeteringQuotaAsync(Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Void> finalizeMeteringQuotaWithResponse(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> finalizeMeteringQuotaWithResponseAsync(Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Finalized metering settlement | none |

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

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJmaW5hbGl6ZU1ldGVyaW5nUXVvdGEifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJnZXRTYWFzQmx1ZXByaW50IiwibWV0aG9kIjoiR0VUIiwib3BlcmF0aW9uX2lkIjoiZ2V0U2Fhc0JsdWVwcmludCIsInBhdGgiOiIvdjEvc2Fhcy9ibHVlcHJpbnQiLCJyZXNvdXJjZSI6InNhYXMiLCJzZWN0aW9uX3NoYTI1NiI6IjlhZGRmMzZiYzVmOGM1MmI2YmNjODRiMGI2NmJkY2VmNzNiZDQwNzRlZDYzY2RmYTA3NGU2ZGI2NTkwNWI0MzAiLCJzaWduYXR1cmVfc2hhMjU2IjoiMTExZGI3YmI0MGEzZGNkMjFkNWZlMTVjYWU2NjMxOTI4ODQ1OThkYTRmN2EyYjQwMTVkZGNlNjg5NWRlMTU4OCJ9 -->
### `client.getSaasBlueprint`

Operation ID: `getSaasBlueprint`  
Route: `GET` `/v1/saas/blueprint`  

#### Signature

```java
public Void getSaasBlueprint()
public ApiResponse<Void> getSaasBlueprintWithResponse()
public CompletableFuture<ApiResponse<Void>> getSaasBlueprintWithResponseAsync()
public CompletableFuture<Void> getSaasBlueprintAsync()
public Void getSaasBlueprint(RequestOptions requestOptions)
public CompletableFuture<Void> getSaasBlueprintAsync(RequestOptions requestOptions)
public ApiResponse<Void> getSaasBlueprintWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> getSaasBlueprintWithResponseAsync(RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Autonomous SaaS blueprint | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRTYWFzQmx1ZXByaW50In0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJpc3N1ZVN1cmZhY2VMZWFzZSIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJpc3N1ZVN1cmZhY2VMZWFzZSIsInBhdGgiOiIvdjEvc2Fhcy9zdXJmYWNlLWxlYXNlL2lzc3VlIiwicmVzb3VyY2UiOiJzYWFzIiwic2VjdGlvbl9zaGEyNTYiOiI4MmEwNmI3OWRlNzI3YjZkNTE2YThmM2EwNWRkOWQ4MzQxNDI2ZTk4MTZkODY1NTU2OWM5ZjE0OWQwODAzZWUzIiwic2lnbmF0dXJlX3NoYTI1NiI6ImU5NDYzOGI1YmMwNmYyY2I3YjM3NGQyZTdmZThmZWE2NDAwNTM2YzkzNTc0YmVhZTAzOWU4Y2QzMDExYTZmNWUifQ -->
### `client.issueSurfaceLease`

Operation ID: `issueSurfaceLease`  
Route: `POST` `/v1/saas/surface-lease/issue`  

#### Signature

```java
public Void issueSurfaceLease(Map<String, Object> body)
public ApiResponse<Void> issueSurfaceLeaseWithResponse(Map<String, Object> body)
public CompletableFuture<ApiResponse<Void>> issueSurfaceLeaseWithResponseAsync(Map<String, Object> body)
public CompletableFuture<Void> issueSurfaceLeaseAsync(Map<String, Object> body)
public Void issueSurfaceLease(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Void> issueSurfaceLeaseAsync(Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Void> issueSurfaceLeaseWithResponse(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> issueSurfaceLeaseWithResponseAsync(Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Issued surface lease token | none |

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

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJpc3N1ZVN1cmZhY2VMZWFzZSJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJyZXNlcnZlTWV0ZXJpbmdRdW90YSIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJyZXNlcnZlTWV0ZXJpbmdRdW90YSIsInBhdGgiOiIvdjEvc2Fhcy9tZXRlcmluZy9yZXNlcnZlIiwicmVzb3VyY2UiOiJzYWFzIiwic2VjdGlvbl9zaGEyNTYiOiJkYjViYjViMmM4ZDM5M2NkMDgzZmQwYmZkM2NjZjZhOTkzNzc2MDA0YTVhNmVlMzdiMzk2MjUwNDY4MDYxZjI5Iiwic2lnbmF0dXJlX3NoYTI1NiI6ImNmYzhkYzA1OTQ0Mjk4ZTNmYjIwN2ExMDkxODExMzA5MGRhMjFhY2FhN2NkZjQ1MGI0NmMzMzYwNzdlMDQ1OTkifQ -->
### `client.reserveMeteringQuota`

Operation ID: `reserveMeteringQuota`  
Route: `POST` `/v1/saas/metering/reserve`  

#### Signature

```java
public Void reserveMeteringQuota(Map<String, Object> body)
public ApiResponse<Void> reserveMeteringQuotaWithResponse(Map<String, Object> body)
public CompletableFuture<ApiResponse<Void>> reserveMeteringQuotaWithResponseAsync(Map<String, Object> body)
public CompletableFuture<Void> reserveMeteringQuotaAsync(Map<String, Object> body)
public Void reserveMeteringQuota(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Void> reserveMeteringQuotaAsync(Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Void> reserveMeteringQuotaWithResponse(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> reserveMeteringQuotaWithResponseAsync(Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Metering reservation record | none |

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

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJyZXNlcnZlTWV0ZXJpbmdRdW90YSJ9 -->

## Resource `sbom`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJnZW5lcmF0ZVNib20iLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoiZ2VuZXJhdGVTYm9tIiwicGF0aCI6Ii92MS9zYm9tIiwicmVzb3VyY2UiOiJzYm9tIiwic2VjdGlvbl9zaGEyNTYiOiJiNzAyYTFkY2M4M2NjZTQ2MTE5MTQyZWI1NDM1NTYyNzgxZGE3NzdhYThiMWFhYzk1ZWY5MGE0MmRhMDcxYTI2Iiwic2lnbmF0dXJlX3NoYTI1NiI6IjczNGI3ZjkxZDQ1M2M1NjAyOWVjZDQzZjRkODQzOTA3ZTNmMjgzN2MzYzljMTA4OGNhMzNmZmE1NmI1YTA2YWQifQ -->
### `client.generateSbom`

Operation ID: `generateSbom`  
Route: `POST` `/v1/sbom`  

#### Signature

```java
public Void generateSbom(ReviewRequest body)
public ApiResponse<Void> generateSbomWithResponse(ReviewRequest body)
public CompletableFuture<ApiResponse<Void>> generateSbomWithResponseAsync(ReviewRequest body)
public CompletableFuture<Void> generateSbomAsync(ReviewRequest body)
public Void generateSbom(ReviewRequest body, RequestOptions requestOptions)
public CompletableFuture<Void> generateSbomAsync(ReviewRequest body, RequestOptions requestOptions)
public ApiResponse<Void> generateSbomWithResponse(ReviewRequest body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> generateSbomWithResponseAsync(ReviewRequest body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `ReviewRequest` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | CycloneDX 1.5 SBOM JSON | none |

#### Canonical required-input example

```json
{
  "body": {
    "files": [
      {
        "filename": "example"
      }
    ]
  },
  "content_type": "application/json",
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZW5lcmF0ZVNib20ifQ -->

## Resource `supply_chain`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJhbmFseXplU3VwcGx5Q2hhaW4iLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoiYW5hbHl6ZVN1cHBseUNoYWluIiwicGF0aCI6Ii92MS9zdXBwbHktY2hhaW4vYW5hbHl6ZSIsInJlc291cmNlIjoic3VwcGx5X2NoYWluIiwic2VjdGlvbl9zaGEyNTYiOiJmZjk2Mjg3MzRiMTcxYmYwMzhiNDQxZDFjNmZlNThmNDk3NjU3NWM3ZDUxNGIwMDFiYWIzZDZjZWM5ZmFhMWJkIiwic2lnbmF0dXJlX3NoYTI1NiI6IjE3YTI5ZTA2ZjY4Y2Q2NjRjM2E4ZTY0YWFlOTY1YTQ3YTc5NTczYWI0YzQ5ZWI3ZGI2ZDgxNGQxN2ZiMDQ4YmMifQ -->
### `client.analyzeSupplyChain`

Operation ID: `analyzeSupplyChain`  
Route: `POST` `/v1/supply-chain/analyze`  

#### Signature

```java
public Void analyzeSupplyChain(ReviewRequest body)
public ApiResponse<Void> analyzeSupplyChainWithResponse(ReviewRequest body)
public CompletableFuture<ApiResponse<Void>> analyzeSupplyChainWithResponseAsync(ReviewRequest body)
public CompletableFuture<Void> analyzeSupplyChainAsync(ReviewRequest body)
public Void analyzeSupplyChain(ReviewRequest body, RequestOptions requestOptions)
public CompletableFuture<Void> analyzeSupplyChainAsync(ReviewRequest body, RequestOptions requestOptions)
public ApiResponse<Void> analyzeSupplyChainWithResponse(ReviewRequest body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> analyzeSupplyChainWithResponseAsync(ReviewRequest body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `ReviewRequest` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Supply-chain security audit | none |

#### Canonical required-input example

```json
{
  "body": {
    "files": [
      {
        "filename": "example"
      }
    ]
  },
  "content_type": "application/json",
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJhbmFseXplU3VwcGx5Q2hhaW4ifQ -->

## Resource `tasks`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJjcmVhdGVDb2RpbmdUYXNrIiwibWV0aG9kIjoiUE9TVCIsIm9wZXJhdGlvbl9pZCI6ImNyZWF0ZUNvZGluZ1Rhc2siLCJwYXRoIjoiL3YxL3Rhc2tzIiwicmVzb3VyY2UiOiJ0YXNrcyIsInNlY3Rpb25fc2hhMjU2IjoiOTA2ZmMzMDQ1NWRkZDIwZTQyYzM0ODI1YmU4MGRkMzdlNmY0ZGJkYzMwMmFkYmExZmVlMDUyYmVjZThhMjJjMCIsInNpZ25hdHVyZV9zaGEyNTYiOiI3ZTk5ODc4OThhYWNkM2NjZmVhOWI2OTdmMDAyYWE5ZjY5MzdkOTdiY2FjM2E4ZGU5ZTkwMzdkMjhjMGE0M2QyIn0 -->
### `client.createCodingTask`

Operation ID: `createCodingTask`  
Route: `POST` `/v1/tasks`  

#### Signature

```java
public Void createCodingTask(Map<String, Object> body)
public ApiResponse<Void> createCodingTaskWithResponse(Map<String, Object> body)
public CompletableFuture<ApiResponse<Void>> createCodingTaskWithResponseAsync(Map<String, Object> body)
public CompletableFuture<Void> createCodingTaskAsync(Map<String, Object> body)
public Void createCodingTask(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<Void> createCodingTaskAsync(Map<String, Object> body, RequestOptions requestOptions)
public ApiResponse<Void> createCodingTaskWithResponse(Map<String, Object> body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> createCodingTaskWithResponseAsync(Map<String, Object> body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `object` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `201` | Created coding task | none |

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

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJjcmVhdGVDb2RpbmdUYXNrIn0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJsaXN0Q29kaW5nVGFza3MiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJsaXN0Q29kaW5nVGFza3MiLCJwYXRoIjoiL3YxL3Rhc2tzIiwicmVzb3VyY2UiOiJ0YXNrcyIsInNlY3Rpb25fc2hhMjU2IjoiYjJiZDNkNTRjMDcxMzRlNTNiZTY3OGY5MzcyN2E3MDllYjU4NTVkMWEwZjg3YTZiNjA1MDU0OWRhZjFiOGExZiIsInNpZ25hdHVyZV9zaGEyNTYiOiI0MTEzMzFlYzgwMzAwMDEzNTAwNTk3MGUwMThlMzFlNjg2MjJjYjMzNjBmNzJjNzUxNTgzYzk1YjU2OGY5Y2VhIn0 -->
### `client.listCodingTasks`

Operation ID: `listCodingTasks`  
Route: `GET` `/v1/tasks`  

#### Signature

```java
public Void listCodingTasks()
public ApiResponse<Void> listCodingTasksWithResponse()
public CompletableFuture<ApiResponse<Void>> listCodingTasksWithResponseAsync()
public CompletableFuture<Void> listCodingTasksAsync()
public Void listCodingTasks(RequestOptions requestOptions)
public CompletableFuture<Void> listCodingTasksAsync(RequestOptions requestOptions)
public ApiResponse<Void> listCodingTasksWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> listCodingTasksWithResponseAsync(RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Task list | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsaXN0Q29kaW5nVGFza3MifQ -->

## Resource `triage`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJnZXRUcmlhZ2VRdWV1ZSIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6ImdldFRyaWFnZVF1ZXVlIiwicGF0aCI6Ii92MS90cmlhZ2UiLCJyZXNvdXJjZSI6InRyaWFnZSIsInNlY3Rpb25fc2hhMjU2IjoiMzllM2EyZmNjMzE3YTk5NWZmYWE5NDI3ZTFlOTVjYTU0M2UxZDIxNTg5NjM2MmFhMmZhYTczNWUyODIzNzcxNiIsInNpZ25hdHVyZV9zaGEyNTYiOiJhZmI4NDU5MzRiMWMxMWI3MGUwOTE3MWRmZDM0OGU2NWVmMTgyMjZlZjU1NTk2OGZjYjZlNDE5MTU3ZjI3Njg3In0 -->
### `client.getTriageQueue`

Operation ID: `getTriageQueue`  
Route: `GET` `/v1/triage`  

#### Signature

```java
public Void getTriageQueue()
public ApiResponse<Void> getTriageQueueWithResponse()
public CompletableFuture<ApiResponse<Void>> getTriageQueueWithResponseAsync()
public CompletableFuture<Void> getTriageQueueAsync()
public Void getTriageQueue(RequestOptions requestOptions)
public CompletableFuture<Void> getTriageQueueAsync(RequestOptions requestOptions)
public ApiResponse<Void> getTriageQueueWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> getTriageQueueWithResponseAsync(RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Triaged PR queue | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRUcmlhZ2VRdWV1ZSJ9 -->

## Resource `waitlist`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJsaXN0V2FpdGxpc3QiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJsaXN0V2FpdGxpc3QiLCJwYXRoIjoiL3YxL3dhaXRsaXN0IiwicmVzb3VyY2UiOiJ3YWl0bGlzdCIsInNlY3Rpb25fc2hhMjU2IjoiNDFmNjFiNGYzOTA5YjZhN2U0M2VkZGZmZGUyOTY2MTljMDQ1YzBkMThjOTBkYjlkMjZiMjViOGI1NjJhM2U1NSIsInNpZ25hdHVyZV9zaGEyNTYiOiIwNWRlOTkzZGU1OGJiMTA2YTYwMDg4ZWZiMTdjZDRmN2Q2YTQ2MTY0N2Q2ZDMxMmQ1YmIzMjhhMTU0NzAwOGUwIn0 -->
### `client.listWaitlist`

Operation ID: `listWaitlist`  
Route: `GET` `/v1/waitlist`  

#### Signature

```java
public Void listWaitlist()
public ApiResponse<Void> listWaitlistWithResponse()
public CompletableFuture<ApiResponse<Void>> listWaitlistWithResponseAsync()
public CompletableFuture<Void> listWaitlistAsync()
public Void listWaitlist(RequestOptions requestOptions)
public CompletableFuture<Void> listWaitlistAsync(RequestOptions requestOptions)
public ApiResponse<Void> listWaitlistWithResponse(RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> listWaitlistWithResponseAsync(RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Waitlist entries | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsaXN0V2FpdGxpc3QifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJyZWdpc3RlcldhaXRsaXN0IiwibWV0aG9kIjoiUE9TVCIsIm9wZXJhdGlvbl9pZCI6InJlZ2lzdGVyV2FpdGxpc3QiLCJwYXRoIjoiL3YxL3dhaXRsaXN0IiwicmVzb3VyY2UiOiJ3YWl0bGlzdCIsInNlY3Rpb25fc2hhMjU2IjoiODk3ZWFjMWI5MzZhN2I2Y2RiZGY3M2VkMjFiNTk2YTJkNmZjYTY2N2U2OTczN2RlODAyMzkzYWM4N2FlZTJmYiIsInNpZ25hdHVyZV9zaGEyNTYiOiIxZDVhZDBjYzE5NGU1ZTNiMjgwZTI2ZWYyM2Y5ZTg3NGZkYWFjNjI4YTUzMTFkMGM4NWU0MjJhMzIyNjljYmQ3In0 -->
### `client.registerWaitlist`

Operation ID: `registerWaitlist`  
Route: `POST` `/v1/waitlist`  

#### Signature

```java
public Void registerWaitlist(WaitlistRequest body)
public ApiResponse<Void> registerWaitlistWithResponse(WaitlistRequest body)
public CompletableFuture<ApiResponse<Void>> registerWaitlistWithResponseAsync(WaitlistRequest body)
public CompletableFuture<Void> registerWaitlistAsync(WaitlistRequest body)
public Void registerWaitlist(WaitlistRequest body, RequestOptions requestOptions)
public CompletableFuture<Void> registerWaitlistAsync(WaitlistRequest body, RequestOptions requestOptions)
public ApiResponse<Void> registerWaitlistWithResponse(WaitlistRequest body, RequestOptions requestOptions)
public CompletableFuture<ApiResponse<Void>> registerWaitlistWithResponseAsync(WaitlistRequest body, RequestOptions requestOptions)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `body` | body | yes | `WaitlistRequest` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `201` | Waitlist entry created | none |

#### Canonical required-input example

```json
{
  "body": {
    "email": "example-c65f@example.test"
  },
  "content_type": "application/json",
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJyZWdpc3RlcldhaXRsaXN0In0 -->

