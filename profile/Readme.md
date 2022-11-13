
**********************************************************************************************************************
|
| How to generate a full stack ReactJS, JSF, SpringBoot, Spring, Hibernate, PostgreSQL, Docker projet in 1 minute?
|
**********************************************************************************************************************

# Prerequisites

Install following tools:

* Java 17
* maven 3.6

# Create a projet

Following command will create a fullstack java project

```
export VERSION=0.0.36
mvn archetype:generate  -DarchetypeCatalog=local -DarchetypeGroupId=com.katappult -DarchetypeArtifactId=katappult-core-archetype -DarchetypeVersion=$VERSION
```

# Build

Now build the project, generate local H2 database schema, build reactjs UI

```
mvn clean install -PdropDb,updateDb,install-reactui,npm-install,npm-build
```


# Run

Launch the application

```
> mvn spring-boot:run -Dspring-boot.run.jvmArguments="-Dspring.devtools.restart.enabled=false" -Dspring-boot.run.arguments=--env=local-h2
```


# Access

http://localhost:8080

