---
title: Tutorial - Find space by location
description: Learn how to query for spaces by location
tags:
  - tutorial
  - spaces
  - GET
  - query
---

# How to retrieve a Space record in the OpenSpot API by location

In this tutorial, you'll learn how to find spaces by their location in the OpenSpot API JSON mock database. In order to find spaces, you'll need to use the `GET` HTTP method.

The `GET` method queries the database for all instances of specified properties and returns a `spaces` array. This is useful when you need to see a full list of coworking or coliving spaces in a particular area.

You can reasonably expect this tutorial to take about 10 minutes or less to complete.

## Before you start

Make sure you have set up your database environment by following the steps in the [Set up your server](../overview/getting-started.md) guide.

You will also need to download and use [Postman](https://www.postman.com/downloads/) or use cURL from the command line.

## Find spaces by location

For this tutorial we will be using the `_like` JSON Server filter operator. This will allow us to filter locations that may only be partial matches. For example, you can use `_like` in queries similar to `GET /spaces?location_like=berlin` to find all spaces within Berlin without needing the exact 'City, Country' match.

This is useful when an API may not specify the exact format of the resource's variables. You can think of it as emulating intelligent search that you would typically find when interacting with real APIs.

Follow the steps below to find all instances of spaces by their location.

### cURL walkthrough

1. Open a CLI (command line interface) and enter the following command:

    `curl "http://localhost:3000/spaces?location_like=canada"`

1. Hit **Enter** to run the command.

    ![Expected result](media/find-space-by-location/curl-example.png)

### Postman walkthrough

1. Open an instance of Postman and create a new Request by clicking the **'+'**.

1. Select **GET** from the dropdown.

1. Enter the following URL into the URL field:

    `http://localhost:3000/spaces?location_like=canada`

1. Click **Send**.

    ![](media/find-space-by-location/postman-example.png)

!!! note
    In Postman when you enter the query information, this will open the **Params** tab and render a table of key-value pairs. You can further narrow filters by entering additional keys and values with this handy GUI table.

You have now successfully found all the spaces filtered by location using a partial match.

## Additional resources

[GET /spaces](../api-reference/spaces/get-space.md)
