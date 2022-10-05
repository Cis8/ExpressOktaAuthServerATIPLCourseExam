# ExpressOktaAuthServerATIPLCourseExam
A Express JS server that requires an Okta token to verify the user's identity in order to allow access to protected resources.

## Setup
In the main.js file replace the ORG_NAME_HERE with your Okta organization's name. The name can be found in the top right side of your Okta dev page, and should be something similar to dev-12345678.

Ensure to have checked to have correctly setted up the following complementary projects:
- Okta setup with Pulumi: https://github.com/Cis8/PulumiOktaApplicationSetupATIPLCourse
- Angular WebApp: https://github.com/Cis8/AngularWebAppWithOktaAuthenticationRedirectAndREST_API_ATIPLCourse


## Server architecture
The server is hosted on http://localhost:8080

PORT describes the port on which the server gonna be hosted (in our configuration is 8080).

CORS are used since the origin of the REST API is different from from the server's one.

OktaJwtVerifier is the library that allows the server to verify if the token passed in with the REST API from the angular web app is valid.

The method authenticationRequired has the objective to actually check the user token's validity. If it is not valid, a "401 - Unauthorized" code is returned.

Then 3 protected APIs are exposed:
- /hello
- /whoami
- /tshirt
