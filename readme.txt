//This packages all dependencies within a single war as configured by the spring-boot-maven-plugin in the root pom.xml
mvn clean install

//Spins up the app in jetty on port 8080
java -jar target/spring-boot-1.0-SNAPSHOT-spring-boot.war


//DOCKER
//This generates a docker war file with structure {DOCKER_USERNAME}/{FILENAME}.war
mvn clean install dockerfile:build

//This should deploy to docker using maven but having some permission problems
mvn dockerfile:push

//So use this instead
docker push mriddle88/spring-boot