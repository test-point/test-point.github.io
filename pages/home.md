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

Testpoint.io exists to support the [ausdigital.org](http://ausdigital.org/) implementer community.  Unlike single provider RESTful services(e.g. Google or Facebook APIs), a B2B process like e-invoicing needs multiple providers to support the same standard interface and to make their services discoverable.  As the detailed specifcations at [ausdigital.org](http://ausdigital.org/) describe, there are a number of moving parts.  Without a suite of test services and test cases, there would be a major risk of incompatible implmenetations.

### How to use testpoint.io

In short, build your implementation of whichever specifications you intend to support in your product, then run the testpoint.io test suite for each specification. Although there will be some network service providers that will implement a number of the ausdigital technical specifications, by far the most common implementer is the vendor of a software product (eg a ledger solution) that will the the ultimate sender or receiver of invoices and other business documents.  Therefore our primary focus is to support that implementer role. There are two key implementation and testing steps:

* **Support the standard billing process**.  As defined by the ausdigital [BILL](http://ausdigital-bill.readthedocs.io/en/latest/) specification.  Note that, although there is just one invoice schema, it can be used (with slight variations) in six process contexts (invoice, adjustment invoice, tax receipt, RCTI, credit note, debit note).  Also please note that the business response message that describes the state of the invoice (acknowledged, approved, disputed, rejected) is as important as the invoice itself.  The testpoint.io [BILL](http://testpoint.io/bill) service offers a validation API for you to test your implementation.
* **Plug into the network**.  Build a [TAP-GW](http://ausdigital-tap-gw.readthedocs.io/en/latest/) client into your product. For this purpose, you may choose to use one of the free testpoint.io [TAP-GW client reference implementations](https://github.com/test-point/testpoint-tap-gw).  Use the teastpoint.io TAP-GW test service to test sending and receiving invoices and responses with the test network.  To do that without collisions with other testers, please ise the testpoint.io IDP service to create your test account and claim any number of test ABNs. You can then use the TAP-GW API to publish to the testpoint.io DCL and DCP.  After that you will be able to send messages **from** your ABNs to any other ABN on the test network.  You will also be able to use the testpoint.io BILL message sender service to send invoices **from** a testpoint.io ABN **to** one of your own ABNs.

Once you are able to create and consume valid invoices and response, and have successfully exchanged messages with external ABNs via the testpoint.io TAP-GW, and have completed all relevant test cases, then you are ready for production.

