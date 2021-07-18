# okta-sample

Ref : https://developer.okta.com/blog/2019/03/12/oauth2-spring-security-guide

# A Quick Guide to OAuth 2.0 with Spring Security

Okta is a Software as a service identity provider, have built on top of spring boot to make security implementation even easier.

In this tutorial, you will first build an OAuth 2.0 web application and authentication server using spring boot and spring security.
After that, you will use okta to get rid of your self hosted authentication server and simplify you SpringBoot application even more

Table of Contents
1. Create an OAuth 2.0 Server
2. Build your client App
3. Test the Resource Server
4. Create an OpenID connect Application
5. Create a New Spring Boot App
6. Learn More About Spring Boot and Spring Security and OAuth 2.0


## Create an OAuth 2.0

go to https://start.spring.io/

1. Change project type from Maven to Gradle.
2. Change the Group to com.okta.spring.
3. Change the Artifact to AuthorizationServerApplication.
4. Add one dependency: Web.

add dependency
```
implementation 'org.springframework.security.oauth:spring-security-oauth2:2.4.1.RELEASE'
```

Ref : AuthorizationServerApplication

# Build your client app

1. Project type should be Gradle (not Maven).
2. Group: com.okta.spring.
3. Artifact: SpringBootOAuthClient.
4. Add three dependencies: Web, Thymeleaf, OAuth2 Client.

Ref: SpringBootOauthClient

```
./gradlew bootRun
```

# Test the Resource Server

Navigate in your browser of choice to your client app at http://localhost:8082/.

Click the Login link.

Enter username Hariharan and password hari0102 (from the application.properties file from the authentication server).

Click Sign In and you’ll be taken to the super fancy securedPage.html template that should say “Secured Page” and “Andrew”.

Great! It works. Now you’re gonna make it even simpler.

You can stop both server and client Spring Boot apps.


# Create an OpenID connect Application

Okta is a SaaS (software-as-service) authentication and authorization provider. We provide free accounts to developers so they can develop OIDC apps with no fuss.

Before you begin, you’ll need a free Okta developer account. Install the Okta CLI and run okta register to sign up for a new account. If you already have an account, run okta login. Then, run okta apps create. Select the default app name, or change it as you see fit. Choose Web and press Enter.

Select Other. Then, change the Redirect URI to http://localhost:8080/login/oauth2/code/okta and use http://localhost:8080 for the Logout Redirect URI.

What does the Okta CLI do?

You’ll need to use the values from the generated .okta.env to configure OIDC in your Spring Boot apps.


## Create a New Spring Boot App (Okta client)

1. Change project type from Maven to Gradle.
2. Change the Group to com.okta.spring.
3. Change the Artifact to OktaOAuthClient.
4. Add three dependencies: Web, Thymeleaf, Okta.
5. Click Generate Project.

Ref OktaOAuthClient

```
./gradlew bootRun
```

Navigate to http://localhost:8080.

Click the Login button.

This time you’ll be directed to the Okta login page. You may need to use an incognito browser or log out of your developer.okta.com dashboard here so that you don’t skip the login page and get directed immediately to the secured endpoint.

















