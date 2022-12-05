###Git Work Flow
- The git commits were centered around the tasks that needed to be carried out
- To ensure easy tracking of the changes made, the commits were made small and descriptive  

###Image Selection
- There were two base images to be selected:
- The frontend and backend apps extended the node base image. For lighter images, the alpine variant was selected
- For the database, the mongo image was selected since the app connected to a mongo database

###Image Versioning
- Images were named accoring to the semver convention: <DOCKER-HUB-USERNAME>/<IMAGE-NAME> i.e. jerryauvagha/yolo_client and jerryauvagha/yolo_backend
- The yolo_client and yolo_backend images were versioned to 1.0 since they were user-created
- The mongo image that was pulled directly from docker hub also 
used the same naming convention jerryauvagha/mongo but the version matched the one of the base image so it was version 6.0.3

###Image Deployment
- To push to docker hub, login is required via sudo docker login 
- To push the image, the tag needs to be specified correctly, including the version number

###Service Orchestration
- To ensure the services were able to communicate with each other, they were put in the same named bridge network. In this case: yolo_network
- To ensure data persistence the yolo_volume was assigned to the mongo service 
- To ensure services ran in the correct order the service dependencies were specified in the docker compose. i.e. backend depends on mongo and client depends on backend    