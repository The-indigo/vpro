FROM openjdk:11 AS BUILD_IMAGE
RUN apt update && apt install maven -y
RUN git clone https://github.com/The-indigo/vpro.git
RUN cd vpro && git checkout docker && mvn install

FROM tomcat:9-jre11
LABEL "Project"="VPROFILE"
LABEL "Author"="Adeyemi"
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILD_IMAGE vpro/target/vprofile-v2.war  /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
ENTRYPOINT [ "catalina.sh", "run" ]