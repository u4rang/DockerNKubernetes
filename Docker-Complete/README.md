# Docker & Kubernetes:The Practical Guide[2024 Edition]

### Writing, Reading & Persisting Data
- Image is Read-only

#### Volumes
 <img width="687" alt="image" src="https://github.com/user-attachments/assets/0d59797c-efe1-48b6-9ad5-2aa8651e66bd">
##### External Data Storages
 - Volumes (Managed by Docker)
   - Anonymous Volumes
   - Named Volumes
 - Bind Mounts (Managed by Developer)
   - Define a folder / path on host machine 
   - Great for persistent, editable data
```shell
docker run -d -p <node_port>:<pod_port> --rm --name <container_name> -v <node_dir_path>:<pod_dir_path> <image_name>:<tag>
```
      - shortcuts
        - Linux
```shell
-v $(pwd):/app
```
        - Windows
```shell
-v "%cd%":/app
```

#### nodemon
```shell
docker run -d -p 3000:80 --rm --name feedback-app -v /Users/chaesystersfather/git/DockerNKubernetes/Docker-Complete/data-volumes-01:/app -v /app/node_modules -v feedback:/app/feedback feedback-node:volumes
```

### Docker Command
#### Docker Build
```shell
docker build -t <image_name> .
```

#### Docker Run
```shell
docker run -p <port>:<expose_port> -d --name <container_name> --rm <image_name>:<tag>
```

#### Docker log
```shell
docker log -f <container_name>
```