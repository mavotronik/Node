# Node
*  [Переключить на Русский](https://github.com/AploCoin/Node/blob/dev/README_ru.md)
## Multiarch build image
Rust supports 4 architectures to build:
- amd64
- arm32/v7
- arm64/v8
- i386

1. Update list of packages and install some needed packages
```
sudo apt update
sudo apt install -y git curl
```
2. Install Docker

Actual instructions to [install](https://docs.docker.com/engine/install/ubuntu/) Docker

3. Clone the repo on dev branch

```
git clone https://github.com/AploCoin/Node -b dev node
```
4. Build the docker image
```
docker buildx build --platform=amd64 -t aplo_node_amd64:latest .
```
5. Optional: save the image to archive
```
docker save -o aplo_node_amd64.tar aplo_node_amd64:latest
```
5.1. Unpack the image
```
docker load aplo_node_amd64.tar
```
