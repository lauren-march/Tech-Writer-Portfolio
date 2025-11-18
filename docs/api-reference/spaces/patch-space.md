---
title: PATCH /spaces - Update a Space
description: Partially update an existing space resource
tags:
  - api
  - spaces
  - PATCH
  - update
---

Use the `PATCH` method to partially update an existing space resource.

## Update a space

Partially update a coliving or coworking space. Only the fields provided in the request body will be updated.

### Endpoint

```shell
PATCH /spaces/{id}
```

### Request body

Include only the fields you want to update. All fields are optional.

```json
{
  "name": "string",
  "location": "string",
  "pricePerHour": number,
  "capacity": number,
  "description": "string"
}
```

#### Example

```json
{
  "pricePerHour": 8,
  "capacity": 18
}
```

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `id` | number | Yes | The unique identifier of the space to modify. |

### Responses

| HTTP Code | Description | Schema |
|-----------|-------------|--------|
| 200 | Space updated successfully | `spaces` object |
| 404 | Space not found | `error` object |
| 400 | Bad request - invalid data | `error` object |

### Example request

#### cURL

```bash
curl -X PATCH http://localhost:3000/spaces/2 \
  -H "Content-Type: application/json" \
  -d '{
    "pricePerHour": 8
  }'
```

#### Postman

1. Set method to `PATCH`
1. Enter URL: `http://localhost:3000/spaces/2`
1. Go to **Body** tab
1. Select **raw** and choose **JSON** from dropdown
1. Paste the request body JSON (only fields to update):

    ```json
    {
    "pricePerHour": 8
    }
    ```

1. Click **Send**

    ![](../media/patch-postman-example.png)

### Example response

```json
{
  "id": 2,
  "name": "WorkHub Central",
  "location": "Austin, USA",
  "pricePerHour": 8,
  "capacity": 40,
  "description": "Downtown coworking hub with high-speed Wi-Fi and free coffee." 
}
```

### Notes

* Only the fields included in the request body will be updated
* All other fields remain unchanged
* The `id` field cannot be modified

#### PATCH vs PUT

| Method | Use Case | Example |
|--------|----------|---------|
| **PATCH** | Update specific fields only | Change only price |
| **PUT** | Replace entire resource | Update all fields at once |
