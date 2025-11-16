# PUT /spaces

Use the `PUT` method to completely replace an existing space resource.

## Replace a space

Replace an entire coliving or coworking space. All fields must be provided in the request body.

### Endpoint

```shell
PUT /spaces/{id}
```

### Request Body

All fields (except `id`) must be included in the request body to replace the entire resource.

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
  "name": "The Nest Renovated",
  "location": "Lisbon, Portugal",
  "pricePerHour": 8,
  "capacity": 25,
  "description": "Newly renovated community-driven coliving for digital nomads with ocean views."
}
```

### Responses

| HTTP Code | Description | Schema |
|-----------|-------------|--------|
| 200 | Space replaced successfully | `spaces` object|
| 404 | Space not found | `error` object |
| 400 | Bad request * invalid or missing data | `error` object |

### Example Request

#### cURL

```bash
curl -X PUT http://localhost:3000/spaces/3 \
  -H "Content-Type: application/json" \
  -d '{
    "name": "The Nest Renovated",
    "location": "Lisbon, Portugal",
    "pricePerHour": 8,
    "capacity": 25,
    "description": "Newly renovated community-driven coliving for digital nomads with ocean views."
  }'
```

#### Postman

1. Set method to `PUT`
1. Enter URL: `http://localhost:3000/spaces/3`
1. Go to **Body** tab
1. Select **raw** and choose **JSON** from dropdown
1. Paste the complete request body JSON:

    ```json
    {
    "name": "The Nest Renovated",
    "location": "Lisbon, Portugal",
    "pricePerHour": 8,
    "capacity": 25,
    "description": "Newly renovated community-driven coliving for digital nomads with ocean views."
    }
    ```

1. Click **Send**

    ![](../media/put-postman-example.png)

### Example Response

```json
{
  "id": 3,
  "name": "The Nest Renovated",
  "location": "Lisbon, Portugal",
  "pricePerHour": 8,
  "capacity": 25,
  "description": "Newly renovated community-driven coliving for digital nomads with ocean views."
}
```

### Notes

* PUT replaces the **entire resource**, so all fields must be provided
* Missing fields will be set to `null` or removed (depending on json-server behavior)
* The `id` field cannot be modified and should not be included in the request body

### PUT vs PATCH

| Method | Use Case | Example |
|--------|----------|---------|
| **PATCH** | Update specific fields only | Change only price |
| **PUT** | Replace entire resource | Update all fields at once |
