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

11. can we use multiple FROM commands in same dockerfile, see [practice/multi-stage.md]
    see - https://docs.docker.com/develop/develop-images/multistage-build/

12. ADD vs COPY

13. docker networks

14. docker regustry setup and push images to private registry

15. how to pull the docker images to k8s cluster (using k8s secrets - need to add docker config file )

16. difference between ARG and env in docker file
