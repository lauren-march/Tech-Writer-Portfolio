---
title: Availability Resource Overview
description: Overview of the /availability resource for tracking space availability
tags:
  - api
  - availability
  - resource
  - overview
---

The `availability` resource represents the spots available for coliving and coworking spaces in the OpenSpot API. Each availability object contains information about its available spots and the date.

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

- **Retrieve** all availability records or filter by space ID or date
- **Create** new availability records
- **Update** existing availability records (partial or full)
- **Delete** availability records

## Common Use Cases

- Check availability for a specific space on a given date
- Update available spots when bookings are made or cancelled
- Add availability records for new dates or spaces
- Remove outdated availability records
- Track real-time capacity across all spaces

## Base URL

```shell
http://localhost:3000/availability
```
