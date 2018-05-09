# Callback URL Validation

To ensure your webhook service endpoint is authentic and working we will verify your callback URL before creating subscription.
For verification we will send you a validation token which you need to send us back within 5 seconds. A look at the entire process:

1.  Request Kaizala to register your webhook using [POST /Webhook](webHooks.md). 
2.	Kaizala will generate a validation token and send a GET request to your webhook with a query parameter “validationToken”.
3.	Your service is supposed to return the validation token (received in request) in the response body as a plain-text
4.	If we receive the response within 5 seconds and the validation token received matches the one sent in Step 2, Webhook will be successfully registered, else it shall be rejected. 
