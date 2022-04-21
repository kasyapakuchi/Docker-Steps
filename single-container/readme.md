Below are the steps to be followed to run multiple Springboot microservices in one container.

Step 1: Create jar files using the command mvn clean package<br />
Step 2: Create a supervisor.conf file as present in this repo to run all the jars in one container.<br />
Step 3: Create DockerFile as present in this repo to install Supervisord and run it as per the configuration in .conf file.<br\>
        Also specify all the ports that are to be exposed.<br\>
Step 4: Create docker-compose.yml file as present in this repo with this combined-service and also any other required Database or other services.<br\>
Step 5: run docker-compose up<br\>
Step 6: All the services can be monitored in Docker Desktop.<br\>
