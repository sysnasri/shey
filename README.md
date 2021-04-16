# sheypoor challange for DevOps opportunaty 
   The challange consist of several steps which are listed in the following section :
     # Part 1: Application

          A simple application which should have a version and a health check api
          - Should be Containerized with a multi-stage docker image

     # Part 2: Kubernetes

          Create a Kubernetes cluster with 2 masters
          - describe your design choices
          - install the above application on the cluster using helm
          - describe a solution for zero-downtime deployment with Kubernetes

     # Part 3: Automation

          - To run this project we expect to run only a simple vagrant up command
# Part 1 
  For this part I have used a simple application which prints "Welcome to my awesome app" and has been written in Golang
  The application has been containerized with a builder stage, if you want build the application you may need a proxy server
  which can be used in Dockerfile or just uncomment the following envs 

     ENV HTTPS_PROXY=http://IP:Port
     ENV HTTP_PROXY=http://IP:Port

  In this scenario It is going to be built via travis-ci and push the images to docker hub, pelase refer to travis-ci docs.
  
# Part 2 
  kubernetes has been setup via kubespray with 4 nodes , 2 masters and 2 workers, also etcd is High available with three nodes.
  you can refer to helm folder for helm chart instruction. 

# Part 3 
  I have used cloud instances for deployment but if you want to setup cluster locally, you can use the vagrant to bootstrap the cluster. 
     
     simply do vagrant up , it installs ubuntu and docker
     





