Set of instructions to create a [[Container Image]]

## Dockerfile Basics
Build docker image from dockerfile: `docker build -t <container-image-name> <directory-containing-dockerfile>`

Run docker image: `docker run -dp <curr-machine-port>:<container-port> <container-image-name>`

List all active docker containers: `docker ps`

Stop an active docker container: `docker stop <the-container-id>`

Remove docker image: `docker rm <the-container-id>`

Push docker image to docker hub: `docker push YOUR-USER-NAME/getting-started`

### Volume Mount
Done for persisting data through different container runs

Creating volume: `docker volume create todo-db`
Mounting named volume to 'etc/tools': `docker run -dp 3000:3000 -v todo-db:/etc/todos getting-started`

### Bind Mounts
Allows us to mount our source code into the container to let it see code changes and respond to it right away, **instead of having to restart the container everytime.**

```Bash
docker run -dp 3000:3000 \ 
-w /app -v "$(pwd):/app" \
node:12-alpine \
sh -c "apk add --no-cache python2 g++ make && yarn install && yarn run dev"
```

-   `-w /app` - sets the container's present working directory where the command will run from
- `-v "$(pwd):/app"` - bind mount (link) the host's present `getting-started/app`directory to the container's `/app` directory. Note: Docker requires absolute paths for binding mounts,
- `sh -c "yarn install && yarn run dev"` - the command. We're starting a shell using `sh`

## The Container's Filesystem

When a container runs, it uses the various layers from an image for its filesystem. Each container also gets its own "scratch space" to create/update/remove files. Any changes won't be seen in another container, _even if_ they are using the same image.


