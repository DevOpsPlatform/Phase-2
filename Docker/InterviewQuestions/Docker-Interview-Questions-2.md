apt-get update && apt-get install docker.io -y && docker version && mkdir dockerpractice && cd dockerpractice

Docker interview questions:

1. what is docker image?

2. what is dockerfile?

3. diff b.w docker image and container ?

4. docker archetecture

5. diff b.w docker daemon and hypervisor

6. container vs vm

7. advantages of container

8. drawbacks of container/docker

9. CMD vs RUN

10. CMD vs ENTRYPOINT

11. can we use multiple FROM commands in same dockerfile - https://docs.docker.com/develop/develop-images/multistage-build/

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

docker build -t add:1.0 .
docker run add:1.0

12. ADD vs COPY

13. docker networks

14. docker regustry setup and push images to private registry

15. how to pull the docker images to k8s cluster (using k8s secrets - need to add docker config file )

16. difference between ARG and env in docker file
