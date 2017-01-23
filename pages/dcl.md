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

dcl.testpoint.io is both a free service and a reference implementation of a Digital Capability Locator service (per [DCL-SPEC](http://ausdigital-dcl.readthedocs.io/)).

The reference implementation is Free Open-Source Software (FOSS) released under [GPL3 License](https://www.gnu.org/licenses/gpl-3.0.en.html). 

* [DCL server code and documentation](https://github.com/test-point/testpoint-dcl/tree/master/src-py)
* [DCL test automation client](https://github.com/test-point/testpoint-dcl/tree/master/tests/bdd-remote)

For support, please first [ask the community](https://ausdigital.slack.com/messages/testpoint/) and, if that doest work then [raise a ticket](https://github.com/test-point/testpoint-dcl/issues).


### Query API

The reference implementation complies with the [DCL-SPEC Discovery API](http://ausdigital-dcl.readthedocs.io/en/latest/discovery_api/).

The [normative example](http://ausdigital-dcl.readthedocs.io/en/latest/normative_examples/) in the DCL-SPEC uses the dcl.testpoint.io free service to demonstrate the Query API in detail. Basically, this means a well formed NAPTR type DNS query to the *.dcl.testpoint.io domain will return a CNAME of a service metadata publisher.


### Management API

The full DCL Management API is a work in progress. Please contribute to discussions about Management API design in the [AusDigital](http://ausdigital.org/) community site, especially the [GitHub issues](https://github.com/ausdigital/ausdigital-dcl/issues) to identify your Management API needs.

The dcl.testpoint.io reference implementation (and free service) provides a simplified management interface that is adequate for many testing and development purposes.

To use the simplified management interface, first you need a synthetic user credentials from the TestPoint IDP:

1.  Navigate to the [IDP login page](https://idp.testpoint.io/login/)
2.  Login with Github
3.  Create synthetic user with any available ABN

Using the credentials you created above, you can manage the DCL entry for that ABN:

1.  Navigate to the [DCL login page](https://dcl.testoint.io/login/)
2.  Log in with your synthetic credentials (this will take you past https://idp.testpoint.io using OIDC code-flow)
3.  Update the "New DCP Value" and click "Submit".
