# Orchestration of e-commerce platform

The Playbook is organized with the following parts
- VM host network access
- Variables
- Mongo setup
- ecommerce - Web Configurations
- ecommerce - Web Provisioning
- ecommerce - BackEnd Configuration
- ecommerce - BackEnd Provisioning
 

## Configuration of Network access
 `config.vm.network "forwarded_port", guest: 80, host: 80`
 `config.vm.network "forwarded_port", guest: 5000, host: 5000`

- The above configurations in Vagrantfiles are to ensure that all traffic to the HOST is routed to the  VM: 192.168.60.10
- Necessitated since my Host Itself was running on a VM



## Varible file has been defined for ease of playbook management
`vars.yml`

- Specifics are the packages to be installed on the ansible provisioned VM
`packages: [ 'git', 'docker.io', 'curl']`


  
## ROLE:  mongo_setup
- Get the key for installing Mongo
- Get repo list
- reload the apt database
- install mongo
- start the database
- enable the service on the VM
- allow access to mongo from other IPs
- restart db in readiness for connectivity



## ROLE:  app_set_up
- install docker in VM
- install git in VM
- clone the repo to the VM
- adjust the app files to make it work in the network 192.168.60.10
- create the docker file for deployment of the ecommerce-web app

 

## ROLE:  docker_app_build
- build the ecommerce WEB container
- run the container



## ROLE:  app_set_up_BE
- create the docker file for deployment of the ecommerce-web BACKEND



## ROLE: docker_app_BE_build
- build the ecommerce BACKEND container
- run the container - SPECIFY DB PATH environmental variable



