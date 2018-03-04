# Spring Boot Docker build using Fabric8.io Maven plugin

PREREQUISITE: Docker For Mac

1. Build the application

   > mvn clean [install | package] -P [local | dev | uat] (default is local)

2. check the target folder:

   - the profile name is appended to JAR file name
   - check the application.properties file in classpath resource. properties should reflect the profile used

3. Build Docker image:

   > mvn docker:build

   Note: This will build image based on the created artifacts in step #1

4. Check the docker dir created in target dir. Inspect the Dockerfile and the maven/ subdir.

5. Build and Run the image:

  > mvn docker:run

  Note: This will build a new image and execute 'docker run'


Check using MVC Controller. Browse the following URL:

LOCAL profile - http://localhost:8091/spring-boot-docker-LOCAL/profiles/active
DEV profile - http://localhost:8091/spring-boot-docker-DEV/profiles/active
UAT profile - http://localhost:8091/spring-boot-docker-UAT/profiles/active

Note:
- the context root name changes based on profile used to illustrate property value change.
- the profile name displayed by the browser is being retrieved using Spring's Environment bean getActiveProfiles() method.