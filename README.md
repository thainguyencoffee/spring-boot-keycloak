## Original project
This project is a fork of the [spring-boot-keycloak](https://github.com/eugenp/tutorials/blob/master/spring-boot-modules/spring-boot-keycloak)
[Link articles](https://www.baeldung.com/spring-boot-keycloak)

<h2 id="baeldung-tutorial"><strong>1. Branch baeldung-tutorial</strong></h2>
<h3 id="about-run"><strong>1.1 Run docker compose</strong></h3>

We would then start the container with the following shell commands:

```bash
export KEYCLOAK_ADMIN_PASSWORD=secret
docker compose up -d
```

After running these commands, we can access the Keycloak admin console at `http://localhost:8080` with the username/password: `admin/secet`.

<h3 id="about-run"><strong>1.2 Spring MVC Application with oauth2Login</strong></h3>

```bash
cd spring-boot-mvc-client
./gradlew bootRun
```

After running these commands, we can access the Spring MVC application at `http://localhost:8081`.

<h3 id="about-run"><strong>1.3 Spring Boot Application with oauth2ResourceServer</strong></h3>

```bash
cd spring-boot-resource-server
./gradlew bootRun
```
After running these commands, we can access the Spring Boot application at `http://localhost:8082`.
Open postman, at the Authorization tab, select OAuth 2.0, and fill the form with values set in Keycloak and you can see  at:
[.well-known endpoint](http://localhost:8080/realms/baeldung-keycloak/.well-known/openid-configuration)

![](https://www.baeldung.com/wp-content/uploads/2024/08/postman_token_config.png)

After you have the token, test /me and you will see a json payload with the user information.
