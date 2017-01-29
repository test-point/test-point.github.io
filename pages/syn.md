---
title: A Testpoint.io UBL Syntax 2.0 test service
description: The AusDigital UBL Syntax 2.0 Specification reference implementation and test suite.
diagram: /images/diagrams/test-tdr.png
diagramMobile: /images/diagrams/test-tdr-mobile.png
contentTitle: UBL JSON Format
permalink: /syn
menuTitle: Test UBL Syntax 2.0
menuOrder: 6
---
### Transformation API

In accordance wih the ausdigital [UBL Syntax 2.0 Specification](https://github.com/ausdigital/ausdigital-syn), testpoint.io offers free transformation APIs for lossless bi-directional transformation between international namespace qualified UBL XML and a simple signle root JSON representation.  We expect that the majority of national invoices will use the JSON representation but it is useful to be able to transform to/from UBL for international interoperability with other jusrisdictions (mostly the EU) that also use UBL.

Please POST your UBL XML to:

* json.testpoint.io/api/v0/ubl2json

or your UBL JSON to:

* json.testpoint.io/api/v0/json2ubl

In accordance with the ausdigital [UBL Syntax 2.0 API](https://app.swaggerhub.com/api/ausdigital/ausdigital-syn/1.0).  No authentication is required.

### Transformation Docker Container

As an implemener, you may use the SaaS API for transformations as needed.  However you may also wish to perform transformations locally, thereby avoiding the need to send un-encrypted invoice data outside of your controlled network.   Testpoint is pleased to offer a free containderised version of the transformation API.

More to come on this....
