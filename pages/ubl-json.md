---
title: A Testpoint.io UBL JSON Format test service
description: The AusDigital UBL JSON Format reference implementation and test suite.
diagram: /images/diagrams/test-tdr.png
diagramMobile: /images/diagrams/test-tdr-mobile.png
contentTitle: UBL JSON Format
permalink: /ubl-json
menuTitle: Test UBL JSON
menuOrder: 6
---
### Transformation API

In accordance wih the ausdigital [UBL JSON Specification](https://github.com/ausdigital/ausdigital-ubl-json), testpoint.io offers free transformation APIs for lossless bi-directional transformation between international namespace qualified XML UBL and a simple signle root JSON representation.  We expect that the majority of national invoices will use the JSON representation but it is useful to be able to transform to/from UBL for international interoperability with other jusrisdictions (mostly the EU) that also use UBL.

Please POST your XML or JSON UBL to:

* json.testpoint.io/api/v0/ubl2json
* json.testpoint.io/api/v0/json2ubl

In accordance with the ausdigital [API Specification](https://app.swaggerhub.com/api/ausdigital/ausdigital-ubl-json/1.0.0).  No authentication is required.

### Transformation Docker Container

As an implemener, you may use the SaaS API for transformations as needed.  However you may also wish to perform transformations locally, thereby avoiding the need to send un-encrypted invoice data outside of your controlled network.   Testpoint is pleased to offer a free containderised version of the transformation API.

More to come on this....
