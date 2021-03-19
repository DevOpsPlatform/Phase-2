Ref: - https://docs.docker.com/develop/develop-images/multistage-build/


Dockerfile-1

```
FROM maven:3.6.3-jdk-8 AS maven3

RUN apt-get install git -y

RUN git clone https://github.com/CalculatorApps/Addition.git

WORKDIR Addition

RUN mvn clean install

CMD ["java", "-jar", "target/Addition-1.0.0-SNAPSHOT.jar"]
```

```
docker build -t add:1.0 -f Dockerfile-1  .

docker images -a
```

![image](https://user-images.githubusercontent.com/24622526/111821931-8083b100-88e3-11eb-9b49-7da81b3e739b.png)

```
docker run add:1.0
```


Dockerfile-2

```
FROM maven:3.6.3-jdk-8 AS maven3

RUN apt-get install git -y

RUN git clone https://github.com/CalculatorApps/Addition.git

WORKDIR Addition

RUN mvn clean install


FROM ubuntu:latest

RUN apt-get update && apt-get install openjdk-8-jdk -y

RUN java -version

COPY --from=maven3  Addition/target/Addition-1.0.0-SNAPSHOT.jar .

CMD ["java", "-jar", "Addition-1.0.0-SNAPSHOT.jar"]
```

```
docker build -t add:2.0 -f Dockerfile-2  .

docker images -a
```

![image](https://user-images.githubusercontent.com/24622526/111823380-2edc2600-88e5-11eb-941f-e8220eb7a389.png)

    
Dockerfile-3

```
FROM maven:3.6.3-jdk-8 AS maven3

RUN apt-get install git -y

RUN git clone https://github.com/CalculatorApps/Addition.git

WORKDIR Addition

RUN mvn clean install


FROM openjdk:8-jdk

COPY --from=maven3  Addition/target/Addition-1.0.0-SNAPSHOT.jar .

CMD ["java", "-jar", "Addition-1.0.0-SNAPSHOT.jar"]
```

```
docker build -t add:3.0 -f Dockerfile-3  .

docker images -a
```

![image](https://user-images.githubusercontent.com/24622526/111823708-8e3a3600-88e5-11eb-9754-840a5cfcaf9b.png)


