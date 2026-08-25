Container - A way to package application with all the necessary dependencies and configurations.
The portable artefact can be easily shared and moved around.
This later makes development and deployment more efficient
Containers live inside container repository. 
The public docker repository is called dockerhub

A container is made up of layers of images
Mostly Linux Based Images because they are small in size.
To get an image for example postgres i.e. docker run postgres:9.6 (This will get the postgres version9.6). To get the latest postgres, ommit the version and the colon just run docker run postgres. It will check if you have the container and run it, if you do not have, then it will download it from  dockerhub and run it.
docker ps - Is a docker command that gets all the running containers

Sometimes for example some OS do not run other linux images for example windows version below windows 10 do not support linux based images. In this case, Docker ToolBox is used.
Docker ToolBox abstracts the kernel for your host OS to run different docker images.

==Next Up: Docker Installation==

Docker refused to install in my machine, I will have to look for an alternative