---
title: Getting Started
description: Get started with the OpenSpot API in just a few minutes
tags:
  - getting-started
  - quickstart
  - tutorial
---

When working with the OpenSpot API locally, you will use **Node.js** and **JSON Server** to create a fully functional mock REST API powered by your OpenSpot JSON database file.

This guide will help you to do the following:

* Install Node.js

* Install JSON server

* Download OpenSpot API mock json file

* Run a simple `GET` command from the CLI using cURL

## Installing Node.js

Node.js is a JavaScript runtime that allows you to run JavaScript without the use of a browser.

It also includes **npm** (Node Package Manager), which is required to install JSON Server.

You'll first want to verify that you have Node.js already installed.

1. Open a CLI (command line interface) and enter `node -v`.

  If a version number appears, then you already have Node.js installed and you can move on to installing JSON server.

If you do not have it installed, then continue with the following steps:

1. Visit: **<https://nodejs.org/en/download>**

1. Download the latest LTS for your operating system.

1. Run the installer and complete the setup.

1. Verify the install by entering the following command in the CLI:

  `node -v`

## Installing JSON server

Once you have Node.js installed, you can go ahead and install JSON server. For this documentation, you should use v0.17.4 since the OpenSpot API json file is formatted to work with this version.

1. From the CLI enter:

  `npm install -g json-server@0.17.4`

1. After the install is complete, confirm by entering:

  `json-server --version`

  You should see 0.17.4

## Using the OpenSpot API json file

In order to use the OpenSpot API json file, you will need to fork and clone the [OpenSpot API repository](https://github.com/lauren-march/openspot-api) from Github first.

Once you have completed cloning you can now open the json file with JSON server.

1. Navigate to the folder where you cloned the OpenSpot API project.

   For example:
   `C:\<projectpath>\openspot-api`

1. Right click inside of this folder and select **Open in Terminal** (Windows 11).

1. Then run the following command:

  `json-server --watch openspot-db-source.json --port 3000`

  This is the output you should see:

  ```shell
    \{^_^}/ hi!

    Loading openspot-db-source.json
    Done

    Resources
    http://localhost:3000/spaces
    http://localhost:3000/availability

    Home
    http://localhost:3000
  ```

## Run a `GET` request with cURL

1. Open a command line and enter:

    `curl http://localhost:3000/spaces`

You should now see the list of all the spaces included in the OpenSpot API json file.

## Additional resources

[Tutorial: Add a new space](../tutorials/add-a-new-space.md)

[API Reference Guide](../api-reference/api-reference-guide.md)
