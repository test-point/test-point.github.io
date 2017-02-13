---
title: A Testpoint.io notary test service
description: A Notary can be used to prove a message existed. This enables secure-by-design B2B protocols that require less trust to function. This increases efficiency where it reduces the need for expensive and unreliable perimeter security.
diagram: /images/diagrams/test-nry.png
diagramMobile: /images/diagrams/test-nry-mobile.png
contentTitle: Notary
permalink: /nry
tagline: Notary
menuTitle: Test NRY
menuOrder: 1
---
### Work in Progress

[AusDigital](http://ausdigital.org/) are developing open standards for notary services to support B2B protocols. These are under development at [GitHub](https://github.com/ausdigital/ausdigital-nry)

We will release a free nry.testpoint.io service when the spec is more developed.

### Demo notarization service

After reading our ausdigital/nry specification you can try this demo service to do some notarizations and to browse notarized archives.

[API Documentation](https://app.swaggerhub.com/api/ausdigital/ausdigital-nry/1.0)

[Identity Provider](https://idp.testpoint.io/)

### Notarizing the document

1. Get some valid JWT from IDP (nry.testpoint.io currently trusts only idp.testpoint.io)
2. Send your target document to public or private POST endpoint
3. Wait till next periodic notarization (1h)
4. Check [/archives/](https://nry.testpoint.io/archives/) endpoint to see recent HOC Archives
5. Get your archive final IPFS hash from this endpoint or from blockchain
6. Download archive (for example, [some random one](http://ipfs.io/ipfs/QmbairJbKaVX5rqTHjY5WfSABQkzzYgPTc3iQxhNtqhK6Q)) and verify it

### Archive verification

1. download archive proof.json
2. validate proof.sig signature using the public key from the proof.sig
3. validate public key - check if it's provided in DCP
4. download and validate HocDetails files
5. View notarized documents if they are public or if you have access to them


### Implementation details

* jsonapi.org is used
* currently we have periodical (hourly) notarization, but it may be changed any time
* currently we have Blockchain (main bitcoin testnet chain) notarization supported, but it's manual operation - to avoid spamming testnet. So you can safely assume any archive at https://nry.testpoint.io/archives/ available in bitcoin OP_RETURN data as `NRY /ipfs/{final_qmhash}` (NRY prefix may change).

### Example of list documents request

<pre>curl --header 'Accept: application/json; indent=4' \
    'https://nry.testpoint.io/public/'
</pre>

### Help and support

The service is currently in BETA, so some minor problems are expected. Don't hesitate to contact us by [Slack channel](https://ausdigital.slack.com/messages/spec-nry/) of you have any problems or questions.
