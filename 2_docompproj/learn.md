# Creating a docker compose file 
- It has 4 top level keys version, services, volumes & networks
- Use docker-compose for multi contianers apps
- the default file name is docker-compose.yml /yaml 
- you can have different file name with -f <filename ...> cli argument 
- docker-compose --help
- docker-compose --version
- docker-compose -f wordpress.yml up
- Ctrl + Z to exit out of containers without stopping them
- use -d flag to run containers in detachable mode
- docker-compose down 
- docker-compose down --rmi all --volumes --remove-orphans 
- docker-compose -f wordpress.yml config >> This command displays the configuration from your docker file. 
# Configurations in a Compose file: short and long forms:
- Short Form: sets the build value to the path of the build context where the Dockerfile is located.
- Long Form: uses a nested mapping to build the context using a required key and it has the same meaning as the context for the short form.

# Dev Practices 
- 
- 

# Production Practices 
- Remove any volumes for source code 
- restart:always policy 
- db volume for persistent data 
- Don't specify host port number, only specify the container port
- production mode environment variables
- additional services such as monitoring & log aggregation 

# work with 2 environments together 
- multi-container and multi evironment applications
- dev.Dockerfile 
- prod.Dockerfile 
- docker-compose.yml 
- dev.docker-compose.yml 
- prod.docker-compose.yml 

