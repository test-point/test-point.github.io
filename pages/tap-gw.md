---
title: A Testpoint.io access point gateway test service
description: The TAP-GW service provides a test API for ledger application vendors to test their access into the network.
diagram: /images/diagrams/test-ap.png
diagramMobile: /images/diagrams/test-ap-mobile.png
contentTitle: Test TAP-GW service
permalink: /tap-gw
tagline: TAP Gateway
menuTitle: Test TAP-GW
menuOrder: 5
---
### Work In Progress

[AusDigital](http://ausdigital.org) [TAP-GW specification](http://ausdigital.org/specs/ausdigital-tap-gw/1.0/) is under development at [GitHub](https://github.com/ausdigital/ausdigital-tap/). This describes how business messages are securely delivered to a participant endpoints in a peer-to-peer way.

A testpoint TAP-GW service is under construction. We've done all the heavy lifting by building all the other services upon which the TAP-GW depends.  So we won't be long.

With tap-gw.testpoint.io you are able:
* create tap-gw endpoint
* query all messages, received by your endpoints
* send messages to any endpoint which you are aware of

tap-gw.testpoint.io uses nry.testpoint.io installation, so sent messages may be downloaded directly from it with JWT of:
* participant_id, passed on endpoint creation as a parameter
* your participant_id, passed to endpoint creation endpoint by your JWT

This service required valid JWT token from idp.testpoint.io, which is trivial to get.
