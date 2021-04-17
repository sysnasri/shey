# Here we can install docker via ansible
    docker ansible role can be obtained from the ansible galaxy 

            https://galaxy.ansible.com/sysnasri/docker

            ansible-galaxy install sysnasri.docker

            

in vars.yaml , you can overide default variables: 

    images_name: 
      - nasri/snapp:v1

If you are located in restricated area you can use proxy 

    proxy: 
       username: ""
       password: ""
       server: ""
       port: ""     

Pipe modules can be named here for deployment purpose  these are usefull when deploy application with docker compose and ansible 

    pip_modules:
        - pip
        - docker
        - docker-compose


you have option to chose shecan.ir name server for docker or just use http proxy which is more secure and faster. 


    nameserver:
      ns1: 8.8.8.8
      ns2: 4.2.2.4 

in some situation docker needs to be loged in. we could use ansible vault for credentials. 


    docker:
      username: ""
      password: ""                    