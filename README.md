## 👋 Welcome to gist 🚀  

gist README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update gist
```
  
## Install and run container
  
```shell
mkdir -p "$HOME/.local/share/srv/docker/gist/rootfs"
git clone "https://github.com/dockermgr/gist" "$HOME/.local/share/CasjaysDev/dockermgr/gist"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/gist/rootfs/." "$HOME/.local/share/srv/docker/gist/rootfs/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-gist \
--hostname gist \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-gist/rootfs/data:/data:z" \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-gist/rootfs/config:/config:z" \
-p 80:80 \
casjaysdevdocker/gist:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/gist
    container_name: casjaysdevdocker-gist
    environment:
      - TZ=America/New_York
      - HOSTNAME=gist
    volumes:
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-gist/rootfs/data:/data:z"
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-gist/rootfs/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/gist
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/gist" "$HOME/Projects/github/casjaysdevdocker/gist"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/gist"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
