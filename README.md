# docker-example



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
