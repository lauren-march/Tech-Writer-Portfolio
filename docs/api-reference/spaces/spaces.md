# Overview

The `spaces` resource represents coliving and coworking spaces available in the OpenSpot API. Each space contains information about its location, pricing, capacity, and a description of its amenities.

## Resource Structure

A `spaces` resource includes the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | integer | Unique identifier for the space (auto-generated) |
| `name` | string | Name of the coliving or coworking space |
| `location` | string | Geographic location in "City, Country" format |
| `pricePerHour` | number | Hourly rate for the space in USD |
| `capacity` | integer | Maximum occupancy of the space |
| `description` | string | Detailed description of the space and its features |

## Available Operations

The `spaces` resource supports the following operations:

- **Retrieve** all spaces or filter by location
- **Create** new spaces
- **Update** existing spaces (partial or full)
- **Delete** spaces

## Common Use Cases

- Browse available coworking and coliving spaces
- Search for spaces by location
- Add new spaces to the system
- Update space details such as pricing or capacity
- Remove spaces that are no longer available

## Base URL

```shell
http://localhost:3000/spaces
```
