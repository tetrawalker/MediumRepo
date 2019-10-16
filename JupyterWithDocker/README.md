Step 1: Download all the files to a directory on you computer. We will denote this as the project directory. 

Step 2: Install Docker on your computer https://docs.docker.com/install/

Step 3: In the project directory run:

	docker build -t datascience . 

Step 4: In the project directory run:

	docker-compose up 

Step 5: Visit http://localhost:8888 on you web browser 

To add python scipts to the container simply add it in the project folder and mount it in docker-compose.yml file 
then retype: 

	docker-compose up 
 
If you run into trouble run the following command to download the logfile to your current directory

	docker cp {container_name}:/root/DockerLogs .
	
