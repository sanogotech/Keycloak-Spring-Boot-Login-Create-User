# Keycloak with Spring Boot
What does this example show?

1. How to guard endpoints with `@RolesAllowed` & path prefix
2. Create user with spring boot
3. Login user, get access token with spring boot

The details post is available here (https://datmt.com/backend/integrate-keycloak-with-spring-boot-step-by-step/)


## Tests


http://localhost:9090/public/hello

* Reponse : " Hello public user".

As you can see, it works as expected. The path begins with /public so anyone can access without any authentication.


