# Keycloak with Spring Boot
What does this example show?

1. How to guard endpoints with `@RolesAllowed` & path prefix
2. Create user with spring boot
3. Login user, get access token with spring boot

The details post is available here (https://datmt.com/backend/integrate-keycloak-with-spring-boot-step-by-step/)


## Tests


- http://localhost:9090/public/hello

* Reponse : " Hello public user".

As you can see, it works as expected. The path begins with /public so anyone can access without any authentication.



- http://localhost:9090/member/hello

"There was an unexpected error (type=Unauthorized, status=401).
Unauthorized"


## How to get an Access Token in Postman

* https://sis-cc.gitlab.io/dotstatsuite-documentation/configurations/authentication/token-in-postman/

The purpose of this short tutorial is to explain how to setup Postman (as an example of an API platform tool) in order to get an Access Token and thus being able to make requests on .Stat Suite services (nsiws) using the authorisation service and underlying permission rules.

Note that, like other variables and settings, Authorization can be setup on different level/scope (Collection, Folder or Individual request). In the following examples, screenshots of the Postman UI are done for an individual request. But if setup on a collection or folder level, this setup will apply to all http requests at the same level.

Navigate to the Postman Authorization tab of your request. From the Type dropdown menu, select OAuth 2.0:

Click on the Get New Access Token button that will open a dialog box for configuring the identity server (Keycloak in our case). Fill in the appropriate fields with the corresponding values for your environment, as such:

Token name => give any name here
Grant Type => select Authorization Code (or Authorization Code with PKCE depending on your auth. configuration)
Auth URL => http://{YOUR-KEYCLOAK-BASE-URL}/auth/realms/{YOUR-REALM}/protocol/openid-connect/auth
Access Token URL => http://{YOUR-KEYCLOAK-BASE-URL}/auth/realms/{YOUR-REALM}/protocol/openid-connect/token
Client ID => Id of a client in your Keycloak setup
Scope => which resource you want to provide (email openid profile)
Authorize using browser should be unchecked, use a url that is authorised by keyclaok (e.g your data-explorer url). If you tick the box, you have to authorise the url defined by postman in your keycloak.



##  Token

http://ip:port/auth/realms/datmt-test-realm/protocol/openid-connect/token/


http://10.10.156.15:8024/auth/realms/datmt-test-realm/protocol/openid-connect/token/