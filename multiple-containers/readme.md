<b>Below are the steps to be followed to run multiple Springboot microservices in one different containers.</b>

Step 1: Create jar files using the command <code>mvn clean package</code><br />
Step 2: Create DockerFiles for each service. Refer sample <code>DockerFile</code> present in this repo.<br />
Step 3: Build docker image for that service using DockerFile. Sample Command to create image - <code>docker build --tag=vaccine-vendor:latest . </code><br />
Step 4: Create <code>docker-compose.yml</code> file as present in this repo with all the services needed and also any other required Database or other services.<br />
Step 5: run <code>docker-compose up</code><br />
Step 6: Each service will run on a different container. All the services can be monitored in Docker Desktop.
