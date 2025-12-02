---
title: API Reference Guide
description: Landing page for API references
tags:
  - api
  - reference
  - overview
---

This section provides a high-level reference for all endpoints in the OpenSpot API mock server. Each resource includes its own detailed page with request and response examples.

The OpenSpot API models coworking and coliving data using JSON Server. It exposes two primary resources:

- [`spaces`](spaces/spaces.md) – coworking and coliving locations
- [`availability`](availability/availability.md) – date-based availability for each space

## Base URL

All endpoints are served from the following base URL when running JSON Server locally:

```shell
http://localhost:3000
```

## HTTP Requests

Each resource supports standard CRUD-style operations (Create, Read, Update, Delete) via HTTP methods such as `GET`, `POST`, `PUT`, `PATCH`, and `DELETE`.

| Method | Description | Example |
| ------ | ----------- | ------- |
| `GET`    | Retrieve one or more resource objects. | `GET /spaces, GET spaces/1` |
| `POST`    | Create a new resource object. | `POST /spaces` |
| `PUT`    | Replace an existing resource object completely. | `PUT /spaces/1` |
| `PATCH`    | Partially update an existing resource object. | `PATCH /availability/2` |
| `DELETE`    | Delete an existing resource object. | `DELETE /spaces/1` |
