# azure-serverless-authorizer
Serverless based AWS API Gateway Authorizer using Azure JWT.

This lambda function will receive the Azure JWT token and will:

1. Validate it
2. Extract audience
3. Extract scopes
4. Based on the extracted information, authorize or not authorize the request

This code is based on this repository:

https://github.com/RafPe/okta-serverless-authorizer

## Deployment process into AWS

Pre-requisites are:

1. Serverless (sls) CLI
2. Go 
3. npm

To download and install Serverless (sls) CLI:
https://www.serverless.com/framework/docs/getting-started/

To download and install go:
https://www.tecmint.com/install-go-in-linux/

To download and instal npm:
https://www.npmjs.com/get-npm

## Compile 

