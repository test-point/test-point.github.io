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
### Resources

[AusDigital](http://ausdigital.org) [TAP-GW specification](http://ausdigital.org/specs/ausdigital-tap-gw/1.0/) is under development at [GitHub](https://github.com/ausdigital/ausdigital-tap/). This describes how business messages are securely delivered to a participant endpoints in a peer-to-peer way.

With tap-gw.testpoint.io you are able:
* create tap-gw endpoints for some participant_ids
* query all messages, received by your endpoints
* send messages to any endpoint which you are aware of

This service is shared between the developers, so access control works this way:
* you claim some ABN on idp.testpoint.io (let's call it main participant identifier)
* you imagine some more abn which will be your virtual customers
* and you create endpoints for these virtual customers ABNs.
* any user have access only to endpoints which were created by himself. Virtual customers won't have access even to their own endpoints (but they can download documents directly from NRY when you tell them DocId from received message).

The api documentation is coming.

tap-gw.testpoint.io uses nry.testpoint.io installation, so sent messages may be downloaded directly from it with JWT of:
* participant_id, passed on endpoint creation as a parameter
* your participant_id, passed to endpoint creation endpoint by your JWT

This service requires valid JWT token from idp.testpoint.io, which is trivial to get.

### Help and support

The service is currently in BETA, so some problems are expected. Don't hesitate to contact us by [Slack channel](https://ausdigital.slack.com/messages/spec-tap/) of you have any problems or questions.

