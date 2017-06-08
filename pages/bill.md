---
title: A Testpoint.io Billing test service
description: A document validation API and message sender service for ausdigital.org billing specification implementers.
diagram: /images/diagrams/test-tdr.png
diagramMobile: /images/diagrams/test-tdr-mobile.png
contentTitle: Billing Test Services
permalink: /bill
menuTitle: Test BILL
menuOrder: 7
---
### Validation Service

POST a JSON invoice that complies with the [BILL 1.0](http://ausdigital.org/specs/ausdigital-bill/1.0/) specification to the following end point:

http://bill.testpoint.io/api/v0/validator

In accordance with the validation [API specification](http://swagger.testpoint.io/?url=http://ausdigital.org/specs/ausdigital-syn-json/1.0/swagger.json)

### Invoice Sender Service

A Synthtic Ledger Service allows to confirm that you can send an valid invoice to an ABN to another party which is on the network (ie has a DCP entry). 

Please note that the current implementation doesn't include validation of Document Type ID, Processes and documents itself yet.

If you already have synthetic user credntials, follow the instructions from the step 5.
Instructions:

1.  Navigate to the [login page](https://idp.testpoint.io/login/)
2.  Login with Github
3.  Create synthetic user with any available ABN
4.  Logout with Github
5.  Login again using synthetic user credentials you made in the step 3.
6.  Select Virtual Ledger as a client and click on "Issue new token for this client"
7.  Make note of the JWT token (copy/paste), which you can use to access Virtual Ledger as this user
8.  Go to [Ledger](http://ledger.testpoint.io/login) login page
9.  Provide the JWT token from the step 7
10. Choose ABN, Document Type ID and Endpoint and provide your document in JSON format.
11. Click "Confirm" to send a message to the enpoint.
