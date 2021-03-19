https://vsupalov.com/docker-arg-vs-env/#:~:text=ENV%20is%20for%20future%20running,for%20your%20future%20environment%20variables.&text=ARG%20values%20are%20not%20available%20after%20the%20image%20is%20built.


Dockerfile

```
FROM ubuntu:latest

ARG VAR_A=5
ENV VAR_B=6
RUN echo $VAR_A
RUN echo $VAR_B
```

```
docker build -t agrvsenv:1.0 .
docker run -it agrvsenv:1.0 /bin/bash
```

Output:

![image](https://user-images.githubusercontent.com/24622526/111826727-57feb580-88e9-11eb-9f02-b1d8c07b5445.png)


Same Dockerfile as above 

```
docker build -t agrvsenv:2.0 .   --build-arg VAR_A=10
```

Output:

![image](https://user-images.githubusercontent.com/24622526/111826478-05bd9480-88e9-11eb-992d-89c57b5d63ed.png)


Dockerfile2

```
FROM ubuntu:latest

ARG VAR_A=5
ENV VAR_B=${VAR_A}
RUN echo $VAR_A
RUN echo $VAR_B
```

```
docker build -t agrvsenv:3.0 -f Dockerfile2 .  --build-arg VAR_A=10
docker run -it agrvsenv:3.0 /bin/bash
```

Output:

![image](https://user-images.githubusercontent.com/24622526/111826160-a495c100-88e8-11eb-8d7a-2273012761e7.png)
