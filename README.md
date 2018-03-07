# docker-example


How Dockerfile work?
=========

You can easily build your own image

    mkdir myImage
    cd myImage
    touch Dockerfile    # editer it with your host machine
    touch app.py        # Your application which you expect to run as daminn
    
    docker build -t myImage .


One liner to stop /remove all of Dockerntainers
=====

    
    docker stop $(docker ps -a -q)
    docker rm $(docker ps -a -q)


Modify a image after pull
============

    
    docker ps                                       # pick one id you want to attach
    sudo docker exec -i -t 98bf9ddc755f /bin/bash   # the id is above command result
    docker commit 98bf9ddc755f heygirl:part2x       # id is after your run above command will got!
    docker images                                   # Check current avaiable image on your machine

To Check what we have modify on our container ?
==========
    
    # docker diff container-id
    docker diff 98bf9ddc755f

Run your new load-balanced app
===========

    docker swarm init
    docker stack deploy -c docker-compose.yml getrestartlab
    docker service ls
    docker service ps getrestartlab_web
    

Check service logs
===========
    
    # docker service logs service-id
    docker service logs g2ztpyg2yanp


Create VMs using docker-machine
===========
    

    docker-machine create --driver virtualbox myvm1
    docker-machine create --driver virtualbox myvm2

    # Check you have create
    docker-machine ls

    # Here is example output from this command
    docker-machine ls

    # docker-machine ssh myvm1 "docker swarm init --advertise-addr <myvm1 ip>"
    docker swarm join-token manager

