# Create an OAuth 2.0

go to https://start.spring.io/

Change project type from Maven to Gradle.
Change the Group to com.okta.spring.
Change the Artifact to AuthorizationServerApplication.
Add one dependency: Web.

add dependency
```
implementation 'org.springframework.security.oauth:spring-security-oauth2:2.4.1.RELEASE'
runtimeOnly 'org.glassfish.jaxb:jaxb-runtime'
```

run 
```
./gradlew bootRun
```

