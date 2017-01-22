---
title: Free restful test end-points for integrated b2b communities
description: Unlike single provider RESTful services(e.g. Google or Facebook APIs), a B2B process like e-invoicing needs multiple providers to support the same standard interface. Testpoint.io supports the community by providing teset services for implementers of standard API specifications
diagram: /images/home-diagram.png
diagramMobile: /images/home-diagram.png
contentTitle: Available testpoints
permalink: /
tagline: B2B Developer Resources
classWrapper: home
---
### Digital Capability Locator

The [Ausdigital](http://ausdigital.org/) DCL specification is under active development at [GitHub](https://github.com/ausdigital/ausdigital-dcl).

The [Testpoint DCL service](http://testpoint.io/dcl.html) is a free DCL implementation to facilitate B2B development.

The Testpoint DCL management interface is integrated with the [testpoint IDP](http://testpoint.io/idp.html) for access control, and the [testpoint DCP](http://testpoint.io/dcp.html), however other DCPs can also be used.

### Digital Capability Publisher

The testpoint [DCP service](http://testpoint.io/dcp.html) is the reference implementation behind the [DCP SwaggerHub specification](https://swaggerhub.com/api/ausdigital/ausdigital-dcp/1.0).

This is under active development, support is available through the [GitHub group](https://github.com/ausdigital/ausdigital-dcp/issues).

### Identity Provider


The [testpoint IDP](http://testpoint.io/idp.html) provides developer-managed credentials for ABNs, which can be used to access the testpoint [DCP](http://testpoint.io/dcp.html) and [DCL](http://testpoint.io/dcl.html) services.

Authenticate with a GitHub account to claim and manage ABN credentials and register OIDC Relying Parties for your own testing purposes.

### Transaction Access Point

[Ausdigital](http://ausdigital.org) TAP specifications are under active development at [GitHub](https://github.com/ausdigital/ausdigital-tap)

A testpoint TAP service is under construction. This will provide a reference and enable B2B development interactions.

### Notary

A notary can be used to prove a message existed. This enables secure-by-design B2B protocols that require less trust to function. This increases efficiency where it reduces the need for expensive and unreliable perimeter security.

AusDigital are developing open standards for notary services to support B2B protocols. These are under development at [GitHub](https://github.com/ausdigital/ausdigital-nry)

We will release a free nry.testpoint.io service when the spec is more developed.
