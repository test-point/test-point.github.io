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

With [tap-gw.testpoint.io](https://tap-gw.testpoint.io) you can:
* behave as a ledger or as a independent eInvoicing participant/business
* create tap-gw endpoints for your customers or for yourself
* query all messages received by your endpoints
* send messages to any endpoint which you are aware of

This service is shared between the developers, so access control works this way:
* ledger claims some ABN on [idp.testpoint.io](https://idp.testpoint.io) (let's call it main/ledger participant identifier)
* ledger picks up some more ABN/participant IDs which will be his virtual customers
* ledger creates endpoints for these virtual customers, providing corresponding participant ID
* any ledger have access only to endpoints which were created by himself. Virtual customers will not have access even to endpoints created for them (but they can download documents directly from NRY by DocId, and DocId is known to ledger from messages list).

tap-gw.testpoint.io uses [nry.testpoint.io](https://nry.testpoint.io) installation, so sent messages may be downloaded directly from it with JWT belonging to:
* participant_id, passed on endpoint creation as a parameter
* ledger participant_id, passed to endpoint creation endpoint by your JWT

This service requires valid JWT token from [idp.testpoint.io](https://idp.testpoint.io), which is trivial to get.

### API documentation and clients

[API documentation in ReadTheDocs format](https://tap-gw.testpoint.io/api/docs/)

Request quick example:

```
export AUTH_JWT="{YOUR-TOKEN-HERE}"
curl -H "Accept: application/json; indent=4"
     -H "Authorization: JWT ${AUTH_JWT}" \
    https://tap-gw.testpoint.io/api/endpoints/
```

[More detailed bash examples](https://github.com/test-point/testpoint-tap-gw/tree/master/client-sh) (check out readme in this repo about usage)

[Use cases for message creation](https://tap-gw.testpoint.io/api/docs/testcases.html#create-and-sign-a-message)

[Test TAP message creation script](https://github.com/test-point/testpoint-tap/tree/master/tap-message-composer)

### Help and support

The service is currently in BETA, so some problems are expected. Don't hesitate to contact us by [Slack channel](https://ausdigital.slack.com/messages/spec-tap/) of you have any problems or questions.

