---
title: Digital Capability Publisher
description: Implementation of the the DCP component, suitable for non-production use by developers adopting AusDigital open standards. 
diagram: /images/diagrams/test-dcp.png
diagramMobile: /images/diagrams/test-dcp-mobile.png
contentTitle: Resources
permalink: /dcp
tagline: Digital Capability Publisher
menuTitle: Test DCP
menuOrder: 3
---
### API

Testpoint DCP implements the [AusDigital](http://ausdigital.org/) Digital Capability Locator specifications. The API is directly available to developers, and also backs the [SwaggerHub specifications](https://swaggerhub.com/api/ausdigital/metadata-publisher/1.0). Support is available through the [GitHub site](https://github.com/ausdigital/ausdigital-dcl).


### Data Fixtures

All australian businesses loaded to this test database

This implementation currently relies on the [Testpoint IDP](https://idp.testpoint.io) for business authentication and access control. Using this service, developers can 'claim' ABNs for exclusive use on the Testpoint DCP site, and manage their own credentials.. A develper's collection of ABN credentials can be used for testing purposes at the Testpoint DCP API.