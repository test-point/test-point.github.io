---
title: Free RESTful test end-points for integrated b2b communities
description: A suite of test services, test client, and test cases designed to support the ausdigital.org implementer community.
diagram: /images/home-diagram.png
diagramMobile: /images/home-diagram.png
contentTitle: Testpoint Overview
permalink: /
tagline: B2B Developer Resources
classWrapper: home
---
### Why did we build testpoint.io?

Testpoint.io exists to support the [ausdigital.org](http://ausdigital.org/) implementer community.  Unlike single provider RESTful services(e.g. Google or Facebook APIs), a B2B process like e-invoicing needs multiple providers to support the same standard interface and to make their services discoverable.  As the detailed specifcations at [ausdigital.org](http://ausdigital.org/) describe, there are a number of moving parts.  Without a suite of test services and test cases, there would be a major risk of incompatible implementations.

### How to use testpoint.io

In short, build your implementation of whichever specifications you intend to support in your product, then run the testpoint.io test suite for each specification. 

Although there will be some network service providers that will implement a number of the ausdigital technical specifications, by far the most common implementer is the vendor of a software product (eg a ledger solution) that is the ultimate sender or receiver of invoices and other business documents.  For the ledger solution, there are only two key implementation steps:

* **Support the standard billing process**.  As defined by the ausdigital [BILL specification](http://ausdigital-bill.readthedocs.io/en/latest/) including the different invoice types and the buisness response documents.  The testpoint.io [BILL service](http://testpoint.io/bill) offers a validation API for you to test your implementation.
* **Plug into the network**.  Build a TAP-GW client into your product as per the [TAP-GW specification](http://ausdigital-tap-gw.readthedocs.io/en/latest/), optionally using one of the free testpoint.io [TAP-GW client implementations](https://github.com/test-point/testpoint-tap-gw).  Use testpoint.io [IDP service](http://testpoint.io/idp) to create your tester account and claim any number of test ABNs and credentials. Publish capabilities for each ABN to the testpoint.io [DCL](http://testpoint.io/dcl) and [DCP](http://testpoint.io/dcp).  After that you will be able to send messages **from** your ABNs to any other ABN on the test network using the using the testpoint.io [TAP-GW service](http://testpoint.io/tap-gw).  You will also be able to use the testpoint.io BILL message sender service to send invoices **from** a testpoint.io ABN **to** one of your own ABNs.

Once you are able to create and consume valid invoices and response, and have successfully exchanged messages with external ABNs via the testpoint.io TAP-GW, and have completed all relevant test cases, then you are ready for production.

