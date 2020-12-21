FROM maven:3-openjdk-8 AS packaging
RUN git clone https://github.com/wakaleo/game-of-life.git
RUN cd /game-of-life/ && mvn package

FROM tomcat:jdk8-openjdk
LABEL author='eswar'
COPY --from=packaging /game-of-life/gameoflife-web/target/gameoflife.war /usr/local/tomcat/webapps/gameoflife.war
VOLUME /usr/local/tomcat
EXPOSE 8080
 