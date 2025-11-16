# DELETE /spaces endpoint reference

Use the `DELETE` method to remove an existing space resource.

## Permanently delete a space

Permanently delete a coliving or coworking space from the database.

### Endpoint

```shell
DELETE /spaces/{id}
```

### Request body

None.

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `id` | number | Yes | The unique identifier of the space to delete |

### Responses

| HTTP Code | Description | Schema |
|-----------|-------------|--------|
| 200 | Space deleted successfully | `success` - empty object |
| 404 | Space not found | `error` object |

### Example request

#### cURL

```bash
curl -X DELETE http://localhost:3000/spaces/3
```

#### Postman

1. Set method to `DELETE`
1. Enter URL: `http://localhost:3000/spaces/3`
1. Ensure **Body** is set to **none**.
1. Click **Send**

    ![](../media/delete-postman-example.png)

### Example response

```json
{}
```
