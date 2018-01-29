# Kaizala Actions

## Overview
Kaizala Actions are basic 'units of work' that help users get work done within a conversation context inside Kaizala. Some of these Actions like Job, Survey, Poll, etc. are 
shipped out-of-the-box and provide scoped functionality. These Actions can be discovered within the Kaizala app and can be invoked in a conversation context from the Action 
Palette. 

[Kaizala Management Portal](https://manage.kaiza.la) is the gateway for all development, testing, approval or publishing of new Kaizala Actions.

The ability to invoke or create a new instance of an Action can currently be scoped to members of a specific group only. Support for publishing to members of all groups mapped to an organization through the Kaizala Management Portal is coming soon.

All Actions that are published to a set of users can be invoked by them on any conversations they are part of. These include their 1:1 conversations, private groups or groups mapped to an organization.

A Kaizala Action currently contains four different views that can be defined:

* A creation view when an Action is invoked from the palette
* A card view that appears on the chat canvas when an instance of the Action is sent
* A responder view for users to respond to the Kaizala Action
* A summary view to view aggregated responses

You can create new Kaizala Actions that leverage Kaizala’s people network and mobile capabilities to create compelling experiences in the following ways:

* **Design a new Kaizala Action through the Kaizala Management Portal** - You can design a custom Kaizala Action through the Action Designer interface by building on the existing Action templates.
* **Develop a new Kaizala Action package** - You can create complex new Kaizala Actions that provide custom functionality using web technologies like HTML, CSS and JavaScript. Follow the links below to learn about various stages of developement of a Kaizala Action.
    *   [Anatomy of a Kaizala Action package](anatomy.md)
    *   [Get Started](get_started.md)
    *   [Develop](develop.md)
    *   [Test and Debug](test.md)
    *   [Publish](publish.md)

All Kaizala Actions need to confirm to the [validation policies](validation.md) to be eligible to be published to Kaizala clients.

## Build your first Kaizala Action

You can try out building your first Kaizala Action by following our simple [tutorial](tutorial.md)

## Download Sample Action Packages

*  [Sample Actions in Request-Response format](https://manage.kaiza.la/MiniApps/DownloadSDK)
