**Step 1:** Download all the files to a directory on you computer. We will denote this as the project directory. 

**Step 2**: Install Docker on your computer https://docs.docker.com/install/

**Step 3:** In the project directory run:

	docker build -t datascience . 
	
**Step 4:** Update the docker-compose.yml file to include .ipynb or .py files which you want to mount from host to the container

**Step 5:** In the project directory run:

	docker-compose up 
	
	

**Addendum**
	

DONE!!!!! Now visit http://localhost:8888 on you web browser 

 
If you run into trouble run the following command to download the logfile to your current directory

	docker cp <container-name>:/root/dockerLogs/install-logs.log .
	
If you want to start an interactive session inside the container type in the following command 

	docker exec -it <container name> /bin/bash
