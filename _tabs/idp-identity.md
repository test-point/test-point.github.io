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