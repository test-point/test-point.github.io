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

TestPoint DCP implements the [AusDigital](http://ausdigital.org/) Digital Capability Locator specifications. The API is directly available to developers, and also backs the [SwaggerHub specifications](https://swaggerhub.com/api/ausdigital/metadata-publisher/1.0). Support is available through the [GitHub site](https://github.com/ausdigital/ausdigital-dcl).

The DCP is available with and without authentication at https://dcp.testpoint.io/api/v0/

As with other TestPoint APIs, authenticated access is available using synthetic user accounts from the [TestPoint IDP](http://testpoint.io/idp.html). If you don't already have a synthetic user account:

1.  Navigate to the [IDP login](https://idp.testpoint.io/login/) page
2.  Login with Github
3.  Create synthetic user with any available ABN
4.  Logout with Github

With these synthetic user credentials, you can use the TestPoint IDP to create a JWT for the TestPoint DCP:

1.  [Login again](https://idp.testpoint.io/login/) to the IDP, this time using the synthetic user credentials you made above.
2.  Select the `dcp.testpoint.io` client and click **Issue new token for this client**
3.  Make note of the JWT token (copy/paste), which you can use to access the TestPoint DCP (as the synthetic user)

You can now use this JWT to gain authenticated access the TestPoint DCP. For example:

```
export IDP_AUTH="JWT {YOUR-TOKEN-HERE}"
curl -v -X GET --header 'Content-Type: application/json' \
    --header 'Accept: application/json; indent=4' \
    --header "Authorization: ${IDP_AUTH}" \
    'https://dcp.testpoint.io/api/v0/demo_auth'
```

### Data Fixtures

All australian businesses loaded to this test database

This implementation currently relies on the [Testpoint IDP](https://idp.testpoint.io) for business authentication and access control. Using this service, developers can 'claim' ABNs for exclusive use on the Testpoint DCP site, and manage their own credentials.. A develper's collection of ABN credentials can be used for testing purposes at the Testpoint DCP API.