---
title: A Testpoint.io capability lookup test service
description: The Digital Capability Lookup service is a common entry point for both the modern RESTful e-Invoicing and legacy EDI systems. This uses the Domain Name System (NAPTR records) to enables dynamic discovery of Digital Capability Publisher for business identities.
diagram: /images/diagrams/test-dcl.png
diagramMobile: /images/diagrams/test-dcl-mobile.png
contentTitle: Digital capability locator
permalink: /dcl
menuTitle: Test DCL
menuOrder: 4
---
### Open Source DCL

[dcl.testpoint.io](https://dcl.testpoint.io) is a free service and a reference implementation of a Digital Capability Locator service (as per [DCL 1.0 spec](http://ausdigital.org/specs/ausdigital-dcl/1.0)). At the moment it supports only [Simplified Web UI](http://ausdigital.org/specs/ausdigital-dcl/1.0/#simplified-web-ui). Support of the [DCL 1.0 API](http://ausdigital.org/specs/ausdigital-dcl/1.0/api) will be added soon.

The reference implementation is Free Open-Source Software (FOSS) released under [GPL3 License](https://www.gnu.org/licenses/gpl-3.0.en.html). 

* [DCL server code and documentation](https://github.com/test-point/testpoint-dcl/tree/master/src-py)
* [DCL test automation client](https://github.com/test-point/testpoint-dcl/tree/master/tests/bdd-remote)

For support, please first [ask the community](https://ausdigital.slack.com/messages/testpoint/) and, if that doesn't work then [raise a ticket](https://github.com/test-point/testpoint-dcl/issues).


### Query API

The reference implementation complies with the [DCL 1.0 spec Discovery API](http://ausdigital.org/specs/ausdigital-dcl/1.0/#discovery-api).

The [normative example](http://ausdigital.org/specs/ausdigital-dcl/1.0/#normative-examples) in the DCL spec uses the dcl.testpoint.io free service to demonstrate the Query API in detail. Basically, this means a well formed NAPTR type DNS query to the *.dcl.testpoint.io domain will return a CNAME of a service metadata publisher.


### Management API

The full DCL Management API is a work in progress. Please contribute to discussions about Management API design in the [AusDigital](http://ausdigital.org/) community site, especially the [GitHub issues](https://github.com/ausdigital/ausdigital-dcl/issues) to identify your Management API needs.

The dcl.testpoint.io reference implementation (and free service) provides a simplified management interface that is adequate for many testing and development purposes.

To use the simplified management interface, first you need a synthetic user credentials from the TestPoint IDP (if you haven't already done so):

1.  Navigate to the [IDP login page](https://idp.testpoint.io/login/)
2.  Login with Github
3.  Create synthetic user with any available ABN

Using the credentials you created above, you can manage the DCL entry for that ABN:

1.  Navigate to the [DCL login page](https://dcl.testpoint.io/login/)
2.  Log in with your synthetic credentials (this will take you past https://idp.testpoint.io using OIDC code-flow)
3.  Update the "New DCP Value" and click "Submit".

### ADBC DCL Interface implementation

In addition to AusDigital DCL 1.0 spec with a minimum required set of functions Testpoint.io provides an implementation of ADBC DCL Interface Specification 2.0.0(dbc-dcl/2.0.0) - [dbc-dcl.testpoint.io](https://dbc-dcl.testpoint.io).

The swagger document was developed based on ADBC DCL Implementation Guide (v2.0.0 available [here](http://ausdigital.org/specs/ausdigital-dcl/1.0/Attachment_5c_Digital_Capability_Locator_Implementation_Guide_v2.0.0.pdf)) and available on [swaggerhub.com](https://app.swaggerhub.com/apis/ADBC/DCL-interface-spec/2.0.0)

#### Host

https://dbc-dcl.testpoint.io/

#### Authentification

Host supports TLS and JWT auth. Auth is method-agnostic, so regardless of used method user may be granted some access to system objects.

#### Resources

[Server configuration for TLS auth](https://github.com/test-point/testpoint-dcl/tree/master/client-py-tls)

[Source code](https://github.com/test-point/testpoint-dcl/tree/master/src-py)

[Feature files](https://github.com/test-point/testpoint-dcl/tree/master/tests/bdd-remote)

#### Admin Panel

https://dbc-dcl.testpoint.io/admin/

Admin panel may be used for party management, status change and audit records review.

Using the [User-Party access](https://dbc-dcl.testpoint.io/admin/accreditations/userpartyaccess/) interface dcl users can get permission to access specific parties.

A dcl user record is created, once a user authenticates in DCL for the first time. An endpoint https://dbc-dcl.testpoint.io/api/dbc/v0/demo_auth/ can be used to validate a current authentication status and trigger a dcl user creation process.

Only when a dcl user record was added, admin user can set permissions for this user.
