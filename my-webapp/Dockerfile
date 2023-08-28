# Use the official Tomcat image as the base image for deployment
FROM tomcat:8.5.47-jdk11-openjdk

# Remove the default ROOT web application

# Copy your web application WAR file to the Tomcat webapps directory
COPY ./target/my-webapp.war /usr/local/tomcat/webapps

