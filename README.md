# spring-boot-maven
Configuring Maven and SpringBoot profiles

How to check build profile:

1. Build the application

   > mvn clean install -P local | dev | uat (default is local)

2. check the target folder:

   - the profile name is appended to WAR file name
   - check the application.properties file in classpath resource. properties should reflect the profile used

3. See if the Spring Boot application runs:

   > mvn spring-boot:run -P local | dev | uat (default is local)

   Note: spring-boot maven plugin will do a clean build

4. Ctrl + C to stop


Check using MVC Controller:

1. Browse the following URL:

LOCAL profile - http://localhost:8080/spring-boot-maven-LOCAL/profiles/active
DEV profile - http://localhost:8080/spring-boot-maven-DEV/profiles/active
UAT profile - http://localhost:8080/spring-boot-maven-UAT/profiles/active

Note:
- the context root name changes based on profile used to illustrate property value change.
- the profile name displayed by the browser is being retrieved using Spring's Environment bean getActiveProfiles() method.