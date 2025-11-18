---
# markdownlint-disable
# vale  off
title: PATCH /availability - Update Availability
description: Partially update an existing availability record
tags:
  - api
  - availability
  - PATCH
  - update
  # vale  on
# markdownlint-enable
---

Use the `PATCH` method to partially update an existing availability resource.

## Update an availability record

Partially update an availability record. Only the fields provided in the request body will be updated.

### Endpoint

```shell
PATCH /availability/{id}
```

### Request body

Include only the fields you want to update. All fields are optional.

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
  "availableSpots": 5
}
```

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `id` | number | Yes | The unique identifier of the availability record to modify. |

### Responses

| HTTP Code | Description | Schema |
|-----------|-------------|--------|
| 200 | Availability record updated successfully | `availability` object |
| 404 | Availability record not found | `error` object |
| 400 | Bad request - invalid data | `error` object |

### Example request

#### cURL

```bash
curl -X PATCH http://localhost:3000/availability/1 \
  -H "Content-Type: application/json" \
  -d '{
    "availableSpots": 5
  }'
```

#### Postman

1. Set method to `PATCH`
1. Enter URL: `http://localhost:3000/availability/1`
1. Go to **Body** tab
1. Select **raw** and choose **JSON** from dropdown
1. Paste the request body JSON (only fields to update):

    ```json
    {
    "availableSpots": 5
    }
    ```

1. Click **Send**

    ![](../media/patch-availability-postman-example.png)

### Example response

```json
{
  "id": 1,
  "spaceId": 1,
  "availableSpots": 5,
  "date": "2025-12-10"
}
```

### Notes

* Only the fields included in the request body will be updated
* All other fields remain unchanged
* The `id` field cannot be modified
* Date must be in "YYYY-MM-DD" format if updating
* `spaceId` must reference an existing space if updating

#### PATCH vs PUT

| Method | Use Case | Example |
|--------|----------|---------|
| **PATCH** | Update specific fields only | Change only available spots |
| **PUT** | Replace entire resource | Update all fields at once |
