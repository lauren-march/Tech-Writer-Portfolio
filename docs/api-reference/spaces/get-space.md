---
# markdownlint-disable
# vale  off
layout: default
parent: user resource
nav_order: 1
# tags used by AI files
description: GET all `user` resources from the service
tags:
    - api
categories:
    - api-reference
ai_relevance: high
importance: 7
prerequisites:
    - /api/user
related_pages: []
examples: []
api_endpoints: 
    - GET /users
version: "v1.0"
last_updated: "2025-09-03"
# vale  on
# markdownlint-enable
---

# GET /spaces

Use the `GET` method to access `/spaces` resource data.

## Retrieve all spaces

Retrieve all coliving and coworking spaces.

### Endpoint

```shell
GET /spaces
```

### Request body

None

### Parameters

None

### Responses

| HTTP Code | Description | Schema |
|-----------|-------------|--------|
| 200 | List of all spaces | `spaces[]` |
| 404 | Space not found | `error` object |

### Example request

#### cURL

```bash
curl GET http://localhost:3000/spaces
```

#### Postman

1. Set method to `GET`
1. Enter URL: `http://localhost:3000/spaces`
1. Click **Send**

### Example response

```json
{
      "id": 1,
      "name": "Urban Loft",
      "location": "Berlin, Germany",
      "pricePerHour": 7,
      "capacity": 12,
      "description": "Modern coliving space with shared kitchen and rooftop workspace."
    },
    {
      "id": 2,
      "name": "WorkHub Central",
      "location": "Austin, USA",
      "pricePerHour": 3,
      "capacity": 40,
      "description": "Downtown coworking hub with high-speed Wi-Fi and free coffee."
    },
    {
      "id": 3,
      "name": "The Nest",
      "location": "Lisbon, Portugal",
      "pricePerHour": 5,
      "capacity": 20,
      "description": "Community-driven coliving for digital nomads near the beach."
    },
    {
      "id": 4,
      "name": "The Green Desk",
      "location": "Vancouver, Canada",
      "pricePerHour": 10,
      "capacity": 8,
      "description": "Sustainable coworking space surrounded by nature."
    }
```

## Retrieve a space by ID

Retrieve a single coliving and coworking space by ID.

### Endpoint

```shell
GET /spaces/{id}
```

### Request body

None

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `id` | number | Yes | The unique identifier of the space to retrieve |

### Responses

| HTTP Code | Description | Schema |
|-----------|-------------|--------|
| 200 | List of a single space by its ID | `spaces` object |
| 404 | Space not found | `error` object |

### Example request

#### cURL

```bash
curl GET http://localhost:3000/spaces/2
```

#### Postman

1. Set method to `GET`
1. Enter URL: `http://localhost:3000/spaces/2`
1. Click **Send**

### Example response

```json
{
    "id": 2,
    "name": "WorkHub Central",
    "location": "Austin, USA",
    "pricePerHour": 3,
    "capacity": 40,
    "description": "Downtown coworking hub with high-speed Wi-Fi and free coffee."
}
```

## Retrieve spaces by location

Retrieve coliving and coworking spaces by location.

### Endpoint exact match

```shell
GET /spaces?location=<CityName>,<CountryName>
```

### Endpoint partial match

```shell
GET /spaces?location_like=<PartialLocation>
```

### Request body

None

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `location` | string | Yes | Exact location match. Format: "City, Country" (e.g., "Lisbon, Portugal") |
| `location_like` | string | No* | Partial location match. Searches for any location containing the string (e.g., "Lisbon" or "Portugal") |

> [!NOTE]  
> \*`location_like` is not required for this query, but offers a bit more flexibility.

### Responses

| HTTP Code | Description                        | Schema                |
|-----------|------------------------------------|-----------------------|
| 200       | List of spaces matching location   | `spaces[]`            |
| 404       | No matching spaces found           | `error` object        |

### Example Request

#### cURL

```bash
curl GET http://localhost:3000/spaces?location="Lisbon, Portugal"
```

#### Postman

1. Set method to `GET`
1. Enter URL: `http://localhost:3000/spaces/2`
1. Click **Send**

### Example Response

```json
{
    "id": 2,
    "name": "WorkHub Central",
    "location": "Austin, USA",
    "pricePerHour": 3,
    "capacity": 40,
    "description": "Downtown coworking hub with high-speed Wi-Fi and free coffee."
}
```
