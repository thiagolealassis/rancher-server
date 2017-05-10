# Rancher Server

## Pré-requisitos

## Instalação

1. Checkout do projeto

2. Docker volume

2. Instalação do certificado

2. Executar o comando de start

3. Verificar a instalação

## Parando os serviços

## Inciciallizando os serviços

## Atualizando os serviços

## Notes

docker-machine create -d virtualbox --swarm --swarm-master --virtualbox-boot2docker-url /Users/Thiago/Downloads/rancheros.iso rancher

docker-machine ssh rancher

docker swarm init --advertise-addr 10.0.2.15
wget https://raw.githubusercontent.com/thiagolealassis/rancher-server/master/docker-compose-local.yml
docker stack deploy -c docker-compose-local.yml rancher-server



docker stack ps rancher-server

## scaleway

IP swarm master: 51.15.132.183

sudo chown -R Thiago /usr/local
brew update
brew tap scaleway/scaleway
brew install scaleway/scaleway/docker-machine-driver-scaleway

docker-machine create -d scaleway \
    --scaleway-organization=c65ff546-ee3f-46ed-9390-da4ae52fca0e \
    --scaleway-token=a7c1b9b9-7c92-4c42-aac5-2c8d76ea52b6 \
    --scaleway-name="rancher-server" \
    --scaleway-commercial-type="C2S" \
    --scaleway-volumes="50G" \
    --scaleway-ip="51.15.132.183" \
    --scaleway-image=docker \
    rancher-server

docker-machine ssh rancher-server apt-get update
docker-machine ssh rancher-server apt-get install docker-engine
docker-machine ssh rancher-server docker swarm init
docker-machine ssh rancher-server wget https://raw.githubusercontent.com/thiagolealassis/rancher-server/master/docker-compose-local.yml
docker-machine ssh rancher-server docker stack deploy -c docker-compose-local.yml rancher-server

apt-get install docker-engine
docker swarm init

