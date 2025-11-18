---
# markdownlint-disable
# vale  off
title: GET /availability - Retrieve Availability
description: Retrieve availability records for spaces by ID, space, or date
tags:
  - api
  - availability
  - GET
  - retrieve
  - filter
# vale  on
# markdownlint-enable
---

Use the `GET` method to access `/availability` resource data.

## Retrieve all availability records

Retrieve all availability records for coliving and coworking spaces.

### Endpoint

```shell
GET /availability
```

### Request body

None

### Parameters

None

### Responses

| HTTP Code | Description | Schema |
|-----------|-------------|--------|
| 200 | List of all availability records | `availability[]` |
| 404 | Availability records not found | `error` object |

### Example request

#### cURL

```bash
curl GET http://localhost:3000/availability
```

#### Postman

1. Set method to `GET`
1. Enter URL: `http://localhost:3000/availability`
1. Click **Send**

### Example response

```json
[
  {
    "id": 1,
    "spaceId": 1,
    "availableSpots": 3,
    "date": "2025-12-10"
  },
  {
    "id": 2,
    "spaceId": 2,
    "availableSpots": 10,
    "date": "2025-12-10"
  },
  {
    "id": 3,
    "spaceId": 3,
    "availableSpots": 5,
    "date": "2025-12-10"
  },
  {
    "id": 4,
    "spaceId": 4,
    "availableSpots": 4,
    "date": "2025-12-10"
  }
]
```

## Retrieve an availability record by ID

Retrieve a single availability record by ID.

### Endpoint

```shell
GET /availability/{id}
```

### Request body

None

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `id` | number | Yes | The unique identifier of the availability record to retrieve |

### Responses

| HTTP Code | Description | Schema |
|-----------|-------------|--------|
| 200 | Single availability record by its ID | `availability` object |
| 404 | Availability record not found | `error` object |

### Example request

#### cURL

```bash
curl GET http://localhost:3000/availability/1
```

#### Postman

1. Set method to `GET`
1. Enter URL: `http://localhost:3000/availability/1`
1. Click **Send**

### Example response

```json
{
  "id": 1,
  "spaceId": 1,
  "availableSpots": 3,
  "date": "2025-12-10"
}
```

## Retrieve availability by space ID

Retrieve availability records for a specific space.

### Endpoint

```shell
GET /availability?spaceId={spaceId}
```

### Request body

None

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `spaceId` | number | Yes | The unique identifier of the space to check availability for |

### Responses

| HTTP Code | Description | Schema |
|-----------|-------------|--------|
| 200 | List of availability records for the space | `availability[]` |
| 404 | No availability records found | `error` object |

### Example request

#### cURL

```bash
curl GET http://localhost:3000/availability?spaceId=1
```

#### Postman

1. Set method to `GET`
1. Enter URL: `http://localhost:3000/availability?spaceId=1`
1. Click **Send**

### Example response

```json
[
  {
    "id": 1,
    "spaceId": 1,
    "availableSpots": 3,
    "date": "2025-12-10"
  }
]
```

## Retrieve availability by date

Retrieve availability records for a specific date.

### Endpoint

```shell
GET /availability?date={date}
```

### Request body

None

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `date` | string | Yes | The date to check availability for in "YYYY-MM-DD" format (e.g., "2025-12-10") |

### Responses

| HTTP Code | Description | Schema |
|-----------|-------------|--------|
| 200 | List of availability records for the date | `availability[]` |
| 404 | No availability records found | `error` object |

### Example request

#### cURL

```bash
curl GET http://localhost:3000/availability?date=2025-12-10
```

#### Postman

1. Set method to `GET`
1. Enter URL: `http://localhost:3000/availability?date=2025-12-10`
1. Click **Send**

### Example response

```json
[
  {
    "id": 1,
    "spaceId": 1,
    "availableSpots": 3,
    "date": "2025-12-10"
  },
  {
    "id": 2,
    "spaceId": 2,
    "availableSpots": 10,
    "date": "2025-12-10"
  },
  {
    "id": 3,
    "spaceId": 3,
    "availableSpots": 5,
    "date": "2025-12-10"
  },
  {
    "id": 4,
    "spaceId": 4,
    "availableSpots": 4,
    "date": "2025-12-10"
  }
]
```
