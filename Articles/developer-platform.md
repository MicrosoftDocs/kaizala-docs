---
title: Overview
description: Overview of Microsoft Kaizala Developer Platform
topic: overview
author: nitinjms
---
# Microsoft Kaizala Developer Documentation

Kaizala is a messaging and productivity app that enable your mobile users to achieve more. With Kaizala, you can have 1:1 chat with individuals, group chat with your teams, and even add groups to your existing groups to communicate within large organizations or communities.

> **Don't have Kaizala? Download the app now for Windows Phone, Android & iOS. [Here's how](install.md).**

## Microsoft Kaizala Developer Platform 
The Kaizala Developer Platform offers multiple ways to integrate and extend Kaizala to suit your organizational needs. With the developer preview, you can use Connectors to integrate Kaizala with your business processes and design custom Actions through the Kaizala Management Portal.

## Connectors

Kaizala Connectors enable 3rd party developers to integrate Kaizala into their business processes by providing the ability to perform a curated set of actions in Kaizala 
using REST based API calls. The scope of the API is for external systems to call the end-point and perform actions on-demand. That is, this will be a PULL model – where 
individual endpoints need to be called to perform specific actions using Kaizala **[APIs](connectors/API.md)**. The PUSH model where Kaizala platform can trigger actions can be configured using **[webhooks](connectors/webHooks.md)**.

[Get started with Connectors](connectors/README.md)

## Kaizala Actions

Kaizala Actions are basic 'units of work' that help users get work done within a conversation context inside Kaizala. Some of these Actions like Job, Survey, Poll, etc. are
shipped out-of-the-box and provide scoped functionality. These Actions can be discovered within the Kaizala app and can be invoked in a conversation context from the Action Palette.

[Get started with Kaizala Actions](Actions/README.md)

## Kaizala API Throttling Limit

[The API gateway](https://docs.microsoft.com/en-in/azure/api-management/api-management-key-concepts) for Kaizala APIs has the throttling limit of 100 calls per min. The limit key is a combination of UserId and ConnectorId. When throttling limit exceeds, response header "Retry-After" is returned along with http status code 429. This specifies how many seconds to wait before making a follow-up request. The API consumers need to make a note of this and handle it appropriately.

## Submit your questions, bugs, feature requests, and contributions

We listen to the developer community across [several channels](feedback.md).
