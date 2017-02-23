# Connectors

## Overview
Kaizala Connectors enable 3rd party developers to integrate Kaizala into their business processes by providing the ability to perform a curated set of actions in Kaizala 
using REST based API calls. The scope of the API is for external systems to call the end-point and perform actions on-demand. That is, this will be a PULL model – where 
individual endpoints need to be called to perform specific actions. The PUSH model where Kaizala platform can trigger actions is on the roadmap.

Kaizala Connectors are currently group-scoped - i.e. each Kaizala Connector needs to explicitly be granted permissions to a Conversation group - and then can perform actions through the API end-points only within the context of the group. However, each Kaizala Connector can be granted access to multiple groups.

* [Setup for using the Kaizala Connectors](connectors_setup.md)
* [API Documentation](connectors_API.md)
