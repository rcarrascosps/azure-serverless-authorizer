# azure-serverless-authorizer
Serverless based AWS API Gateway Authorizer using Azure JWT.

This lambda function will receive the Azure JWT token and will:

1. Validate it
2. Extract audience
3. Extract scopes
4. Based on the extracted information, authorize or not authorize the request

This code is based on this repository:

https://github.com/RafPe/okta-serverless-authorizer

