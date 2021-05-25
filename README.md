# maven-spring-demo (complete)

For myself to learn maven & springboot during an internship,
following https://spring.io/guides/gs/serving-web-content/

Run the project:
`mvnw spring-boot:run`

For intranet build:

```shell
mvn spring-boot:run
```

Another way:
```shell
./mvnw clean package
java -jar target/gs-serving-web-content-0.1.0.jar
```

### Build project
```shell
mvn install --settings C:\Users\jiateo\.m2\settings.xml
```

Another way is to temporarily rename settings.xml to another file name, so we can mvn install directly from maven repo:
```shell
mvn install 
```

If company blocks intranet:

```shell
mvn install:install-file -Dfile=.mvn\jna-platform-5.8.0.jar -DgroupId=net.java.dev.jna -DartifactId=jna-platform -Dversion=5.8.0 -Dpackaging=jar
```

From:

```xml
<!-- https://mvnrepository.com/artifact/net.java.dev.jna/jna-platform -->
<dependency>
    <groupId>net.java.dev.jna</groupId>
    <artifactId>jna-platform</artifactId>
    <version>5.8.0</version>
</dependency>
        
<!-- https://mvnrepository.com/artifact/net.java.dev.jna/jna-platform -->
<dependency>
    <groupId>net.java.dev.jna</groupId>
    <artifactId>jna-platform</artifactId>
    <version>5.5.0</version>
</dependency>
```

To test:

- http://localhost:8080/greeting

To add a parameter:

- http://localhost:8080/greeting?name=Jia%20Cheng 


To copy dependencies:

```
mvn dependency:copy-dependencies -DoutputDirectory=${project.build.directory}/lib
```

Files are copied to build dir (`/target/lib`) 