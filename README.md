### Assigment problem file tree

- assignmnet-problem/  
    - node-app/  
        - package.json  
        - server.js  
    - python-app/  
        - bmi.py


1) Create two seperate images for two different app

- `docker build .` for each app. 

2) Launch a container for each created image

- `docker run -d -p 3000:3000 [image_id/name]` for node-app.
- `docker run -it [image_id/name]` for python-app.

3) Re-create both containers and assign names to both containers.

- `docker run -d -p 3000:3000 --name node-app_container [image_id/name]` for node-app
- `docker run -it --name python_container [image_id/name]` for python-app

4) Clean up (remove) all stopped (and running) containers, clean up all created images.

- `docker stop [container_ids]`
- `docker rm [container_ids]`
- `docker image prune`

5) Re-build the images - this time with names and tags assigned to them.

- `docker build -t node-app:latest .` for node-app
- `docker build -t python-app:latest .` for python-app

6) Run new containers based on the re-built images, ensuring that the containers
are removed automatically when stopped.

- `docker run -d --rm --name node-app-container node-app:latest` for node-app
- `docker run -it --rm --name python-app-container python-app:latest` for python-app