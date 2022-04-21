<b>Below are the steps to be followed to run multiple Springboot microservices in one container.</b>

Step 1: Create jar files using the command <code>mvn clean package</code><br />
Step 2: Create a <code>supervisor.conf</code> file as present in this repo to run all the jars in one container.<br />
Step 3: Create <code>DockerFile</code> as present in this repo to install Supervisord and run it as per the configuration in .conf file.<br />
        Also specify all the ports that are to be exposed.<br />
Step 3: Build docker image for the cominbed-service using DockerFile. Sample Command to create image - <code>docker build --tag=vaccine-vendor:latest .<code><br \>
Step 5: Create <code>docker-compose.yml</code> file as present in this repo with this combined-service and also any other required Database or other services.<br />
Step 6: run <code>docker-compose up</code><br />
Step 7: All the services can be monitored in Docker Desktop.
