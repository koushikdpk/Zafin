# Use the official Tomcat image as the base image for deployment
#FROM tomcat:8.5.47-jdk11-openjdk

# Remove the default ROOT web application

# Copy your web application WAR file to the Tomcat webapps directory
#COPY ./target/my-webapp.war /usr/local/tomcat/webapps



# Build stage
FROM maven:3.6.3-openjdk-16-slim AS build
WORKDIR /app
COPY pom.xml .
RUN mvn dependency:go-offline
COPY src ./src
RUN mvn clean package

# Final stage
#FROM tomcat:8.5.47-jdk11-openjdk
FROM tomcat:8
# Remove the default ROOT web application
#RUN rm -rf /usr/local/tomcat/webapps/ROOT
# Copy your web application WAR file
COPY --from=build  /app/target/my-webapp.war /usr/local/tomcat/webapps
