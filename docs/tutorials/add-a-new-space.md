---
title: Tutorial - Add a New Space
description: Step-by-step guide to adding a new coliving or coworking space
tags:
  - tutorial
  - spaces
  - POST
  - create
---

In this tutorial, you'll learn how to create a new space in the OpenSpot API JSON mock database. In order to add a new space, you'll need to use the `POST` HTTP method.

The `POST` method appends a new `space` object to the `spaces` array. This is useful when you need to add a newly available coworking or coliving space.

You can reasonably expect this tutorial to take about 15 minutes or less to complete.

## Before you start

Make sure you have set up your database environment by following the steps in the [Set up your server](../overview/getting-started.md) guide.

You will also need to download and use [Postman](https://www.postman.com/downloads/). You can optionally use cURL, however, Postman for `POST` calls are generally more intuitive. Since you will be entering **body** information, the formatting is more simple in Postman as opposed to cURL in the CLI.

## Add a new space

Follow the steps below to create a new space.

1. Open an instance of Postman and create a new Request by clicking the **'+'**.

1. Select **POST** from the dropdown.

1. Enter the following URL into the URL field:

    `http://localhost:3000/spaces`

1. Select the **Body** tab and select the **raw** radio button.

1. Enter the following body information:

   ```json
    {
    "name": "Sunset Studio",
    "location": "Barcelona, Spain",
    "pricePerHour": 6,
    "capacity": 15,
    "description": "Bright coworking space with Mediterranean views and creative atmosphere."
    }
    ```

1. Click **Send**.

    ![](../tutorials/media/postman-example.png)

You have now successfully added a new space to the OpenSpot API.

## Additional resources

[POST /spaces](../api-reference/spaces/post-space.md)
