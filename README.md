# azure-serverless-authorizer
Serverless based AWS API Gateway Authorizer using Azure JWT.

This lambda function will receive the Azure JWT token and will:

1. Validate it
2. Extract audience
3. Extract scopes
4. Based on the extracted information, authorize or not authorize the request

This code is based on this repository:

https://github.com/RafPe/okta-serverless-authorizer

All credits on RafPe, who designed this.

# Use case

AWS API Gateway is being used to expose APIs that will be consumed for different web applications and consumers.
Users for those Web applications, are being authenticated and authorized using Microsoft Azure. This process is via OAUTH 2.0, and the result of the process is that the applications obtain an access token; this access token needs to be used by the application to consume APIs (exposed by AWS API Gateway). 
AWS API Gateway will receive the request from those different applications; the requests needs to come with the access token and the AWS API Gateway will have to validate it. In order to validate it, the API Gateway will use a lambda function that will contain the logic to validate the signature of the JWT token, and also retrieve information like:

* Scopes
* Audiences
* Expiration Date
* Issuer

If the token is valid and the scope is the expected one, then the lamda will return a succesful authorization, otherwise it will not authorize it.

![Lambda Authorizer](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2020/03/22/Secure-API-Gateway-b-Figure-1.png)


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

## Build 

