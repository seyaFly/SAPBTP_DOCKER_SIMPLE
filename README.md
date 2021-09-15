[English](/README.md)

This demo can be used for developer to build the deploy docker image to SAP BTP enviroment

## Table Of Content
<!-- MarkdownTOC -->
- [Table Of Content](#table-of-content)
  - [Preparation](#preparation)
  - [Build](#build)
  - [Test](#test)
  - [Push to docker Hub](#push-to-docker-hub)
  - [Push to SAP BTP](#push-to-sap-btp)
  - [Reference](#reference)
<!-- /MarkdownTOC -->

### Preparation

Insall [Docker](https://www.docker.com/get-started) on your development enviroment

### Build 

Build docker images with the command : ```docker build -t=”docker_node_helloworld . ```

**Notes** : Don't messing DOT 

### Test 

Run the command to start the image : ``` docker run -p 4000:4000 docker_node_helloworld ```

Test it with the link : [: http://localhost:4000](http://localhost:4000)

Response : ``` Hello World ```

### Push to docker Hub 

Command :

```docker
docker login
docker tag docker_node_helloworld {{your dockerhubName}}/my_docker_image_v1
docker push {{your DokerhubName}}/my_docker_image_v1
```

### Push to SAP BTP 

Command:

```
cf api {{apiendpoint}}
cf login -u {{username}} -p {{password}}
cf push my_docker_appv1 --docker-image {{your dokerhubName}}/my_docker_image_v1:latest --docker-username {{your dockerhubName}}
```

### Reference

Deploy Docker Image : [deploy-application-using-docker-container-on-sap-cloud-foundry-2020/](https://blogs.sap.com/2020/07/07/deploy-application-using-docker-container-on-sap-cloud-foundry-2020/)