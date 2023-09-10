## 👋 Welcome to vault 🚀  

vault README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update vault
```
  
## Install and run container
  
```shell
mkdir -p "$HOME/.local/share/srv/docker/vault/rootfs"
git clone "https://github.com/dockermgr/vault" "$HOME/.local/share/CasjaysDev/dockermgr/vault"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/vault/rootfs/." "$HOME/.local/share/srv/docker/vault/rootfs/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-vault \
--hostname vault \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-vault/rootfs/data:/data:z" \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-vault/rootfs/config:/config:z" \
-p 80:80 \
casjaysdevdocker/vault:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/vault
    container_name: casjaysdevdocker-vault
    environment:
      - TZ=America/New_York
      - HOSTNAME=vault
    volumes:
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-vault/rootfs/data:/data:z"
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-vault/rootfs/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/vault
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/vault" "$HOME/Projects/github/casjaysdevdocker/vault"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/vault"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
