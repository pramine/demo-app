## Quickstart

Prerequisites:

```
# MySQL in einem Docker Container starten
docker run --name javalandDB -e MYSQL_ROOT_PASSWORD=password -e MYSQL_DATABASE=monitoring -p 3306:3306 -d mysql
```

For running the monitoring incl. the Spring Boot Admin client use the following commands.

```
# Start monitoring monitoring
cd monitoring
mvn clean install
java -jar target/monitoring*.jar

# Start conference-monitoring with environment configuration
cd conference-monitoring
mvn clean install
java -jar -Dspring.config.location=config/production.properties target/conference-monitoring*.war
java -jar -Dspring.config.location=config/staging.properties target/conference-monitoring*.war
java -jar -Dspring.config.location=config/test.properties target/conference-monitoring*.war
```

For demo reasons we start the monitoring three times with different ports. 
In your spring admin client web monitoring you should see three versions of the conference monitoring.

* http://localhost:8888

You can access the conference monitorings under:

| Environment         | Link          | 
| ------------------- |:-------------:|
| Test        | http://localhost:8080 |
| Staging     | http://localhost:8081 | 
| Production  | http://localhost:8082 |
| Monitoring  | http://localhost:8888 |
