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

TestPoint DCP implements the [AusDigital](http://ausdigital.org/ausdigital-dcp/) Digital Capability Locator specifications. 
The API is directly available to developers, and also backs the [SwaggerHub specifications](http://ausdigital.org/specs/ausdigital-dcp/1.0/api). Support is available through the [GitHub site](https://github.com/ausdigital/ausdigital-dcp).

The OASIS-compliant DCP is available at https://dcp.testpoint.io/

As with other TestPoint APIs, authenticated access is available using synthetic user accounts from the [TestPoint IDP](http://testpoint.io/idp.html). If you don't have any user there just follow the instructions on idp.testpoint.io.

With synthetic user credentials on idp.testpoint.io, you are able to use the TestPoint IDP to create a JWT for the TestPoint DCP:

1.  [Login again](https://idp.testpoint.io/login/) to the IDP, this time using the synthetic user credentials you made above.
2.  Select the `dcp.testpoint.io` client and click **Issue new token for this client**
3.  Make note of the JWT token (copy/paste), which you can use to access the TestPoint DCP (as the synthetic user)

You can now use this JWT to gain authenticated access the TestPoint DCP. For example:

```
export IDP_AUTH="JWT {YOUR-TOKEN-HERE}"
curl -v -X GET --header 'Content-Type: application/json' \
    --header 'Accept: application/json; indent=4' \
    --header "Authorization: ${IDP_AUTH}" \
    'https://dcp.testpoint.io/api/v0/demo_auth/'
```

Or use more complex queries (for example, [Update service metadata](https://github.com/test-point/testpoint-dcp/blob/master/client-bash/do_service_put.sh.sample)). Check [readme](https://github.com/test-point/testpoint-dcp/tree/master/client-bash) for more details.

### Data Fixtures

This implementation currently relies on the [Testpoint IDP](https://idp.testpoint.io) for business authentication and access control. Using this service, developers can 'claim' ABNs for exclusive use on the Testpoint DCP site, and manage their own credentials. A developer's collection of ABN credentials can be used for testing purposes at the Testpoint DCP API.

While these participant identifiers looks exactly like some real Australian businesses - it's complete coincidence and they have no relation to real-world business. Any testpoint.io service MUST NOT be used for real-world applications.
