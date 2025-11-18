---
title: DELETE /availability - Delete Availability
description: Permanently delete an availability record
tags:
  - api
  - availability
  - DELETE
  - remove
---

Use the `DELETE` method to remove an existing availability resource.

## Permanently delete a availability

Permanently delete the availability information for a coliving or coworking space from the database.

### Endpoint

```shell
DELETE /availability/{id}
```

### Request body

None.

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `id` | number | Yes | The unique identifier of the availability to delete |

### Responses

| HTTP Code | Description | Schema |
|-----------|-------------|--------|
| 200 | Availability deleted successfully | `success` - empty object |
| 404 | Availability not found | `error` object |

### Example request

#### cURL

```bash
curl -X DELETE http://localhost:3000/availability/3
```

#### Postman

1. Set method to `DELETE`
1. Enter URL: `http://localhost:3000/availability/3`
1. Ensure **Body** is set to **none**.
1. Click **Send**

    ![](../media/delete-availability-postman-example.png)

### Example response

```json
{}
```
