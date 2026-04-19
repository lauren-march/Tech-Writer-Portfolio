---
title: Availability Resource Overview for OpenSpot API
description: Reference for the /availability resource in the OpenSpot API. Track available spots by space and date with GET, POST, PUT, PATCH, and DELETE operations.
tags:
  - api
  - rest api
  - availability
  - openspot api
  - api reference
  - coworking
  - coliving
---

# Availability Resource Overview for OpenSpot API

The `availability` resource contains availability information of coliving and coworking spaces in the OpenSpot API. Each availability object is linked to a space and stores information regarding its available number of spots and the date of availability.

## Resource Structure

A `spaces` resource includes the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | integer | Unique identifier for the availability record (auto-generated) |
| `spaceId` | integer | Reference to the associated space ID |
| `availableSpots` | integer | Number of spots currently available |
| `date` | string | Date of availability in "YYYY-MM-DD" format |

## Available Operations

The `availability` resource supports the following operations:

- **Retrieve** all availability records or filter by space ID or date.
- **Create** new availability records.
- **Update** existing availability records (partial or full).
- **Delete** availability records.

## Common Use Cases

- Check availability for a specific space on a given date.
- Update available spots when bookings are made or cancelled.
- Add availability records for new dates or spaces.
- Remove outdated availability records.
- Track real-time capacity across all spaces.

## Base URL

```shell
http://localhost:3000/availability
```
