# Stage 1: Clone the repository and build with Maven
FROM maven:3.8.4-openjdk-11 AS build
WORKDIR /app
RUN git clone --branch containers https://github.com/devopshydclub/vprofile-project.git .
RUN cd vprofile-project
RUN mvn clean install

# Stage 2: Copy the built WAR file to Tomcat
FROM tomcat:9
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=build /app/vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

# Expose the port on which Tomcat will run
EXPOSE 8080

# Start Tomcat
CMD ["catalina.sh", "run"]