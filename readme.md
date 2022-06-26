Data Volumes: Starting Setup.
==

First, you need to create an image with the following command in your terminal:
**docker build .**  

To start the setup of the data volumes, you have to enter the following commands in your terminal:  
**docker run -d** \ run docker in *detached mode*,   
**--name feedback-app-container** \ assign a name to the container as *feedback-app-container*. This name can be used to stopping or removing the container,  
**-p 800:800** \ publish the container on *localhost:800*,  
**--rm** \ remove automatically the container when it's stopped,  
**-v feedback:/app/feedback** \ create a named volume, *feedback*, managed by Docker, to store the data. The data survives container shutdown/restart-removal via docker cli, and can be shared across containers or re-used for same containers,  
**-v "C:\Users\fedro\Desktop\dossier_du_moment\docker\data-volumes-starting-setup:/app"** \ create a bind mount, located on the host file system, managed by you. Here, the working directory of the container is located on data-volumes-starting-setup, allowing us to make specific adjustements in the code without restart/delete the container because of the use of nodemon too.  
**feedback-app** \ name of the image to create the container.