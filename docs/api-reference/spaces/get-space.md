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

## GET all spaces

Retrieve all coliving and coworking spaces.

### Endpoint

```shell
GET /spaces
```

### Resource body

None

### Responses

| HTTP Code | Description | Schema |
|-----------|-------------|--------|
| 200 | List of all spaces | `spaces[]` |
| 404 | Space not found | `error` object |

### Example Request

#### cURL

```bash
curl GET http://localhost:3000/spaces
```

#### Postman

1. Set method to `GET`
1. Enter URL: `http://localhost:3000/spaces`
1. Click **Send**

### Example Response

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

## GET spaces by ID

Retrieve a single coliving and coworking space by ID.

### Endpoint

```shell
GET /spaces/{id}
```

### Resource body

None

### Responses

| HTTP Code | Description | Schema |
|-----------|-------------|--------|
| 200 | List of a single space by its ID | `spaces` object |
| 404 | Space not found | `error` object |

### Example Request

#### cURL

```bash
curl GET http://localhost:3000/spaces/2
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

## GET spaces by location

Retrieve coliving and coworking spaces by location.

### Endpoint exact match

```shell
GET /spaces?location=<CityName>,<CountryName>
```

### Endpoint partial match

```shell
GET /spaces?location_like=<PartialLocation>
```

### Resource body

None

#### Exact vs partial

* Use `location` for an exact match, e.g. Berlin,Germany.

* Use `location_like` for a partial match, such as "Ber" or "Germany".

### Responses

| HTTP Code | Description                        | Schema                |
|-----------|------------------------------------|-----------------------|
| 200       | List of spaces matching location   | `spaces[]`             |
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
