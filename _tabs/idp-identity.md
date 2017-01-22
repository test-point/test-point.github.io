---
layout: default
title: Identity
page: idp
---
### Manage Identities

Claim an Identity (eg an ABN) and generate authentication keys. You can then use this identity for subsequent tests

There are two ways to interact with the IDP service. Authenticating directly to the IDP with GitHub credentials will give you developer access. With developer access, you can manage your own collection of ABN accounts for testing purposes.

Instructions:

1.  Navigate to the [login page](https://idp.testpoint.io/login/)
2.  Login with Github
3.  Create synthetic user with any available ABN
4.  Logout with Github
5.  Go to any supporting service (e.g. [Testpoint DCP](https://testpoint.io/dcp.html)) and try login with idp.testpoint.io
6.  Enter your ABN and password (which doesn't have to be very secure) at login form
7.  Enjoy accessing the supporting service (e.g. DCP) as the synthetic business user

After you logged in on this website you can click your synthetic username in top menu and get or generate your own OIDC token (check "Rendered" version). While you possess this token and it's not expired yet you can use it to authenticate on any supporting API installation. Please reffer specific API documentation or examples about how to use this token in this case. Usually it's like:

<pre>export IDP_AUTH="JWT {YOUR-TOKEN-HERE}"
curl -v -X GET --header 'Content-Type: application/json' \
    --header 'Accept: application/json; indent=4' \
    --header "Authorization: ${IDP_AUTH}" \
    'https://dcp.testpoint.io/api/v0/demo_auth'
</pre>