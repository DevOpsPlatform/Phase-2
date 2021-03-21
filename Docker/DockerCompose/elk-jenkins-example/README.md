Ref: https://dzone.com/articles/putting-jenkins-build-logs-into-elk-stack-filebeat

Step-1: Configure EC2 Ubuntu instance on AWS.

Step-2: Install docker on Ubuntu server

```
sudo apt-get update -y && sudo apt-get install docker.io -y

sudo docker version
```

Step-3: Install docker-compose:https://github.com/DevOpsPlatform/Phase-2/blob/master/Docker/DockerCompose/Installation-and-example-1.md

Step-4: 

```
git clone https://github.com/kenych/dockerizing-jenkins && \
   cd dockerizing-jenkins && \
   git checkout dockerizing_jenkins_part_4_elk_stack_simplified && \
   ./runall.sh
```
