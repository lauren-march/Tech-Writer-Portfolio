---
title: PUT /availability - Replace Availability
description: Completely replace an existing availability record
tags:
  - api
  - availability
  - PUT
  - replace
  - update
---

Use the `PUT` method to completely replace an existing availability resource.

## Replace an availability record

Replace an entire availability record. All fields must be provided in the request body.

### Endpoint

```shell
PUT /availability/{id}
```

### Request body

All fields (except `id`) must be included in the request body to replace the entire resource.

```json
{
  "spaceId": number,
  "availableSpots": number,
  "date": "string"
}
```

#### Example

```json
{
  "spaceId": 1,
  "availableSpots": 8,
  "date": "2025-12-15"
}
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `id` | number | Yes | The unique identifier of the availability record to modify. |

### Responses

| HTTP Code | Description | Schema |
|-----------|-------------|--------|
| 200 | Availability record replaced successfully | `availability` object|
| 404 | Availability record not found | `error` object |
| 400 | Bad request - invalid or missing data | `error` object |

### Example Request

#### cURL

```bash
curl -X PUT http://localhost:3000/availability/1 \
  -H "Content-Type: application/json" \
  -d '{
    "spaceId": 1,
    "availableSpots": 8,
    "date": "2025-12-15"
  }'
```

#### Postman

1. Set method to `PUT`
1. Enter URL: `http://localhost:3000/availability/1`
1. Go to **Body** tab
1. Select **raw** and choose **JSON** from dropdown
1. Paste the complete request body JSON:

    ```json
        {
        "spaceId": 1,
        "availableSpots": 8,
        "date": "2025-12-15"
        }
    ```

1. Click **Send**

    ![](../media/put-availability-postman-example.png)

### Example Response

```json
{
  "id": 1,
  "spaceId": 1,
  "availableSpots": 8,
  "date": "2025-12-15"
}
```

### Notes

* PUT replaces the **entire resource**, so all fields must be provided
* Missing fields will be removed from the record
* The `id` field cannot be modified and should not be included in the request body
* `spaceId` must reference an existing space

### PUT vs PATCH

| Method | Use Case | Example |
|--------|----------|---------|
| **PATCH** | Update specific fields only | Change only available spots |
| **PUT** | Replace entire resource | Update all fields at once |
