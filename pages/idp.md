---
title: A Testpoint.io identity provider test service
description: B2B frameworks may leverage multiple providers of identity with varying degrees of identity confidence, The higher the identity integrity, the lower the risk associated with B2B transactions and the lower the cost of services such as trade financing. This test service simulates various OIDC providers and scopes. 
diagram: /images/diagrams/test-idp.png
diagramMobile: /images/diagrams/test-idp-mobile.png
contentTitle: Available iodc idp test resources
permalink: /idp
tagline: Identity Provider
menuTitle: Test IDP
menuOrder: 2
---
### Manage Identities

Claim an Identity (eg an ABN) and generate authentication keys. You can then use this identity for subsequent tests

There are two ways to interact with the IDP service. Authenticating directly to the IDP with GitHub credentials will give you developer access. With developer access, you can manage your own collection of ABN accounts for testing purposes.

Instructions:

1.  Navigate to the [login page](https://idp.testpoint.io/login/)
2.  Login with Github
3.  Create synthetic user with any available ABN
4.  Logout with Github
5.  Login again using synthetic user credentials you made in step 3.
6.  Select a client (e.g. dcp.testpoint.io) and select "Issue new token for this client"
7.  Make note of the JWT token (copy/paste), which you can use to access that service as this user

For example:

<pre>export IDP_AUTH="JWT {YOUR-TOKEN-HERE}"
curl -v -X GET --header 'Content-Type: application/json' \
    --header 'Accept: application/json; indent=4' \
    --header "Authorization: ${IDP_AUTH}" \
    'https://dcp.testpoint.io/api/v0/demo_auth'
</pre>

### Relying Party

The Testpoint IDP is a standards compliant OICD Identity Provider. In addition to using it to authenticate and authorise synthetic ABN users against Testpoint services, you can also register your own services (OIDC Relying Parties). This way, it can be used to support development of arbitrary services requiring consent-based access to ABN identities.

Instructions:

1.  Navigate to the [login page](https://idp.testpoint.io/login/)
2.  Login to the IDP client with GitHub
3.  Create your RP client using the web interface
4.  Record the client id and client secret issued by the IDP
5.  Configure your service (OIDC client) to use the credentials provided

### Support

Say hello in the [AusDigital](http://ausdigital.org) Development Special Interest Group. That's the 'SIG Development' channel on the [chat server](https://chat.ausdigital.org/). We'd be happy to help you out, and would love to hear about how you are using the IDP.